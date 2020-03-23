
---
title: "Application"
block_external_search_index: true
---
<style>
table td p { margin-top: 0; margin-bottom: 0; }
</style>

Manages an Application within Azure Active Directory.

> **NOTE:** If you're authenticating using a Service Principal then it must have permissions to both `Read and write owned by applications` and `Sign in and read user profile` within the `Windows Azure Active Directory` API.

> This content is derived from https://github.com/terraform-providers/terraform-provider-azuread/blob/master/website/docs/r/application.html.markdown.



## Create a Application Resource

{{< langchoose csharp nojavascript >}}

<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/azuread//#Application">Application</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/azuread//#ApplicationArgs">ApplicationArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">Application</span><span class="p">(resource_name, opts=None, </span>app_roles=None<span class="p">, </span>available_to_other_tenants=None<span class="p">, </span>group_membership_claims=None<span class="p">, </span>homepage=None<span class="p">, </span>identifier_uris=None<span class="p">, </span>logout_url=None<span class="p">, </span>name=None<span class="p">, </span>oauth2_allow_implicit_flow=None<span class="p">, </span>oauth2_permissions=None<span class="p">, </span>owners=None<span class="p">, </span>public_client=None<span class="p">, </span>reply_urls=None<span class="p">, </span>required_resource_accesses=None<span class="p">, </span>type=None<span class="p">, __props__=None);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewApplication<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-azuread/sdk/go/azuread/?tab=doc#ApplicationArgs">ApplicationArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-azuread/sdk/go/azuread/?tab=doc#Application">Application</a></span>, error)</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Azuread/Pulumi.Azuread..Application.html">Application</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Azuread/Pulumi.Azuread.ApplicationArgs.html">ApplicationArgs</a></span>? <span class="nx">args = null<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>

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
            <td class="align-top">App<wbr>Roles</td>
            <td class="align-top">
                
                <code><a href="#applicationapprole">List&lt;Pulumi.<wbr>Azuread.<wbr>Application<wbr>App<wbr>Role<wbr>Args&gt;?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A collection of `app_role` blocks as documented below. For more information https://docs.microsoft.com/en-us/azure/architecture/multitenant-identity/app-roles
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Available<wbr>To<wbr>Other<wbr>Tenants</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Is this Azure AD Application available to other tenants? Defaults to `false`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Group<wbr>Membership<wbr>Claims</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Configures the `groups` claim issued in a user or OAuth 2.0 access token that the app expects. Defaults to `SecurityGroup`. Possible values are `None`, `SecurityGroup` or `All`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Homepage</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The URL to the application&#39;s home page. If no homepage is specified this defaults to `https://{name}`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Identifier<wbr>Uris</td>
            <td class="align-top">
                
                <code>List<string>?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A list of user-defined URI(s) that uniquely identify a Web application within it&#39;s Azure AD tenant, or within a verified custom domain if the application is multi-tenant.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Logout<wbr>Url</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The URL of the logout page.
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
The display name for the application.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Oauth2Allow<wbr>Implicit<wbr>Flow</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Does this Azure AD Application allow OAuth2.0 implicit flow tokens? Defaults to `false`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Oauth2Permissions</td>
            <td class="align-top">
                
                <code><a href="#applicationoauth2permission">List&lt;Pulumi.<wbr>Azuread.<wbr>Application<wbr>Oauth2Permission<wbr>Args&gt;?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A collection of OAuth 2.0 permission scopes that the web API (resource) app exposes to client apps. Each permission is covered by a `oauth2_permission` block as documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Owners</td>
            <td class="align-top">
                
                <code>List<string>?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A list of Azure AD Object IDs that will be granted ownership of the application. Defaults to the Object ID of the caller creating the application. If a list is specified the caller Object ID will no longer be included unless explicitly added to the list. 
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Public<wbr>Client</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Is this Azure AD Application a public client? Defaults to `false`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Reply<wbr>Urls</td>
            <td class="align-top">
                
                <code>List<string>?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A list of URLs that user tokens are sent to for sign in, or the redirect URIs that OAuth 2.0 authorization codes and access tokens are sent to.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Required<wbr>Resource<wbr>Accesses</td>
            <td class="align-top">
                
                <code><a href="#applicationrequiredresourceaccess">List&lt;Pulumi.<wbr>Azuread.<wbr>Application<wbr>Required<wbr>Resource<wbr>Access<wbr>Args&gt;?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A collection of `required_resource_access` blocks as documented below.
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
Specifies whether the id property references an `OAuth2Permission` or an `AppRole`. Possible values are `Scope` or `Role`.
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
                
                <code><a href="#applicationapprole">[]Application<wbr>App<wbr>Role</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A collection of `app_role` blocks as documented below. For more information https://docs.microsoft.com/en-us/azure/architecture/multitenant-identity/app-roles
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Available<wbr>To<wbr>Other<wbr>Tenants</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Is this Azure AD Application available to other tenants? Defaults to `false`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Group<wbr>Membership<wbr>Claims</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Configures the `groups` claim issued in a user or OAuth 2.0 access token that the app expects. Defaults to `SecurityGroup`. Possible values are `None`, `SecurityGroup` or `All`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Homepage</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The URL to the application&#39;s home page. If no homepage is specified this defaults to `https://{name}`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Identifier<wbr>Uris</td>
            <td class="align-top">
                
                <code>[]string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A list of user-defined URI(s) that uniquely identify a Web application within it&#39;s Azure AD tenant, or within a verified custom domain if the application is multi-tenant.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Logout<wbr>Url</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The URL of the logout page.
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
The display name for the application.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Oauth2Allow<wbr>Implicit<wbr>Flow</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Does this Azure AD Application allow OAuth2.0 implicit flow tokens? Defaults to `false`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Oauth2Permissions</td>
            <td class="align-top">
                
                <code><a href="#applicationoauth2permission">[]Application<wbr>Oauth2Permission</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A collection of OAuth 2.0 permission scopes that the web API (resource) app exposes to client apps. Each permission is covered by a `oauth2_permission` block as documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Owners</td>
            <td class="align-top">
                
                <code>[]string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A list of Azure AD Object IDs that will be granted ownership of the application. Defaults to the Object ID of the caller creating the application. If a list is specified the caller Object ID will no longer be included unless explicitly added to the list. 
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Public<wbr>Client</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Is this Azure AD Application a public client? Defaults to `false`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Reply<wbr>Urls</td>
            <td class="align-top">
                
                <code>[]string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A list of URLs that user tokens are sent to for sign in, or the redirect URIs that OAuth 2.0 authorization codes and access tokens are sent to.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Required<wbr>Resource<wbr>Accesses</td>
            <td class="align-top">
                
                <code><a href="#applicationrequiredresourceaccess">[]Application<wbr>Required<wbr>Resource<wbr>Access</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A collection of `required_resource_access` blocks as documented below.
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
Specifies whether the id property references an `OAuth2Permission` or an `AppRole`. Possible values are `Scope` or `Role`.
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
                
                <code><a href="#applicationapprole">Application<wbr>App<wbr>Role[]?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A collection of `app_role` blocks as documented below. For more information https://docs.microsoft.com/en-us/azure/architecture/multitenant-identity/app-roles
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">available<wbr>To<wbr>Other<wbr>Tenants</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Is this Azure AD Application available to other tenants? Defaults to `false`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">group<wbr>Membership<wbr>Claims</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Configures the `groups` claim issued in a user or OAuth 2.0 access token that the app expects. Defaults to `SecurityGroup`. Possible values are `None`, `SecurityGroup` or `All`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">homepage</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The URL to the application&#39;s home page. If no homepage is specified this defaults to `https://{name}`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">identifier<wbr>Uris</td>
            <td class="align-top">
                
                <code>string[]?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A list of user-defined URI(s) that uniquely identify a Web application within it&#39;s Azure AD tenant, or within a verified custom domain if the application is multi-tenant.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">logout<wbr>Url</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The URL of the logout page.
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
The display name for the application.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">oauth2Allow<wbr>Implicit<wbr>Flow</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Does this Azure AD Application allow OAuth2.0 implicit flow tokens? Defaults to `false`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">oauth2Permissions</td>
            <td class="align-top">
                
                <code><a href="#applicationoauth2permission">Application<wbr>Oauth2Permission[]?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A collection of OAuth 2.0 permission scopes that the web API (resource) app exposes to client apps. Each permission is covered by a `oauth2_permission` block as documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">owners</td>
            <td class="align-top">
                
                <code>string[]?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A list of Azure AD Object IDs that will be granted ownership of the application. Defaults to the Object ID of the caller creating the application. If a list is specified the caller Object ID will no longer be included unless explicitly added to the list. 
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">public<wbr>Client</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Is this Azure AD Application a public client? Defaults to `false`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">reply<wbr>Urls</td>
            <td class="align-top">
                
                <code>string[]?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A list of URLs that user tokens are sent to for sign in, or the redirect URIs that OAuth 2.0 authorization codes and access tokens are sent to.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">required<wbr>Resource<wbr>Accesses</td>
            <td class="align-top">
                
                <code><a href="#applicationrequiredresourceaccess">Application<wbr>Required<wbr>Resource<wbr>Access[]?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A collection of `required_resource_access` blocks as documented below.
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
Specifies whether the id property references an `OAuth2Permission` or an `AppRole`. Possible values are `Scope` or `Role`.
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
                
                <code><a href="#applicationapprole">List[Application<wbr>App<wbr>Role]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A collection of `app_role` blocks as documented below. For more information https://docs.microsoft.com/en-us/azure/architecture/multitenant-identity/app-roles
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">available_<wbr>to_<wbr>other_<wbr>tenants</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Is this Azure AD Application available to other tenants? Defaults to `false`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">group_<wbr>membership_<wbr>claims</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Configures the `groups` claim issued in a user or OAuth 2.0 access token that the app expects. Defaults to `SecurityGroup`. Possible values are `None`, `SecurityGroup` or `All`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">homepage</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The URL to the application&#39;s home page. If no homepage is specified this defaults to `https://{name}`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">identifier_<wbr>uris</td>
            <td class="align-top">
                
                <code>List[str]</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A list of user-defined URI(s) that uniquely identify a Web application within it&#39;s Azure AD tenant, or within a verified custom domain if the application is multi-tenant.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">logout_<wbr>url</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The URL of the logout page.
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
The display name for the application.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">oauth2_<wbr>allow_<wbr>implicit_<wbr>flow</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Does this Azure AD Application allow OAuth2.0 implicit flow tokens? Defaults to `false`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">oauth2_<wbr>permissions</td>
            <td class="align-top">
                
                <code><a href="#applicationoauth2permission">List[Application<wbr>Oauth2Permission]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A collection of OAuth 2.0 permission scopes that the web API (resource) app exposes to client apps. Each permission is covered by a `oauth2_permission` block as documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">owners</td>
            <td class="align-top">
                
                <code>List[str]</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A list of Azure AD Object IDs that will be granted ownership of the application. Defaults to the Object ID of the caller creating the application. If a list is specified the caller Object ID will no longer be included unless explicitly added to the list. 
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">public_<wbr>client</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Is this Azure AD Application a public client? Defaults to `false`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">reply_<wbr>urls</td>
            <td class="align-top">
                
                <code>List[str]</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A list of URLs that user tokens are sent to for sign in, or the redirect URIs that OAuth 2.0 authorization codes and access tokens are sent to.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">required_<wbr>resource_<wbr>accesses</td>
            <td class="align-top">
                
                <code><a href="#applicationrequiredresourceaccess">List[Application<wbr>Required<wbr>Resource<wbr>Access]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A collection of `required_resource_access` blocks as documented below.
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
Specifies whether the id property references an `OAuth2Permission` or an `AppRole`. Possible values are `Scope` or `Role`.
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
            <td class="align-top">App<wbr>Roles</td>
            <td class="align-top">
                
                <code><a href="#applicationapprole">List&lt;Pulumi.<wbr>Azuread.<wbr>Application<wbr>App<wbr>Role&gt;?</a></code>
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
            <td class="align-top">{{% md %}} The Application ID.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Available<wbr>To<wbr>Other<wbr>Tenants</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} Is this Azure AD Application available to other tenants? Defaults to `false`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Group<wbr>Membership<wbr>Claims</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} Configures the `groups` claim issued in a user or OAuth 2.0 access token that the app expects. Defaults to `SecurityGroup`. Possible values are `None`, `SecurityGroup` or `All`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Homepage</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The URL to the application&#39;s home page. If no homepage is specified this defaults to `https://{name}`.
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
                
                <code>string?</code>
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
            <td class="align-top">{{% md %}} The display name for the application.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Oauth2Allow<wbr>Implicit<wbr>Flow</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} Does this Azure AD Application allow OAuth2.0 implicit flow tokens? Defaults to `false`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Oauth2Permissions</td>
            <td class="align-top">
                
                <code><a href="#applicationoauth2permission">List&lt;Pulumi.<wbr>Azuread.<wbr>Application<wbr>Oauth2Permission&gt;</a></code>
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
            <td class="align-top">{{% md %}} The Application&#39;s Object ID.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Owners</td>
            <td class="align-top">
                
                <code>List<string></code>
            </td>
            <td class="align-top">{{% md %}} A list of Azure AD Object IDs that will be granted ownership of the application. Defaults to the Object ID of the caller creating the application. If a list is specified the caller Object ID will no longer be included unless explicitly added to the list. 
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Public<wbr>Client</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} Is this Azure AD Application a public client? Defaults to `false`.
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
                
                <code><a href="#applicationrequiredresourceaccess">List&lt;Pulumi.<wbr>Azuread.<wbr>Application<wbr>Required<wbr>Resource<wbr>Access&gt;?</a></code>
            </td>
            <td class="align-top">{{% md %}} A collection of `required_resource_access` blocks as documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Type</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} Specifies whether the id property references an `OAuth2Permission` or an `AppRole`. Possible values are `Scope` or `Role`.
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
                
                <code><a href="#applicationapprole">[]Application<wbr>App<wbr>Role</a></code>
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
            <td class="align-top">{{% md %}} The Application ID.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Available<wbr>To<wbr>Other<wbr>Tenants</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} Is this Azure AD Application available to other tenants? Defaults to `false`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Group<wbr>Membership<wbr>Claims</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} Configures the `groups` claim issued in a user or OAuth 2.0 access token that the app expects. Defaults to `SecurityGroup`. Possible values are `None`, `SecurityGroup` or `All`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Homepage</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The URL to the application&#39;s home page. If no homepage is specified this defaults to `https://{name}`.
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
                
                <code>*string</code>
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
            <td class="align-top">{{% md %}} The display name for the application.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Oauth2Allow<wbr>Implicit<wbr>Flow</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} Does this Azure AD Application allow OAuth2.0 implicit flow tokens? Defaults to `false`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Oauth2Permissions</td>
            <td class="align-top">
                
                <code><a href="#applicationoauth2permission">[]Application<wbr>Oauth2Permission</a></code>
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
            <td class="align-top">{{% md %}} The Application&#39;s Object ID.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Owners</td>
            <td class="align-top">
                
                <code>[]string</code>
            </td>
            <td class="align-top">{{% md %}} A list of Azure AD Object IDs that will be granted ownership of the application. Defaults to the Object ID of the caller creating the application. If a list is specified the caller Object ID will no longer be included unless explicitly added to the list. 
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Public<wbr>Client</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} Is this Azure AD Application a public client? Defaults to `false`.
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
                
                <code><a href="#applicationrequiredresourceaccess">[]Application<wbr>Required<wbr>Resource<wbr>Access</a></code>
            </td>
            <td class="align-top">{{% md %}} A collection of `required_resource_access` blocks as documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Type</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} Specifies whether the id property references an `OAuth2Permission` or an `AppRole`. Possible values are `Scope` or `Role`.
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
                
                <code><a href="#applicationapprole">Application<wbr>App<wbr>Role[]?</a></code>
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
            <td class="align-top">{{% md %}} The Application ID.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">available<wbr>To<wbr>Other<wbr>Tenants</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} Is this Azure AD Application available to other tenants? Defaults to `false`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">group<wbr>Membership<wbr>Claims</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} Configures the `groups` claim issued in a user or OAuth 2.0 access token that the app expects. Defaults to `SecurityGroup`. Possible values are `None`, `SecurityGroup` or `All`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">homepage</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The URL to the application&#39;s home page. If no homepage is specified this defaults to `https://{name}`.
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
                
                <code>string?</code>
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
            <td class="align-top">{{% md %}} The display name for the application.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">oauth2Allow<wbr>Implicit<wbr>Flow</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} Does this Azure AD Application allow OAuth2.0 implicit flow tokens? Defaults to `false`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">oauth2Permissions</td>
            <td class="align-top">
                
                <code><a href="#applicationoauth2permission">Application<wbr>Oauth2Permission[]</a></code>
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
            <td class="align-top">{{% md %}} The Application&#39;s Object ID.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">owners</td>
            <td class="align-top">
                
                <code>string[]</code>
            </td>
            <td class="align-top">{{% md %}} A list of Azure AD Object IDs that will be granted ownership of the application. Defaults to the Object ID of the caller creating the application. If a list is specified the caller Object ID will no longer be included unless explicitly added to the list. 
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">public<wbr>Client</td>
            <td class="align-top">
                
                <code>boolean</code>
            </td>
            <td class="align-top">{{% md %}} Is this Azure AD Application a public client? Defaults to `false`.
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
                
                <code><a href="#applicationrequiredresourceaccess">Application<wbr>Required<wbr>Resource<wbr>Access[]?</a></code>
            </td>
            <td class="align-top">{{% md %}} A collection of `required_resource_access` blocks as documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">type</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} Specifies whether the id property references an `OAuth2Permission` or an `AppRole`. Possible values are `Scope` or `Role`.
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
                
                <code><a href="#applicationapprole">List[Application<wbr>App<wbr>Role]</a></code>
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
            <td class="align-top">{{% md %}} The Application ID.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">available_<wbr>to_<wbr>other_<wbr>tenants</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} Is this Azure AD Application available to other tenants? Defaults to `false`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">group_<wbr>membership_<wbr>claims</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} Configures the `groups` claim issued in a user or OAuth 2.0 access token that the app expects. Defaults to `SecurityGroup`. Possible values are `None`, `SecurityGroup` or `All`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">homepage</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The URL to the application&#39;s home page. If no homepage is specified this defaults to `https://{name}`.
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
            <td class="align-top">{{% md %}} The display name for the application.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">oauth2_<wbr>allow_<wbr>implicit_<wbr>flow</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} Does this Azure AD Application allow OAuth2.0 implicit flow tokens? Defaults to `false`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">oauth2_<wbr>permissions</td>
            <td class="align-top">
                
                <code><a href="#applicationoauth2permission">List[Application<wbr>Oauth2Permission]</a></code>
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
            <td class="align-top">{{% md %}} The Application&#39;s Object ID.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">owners</td>
            <td class="align-top">
                
                <code>List[str]</code>
            </td>
            <td class="align-top">{{% md %}} A list of Azure AD Object IDs that will be granted ownership of the application. Defaults to the Object ID of the caller creating the application. If a list is specified the caller Object ID will no longer be included unless explicitly added to the list. 
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">public_<wbr>client</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} Is this Azure AD Application a public client? Defaults to `false`.
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
                
                <code><a href="#applicationrequiredresourceaccess">List[Application<wbr>Required<wbr>Resource<wbr>Access]</a></code>
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
            <td class="align-top">{{% md %}} Specifies whether the id property references an `OAuth2Permission` or an `AppRole`. Possible values are `Scope` or `Role`.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}








## Look up an Existing Application Resource

{{< langchoose csharp nojavascript >}}

<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">pulumi.Input&lt;pulumi.ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/azuread//#ApplicationState">ApplicationState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/azuread//#Application">Application</a></span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>app_roles=None<span class="p">, </span>application_id=None<span class="p">, </span>available_to_other_tenants=None<span class="p">, </span>group_membership_claims=None<span class="p">, </span>homepage=None<span class="p">, </span>identifier_uris=None<span class="p">, </span>logout_url=None<span class="p">, </span>name=None<span class="p">, </span>oauth2_allow_implicit_flow=None<span class="p">, </span>oauth2_permissions=None<span class="p">, </span>object_id=None<span class="p">, </span>owners=None<span class="p">, </span>public_client=None<span class="p">, </span>reply_urls=None<span class="p">, </span>required_resource_accesses=None<span class="p">, </span>type=None<span class="p">, __props__=None);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetApplication<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">pulumi.IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-azuread/sdk/go/azuread/?tab=doc#ApplicationState">ApplicationState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-azuread/sdk/go/azuread/?tab=doc#Application">Application</a></span>, error)</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Azuread/Pulumi.Azuread..Application.html">Application</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Pulumi.Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Azuread/Pulumi.Azuread..ApplicationState.html">ApplicationState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>

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
            <td class="align-top">App<wbr>Roles</td>
            <td class="align-top">
                
                <code><a href="#applicationapprole">List&lt;Pulumi.<wbr>Azuread.<wbr>Application<wbr>App<wbr>Role<wbr>Args&gt;?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A collection of `app_role` blocks as documented below. For more information https://docs.microsoft.com/en-us/azure/architecture/multitenant-identity/app-roles
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Application<wbr>Id</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The Application ID.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Available<wbr>To<wbr>Other<wbr>Tenants</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Is this Azure AD Application available to other tenants? Defaults to `false`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Group<wbr>Membership<wbr>Claims</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Configures the `groups` claim issued in a user or OAuth 2.0 access token that the app expects. Defaults to `SecurityGroup`. Possible values are `None`, `SecurityGroup` or `All`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Homepage</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The URL to the application&#39;s home page. If no homepage is specified this defaults to `https://{name}`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Identifier<wbr>Uris</td>
            <td class="align-top">
                
                <code>List<string>?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A list of user-defined URI(s) that uniquely identify a Web application within it&#39;s Azure AD tenant, or within a verified custom domain if the application is multi-tenant.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Logout<wbr>Url</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The URL of the logout page.
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
The display name for the application.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Oauth2Allow<wbr>Implicit<wbr>Flow</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Does this Azure AD Application allow OAuth2.0 implicit flow tokens? Defaults to `false`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Oauth2Permissions</td>
            <td class="align-top">
                
                <code><a href="#applicationoauth2permission">List&lt;Pulumi.<wbr>Azuread.<wbr>Application<wbr>Oauth2Permission<wbr>Args&gt;?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A collection of OAuth 2.0 permission scopes that the web API (resource) app exposes to client apps. Each permission is covered by a `oauth2_permission` block as documented below.
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
The Application&#39;s Object ID.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Owners</td>
            <td class="align-top">
                
                <code>List<string>?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A list of Azure AD Object IDs that will be granted ownership of the application. Defaults to the Object ID of the caller creating the application. If a list is specified the caller Object ID will no longer be included unless explicitly added to the list. 
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Public<wbr>Client</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Is this Azure AD Application a public client? Defaults to `false`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Reply<wbr>Urls</td>
            <td class="align-top">
                
                <code>List<string>?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A list of URLs that user tokens are sent to for sign in, or the redirect URIs that OAuth 2.0 authorization codes and access tokens are sent to.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Required<wbr>Resource<wbr>Accesses</td>
            <td class="align-top">
                
                <code><a href="#applicationrequiredresourceaccess">List&lt;Pulumi.<wbr>Azuread.<wbr>Application<wbr>Required<wbr>Resource<wbr>Access<wbr>Args&gt;?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A collection of `required_resource_access` blocks as documented below.
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
Specifies whether the id property references an `OAuth2Permission` or an `AppRole`. Possible values are `Scope` or `Role`.
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
                
                <code><a href="#applicationapprole">[]Application<wbr>App<wbr>Role</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A collection of `app_role` blocks as documented below. For more information https://docs.microsoft.com/en-us/azure/architecture/multitenant-identity/app-roles
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Application<wbr>Id</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The Application ID.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Available<wbr>To<wbr>Other<wbr>Tenants</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Is this Azure AD Application available to other tenants? Defaults to `false`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Group<wbr>Membership<wbr>Claims</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Configures the `groups` claim issued in a user or OAuth 2.0 access token that the app expects. Defaults to `SecurityGroup`. Possible values are `None`, `SecurityGroup` or `All`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Homepage</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The URL to the application&#39;s home page. If no homepage is specified this defaults to `https://{name}`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Identifier<wbr>Uris</td>
            <td class="align-top">
                
                <code>[]string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A list of user-defined URI(s) that uniquely identify a Web application within it&#39;s Azure AD tenant, or within a verified custom domain if the application is multi-tenant.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Logout<wbr>Url</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The URL of the logout page.
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
The display name for the application.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Oauth2Allow<wbr>Implicit<wbr>Flow</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Does this Azure AD Application allow OAuth2.0 implicit flow tokens? Defaults to `false`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Oauth2Permissions</td>
            <td class="align-top">
                
                <code><a href="#applicationoauth2permission">[]Application<wbr>Oauth2Permission</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A collection of OAuth 2.0 permission scopes that the web API (resource) app exposes to client apps. Each permission is covered by a `oauth2_permission` block as documented below.
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
The Application&#39;s Object ID.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Owners</td>
            <td class="align-top">
                
                <code>[]string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A list of Azure AD Object IDs that will be granted ownership of the application. Defaults to the Object ID of the caller creating the application. If a list is specified the caller Object ID will no longer be included unless explicitly added to the list. 
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Public<wbr>Client</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Is this Azure AD Application a public client? Defaults to `false`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Reply<wbr>Urls</td>
            <td class="align-top">
                
                <code>[]string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A list of URLs that user tokens are sent to for sign in, or the redirect URIs that OAuth 2.0 authorization codes and access tokens are sent to.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Required<wbr>Resource<wbr>Accesses</td>
            <td class="align-top">
                
                <code><a href="#applicationrequiredresourceaccess">[]Application<wbr>Required<wbr>Resource<wbr>Access</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A collection of `required_resource_access` blocks as documented below.
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
Specifies whether the id property references an `OAuth2Permission` or an `AppRole`. Possible values are `Scope` or `Role`.
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
                
                <code><a href="#applicationapprole">Application<wbr>App<wbr>Role[]?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A collection of `app_role` blocks as documented below. For more information https://docs.microsoft.com/en-us/azure/architecture/multitenant-identity/app-roles
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">application<wbr>Id</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The Application ID.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">available<wbr>To<wbr>Other<wbr>Tenants</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Is this Azure AD Application available to other tenants? Defaults to `false`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">group<wbr>Membership<wbr>Claims</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Configures the `groups` claim issued in a user or OAuth 2.0 access token that the app expects. Defaults to `SecurityGroup`. Possible values are `None`, `SecurityGroup` or `All`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">homepage</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The URL to the application&#39;s home page. If no homepage is specified this defaults to `https://{name}`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">identifier<wbr>Uris</td>
            <td class="align-top">
                
                <code>string[]?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A list of user-defined URI(s) that uniquely identify a Web application within it&#39;s Azure AD tenant, or within a verified custom domain if the application is multi-tenant.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">logout<wbr>Url</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The URL of the logout page.
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
The display name for the application.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">oauth2Allow<wbr>Implicit<wbr>Flow</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Does this Azure AD Application allow OAuth2.0 implicit flow tokens? Defaults to `false`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">oauth2Permissions</td>
            <td class="align-top">
                
                <code><a href="#applicationoauth2permission">Application<wbr>Oauth2Permission[]?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A collection of OAuth 2.0 permission scopes that the web API (resource) app exposes to client apps. Each permission is covered by a `oauth2_permission` block as documented below.
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
The Application&#39;s Object ID.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">owners</td>
            <td class="align-top">
                
                <code>string[]?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A list of Azure AD Object IDs that will be granted ownership of the application. Defaults to the Object ID of the caller creating the application. If a list is specified the caller Object ID will no longer be included unless explicitly added to the list. 
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">public<wbr>Client</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Is this Azure AD Application a public client? Defaults to `false`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">reply<wbr>Urls</td>
            <td class="align-top">
                
                <code>string[]?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A list of URLs that user tokens are sent to for sign in, or the redirect URIs that OAuth 2.0 authorization codes and access tokens are sent to.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">required<wbr>Resource<wbr>Accesses</td>
            <td class="align-top">
                
                <code><a href="#applicationrequiredresourceaccess">Application<wbr>Required<wbr>Resource<wbr>Access[]?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A collection of `required_resource_access` blocks as documented below.
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
Specifies whether the id property references an `OAuth2Permission` or an `AppRole`. Possible values are `Scope` or `Role`.
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
                
                <code><a href="#applicationapprole">List[Application<wbr>App<wbr>Role]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A collection of `app_role` blocks as documented below. For more information https://docs.microsoft.com/en-us/azure/architecture/multitenant-identity/app-roles
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">application_<wbr>id</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The Application ID.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">available_<wbr>to_<wbr>other_<wbr>tenants</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Is this Azure AD Application available to other tenants? Defaults to `false`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">group_<wbr>membership_<wbr>claims</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Configures the `groups` claim issued in a user or OAuth 2.0 access token that the app expects. Defaults to `SecurityGroup`. Possible values are `None`, `SecurityGroup` or `All`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">homepage</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The URL to the application&#39;s home page. If no homepage is specified this defaults to `https://{name}`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">identifier_<wbr>uris</td>
            <td class="align-top">
                
                <code>List[str]</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A list of user-defined URI(s) that uniquely identify a Web application within it&#39;s Azure AD tenant, or within a verified custom domain if the application is multi-tenant.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">logout_<wbr>url</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The URL of the logout page.
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
The display name for the application.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">oauth2_<wbr>allow_<wbr>implicit_<wbr>flow</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Does this Azure AD Application allow OAuth2.0 implicit flow tokens? Defaults to `false`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">oauth2_<wbr>permissions</td>
            <td class="align-top">
                
                <code><a href="#applicationoauth2permission">List[Application<wbr>Oauth2Permission]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A collection of OAuth 2.0 permission scopes that the web API (resource) app exposes to client apps. Each permission is covered by a `oauth2_permission` block as documented below.
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
The Application&#39;s Object ID.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">owners</td>
            <td class="align-top">
                
                <code>List[str]</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A list of Azure AD Object IDs that will be granted ownership of the application. Defaults to the Object ID of the caller creating the application. If a list is specified the caller Object ID will no longer be included unless explicitly added to the list. 
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">public_<wbr>client</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Is this Azure AD Application a public client? Defaults to `false`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">reply_<wbr>urls</td>
            <td class="align-top">
                
                <code>List[str]</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A list of URLs that user tokens are sent to for sign in, or the redirect URIs that OAuth 2.0 authorization codes and access tokens are sent to.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">required_<wbr>resource_<wbr>accesses</td>
            <td class="align-top">
                
                <code><a href="#applicationrequiredresourceaccess">List[Application<wbr>Required<wbr>Resource<wbr>Access]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A collection of `required_resource_access` blocks as documented below.
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
Specifies whether the id property references an `OAuth2Permission` or an `AppRole`. Possible values are `Scope` or `Role`.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}










## Supporting Types

#### ApplicationAppRole
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/azuread/types/input/#ApplicationAppRole">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/azuread/types/output/#ApplicationAppRole">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azuread/sdk/go/azuread/?tab=doc#ApplicationAppRoleArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azuread/sdk/go/azuread/?tab=doc#ApplicationAppRoleOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Azuread/Pulumi.Azuread.ApplicationAppRoleArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Azuread/Pulumi.Azuread.ApplicationAppRole.html">output</a> API doc for this type.
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
Specifies whether this app role definition can be assigned to users and groups by setting to `User`, or to other applications (that are accessing this application in daemon service scenarios) by setting to `Application`, or to both.
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
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The unique identifier of the `app_role`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Is<wbr>Enabled</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Determines if the app role is enabled: Defaults to `true`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Value</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
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
Specifies whether this app role definition can be assigned to users and groups by setting to `User`, or to other applications (that are accessing this application in daemon service scenarios) by setting to `Application`, or to both.
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
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The unique identifier of the `app_role`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Is<wbr>Enabled</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Determines if the app role is enabled: Defaults to `true`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Value</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
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
Specifies whether this app role definition can be assigned to users and groups by setting to `User`, or to other applications (that are accessing this application in daemon service scenarios) by setting to `Application`, or to both.
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
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The unique identifier of the `app_role`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">is<wbr>Enabled</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Determines if the app role is enabled: Defaults to `true`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">value</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
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
Specifies whether this app role definition can be assigned to users and groups by setting to `User`, or to other applications (that are accessing this application in daemon service scenarios) by setting to `Application`, or to both.
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
 (Optional)
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
 (Optional)
Determines if the app role is enabled: Defaults to `true`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">value</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Specifies the value of the roles claim that the application should expect in the authentication and access tokens.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}





#### ApplicationOauth2Permission
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/azuread/types/input/#ApplicationOauth2Permission">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/azuread/types/output/#ApplicationOauth2Permission">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azuread/sdk/go/azuread/?tab=doc#ApplicationOauth2PermissionArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azuread/sdk/go/azuread/?tab=doc#ApplicationOauth2PermissionOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Azuread/Pulumi.Azuread.ApplicationOauth2PermissionArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Azuread/Pulumi.Azuread.ApplicationOauth2Permission.html">output</a> API doc for this type.
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
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The description of the admin consent.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Admin<wbr>Consent<wbr>Display<wbr>Name</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The display name of the admin consent.
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
The unique identifier of the `app_role`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Is<wbr>Enabled</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Determines if the app role is enabled: Defaults to `true`.
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
Specifies whether the id property references an `OAuth2Permission` or an `AppRole`. Possible values are `Scope` or `Role`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">User<wbr>Consent<wbr>Description</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The description of the user consent.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">User<wbr>Consent<wbr>Display<wbr>Name</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The display name of the user consent.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Value</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
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
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The description of the admin consent.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Admin<wbr>Consent<wbr>Display<wbr>Name</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The display name of the admin consent.
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
The unique identifier of the `app_role`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Is<wbr>Enabled</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Determines if the app role is enabled: Defaults to `true`.
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
Specifies whether the id property references an `OAuth2Permission` or an `AppRole`. Possible values are `Scope` or `Role`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">User<wbr>Consent<wbr>Description</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The description of the user consent.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">User<wbr>Consent<wbr>Display<wbr>Name</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The display name of the user consent.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Value</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
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
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The description of the admin consent.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">admin<wbr>Consent<wbr>Display<wbr>Name</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The display name of the admin consent.
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
The unique identifier of the `app_role`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">is<wbr>Enabled</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Determines if the app role is enabled: Defaults to `true`.
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
Specifies whether the id property references an `OAuth2Permission` or an `AppRole`. Possible values are `Scope` or `Role`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">user<wbr>Consent<wbr>Description</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The description of the user consent.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">user<wbr>Consent<wbr>Display<wbr>Name</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The display name of the user consent.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">value</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
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
 (Optional)
The description of the admin consent.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">admin<wbr>Consent<wbr>Display<wbr>Name</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The display name of the admin consent.
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
 (Optional)
Determines if the app role is enabled: Defaults to `true`.
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
Specifies whether the id property references an `OAuth2Permission` or an `AppRole`. Possible values are `Scope` or `Role`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">user<wbr>Consent<wbr>Description</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The description of the user consent.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">user<wbr>Consent<wbr>Display<wbr>Name</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The display name of the user consent.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">value</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Specifies the value of the roles claim that the application should expect in the authentication and access tokens.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}





#### ApplicationRequiredResourceAccess
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/azuread/types/input/#ApplicationRequiredResourceAccess">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/azuread/types/output/#ApplicationRequiredResourceAccess">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azuread/sdk/go/azuread/?tab=doc#ApplicationRequiredResourceAccessArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azuread/sdk/go/azuread/?tab=doc#ApplicationRequiredResourceAccessOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Azuread/Pulumi.Azuread.ApplicationRequiredResourceAccessArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Azuread/Pulumi.Azuread.ApplicationRequiredResourceAccess.html">output</a> API doc for this type.
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
                
                <code><a href="#applicationrequiredresourceaccessresourceaccess">List&lt;Pulumi.<wbr>Azuread.<wbr>Application<wbr>Required<wbr>Resource<wbr>Access<wbr>Resource<wbr>Access<wbr>Args&gt;</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
A collection of `resource_access` blocks as documented below.
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
The unique identifier for the resource that the application requires access to. This should be equal to the appId declared on the target resource application.
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
                
                <code><a href="#applicationrequiredresourceaccessresourceaccess">[]Application<wbr>Required<wbr>Resource<wbr>Access<wbr>Resource<wbr>Access</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
A collection of `resource_access` blocks as documented below.
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
The unique identifier for the resource that the application requires access to. This should be equal to the appId declared on the target resource application.
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
                
                <code><a href="#applicationrequiredresourceaccessresourceaccess">Application<wbr>Required<wbr>Resource<wbr>Access<wbr>Resource<wbr>Access[]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
A collection of `resource_access` blocks as documented below.
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
The unique identifier for the resource that the application requires access to. This should be equal to the appId declared on the target resource application.
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
                
                <code><a href="#applicationrequiredresourceaccessresourceaccess">List[Application<wbr>Required<wbr>Resource<wbr>Access<wbr>Resource<wbr>Access]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
A collection of `resource_access` blocks as documented below.
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
The unique identifier for the resource that the application requires access to. This should be equal to the appId declared on the target resource application.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}





#### ApplicationRequiredResourceAccessResourceAccess
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/azuread/types/input/#ApplicationRequiredResourceAccessResourceAccess">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/azuread/types/output/#ApplicationRequiredResourceAccessResourceAccess">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azuread/sdk/go/azuread/?tab=doc#ApplicationRequiredResourceAccessResourceAccessArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azuread/sdk/go/azuread/?tab=doc#ApplicationRequiredResourceAccessResourceAccessOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Azuread/Pulumi.Azuread.ApplicationRequiredResourceAccessResourceAccessArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Azuread/Pulumi.Azuread.ApplicationRequiredResourceAccessResourceAccess.html">output</a> API doc for this type.
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
Specifies whether the id property references an `OAuth2Permission` or an `AppRole`. Possible values are `Scope` or `Role`.
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
Specifies whether the id property references an `OAuth2Permission` or an `AppRole`. Possible values are `Scope` or `Role`.
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
Specifies whether the id property references an `OAuth2Permission` or an `AppRole`. Possible values are `Scope` or `Role`.
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
Specifies whether the id property references an `OAuth2Permission` or an `AppRole`. Possible values are `Scope` or `Role`.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}








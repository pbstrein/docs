
---
title: "User"
block_external_search_index: true
---
<style>
table td p { margin-top: 0; margin-bottom: 0; }
</style>

Manages a User within Azure Active Directory.

> **NOTE:** If you're authenticating using a Service Principal then it must have permissions to `Directory.ReadWrite.All` within the `Windows Azure Active Directory` API.

> This content is derived from https://github.com/terraform-providers/terraform-provider-azuread/blob/master/website/docs/r/user.html.markdown.



## Create a User Resource

{{< langchoose csharp nojavascript >}}

<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/azuread//#User">User</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/azuread//#UserArgs">UserArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">User</span><span class="p">(resource_name, opts=None, </span>account_enabled=None<span class="p">, </span>display_name=None<span class="p">, </span>force_password_change=None<span class="p">, </span>immutable_id=None<span class="p">, </span>mail_nickname=None<span class="p">, </span>password=None<span class="p">, </span>usage_location=None<span class="p">, </span>user_principal_name=None<span class="p">, __props__=None);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewUser<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-azuread/sdk/go/azuread/?tab=doc#UserArgs">UserArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-azuread/sdk/go/azuread/?tab=doc#User">User</a></span>, error)</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Azuread/Pulumi.Azuread..User.html">User</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Azuread/Pulumi.Azuread.UserArgs.html">UserArgs</a></span> <span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>

Creates a User resource with the given unique name, arguments, and options.

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
            <td class="align-top">Account<wbr>Enabled</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
`true` if the account should be enabled, otherwise `false`. Defaults to `true`.
* `mail_nickname`- (Optional) The mail alias for the user. Defaults to the user name part of the User Principal Name.
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
The name to display in the address book for the user.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Force<wbr>Password<wbr>Change</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
`true` if the User is forced to change the password during the next sign-in. Defaults to `false`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Immutable<wbr>Id</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The value used to associate an on-premises Active Directory user account with their Azure AD user object. This must be specified if you are using a federated domain for the user&#39;s userPrincipalName (UPN) property when creating a new user account. 
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Mail<wbr>Nickname</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
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
The password for the User. The password must satisfy minimum requirements as specified by the password policy. The maximum length is 256 characters.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Usage<wbr>Location</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The usage location of the User. Required for users that will be assigned licenses due to legal requirement to check for availability of services in countries. The usage location is a two letter country code (ISO standard 3166). Examples include: `NO`, `JP`, and `GB`. Cannot be reset to null once set. 
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">User<wbr>Principal<wbr>Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The User Principal Name of the Azure AD User.
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
            <td class="align-top">Account<wbr>Enabled</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
`true` if the account should be enabled, otherwise `false`. Defaults to `true`.
* `mail_nickname`- (Optional) The mail alias for the user. Defaults to the user name part of the User Principal Name.
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
The name to display in the address book for the user.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Force<wbr>Password<wbr>Change</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
`true` if the User is forced to change the password during the next sign-in. Defaults to `false`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Immutable<wbr>Id</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The value used to associate an on-premises Active Directory user account with their Azure AD user object. This must be specified if you are using a federated domain for the user&#39;s userPrincipalName (UPN) property when creating a new user account. 
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Mail<wbr>Nickname</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
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
The password for the User. The password must satisfy minimum requirements as specified by the password policy. The maximum length is 256 characters.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Usage<wbr>Location</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The usage location of the User. Required for users that will be assigned licenses due to legal requirement to check for availability of services in countries. The usage location is a two letter country code (ISO standard 3166). Examples include: `NO`, `JP`, and `GB`. Cannot be reset to null once set. 
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">User<wbr>Principal<wbr>Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The User Principal Name of the Azure AD User.
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
            <td class="align-top">account<wbr>Enabled</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
`true` if the account should be enabled, otherwise `false`. Defaults to `true`.
* `mail_nickname`- (Optional) The mail alias for the user. Defaults to the user name part of the User Principal Name.
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
The name to display in the address book for the user.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">force<wbr>Password<wbr>Change</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
`true` if the User is forced to change the password during the next sign-in. Defaults to `false`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">immutable<wbr>Id</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The value used to associate an on-premises Active Directory user account with their Azure AD user object. This must be specified if you are using a federated domain for the user&#39;s userPrincipalName (UPN) property when creating a new user account. 
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">mail<wbr>Nickname</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
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
The password for the User. The password must satisfy minimum requirements as specified by the password policy. The maximum length is 256 characters.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">usage<wbr>Location</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The usage location of the User. Required for users that will be assigned licenses due to legal requirement to check for availability of services in countries. The usage location is a two letter country code (ISO standard 3166). Examples include: `NO`, `JP`, and `GB`. Cannot be reset to null once set. 
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">user<wbr>Principal<wbr>Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The User Principal Name of the Azure AD User.
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
            <td class="align-top">account_<wbr>enabled</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
`true` if the account should be enabled, otherwise `false`. Defaults to `true`.
* `mail_nickname`- (Optional) The mail alias for the user. Defaults to the user name part of the User Principal Name.
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
The name to display in the address book for the user.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">force_<wbr>password_<wbr>change</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
`true` if the User is forced to change the password during the next sign-in. Defaults to `false`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">immutable_<wbr>id</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The value used to associate an on-premises Active Directory user account with their Azure AD user object. This must be specified if you are using a federated domain for the user&#39;s userPrincipalName (UPN) property when creating a new user account. 
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">mail_<wbr>nickname</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
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
The password for the User. The password must satisfy minimum requirements as specified by the password policy. The maximum length is 256 characters.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">usage_<wbr>location</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The usage location of the User. Required for users that will be assigned licenses due to legal requirement to check for availability of services in countries. The usage location is a two letter country code (ISO standard 3166). Examples include: `NO`, `JP`, and `GB`. Cannot be reset to null once set. 
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">user_<wbr>principal_<wbr>name</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The User Principal Name of the Azure AD User.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}







## User Output Properties

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
            <td class="align-top">Account<wbr>Enabled</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} `true` if the account should be enabled, otherwise `false`. Defaults to `true`.
* `mail_nickname`- (Optional) The mail alias for the user. Defaults to the user name part of the User Principal Name.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Display<wbr>Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The name to display in the address book for the user.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Force<wbr>Password<wbr>Change</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} `true` if the User is forced to change the password during the next sign-in. Defaults to `false`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Immutable<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The value used to associate an on-premises Active Directory user account with their Azure AD user object. This must be specified if you are using a federated domain for the user&#39;s userPrincipalName (UPN) property when creating a new user account. 
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Mail</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The primary email address of the Azure AD User.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Mail<wbr>Nickname</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}}  {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Object<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The Object ID of the Azure AD User.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Onpremises<wbr>Sam<wbr>Account<wbr>Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The on premise sam account name of the Azure AD User.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Onpremises<wbr>User<wbr>Principal<wbr>Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The on premise user principal name of the Azure AD User.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Password</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The password for the User. The password must satisfy minimum requirements as specified by the password policy. The maximum length is 256 characters.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Usage<wbr>Location</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The usage location of the User. Required for users that will be assigned licenses due to legal requirement to check for availability of services in countries. The usage location is a two letter country code (ISO standard 3166). Examples include: `NO`, `JP`, and `GB`. Cannot be reset to null once set. 
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">User<wbr>Principal<wbr>Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The User Principal Name of the Azure AD User.
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
            <td class="align-top">Account<wbr>Enabled</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} `true` if the account should be enabled, otherwise `false`. Defaults to `true`.
* `mail_nickname`- (Optional) The mail alias for the user. Defaults to the user name part of the User Principal Name.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Display<wbr>Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The name to display in the address book for the user.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Force<wbr>Password<wbr>Change</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} `true` if the User is forced to change the password during the next sign-in. Defaults to `false`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Immutable<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The value used to associate an on-premises Active Directory user account with their Azure AD user object. This must be specified if you are using a federated domain for the user&#39;s userPrincipalName (UPN) property when creating a new user account. 
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Mail</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The primary email address of the Azure AD User.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Mail<wbr>Nickname</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}}  {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Object<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The Object ID of the Azure AD User.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Onpremises<wbr>Sam<wbr>Account<wbr>Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The on premise sam account name of the Azure AD User.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Onpremises<wbr>User<wbr>Principal<wbr>Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The on premise user principal name of the Azure AD User.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Password</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The password for the User. The password must satisfy minimum requirements as specified by the password policy. The maximum length is 256 characters.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Usage<wbr>Location</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The usage location of the User. Required for users that will be assigned licenses due to legal requirement to check for availability of services in countries. The usage location is a two letter country code (ISO standard 3166). Examples include: `NO`, `JP`, and `GB`. Cannot be reset to null once set. 
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">User<wbr>Principal<wbr>Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The User Principal Name of the Azure AD User.
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
            <td class="align-top">account<wbr>Enabled</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} `true` if the account should be enabled, otherwise `false`. Defaults to `true`.
* `mail_nickname`- (Optional) The mail alias for the user. Defaults to the user name part of the User Principal Name.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">display<wbr>Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The name to display in the address book for the user.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">force<wbr>Password<wbr>Change</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} `true` if the User is forced to change the password during the next sign-in. Defaults to `false`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">immutable<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The value used to associate an on-premises Active Directory user account with their Azure AD user object. This must be specified if you are using a federated domain for the user&#39;s userPrincipalName (UPN) property when creating a new user account. 
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">mail</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The primary email address of the Azure AD User.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">mail<wbr>Nickname</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}}  {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">object<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The Object ID of the Azure AD User.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">onpremises<wbr>Sam<wbr>Account<wbr>Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The on premise sam account name of the Azure AD User.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">onpremises<wbr>User<wbr>Principal<wbr>Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The on premise user principal name of the Azure AD User.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">password</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The password for the User. The password must satisfy minimum requirements as specified by the password policy. The maximum length is 256 characters.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">usage<wbr>Location</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The usage location of the User. Required for users that will be assigned licenses due to legal requirement to check for availability of services in countries. The usage location is a two letter country code (ISO standard 3166). Examples include: `NO`, `JP`, and `GB`. Cannot be reset to null once set. 
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">user<wbr>Principal<wbr>Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The User Principal Name of the Azure AD User.
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
            <td class="align-top">account_<wbr>enabled</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} `true` if the account should be enabled, otherwise `false`. Defaults to `true`.
* `mail_nickname`- (Optional) The mail alias for the user. Defaults to the user name part of the User Principal Name.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">display_<wbr>name</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The name to display in the address book for the user.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">force_<wbr>password_<wbr>change</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} `true` if the User is forced to change the password during the next sign-in. Defaults to `false`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">immutable_<wbr>id</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The value used to associate an on-premises Active Directory user account with their Azure AD user object. This must be specified if you are using a federated domain for the user&#39;s userPrincipalName (UPN) property when creating a new user account. 
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">mail</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The primary email address of the Azure AD User.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">mail_<wbr>nickname</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}}  {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">object_<wbr>id</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The Object ID of the Azure AD User.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">onpremises_<wbr>sam_<wbr>account_<wbr>name</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The on premise sam account name of the Azure AD User.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">onpremises_<wbr>user_<wbr>principal_<wbr>name</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The on premise user principal name of the Azure AD User.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">password</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The password for the User. The password must satisfy minimum requirements as specified by the password policy. The maximum length is 256 characters.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">usage_<wbr>location</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The usage location of the User. Required for users that will be assigned licenses due to legal requirement to check for availability of services in countries. The usage location is a two letter country code (ISO standard 3166). Examples include: `NO`, `JP`, and `GB`. Cannot be reset to null once set. 
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">user_<wbr>principal_<wbr>name</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The User Principal Name of the Azure AD User.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}








## Look up an Existing User Resource

{{< langchoose csharp nojavascript >}}

<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">pulumi.Input&lt;pulumi.ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/azuread//#UserState">UserState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/azuread//#User">User</a></span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>account_enabled=None<span class="p">, </span>display_name=None<span class="p">, </span>force_password_change=None<span class="p">, </span>immutable_id=None<span class="p">, </span>mail=None<span class="p">, </span>mail_nickname=None<span class="p">, </span>object_id=None<span class="p">, </span>onpremises_sam_account_name=None<span class="p">, </span>onpremises_user_principal_name=None<span class="p">, </span>password=None<span class="p">, </span>usage_location=None<span class="p">, </span>user_principal_name=None<span class="p">, __props__=None);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetUser<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">pulumi.IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-azuread/sdk/go/azuread/?tab=doc#UserState">UserState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-azuread/sdk/go/azuread/?tab=doc#User">User</a></span>, error)</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Azuread/Pulumi.Azuread..User.html">User</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Pulumi.Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Azuread/Pulumi.Azuread..UserState.html">UserState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>

Get an existing User resource's state with the given name, ID, and optional extra properties used to qualify the lookup.

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
            <td class="align-top">Account<wbr>Enabled</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
`true` if the account should be enabled, otherwise `false`. Defaults to `true`.
* `mail_nickname`- (Optional) The mail alias for the user. Defaults to the user name part of the User Principal Name.
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
The name to display in the address book for the user.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Force<wbr>Password<wbr>Change</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
`true` if the User is forced to change the password during the next sign-in. Defaults to `false`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Immutable<wbr>Id</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The value used to associate an on-premises Active Directory user account with their Azure AD user object. This must be specified if you are using a federated domain for the user&#39;s userPrincipalName (UPN) property when creating a new user account. 
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Mail</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The primary email address of the Azure AD User.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Mail<wbr>Nickname</td>
            <td class="align-top">
                
                <code>string?</code>
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
The Object ID of the Azure AD User.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Onpremises<wbr>Sam<wbr>Account<wbr>Name</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The on premise sam account name of the Azure AD User.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Onpremises<wbr>User<wbr>Principal<wbr>Name</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The on premise user principal name of the Azure AD User.
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
The password for the User. The password must satisfy minimum requirements as specified by the password policy. The maximum length is 256 characters.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Usage<wbr>Location</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The usage location of the User. Required for users that will be assigned licenses due to legal requirement to check for availability of services in countries. The usage location is a two letter country code (ISO standard 3166). Examples include: `NO`, `JP`, and `GB`. Cannot be reset to null once set. 
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">User<wbr>Principal<wbr>Name</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The User Principal Name of the Azure AD User.
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
            <td class="align-top">Account<wbr>Enabled</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
`true` if the account should be enabled, otherwise `false`. Defaults to `true`.
* `mail_nickname`- (Optional) The mail alias for the user. Defaults to the user name part of the User Principal Name.
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
The name to display in the address book for the user.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Force<wbr>Password<wbr>Change</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
`true` if the User is forced to change the password during the next sign-in. Defaults to `false`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Immutable<wbr>Id</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The value used to associate an on-premises Active Directory user account with their Azure AD user object. This must be specified if you are using a federated domain for the user&#39;s userPrincipalName (UPN) property when creating a new user account. 
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Mail</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The primary email address of the Azure AD User.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Mail<wbr>Nickname</td>
            <td class="align-top">
                
                <code>*string</code>
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
The Object ID of the Azure AD User.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Onpremises<wbr>Sam<wbr>Account<wbr>Name</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The on premise sam account name of the Azure AD User.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Onpremises<wbr>User<wbr>Principal<wbr>Name</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The on premise user principal name of the Azure AD User.
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
The password for the User. The password must satisfy minimum requirements as specified by the password policy. The maximum length is 256 characters.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Usage<wbr>Location</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The usage location of the User. Required for users that will be assigned licenses due to legal requirement to check for availability of services in countries. The usage location is a two letter country code (ISO standard 3166). Examples include: `NO`, `JP`, and `GB`. Cannot be reset to null once set. 
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">User<wbr>Principal<wbr>Name</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The User Principal Name of the Azure AD User.
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
            <td class="align-top">account<wbr>Enabled</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
`true` if the account should be enabled, otherwise `false`. Defaults to `true`.
* `mail_nickname`- (Optional) The mail alias for the user. Defaults to the user name part of the User Principal Name.
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
The name to display in the address book for the user.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">force<wbr>Password<wbr>Change</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
`true` if the User is forced to change the password during the next sign-in. Defaults to `false`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">immutable<wbr>Id</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The value used to associate an on-premises Active Directory user account with their Azure AD user object. This must be specified if you are using a federated domain for the user&#39;s userPrincipalName (UPN) property when creating a new user account. 
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">mail</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The primary email address of the Azure AD User.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">mail<wbr>Nickname</td>
            <td class="align-top">
                
                <code>string?</code>
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
The Object ID of the Azure AD User.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">onpremises<wbr>Sam<wbr>Account<wbr>Name</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The on premise sam account name of the Azure AD User.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">onpremises<wbr>User<wbr>Principal<wbr>Name</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The on premise user principal name of the Azure AD User.
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
The password for the User. The password must satisfy minimum requirements as specified by the password policy. The maximum length is 256 characters.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">usage<wbr>Location</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The usage location of the User. Required for users that will be assigned licenses due to legal requirement to check for availability of services in countries. The usage location is a two letter country code (ISO standard 3166). Examples include: `NO`, `JP`, and `GB`. Cannot be reset to null once set. 
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">user<wbr>Principal<wbr>Name</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The User Principal Name of the Azure AD User.
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
            <td class="align-top">account_<wbr>enabled</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
`true` if the account should be enabled, otherwise `false`. Defaults to `true`.
* `mail_nickname`- (Optional) The mail alias for the user. Defaults to the user name part of the User Principal Name.
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
The name to display in the address book for the user.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">force_<wbr>password_<wbr>change</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
`true` if the User is forced to change the password during the next sign-in. Defaults to `false`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">immutable_<wbr>id</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The value used to associate an on-premises Active Directory user account with their Azure AD user object. This must be specified if you are using a federated domain for the user&#39;s userPrincipalName (UPN) property when creating a new user account. 
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">mail</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The primary email address of the Azure AD User.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">mail_<wbr>nickname</td>
            <td class="align-top">
                
                <code>str</code>
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
The Object ID of the Azure AD User.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">onpremises_<wbr>sam_<wbr>account_<wbr>name</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The on premise sam account name of the Azure AD User.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">onpremises_<wbr>user_<wbr>principal_<wbr>name</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The on premise user principal name of the Azure AD User.
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
The password for the User. The password must satisfy minimum requirements as specified by the password policy. The maximum length is 256 characters.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">usage_<wbr>location</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The usage location of the User. Required for users that will be assigned licenses due to legal requirement to check for availability of services in countries. The usage location is a two letter country code (ISO standard 3166). Examples include: `NO`, `JP`, and `GB`. Cannot be reset to null once set. 
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">user_<wbr>principal_<wbr>name</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The User Principal Name of the Azure AD User.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}










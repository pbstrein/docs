
---
title: "UserPoolClient"
block_external_search_index: true
---

Provides a Cognito User Pool Client resource.

## Example Usage

### Create a basic user pool client

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const pool = new aws.cognito.UserPool("pool", {});
const client = new aws.cognito.UserPoolClient("client", {
    userPoolId: pool.id,
});
```

### Create a user pool client with no SRP authentication

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const pool = new aws.cognito.UserPool("pool", {});
const client = new aws.cognito.UserPoolClient("client", {
    explicitAuthFlows: ["ADMIN_NO_SRP_AUTH"],
    generateSecret: true,
    userPoolId: pool.id,
});
```

> This content is derived from https://github.com/terraform-providers/terraform-provider-aws/blob/master/website/docs/r/cognito_user_pool_client.markdown.



## Create a UserPoolClient Resource

{{< chooser language "javascript,typescript,python,go,csharp" / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/cognito/#UserPoolClient">UserPoolClient</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/cognito/#UserPoolClientArgs">UserPoolClientArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">UserPoolClient</span><span class="p">(resource_name, opts=None, </span>allowed_oauth_flows=None<span class="p">, </span>allowed_oauth_flows_user_pool_client=None<span class="p">, </span>allowed_oauth_scopes=None<span class="p">, </span>callback_urls=None<span class="p">, </span>default_redirect_uri=None<span class="p">, </span>explicit_auth_flows=None<span class="p">, </span>generate_secret=None<span class="p">, </span>logout_urls=None<span class="p">, </span>name=None<span class="p">, </span>read_attributes=None<span class="p">, </span>refresh_token_validity=None<span class="p">, </span>supported_identity_providers=None<span class="p">, </span>user_pool_id=None<span class="p">, </span>write_attributes=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewUserPoolClient<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/cognito?tab=doc#UserPoolClientArgs">UserPoolClientArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/cognito?tab=doc#UserPoolClient">UserPoolClient</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Cognito.UserPoolClient.html">UserPoolClient</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Cognito.UserPoolClientArgs.html">UserPoolClientArgs</a></span> <span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
{{% /choosable %}}

Contructor Arguments

{{% choosable language nodejs %}}

<dl class="resources-ctor-args">
    <dt class="property-required" title="Required">
        name
        <span class="property-indicator"></span>
    </dt>
    <dd>The unique name of the resource.</dd>
    <dt class="property-optional" title="Optional">
        args
        <span class="property-indicator"></span>
    </dt>
    <dd>The arguments to use to populate this resource's properties.</dd>
    <dt class="property-optional" title="Optional">
        opts
        <span class="property-indicator"></span>
    </dt>
    <dd>A bag of options that control this resource's behavior.</dd>
</dl>

{{% /choosable %}}

{{% choosable language python %}}
<dl class="resources-ctor-args">
    <dt class="property-required" title="Required">
        name
        <span class="property-indicator"></span>
    </dt>
    <dd>The unique name of the resource.</dd>
    <dt class="property-optional" title="Optional">
        opts
        <span class="property-indicator"></span>
    </dt>
    <dd>A bag of options that control this resource's behavior.</dd>
</dl>
{{% /choosable %}}

{{% choosable language go %}}

<dl class="resources-ctor-args">
    <dt class="property-required" title="Required">
        name
        <span class="property-indicator"></span>
    </dt>
    <dd>The unique name of the resource.</dd>
    <dt class="property-optional" title="Optional">
        args
        <span class="property-indicator"></span>
    </dt>
    <dd>The arguments to use to populate this resource's properties.</dd>
    <dt class="property-optional" title="Optional">
        opts
        <span class="property-indicator"></span>
    </dt>
    <dd>A bag of options that control this resource's behavior.</dd>
</dl>

{{% /choosable %}}

{{% choosable language csharp %}}

<dl class="resources-ctor-args">
    <dt class="property-required" title="Required">
        name
        <span class="property-indicator"></span>
    </dt>
    <dd>The unique name of the resource.</dd>
    <dt class="property-optional" title="Optional">
        args
        <span class="property-indicator"></span>
    </dt>
    <dd>The arguments to use to populate this resource's properties.</dd>
    <dt class="property-optional" title="Optional">
        opts
        <span class="property-indicator"></span>
    </dt>
    <dd>A bag of options that control this resource's behavior.</dd>
</dl>

{{% /choosable %}}

Resource Arguments




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Allowed<wbr>Oauth<wbr>Flows<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}List of allowed OAuth flows (code, implicit, client_credentials).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Allowed<wbr>Oauth<wbr>Flows<wbr>User<wbr>Pool<wbr>Client<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Whether the client is allowed to follow the OAuth protocol when interacting with Cognito user pools.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Allowed<wbr>Oauth<wbr>Scopes<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}List of allowed OAuth scopes (phone, email, openid, profile, and aws.cognito.signin.user.admin).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Callback<wbr>Urls<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}List of allowed callback URLs for the identity providers.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Default<wbr>Redirect<wbr>Uri<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The default redirect URI. Must be in the list of callback URLs.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Explicit<wbr>Auth<wbr>Flows<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}List of authentication flows (ADMIN_NO_SRP_AUTH, CUSTOM_AUTH_FLOW_ONLY,  USER_PASSWORD_AUTH, ALLOW_ADMIN_USER_PASSWORD_AUTH, ALLOW_CUSTOM_AUTH, ALLOW_USER_PASSWORD_AUTH, ALLOW_USER_SRP_AUTH, ALLOW_REFRESH_TOKEN_AUTH).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Generate<wbr>Secret<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Should an application secret be generated.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Logout<wbr>Urls<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}List of allowed logout URLs for the identity providers.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the application client.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Read<wbr>Attributes<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}List of user pool attributes the application client can read from.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Refresh<wbr>Token<wbr>Validity<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The time limit in days refresh tokens are valid for.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Supported<wbr>Identity<wbr>Providers<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}List of provider names for the identity providers that are supported on this client.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">User<wbr>Pool<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The user pool the client belongs to.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Write<wbr>Attributes<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}List of user pool attributes the application client can write to.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Allowed<wbr>Oauth<wbr>Flows<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}List of allowed OAuth flows (code, implicit, client_credentials).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Allowed<wbr>Oauth<wbr>Flows<wbr>User<wbr>Pool<wbr>Client<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Whether the client is allowed to follow the OAuth protocol when interacting with Cognito user pools.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Allowed<wbr>Oauth<wbr>Scopes<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}List of allowed OAuth scopes (phone, email, openid, profile, and aws.cognito.signin.user.admin).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Callback<wbr>Urls<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}List of allowed callback URLs for the identity providers.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Default<wbr>Redirect<wbr>Uri<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The default redirect URI. Must be in the list of callback URLs.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Explicit<wbr>Auth<wbr>Flows<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}List of authentication flows (ADMIN_NO_SRP_AUTH, CUSTOM_AUTH_FLOW_ONLY,  USER_PASSWORD_AUTH, ALLOW_ADMIN_USER_PASSWORD_AUTH, ALLOW_CUSTOM_AUTH, ALLOW_USER_PASSWORD_AUTH, ALLOW_USER_SRP_AUTH, ALLOW_REFRESH_TOKEN_AUTH).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Generate<wbr>Secret<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Should an application secret be generated.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Logout<wbr>Urls<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}List of allowed logout URLs for the identity providers.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name of the application client.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Read<wbr>Attributes<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}List of user pool attributes the application client can read from.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Refresh<wbr>Token<wbr>Validity<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The time limit in days refresh tokens are valid for.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Supported<wbr>Identity<wbr>Providers<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}List of provider names for the identity providers that are supported on this client.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">User<wbr>Pool<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The user pool the client belongs to.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Write<wbr>Attributes<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}List of user pool attributes the application client can write to.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">allowed<wbr>Oauth<wbr>Flows<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}List of allowed OAuth flows (code, implicit, client_credentials).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">allowed<wbr>Oauth<wbr>Flows<wbr>User<wbr>Pool<wbr>Client<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Whether the client is allowed to follow the OAuth protocol when interacting with Cognito user pools.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">allowed<wbr>Oauth<wbr>Scopes<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}List of allowed OAuth scopes (phone, email, openid, profile, and aws.cognito.signin.user.admin).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">callback<wbr>Urls<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}List of allowed callback URLs for the identity providers.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">default<wbr>Redirect<wbr>Uri<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The default redirect URI. Must be in the list of callback URLs.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">explicit<wbr>Auth<wbr>Flows<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}List of authentication flows (ADMIN_NO_SRP_AUTH, CUSTOM_AUTH_FLOW_ONLY,  USER_PASSWORD_AUTH, ALLOW_ADMIN_USER_PASSWORD_AUTH, ALLOW_CUSTOM_AUTH, ALLOW_USER_PASSWORD_AUTH, ALLOW_USER_SRP_AUTH, ALLOW_REFRESH_TOKEN_AUTH).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">generate<wbr>Secret<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Should an application secret be generated.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">logout<wbr>Urls<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}List of allowed logout URLs for the identity providers.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the application client.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">read<wbr>Attributes<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}List of user pool attributes the application client can read from.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">refresh<wbr>Token<wbr>Validity<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The time limit in days refresh tokens are valid for.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">supported<wbr>Identity<wbr>Providers<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}List of provider names for the identity providers that are supported on this client.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">user<wbr>Pool<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The user pool the client belongs to.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">write<wbr>Attributes<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}List of user pool attributes the application client can write to.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">allowed_<wbr>oauth_<wbr>flows<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}List of allowed OAuth flows (code, implicit, client_credentials).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">allowed_<wbr>oauth_<wbr>flows_<wbr>user_<wbr>pool_<wbr>client<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Whether the client is allowed to follow the OAuth protocol when interacting with Cognito user pools.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">allowed_<wbr>oauth_<wbr>scopes<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}List of allowed OAuth scopes (phone, email, openid, profile, and aws.cognito.signin.user.admin).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">callback_<wbr>urls<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}List of allowed callback URLs for the identity providers.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">default_<wbr>redirect_<wbr>uri<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The default redirect URI. Must be in the list of callback URLs.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">explicit_<wbr>auth_<wbr>flows<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}List of authentication flows (ADMIN_NO_SRP_AUTH, CUSTOM_AUTH_FLOW_ONLY,  USER_PASSWORD_AUTH, ALLOW_ADMIN_USER_PASSWORD_AUTH, ALLOW_CUSTOM_AUTH, ALLOW_USER_PASSWORD_AUTH, ALLOW_USER_SRP_AUTH, ALLOW_REFRESH_TOKEN_AUTH).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">generate_<wbr>secret<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Should an application secret be generated.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">logout_<wbr>urls<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}List of allowed logout URLs for the identity providers.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the application client.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">read_<wbr>attributes<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}List of user pool attributes the application client can read from.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">refresh_<wbr>token_<wbr>validity<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The time limit in days refresh tokens are valid for.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">supported_<wbr>identity_<wbr>providers<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}List of provider names for the identity providers that are supported on this client.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">user_<wbr>pool_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The user pool the client belongs to.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">write_<wbr>attributes<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}List of user pool attributes the application client can write to.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}




## UserPoolClient Output Properties

The following output properties are available:




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Allowed<wbr>Oauth<wbr>Flows<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}List of allowed OAuth flows (code, implicit, client_credentials).
{{% /md %}}</dd>

    <dt class="property-"
            title="">Allowed<wbr>Oauth<wbr>Flows<wbr>User<wbr>Pool<wbr>Client<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Whether the client is allowed to follow the OAuth protocol when interacting with Cognito user pools.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Allowed<wbr>Oauth<wbr>Scopes<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}List of allowed OAuth scopes (phone, email, openid, profile, and aws.cognito.signin.user.admin).
{{% /md %}}</dd>

    <dt class="property-"
            title="">Callback<wbr>Urls<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}List of allowed callback URLs for the identity providers.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Client<wbr>Secret<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The client secret of the user pool client.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Default<wbr>Redirect<wbr>Uri<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The default redirect URI. Must be in the list of callback URLs.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Explicit<wbr>Auth<wbr>Flows<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}List of authentication flows (ADMIN_NO_SRP_AUTH, CUSTOM_AUTH_FLOW_ONLY,  USER_PASSWORD_AUTH, ALLOW_ADMIN_USER_PASSWORD_AUTH, ALLOW_CUSTOM_AUTH, ALLOW_USER_PASSWORD_AUTH, ALLOW_USER_SRP_AUTH, ALLOW_REFRESH_TOKEN_AUTH).
{{% /md %}}</dd>

    <dt class="property-"
            title="">Generate<wbr>Secret<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Should an application secret be generated.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Logout<wbr>Urls<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}List of allowed logout URLs for the identity providers.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the application client.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Read<wbr>Attributes<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}List of user pool attributes the application client can read from.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Refresh<wbr>Token<wbr>Validity<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The time limit in days refresh tokens are valid for.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Supported<wbr>Identity<wbr>Providers<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}List of provider names for the identity providers that are supported on this client.
{{% /md %}}</dd>

    <dt class="property-"
            title="">User<wbr>Pool<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The user pool the client belongs to.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Write<wbr>Attributes<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}List of user pool attributes the application client can write to.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Allowed<wbr>Oauth<wbr>Flows<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}List of allowed OAuth flows (code, implicit, client_credentials).
{{% /md %}}</dd>

    <dt class="property-"
            title="">Allowed<wbr>Oauth<wbr>Flows<wbr>User<wbr>Pool<wbr>Client<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Whether the client is allowed to follow the OAuth protocol when interacting with Cognito user pools.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Allowed<wbr>Oauth<wbr>Scopes<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}List of allowed OAuth scopes (phone, email, openid, profile, and aws.cognito.signin.user.admin).
{{% /md %}}</dd>

    <dt class="property-"
            title="">Callback<wbr>Urls<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}List of allowed callback URLs for the identity providers.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Client<wbr>Secret<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The client secret of the user pool client.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Default<wbr>Redirect<wbr>Uri<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The default redirect URI. Must be in the list of callback URLs.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Explicit<wbr>Auth<wbr>Flows<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}List of authentication flows (ADMIN_NO_SRP_AUTH, CUSTOM_AUTH_FLOW_ONLY,  USER_PASSWORD_AUTH, ALLOW_ADMIN_USER_PASSWORD_AUTH, ALLOW_CUSTOM_AUTH, ALLOW_USER_PASSWORD_AUTH, ALLOW_USER_SRP_AUTH, ALLOW_REFRESH_TOKEN_AUTH).
{{% /md %}}</dd>

    <dt class="property-"
            title="">Generate<wbr>Secret<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Should an application secret be generated.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Logout<wbr>Urls<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}List of allowed logout URLs for the identity providers.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the application client.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Read<wbr>Attributes<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}List of user pool attributes the application client can read from.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Refresh<wbr>Token<wbr>Validity<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The time limit in days refresh tokens are valid for.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Supported<wbr>Identity<wbr>Providers<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}List of provider names for the identity providers that are supported on this client.
{{% /md %}}</dd>

    <dt class="property-"
            title="">User<wbr>Pool<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The user pool the client belongs to.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Write<wbr>Attributes<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}List of user pool attributes the application client can write to.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">allowed<wbr>Oauth<wbr>Flows<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}List of allowed OAuth flows (code, implicit, client_credentials).
{{% /md %}}</dd>

    <dt class="property-"
            title="">allowed<wbr>Oauth<wbr>Flows<wbr>User<wbr>Pool<wbr>Client<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Whether the client is allowed to follow the OAuth protocol when interacting with Cognito user pools.
{{% /md %}}</dd>

    <dt class="property-"
            title="">allowed<wbr>Oauth<wbr>Scopes<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}List of allowed OAuth scopes (phone, email, openid, profile, and aws.cognito.signin.user.admin).
{{% /md %}}</dd>

    <dt class="property-"
            title="">callback<wbr>Urls<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}List of allowed callback URLs for the identity providers.
{{% /md %}}</dd>

    <dt class="property-"
            title="">client<wbr>Secret<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The client secret of the user pool client.
{{% /md %}}</dd>

    <dt class="property-"
            title="">default<wbr>Redirect<wbr>Uri<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The default redirect URI. Must be in the list of callback URLs.
{{% /md %}}</dd>

    <dt class="property-"
            title="">explicit<wbr>Auth<wbr>Flows<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}List of authentication flows (ADMIN_NO_SRP_AUTH, CUSTOM_AUTH_FLOW_ONLY,  USER_PASSWORD_AUTH, ALLOW_ADMIN_USER_PASSWORD_AUTH, ALLOW_CUSTOM_AUTH, ALLOW_USER_PASSWORD_AUTH, ALLOW_USER_SRP_AUTH, ALLOW_REFRESH_TOKEN_AUTH).
{{% /md %}}</dd>

    <dt class="property-"
            title="">generate<wbr>Secret<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Should an application secret be generated.
{{% /md %}}</dd>

    <dt class="property-"
            title="">logout<wbr>Urls<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}List of allowed logout URLs for the identity providers.
{{% /md %}}</dd>

    <dt class="property-"
            title="">name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the application client.
{{% /md %}}</dd>

    <dt class="property-"
            title="">read<wbr>Attributes<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}List of user pool attributes the application client can read from.
{{% /md %}}</dd>

    <dt class="property-"
            title="">refresh<wbr>Token<wbr>Validity<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The time limit in days refresh tokens are valid for.
{{% /md %}}</dd>

    <dt class="property-"
            title="">supported<wbr>Identity<wbr>Providers<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}List of provider names for the identity providers that are supported on this client.
{{% /md %}}</dd>

    <dt class="property-"
            title="">user<wbr>Pool<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The user pool the client belongs to.
{{% /md %}}</dd>

    <dt class="property-"
            title="">write<wbr>Attributes<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}List of user pool attributes the application client can write to.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">allowed_<wbr>oauth_<wbr>flows<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}List of allowed OAuth flows (code, implicit, client_credentials).
{{% /md %}}</dd>

    <dt class="property-"
            title="">allowed_<wbr>oauth_<wbr>flows_<wbr>user_<wbr>pool_<wbr>client<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Whether the client is allowed to follow the OAuth protocol when interacting with Cognito user pools.
{{% /md %}}</dd>

    <dt class="property-"
            title="">allowed_<wbr>oauth_<wbr>scopes<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}List of allowed OAuth scopes (phone, email, openid, profile, and aws.cognito.signin.user.admin).
{{% /md %}}</dd>

    <dt class="property-"
            title="">callback_<wbr>urls<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}List of allowed callback URLs for the identity providers.
{{% /md %}}</dd>

    <dt class="property-"
            title="">client_<wbr>secret<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The client secret of the user pool client.
{{% /md %}}</dd>

    <dt class="property-"
            title="">default_<wbr>redirect_<wbr>uri<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The default redirect URI. Must be in the list of callback URLs.
{{% /md %}}</dd>

    <dt class="property-"
            title="">explicit_<wbr>auth_<wbr>flows<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}List of authentication flows (ADMIN_NO_SRP_AUTH, CUSTOM_AUTH_FLOW_ONLY,  USER_PASSWORD_AUTH, ALLOW_ADMIN_USER_PASSWORD_AUTH, ALLOW_CUSTOM_AUTH, ALLOW_USER_PASSWORD_AUTH, ALLOW_USER_SRP_AUTH, ALLOW_REFRESH_TOKEN_AUTH).
{{% /md %}}</dd>

    <dt class="property-"
            title="">generate_<wbr>secret<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Should an application secret be generated.
{{% /md %}}</dd>

    <dt class="property-"
            title="">logout_<wbr>urls<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}List of allowed logout URLs for the identity providers.
{{% /md %}}</dd>

    <dt class="property-"
            title="">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the application client.
{{% /md %}}</dd>

    <dt class="property-"
            title="">read_<wbr>attributes<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}List of user pool attributes the application client can read from.
{{% /md %}}</dd>

    <dt class="property-"
            title="">refresh_<wbr>token_<wbr>validity<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The time limit in days refresh tokens are valid for.
{{% /md %}}</dd>

    <dt class="property-"
            title="">supported_<wbr>identity_<wbr>providers<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}List of provider names for the identity providers that are supported on this client.
{{% /md %}}</dd>

    <dt class="property-"
            title="">user_<wbr>pool_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The user pool the client belongs to.
{{% /md %}}</dd>

    <dt class="property-"
            title="">write_<wbr>attributes<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}List of user pool attributes the application client can write to.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





## Look up an Existing UserPoolClient Resource

{{< chooser language "javascript,typescript,python,go,csharp  " / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">pulumi.Input&lt;pulumi.ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/cognito/#UserPoolClientState">UserPoolClientState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/cognito/#UserPoolClient">UserPoolClient</a></span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>allowed_oauth_flows=None<span class="p">, </span>allowed_oauth_flows_user_pool_client=None<span class="p">, </span>allowed_oauth_scopes=None<span class="p">, </span>callback_urls=None<span class="p">, </span>client_secret=None<span class="p">, </span>default_redirect_uri=None<span class="p">, </span>explicit_auth_flows=None<span class="p">, </span>generate_secret=None<span class="p">, </span>logout_urls=None<span class="p">, </span>name=None<span class="p">, </span>read_attributes=None<span class="p">, </span>refresh_token_validity=None<span class="p">, </span>supported_identity_providers=None<span class="p">, </span>user_pool_id=None<span class="p">, </span>write_attributes=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetUserPoolClient<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">pulumi.IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/cognito?tab=doc#UserPoolClientState">UserPoolClientState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/cognito?tab=doc#UserPoolClient">UserPoolClient</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Cognito.UserPoolClient.html">UserPoolClient</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Pulumi.Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Cognito.UserPoolClientState.html">UserPoolClientState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
{{% /choosable %}}

Get an existing UserPoolClient resource's state with the given name, ID, and optional extra properties used to qualify the lookup.

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



{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Allowed<wbr>Oauth<wbr>Flows<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}List of allowed OAuth flows (code, implicit, client_credentials).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Allowed<wbr>Oauth<wbr>Flows<wbr>User<wbr>Pool<wbr>Client<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Whether the client is allowed to follow the OAuth protocol when interacting with Cognito user pools.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Allowed<wbr>Oauth<wbr>Scopes<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}List of allowed OAuth scopes (phone, email, openid, profile, and aws.cognito.signin.user.admin).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Callback<wbr>Urls<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}List of allowed callback URLs for the identity providers.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Client<wbr>Secret<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The client secret of the user pool client.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Default<wbr>Redirect<wbr>Uri<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The default redirect URI. Must be in the list of callback URLs.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Explicit<wbr>Auth<wbr>Flows<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}List of authentication flows (ADMIN_NO_SRP_AUTH, CUSTOM_AUTH_FLOW_ONLY,  USER_PASSWORD_AUTH, ALLOW_ADMIN_USER_PASSWORD_AUTH, ALLOW_CUSTOM_AUTH, ALLOW_USER_PASSWORD_AUTH, ALLOW_USER_SRP_AUTH, ALLOW_REFRESH_TOKEN_AUTH).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Generate<wbr>Secret<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Should an application secret be generated.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Logout<wbr>Urls<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}List of allowed logout URLs for the identity providers.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the application client.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Read<wbr>Attributes<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}List of user pool attributes the application client can read from.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Refresh<wbr>Token<wbr>Validity<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The time limit in days refresh tokens are valid for.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Supported<wbr>Identity<wbr>Providers<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}List of provider names for the identity providers that are supported on this client.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">User<wbr>Pool<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The user pool the client belongs to.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Write<wbr>Attributes<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}List of user pool attributes the application client can write to.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Allowed<wbr>Oauth<wbr>Flows<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}List of allowed OAuth flows (code, implicit, client_credentials).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Allowed<wbr>Oauth<wbr>Flows<wbr>User<wbr>Pool<wbr>Client<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Whether the client is allowed to follow the OAuth protocol when interacting with Cognito user pools.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Allowed<wbr>Oauth<wbr>Scopes<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}List of allowed OAuth scopes (phone, email, openid, profile, and aws.cognito.signin.user.admin).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Callback<wbr>Urls<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}List of allowed callback URLs for the identity providers.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Client<wbr>Secret<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The client secret of the user pool client.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Default<wbr>Redirect<wbr>Uri<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The default redirect URI. Must be in the list of callback URLs.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Explicit<wbr>Auth<wbr>Flows<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}List of authentication flows (ADMIN_NO_SRP_AUTH, CUSTOM_AUTH_FLOW_ONLY,  USER_PASSWORD_AUTH, ALLOW_ADMIN_USER_PASSWORD_AUTH, ALLOW_CUSTOM_AUTH, ALLOW_USER_PASSWORD_AUTH, ALLOW_USER_SRP_AUTH, ALLOW_REFRESH_TOKEN_AUTH).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Generate<wbr>Secret<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Should an application secret be generated.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Logout<wbr>Urls<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}List of allowed logout URLs for the identity providers.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name of the application client.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Read<wbr>Attributes<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}List of user pool attributes the application client can read from.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Refresh<wbr>Token<wbr>Validity<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The time limit in days refresh tokens are valid for.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Supported<wbr>Identity<wbr>Providers<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}List of provider names for the identity providers that are supported on this client.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">User<wbr>Pool<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The user pool the client belongs to.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Write<wbr>Attributes<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}List of user pool attributes the application client can write to.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">allowed<wbr>Oauth<wbr>Flows<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}List of allowed OAuth flows (code, implicit, client_credentials).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">allowed<wbr>Oauth<wbr>Flows<wbr>User<wbr>Pool<wbr>Client<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Whether the client is allowed to follow the OAuth protocol when interacting with Cognito user pools.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">allowed<wbr>Oauth<wbr>Scopes<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}List of allowed OAuth scopes (phone, email, openid, profile, and aws.cognito.signin.user.admin).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">callback<wbr>Urls<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}List of allowed callback URLs for the identity providers.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">client<wbr>Secret<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The client secret of the user pool client.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">default<wbr>Redirect<wbr>Uri<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The default redirect URI. Must be in the list of callback URLs.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">explicit<wbr>Auth<wbr>Flows<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}List of authentication flows (ADMIN_NO_SRP_AUTH, CUSTOM_AUTH_FLOW_ONLY,  USER_PASSWORD_AUTH, ALLOW_ADMIN_USER_PASSWORD_AUTH, ALLOW_CUSTOM_AUTH, ALLOW_USER_PASSWORD_AUTH, ALLOW_USER_SRP_AUTH, ALLOW_REFRESH_TOKEN_AUTH).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">generate<wbr>Secret<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Should an application secret be generated.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">logout<wbr>Urls<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}List of allowed logout URLs for the identity providers.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the application client.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">read<wbr>Attributes<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}List of user pool attributes the application client can read from.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">refresh<wbr>Token<wbr>Validity<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The time limit in days refresh tokens are valid for.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">supported<wbr>Identity<wbr>Providers<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}List of provider names for the identity providers that are supported on this client.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">user<wbr>Pool<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The user pool the client belongs to.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">write<wbr>Attributes<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}List of user pool attributes the application client can write to.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">allowed_<wbr>oauth_<wbr>flows<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}List of allowed OAuth flows (code, implicit, client_credentials).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">allowed_<wbr>oauth_<wbr>flows_<wbr>user_<wbr>pool_<wbr>client<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Whether the client is allowed to follow the OAuth protocol when interacting with Cognito user pools.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">allowed_<wbr>oauth_<wbr>scopes<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}List of allowed OAuth scopes (phone, email, openid, profile, and aws.cognito.signin.user.admin).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">callback_<wbr>urls<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}List of allowed callback URLs for the identity providers.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">client_<wbr>secret<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The client secret of the user pool client.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">default_<wbr>redirect_<wbr>uri<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The default redirect URI. Must be in the list of callback URLs.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">explicit_<wbr>auth_<wbr>flows<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}List of authentication flows (ADMIN_NO_SRP_AUTH, CUSTOM_AUTH_FLOW_ONLY,  USER_PASSWORD_AUTH, ALLOW_ADMIN_USER_PASSWORD_AUTH, ALLOW_CUSTOM_AUTH, ALLOW_USER_PASSWORD_AUTH, ALLOW_USER_SRP_AUTH, ALLOW_REFRESH_TOKEN_AUTH).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">generate_<wbr>secret<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Should an application secret be generated.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">logout_<wbr>urls<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}List of allowed logout URLs for the identity providers.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the application client.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">read_<wbr>attributes<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}List of user pool attributes the application client can read from.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">refresh_<wbr>token_<wbr>validity<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The time limit in days refresh tokens are valid for.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">supported_<wbr>identity_<wbr>providers<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}List of provider names for the identity providers that are supported on this client.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">user_<wbr>pool_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The user pool the client belongs to.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">write_<wbr>attributes<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}List of user pool attributes the application client can write to.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}







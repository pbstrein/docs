
---
title: "IdentityPool"
block_external_search_index: true
---

Provides an AWS Cognito Identity Pool.

## Example Usage

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";
import * as fs from "fs";

const defaultSamlProvider = new aws.iam.SamlProvider("default", {
    samlMetadataDocument: fs.readFileSync("saml-metadata.xml", "utf-8"),
});
const main = new aws.cognito.IdentityPool("main", {
    allowUnauthenticatedIdentities: false,
    cognitoIdentityProviders: [
        {
            clientId: "6lhlkkfbfb4q5kpp90urffae",
            providerName: "cognito-idp.us-east-1.amazonaws.com/us-east-1_Tv0493apJ",
            serverSideTokenCheck: false,
        },
        {
            clientId: "7kodkvfqfb4qfkp39eurffae",
            providerName: "cognito-idp.us-east-1.amazonaws.com/eu-west-1_Zr231apJu",
            serverSideTokenCheck: false,
        },
    ],
    identityPoolName: "identity pool",
    openidConnectProviderArns: ["arn:aws:iam::123456789012:oidc-provider/foo.example.com"],
    samlProviderArns: [defaultSamlProvider.arn],
    supportedLoginProviders: {
        "accounts.google.com": "123456789012.apps.googleusercontent.com",
        "graph.facebook.com": "7346241598935552",
    },
});
```

> This content is derived from https://github.com/terraform-providers/terraform-provider-aws/blob/master/website/docs/r/cognito_identity_pool.markdown.



## Create a IdentityPool Resource

{{< chooser language "javascript,typescript,python,go,csharp" / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/cognito/#IdentityPool">IdentityPool</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/cognito/#IdentityPoolArgs">IdentityPoolArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">IdentityPool</span><span class="p">(resource_name, opts=None, </span>allow_unauthenticated_identities=None<span class="p">, </span>cognito_identity_providers=None<span class="p">, </span>developer_provider_name=None<span class="p">, </span>identity_pool_name=None<span class="p">, </span>openid_connect_provider_arns=None<span class="p">, </span>saml_provider_arns=None<span class="p">, </span>supported_login_providers=None<span class="p">, </span>tags=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewIdentityPool<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/cognito?tab=doc#IdentityPoolArgs">IdentityPoolArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/cognito?tab=doc#IdentityPool">IdentityPool</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Cognito.IdentityPool.html">IdentityPool</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Cognito.IdentityPoolArgs.html">IdentityPoolArgs</a></span> <span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
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
            title="Optional">Allow<wbr>Unauthenticated<wbr>Identities<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Whether the identity pool supports unauthenticated logins or not.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Cognito<wbr>Identity<wbr>Providers<span class="property-indicator"></span>
        <span class="property-type"><a href="#identitypoolcognitoidentityprovider">List&lt;Identity<wbr>Pool<wbr>Cognito<wbr>Identity<wbr>Provider<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}An array of Amazon Cognito Identity user pools and their client IDs.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Developer<wbr>Provider<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The &#34;domain&#34; by which Cognito will refer to your users. This name acts as a placeholder that allows your
backend and the Cognito service to communicate about the developer provider.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Identity<wbr>Pool<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Cognito Identity Pool name.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Openid<wbr>Connect<wbr>Provider<wbr>Arns<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}A list of OpendID Connect provider ARNs.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Saml<wbr>Provider<wbr>Arns<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}An array of Amazon Resource Names (ARNs) of the SAML provider for your identity.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Supported<wbr>Login<wbr>Providers<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, string>?</span>
    </dt>
    <dd>{{% md %}}Key-Value pairs mapping provider names to provider app IDs.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the Identity Pool.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Allow<wbr>Unauthenticated<wbr>Identities<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Whether the identity pool supports unauthenticated logins or not.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Cognito<wbr>Identity<wbr>Providers<span class="property-indicator"></span>
        <span class="property-type"><a href="#identitypoolcognitoidentityprovider">[]Identity<wbr>Pool<wbr>Cognito<wbr>Identity<wbr>Provider</a></span>
    </dt>
    <dd>{{% md %}}An array of Amazon Cognito Identity user pools and their client IDs.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Developer<wbr>Provider<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The &#34;domain&#34; by which Cognito will refer to your users. This name acts as a placeholder that allows your
backend and the Cognito service to communicate about the developer provider.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Identity<wbr>Pool<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Cognito Identity Pool name.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Openid<wbr>Connect<wbr>Provider<wbr>Arns<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}A list of OpendID Connect provider ARNs.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Saml<wbr>Provider<wbr>Arns<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}An array of Amazon Resource Names (ARNs) of the SAML provider for your identity.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Supported<wbr>Login<wbr>Providers<span class="property-indicator"></span>
        <span class="property-type">map[string]string</span>
    </dt>
    <dd>{{% md %}}Key-Value pairs mapping provider names to provider app IDs.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the Identity Pool.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">allow<wbr>Unauthenticated<wbr>Identities<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Whether the identity pool supports unauthenticated logins or not.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">cognito<wbr>Identity<wbr>Providers<span class="property-indicator"></span>
        <span class="property-type"><a href="#identitypoolcognitoidentityprovider">Identity<wbr>Pool<wbr>Cognito<wbr>Identity<wbr>Provider[]?</a></span>
    </dt>
    <dd>{{% md %}}An array of Amazon Cognito Identity user pools and their client IDs.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">developer<wbr>Provider<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The &#34;domain&#34; by which Cognito will refer to your users. This name acts as a placeholder that allows your
backend and the Cognito service to communicate about the developer provider.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">identity<wbr>Pool<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Cognito Identity Pool name.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">openid<wbr>Connect<wbr>Provider<wbr>Arns<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}A list of OpendID Connect provider ARNs.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">saml<wbr>Provider<wbr>Arns<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}An array of Amazon Resource Names (ARNs) of the SAML provider for your identity.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">supported<wbr>Login<wbr>Providers<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: string}?</span>
    </dt>
    <dd>{{% md %}}Key-Value pairs mapping provider names to provider app IDs.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the Identity Pool.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">allow_<wbr>unauthenticated_<wbr>identities<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Whether the identity pool supports unauthenticated logins or not.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">cognito_<wbr>identity_<wbr>providers<span class="property-indicator"></span>
        <span class="property-type"><a href="#identitypoolcognitoidentityprovider">List[Identity<wbr>Pool<wbr>Cognito<wbr>Identity<wbr>Provider]</a></span>
    </dt>
    <dd>{{% md %}}An array of Amazon Cognito Identity user pools and their client IDs.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">developer_<wbr>provider_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The &#34;domain&#34; by which Cognito will refer to your users. This name acts as a placeholder that allows your
backend and the Cognito service to communicate about the developer provider.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">identity_<wbr>pool_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The Cognito Identity Pool name.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">openid_<wbr>connect_<wbr>provider_<wbr>arns<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}A list of OpendID Connect provider ARNs.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">saml_<wbr>provider_<wbr>arns<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}An array of Amazon Resource Names (ARNs) of the SAML provider for your identity.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">supported_<wbr>login_<wbr>providers<span class="property-indicator"></span>
        <span class="property-type">Dict[str, str]</span>
    </dt>
    <dd>{{% md %}}Key-Value pairs mapping provider names to provider app IDs.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the Identity Pool.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}




## IdentityPool Output Properties

The following output properties are available:




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Allow<wbr>Unauthenticated<wbr>Identities<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Whether the identity pool supports unauthenticated logins or not.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of the identity pool.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Cognito<wbr>Identity<wbr>Providers<span class="property-indicator"></span>
        <span class="property-type"><a href="#identitypoolcognitoidentityprovider">List&lt;Identity<wbr>Pool<wbr>Cognito<wbr>Identity<wbr>Provider&gt;?</a></span>
    </dt>
    <dd>{{% md %}}An array of Amazon Cognito Identity user pools and their client IDs.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Developer<wbr>Provider<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The &#34;domain&#34; by which Cognito will refer to your users. This name acts as a placeholder that allows your
backend and the Cognito service to communicate about the developer provider.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Identity<wbr>Pool<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Cognito Identity Pool name.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Openid<wbr>Connect<wbr>Provider<wbr>Arns<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}A list of OpendID Connect provider ARNs.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Saml<wbr>Provider<wbr>Arns<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}An array of Amazon Resource Names (ARNs) of the SAML provider for your identity.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Supported<wbr>Login<wbr>Providers<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, string>?</span>
    </dt>
    <dd>{{% md %}}Key-Value pairs mapping provider names to provider app IDs.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the Identity Pool.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Allow<wbr>Unauthenticated<wbr>Identities<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Whether the identity pool supports unauthenticated logins or not.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of the identity pool.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Cognito<wbr>Identity<wbr>Providers<span class="property-indicator"></span>
        <span class="property-type"><a href="#identitypoolcognitoidentityprovider">[]Identity<wbr>Pool<wbr>Cognito<wbr>Identity<wbr>Provider</a></span>
    </dt>
    <dd>{{% md %}}An array of Amazon Cognito Identity user pools and their client IDs.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Developer<wbr>Provider<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The &#34;domain&#34; by which Cognito will refer to your users. This name acts as a placeholder that allows your
backend and the Cognito service to communicate about the developer provider.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Identity<wbr>Pool<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Cognito Identity Pool name.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Openid<wbr>Connect<wbr>Provider<wbr>Arns<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}A list of OpendID Connect provider ARNs.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Saml<wbr>Provider<wbr>Arns<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}An array of Amazon Resource Names (ARNs) of the SAML provider for your identity.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Supported<wbr>Login<wbr>Providers<span class="property-indicator"></span>
        <span class="property-type">map[string]string</span>
    </dt>
    <dd>{{% md %}}Key-Value pairs mapping provider names to provider app IDs.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the Identity Pool.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">allow<wbr>Unauthenticated<wbr>Identities<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Whether the identity pool supports unauthenticated logins or not.
{{% /md %}}</dd>

    <dt class="property-"
            title="">arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of the identity pool.
{{% /md %}}</dd>

    <dt class="property-"
            title="">cognito<wbr>Identity<wbr>Providers<span class="property-indicator"></span>
        <span class="property-type"><a href="#identitypoolcognitoidentityprovider">Identity<wbr>Pool<wbr>Cognito<wbr>Identity<wbr>Provider[]?</a></span>
    </dt>
    <dd>{{% md %}}An array of Amazon Cognito Identity user pools and their client IDs.
{{% /md %}}</dd>

    <dt class="property-"
            title="">developer<wbr>Provider<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The &#34;domain&#34; by which Cognito will refer to your users. This name acts as a placeholder that allows your
backend and the Cognito service to communicate about the developer provider.
{{% /md %}}</dd>

    <dt class="property-"
            title="">identity<wbr>Pool<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Cognito Identity Pool name.
{{% /md %}}</dd>

    <dt class="property-"
            title="">openid<wbr>Connect<wbr>Provider<wbr>Arns<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}A list of OpendID Connect provider ARNs.
{{% /md %}}</dd>

    <dt class="property-"
            title="">saml<wbr>Provider<wbr>Arns<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}An array of Amazon Resource Names (ARNs) of the SAML provider for your identity.
{{% /md %}}</dd>

    <dt class="property-"
            title="">supported<wbr>Login<wbr>Providers<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: string}?</span>
    </dt>
    <dd>{{% md %}}Key-Value pairs mapping provider names to provider app IDs.
{{% /md %}}</dd>

    <dt class="property-"
            title="">tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the Identity Pool.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">allow_<wbr>unauthenticated_<wbr>identities<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Whether the identity pool supports unauthenticated logins or not.
{{% /md %}}</dd>

    <dt class="property-"
            title="">arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ARN of the identity pool.
{{% /md %}}</dd>

    <dt class="property-"
            title="">cognito_<wbr>identity_<wbr>providers<span class="property-indicator"></span>
        <span class="property-type"><a href="#identitypoolcognitoidentityprovider">List[Identity<wbr>Pool<wbr>Cognito<wbr>Identity<wbr>Provider]</a></span>
    </dt>
    <dd>{{% md %}}An array of Amazon Cognito Identity user pools and their client IDs.
{{% /md %}}</dd>

    <dt class="property-"
            title="">developer_<wbr>provider_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The &#34;domain&#34; by which Cognito will refer to your users. This name acts as a placeholder that allows your
backend and the Cognito service to communicate about the developer provider.
{{% /md %}}</dd>

    <dt class="property-"
            title="">identity_<wbr>pool_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The Cognito Identity Pool name.
{{% /md %}}</dd>

    <dt class="property-"
            title="">openid_<wbr>connect_<wbr>provider_<wbr>arns<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}A list of OpendID Connect provider ARNs.
{{% /md %}}</dd>

    <dt class="property-"
            title="">saml_<wbr>provider_<wbr>arns<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}An array of Amazon Resource Names (ARNs) of the SAML provider for your identity.
{{% /md %}}</dd>

    <dt class="property-"
            title="">supported_<wbr>login_<wbr>providers<span class="property-indicator"></span>
        <span class="property-type">Dict[str, str]</span>
    </dt>
    <dd>{{% md %}}Key-Value pairs mapping provider names to provider app IDs.
{{% /md %}}</dd>

    <dt class="property-"
            title="">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the Identity Pool.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





## Look up an Existing IdentityPool Resource

{{< chooser language "javascript,typescript,python,go,csharp  " / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">pulumi.Input&lt;pulumi.ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/cognito/#IdentityPoolState">IdentityPoolState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/cognito/#IdentityPool">IdentityPool</a></span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>allow_unauthenticated_identities=None<span class="p">, </span>arn=None<span class="p">, </span>cognito_identity_providers=None<span class="p">, </span>developer_provider_name=None<span class="p">, </span>identity_pool_name=None<span class="p">, </span>openid_connect_provider_arns=None<span class="p">, </span>saml_provider_arns=None<span class="p">, </span>supported_login_providers=None<span class="p">, </span>tags=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetIdentityPool<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">pulumi.IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/cognito?tab=doc#IdentityPoolState">IdentityPoolState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/cognito?tab=doc#IdentityPool">IdentityPool</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Cognito.IdentityPool.html">IdentityPool</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Pulumi.Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Cognito.IdentityPoolState.html">IdentityPoolState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
{{% /choosable %}}

Get an existing IdentityPool resource's state with the given name, ID, and optional extra properties used to qualify the lookup.

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
            title="Optional">Allow<wbr>Unauthenticated<wbr>Identities<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Whether the identity pool supports unauthenticated logins or not.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ARN of the identity pool.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Cognito<wbr>Identity<wbr>Providers<span class="property-indicator"></span>
        <span class="property-type"><a href="#identitypoolcognitoidentityprovider">List&lt;Identity<wbr>Pool<wbr>Cognito<wbr>Identity<wbr>Provider<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}An array of Amazon Cognito Identity user pools and their client IDs.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Developer<wbr>Provider<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The &#34;domain&#34; by which Cognito will refer to your users. This name acts as a placeholder that allows your
backend and the Cognito service to communicate about the developer provider.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Identity<wbr>Pool<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The Cognito Identity Pool name.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Openid<wbr>Connect<wbr>Provider<wbr>Arns<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}A list of OpendID Connect provider ARNs.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Saml<wbr>Provider<wbr>Arns<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}An array of Amazon Resource Names (ARNs) of the SAML provider for your identity.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Supported<wbr>Login<wbr>Providers<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, string>?</span>
    </dt>
    <dd>{{% md %}}Key-Value pairs mapping provider names to provider app IDs.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the Identity Pool.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Allow<wbr>Unauthenticated<wbr>Identities<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Whether the identity pool supports unauthenticated logins or not.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The ARN of the identity pool.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Cognito<wbr>Identity<wbr>Providers<span class="property-indicator"></span>
        <span class="property-type"><a href="#identitypoolcognitoidentityprovider">[]Identity<wbr>Pool<wbr>Cognito<wbr>Identity<wbr>Provider</a></span>
    </dt>
    <dd>{{% md %}}An array of Amazon Cognito Identity user pools and their client IDs.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Developer<wbr>Provider<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The &#34;domain&#34; by which Cognito will refer to your users. This name acts as a placeholder that allows your
backend and the Cognito service to communicate about the developer provider.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Identity<wbr>Pool<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The Cognito Identity Pool name.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Openid<wbr>Connect<wbr>Provider<wbr>Arns<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}A list of OpendID Connect provider ARNs.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Saml<wbr>Provider<wbr>Arns<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}An array of Amazon Resource Names (ARNs) of the SAML provider for your identity.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Supported<wbr>Login<wbr>Providers<span class="property-indicator"></span>
        <span class="property-type">map[string]string</span>
    </dt>
    <dd>{{% md %}}Key-Value pairs mapping provider names to provider app IDs.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the Identity Pool.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">allow<wbr>Unauthenticated<wbr>Identities<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Whether the identity pool supports unauthenticated logins or not.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ARN of the identity pool.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">cognito<wbr>Identity<wbr>Providers<span class="property-indicator"></span>
        <span class="property-type"><a href="#identitypoolcognitoidentityprovider">Identity<wbr>Pool<wbr>Cognito<wbr>Identity<wbr>Provider[]?</a></span>
    </dt>
    <dd>{{% md %}}An array of Amazon Cognito Identity user pools and their client IDs.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">developer<wbr>Provider<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The &#34;domain&#34; by which Cognito will refer to your users. This name acts as a placeholder that allows your
backend and the Cognito service to communicate about the developer provider.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">identity<wbr>Pool<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The Cognito Identity Pool name.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">openid<wbr>Connect<wbr>Provider<wbr>Arns<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}A list of OpendID Connect provider ARNs.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">saml<wbr>Provider<wbr>Arns<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}An array of Amazon Resource Names (ARNs) of the SAML provider for your identity.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">supported<wbr>Login<wbr>Providers<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: string}?</span>
    </dt>
    <dd>{{% md %}}Key-Value pairs mapping provider names to provider app IDs.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the Identity Pool.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">allow_<wbr>unauthenticated_<wbr>identities<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Whether the identity pool supports unauthenticated logins or not.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ARN of the identity pool.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">cognito_<wbr>identity_<wbr>providers<span class="property-indicator"></span>
        <span class="property-type"><a href="#identitypoolcognitoidentityprovider">List[Identity<wbr>Pool<wbr>Cognito<wbr>Identity<wbr>Provider]</a></span>
    </dt>
    <dd>{{% md %}}An array of Amazon Cognito Identity user pools and their client IDs.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">developer_<wbr>provider_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The &#34;domain&#34; by which Cognito will refer to your users. This name acts as a placeholder that allows your
backend and the Cognito service to communicate about the developer provider.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">identity_<wbr>pool_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The Cognito Identity Pool name.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">openid_<wbr>connect_<wbr>provider_<wbr>arns<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}A list of OpendID Connect provider ARNs.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">saml_<wbr>provider_<wbr>arns<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}An array of Amazon Resource Names (ARNs) of the SAML provider for your identity.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">supported_<wbr>login_<wbr>providers<span class="property-indicator"></span>
        <span class="property-type">Dict[str, str]</span>
    </dt>
    <dd>{{% md %}}Key-Value pairs mapping provider names to provider app IDs.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the Identity Pool.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}







## Supporting Types

#### IdentityPoolCognitoIdentityProvider
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#IdentityPoolCognitoIdentityProvider">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#IdentityPoolCognitoIdentityProvider">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/cognito?tab=doc#IdentityPoolCognitoIdentityProviderArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/cognito?tab=doc#IdentityPoolCognitoIdentityProviderOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Cognito.IdentityPoolCognitoIdentityProviderArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Cognito.IdentityPoolCognitoIdentityProvider.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Client<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The client ID for the Amazon Cognito Identity User Pool.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Provider<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The provider name for an Amazon Cognito Identity User Pool.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Server<wbr>Side<wbr>Token<wbr>Check<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Whether server-side token validation is enabled for the identity provider’s token or not.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Client<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The client ID for the Amazon Cognito Identity User Pool.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Provider<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The provider name for an Amazon Cognito Identity User Pool.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Server<wbr>Side<wbr>Token<wbr>Check<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Whether server-side token validation is enabled for the identity provider’s token or not.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">client<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The client ID for the Amazon Cognito Identity User Pool.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">provider<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The provider name for an Amazon Cognito Identity User Pool.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">server<wbr>Side<wbr>Token<wbr>Check<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Whether server-side token validation is enabled for the identity provider’s token or not.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">client_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The client ID for the Amazon Cognito Identity User Pool.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">provider_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The provider name for an Amazon Cognito Identity User Pool.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">server<wbr>Side<wbr>Token<wbr>Check<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Whether server-side token validation is enabled for the identity provider’s token or not.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}








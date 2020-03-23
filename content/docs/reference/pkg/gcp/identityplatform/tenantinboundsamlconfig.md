
---
title: "TenantInboundSamlConfig"
block_external_search_index: true
---
<style>
table td p { margin-top: 0; margin-bottom: 0; }
</style>




## Create a TenantInboundSamlConfig Resource

{{< langchoose csharp nojavascript >}}

<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/identityplatform/#TenantInboundSamlConfig">TenantInboundSamlConfig</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/identityplatform/#TenantInboundSamlConfigArgs">TenantInboundSamlConfigArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">TenantInboundSamlConfig</span><span class="p">(resource_name, opts=None, </span>display_name=None<span class="p">, </span>enabled=None<span class="p">, </span>idp_config=None<span class="p">, </span>name=None<span class="p">, </span>project=None<span class="p">, </span>sp_config=None<span class="p">, </span>tenant=None<span class="p">, __props__=None);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewTenantInboundSamlConfig<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/identityplatform?tab=doc#TenantInboundSamlConfigArgs">TenantInboundSamlConfigArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/identityplatform?tab=doc#TenantInboundSamlConfig">TenantInboundSamlConfig</a></span>, error)</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Identityplatform.TenantInboundSamlConfig.html">TenantInboundSamlConfig</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Identityplatform.TenantInboundSamlConfigArgs.html">TenantInboundSamlConfigArgs</a></span> <span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>

Creates a TenantInboundSamlConfig resource with the given unique name, arguments, and options.

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
            <td class="align-top">Display<wbr>Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Human friendly display name.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Enabled</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
If this config allows users to sign in with the provider.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Idp<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#tenantinboundsamlconfigidpconfig">Tenant<wbr>Inbound<wbr>Saml<wbr>Config<wbr>Idp<wbr>Config<wbr>Args</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
SAML IdP configuration when the project acts as the relying party
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
The name of the InboundSamlConfig resource. Must start with &#39;saml.&#39; and can only have alphanumeric characters, hyphens,
underscores or periods. The part after &#39;saml.&#39; must also start with a lowercase letter, end with an alphanumeric
character, and have at least 2 characters.
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
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Sp<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#tenantinboundsamlconfigspconfig">Tenant<wbr>Inbound<wbr>Saml<wbr>Config<wbr>Sp<wbr>Config<wbr>Args</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
SAML SP (Service Provider) configuration when the project acts as the relying party to receive and accept an
authentication assertion issued by a SAML identity provider.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Tenant</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The name of the tenant where this inbound SAML config resource exists
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
            <td class="align-top">Display<wbr>Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Human friendly display name.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Enabled</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
If this config allows users to sign in with the provider.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Idp<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#tenantinboundsamlconfigidpconfig">Tenant<wbr>Inbound<wbr>Saml<wbr>Config<wbr>Idp<wbr>Config</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
SAML IdP configuration when the project acts as the relying party
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
The name of the InboundSamlConfig resource. Must start with &#39;saml.&#39; and can only have alphanumeric characters, hyphens,
underscores or periods. The part after &#39;saml.&#39; must also start with a lowercase letter, end with an alphanumeric
character, and have at least 2 characters.
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
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Sp<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#tenantinboundsamlconfigspconfig">Tenant<wbr>Inbound<wbr>Saml<wbr>Config<wbr>Sp<wbr>Config</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
SAML SP (Service Provider) configuration when the project acts as the relying party to receive and accept an
authentication assertion issued by a SAML identity provider.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Tenant</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The name of the tenant where this inbound SAML config resource exists
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
            <td class="align-top">display<wbr>Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Human friendly display name.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">enabled</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
If this config allows users to sign in with the provider.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">idp<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#tenantinboundsamlconfigidpconfig">Tenant<wbr>Inbound<wbr>Saml<wbr>Config<wbr>Idp<wbr>Config</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
SAML IdP configuration when the project acts as the relying party
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
The name of the InboundSamlConfig resource. Must start with &#39;saml.&#39; and can only have alphanumeric characters, hyphens,
underscores or periods. The part after &#39;saml.&#39; must also start with a lowercase letter, end with an alphanumeric
character, and have at least 2 characters.
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
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">sp<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#tenantinboundsamlconfigspconfig">Tenant<wbr>Inbound<wbr>Saml<wbr>Config<wbr>Sp<wbr>Config</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
SAML SP (Service Provider) configuration when the project acts as the relying party to receive and accept an
authentication assertion issued by a SAML identity provider.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">tenant</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The name of the tenant where this inbound SAML config resource exists
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
            <td class="align-top">display_<wbr>name</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Human friendly display name.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">enabled</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
If this config allows users to sign in with the provider.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">idp_<wbr>config</td>
            <td class="align-top">
                
                <code><a href="#tenantinboundsamlconfigidpconfig">Dict[Tenant<wbr>Inbound<wbr>Saml<wbr>Config<wbr>Idp<wbr>Config]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
SAML IdP configuration when the project acts as the relying party
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
The name of the InboundSamlConfig resource. Must start with &#39;saml.&#39; and can only have alphanumeric characters, hyphens,
underscores or periods. The part after &#39;saml.&#39; must also start with a lowercase letter, end with an alphanumeric
character, and have at least 2 characters.
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
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">sp_<wbr>config</td>
            <td class="align-top">
                
                <code><a href="#tenantinboundsamlconfigspconfig">Dict[Tenant<wbr>Inbound<wbr>Saml<wbr>Config<wbr>Sp<wbr>Config]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
SAML SP (Service Provider) configuration when the project acts as the relying party to receive and accept an
authentication assertion issued by a SAML identity provider.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">tenant</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The name of the tenant where this inbound SAML config resource exists
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}







## TenantInboundSamlConfig Output Properties

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
            <td class="align-top">Display<wbr>Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Human friendly display name.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Enabled</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} If this config allows users to sign in with the provider.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Idp<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#tenantinboundsamlconfigidpconfig">Tenant<wbr>Inbound<wbr>Saml<wbr>Config<wbr>Idp<wbr>Config</a></code>
            </td>
            <td class="align-top">{{% md %}} SAML IdP configuration when the project acts as the relying party
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The name of the InboundSamlConfig resource. Must start with &#39;saml.&#39; and can only have alphanumeric characters, hyphens,
underscores or periods. The part after &#39;saml.&#39; must also start with a lowercase letter, end with an alphanumeric
character, and have at least 2 characters.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Project</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}}  {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Sp<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#tenantinboundsamlconfigspconfig">Tenant<wbr>Inbound<wbr>Saml<wbr>Config<wbr>Sp<wbr>Config</a></code>
            </td>
            <td class="align-top">{{% md %}} SAML SP (Service Provider) configuration when the project acts as the relying party to receive and accept an
authentication assertion issued by a SAML identity provider.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Tenant</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The name of the tenant where this inbound SAML config resource exists
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
            <td class="align-top">Display<wbr>Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Human friendly display name.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Enabled</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} If this config allows users to sign in with the provider.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Idp<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#tenantinboundsamlconfigidpconfig">Tenant<wbr>Inbound<wbr>Saml<wbr>Config<wbr>Idp<wbr>Config</a></code>
            </td>
            <td class="align-top">{{% md %}} SAML IdP configuration when the project acts as the relying party
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The name of the InboundSamlConfig resource. Must start with &#39;saml.&#39; and can only have alphanumeric characters, hyphens,
underscores or periods. The part after &#39;saml.&#39; must also start with a lowercase letter, end with an alphanumeric
character, and have at least 2 characters.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Project</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}}  {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Sp<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#tenantinboundsamlconfigspconfig">Tenant<wbr>Inbound<wbr>Saml<wbr>Config<wbr>Sp<wbr>Config</a></code>
            </td>
            <td class="align-top">{{% md %}} SAML SP (Service Provider) configuration when the project acts as the relying party to receive and accept an
authentication assertion issued by a SAML identity provider.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Tenant</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The name of the tenant where this inbound SAML config resource exists
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
            <td class="align-top">display<wbr>Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Human friendly display name.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">enabled</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} If this config allows users to sign in with the provider.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">idp<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#tenantinboundsamlconfigidpconfig">Tenant<wbr>Inbound<wbr>Saml<wbr>Config<wbr>Idp<wbr>Config</a></code>
            </td>
            <td class="align-top">{{% md %}} SAML IdP configuration when the project acts as the relying party
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The name of the InboundSamlConfig resource. Must start with &#39;saml.&#39; and can only have alphanumeric characters, hyphens,
underscores or periods. The part after &#39;saml.&#39; must also start with a lowercase letter, end with an alphanumeric
character, and have at least 2 characters.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">project</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}}  {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">sp<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#tenantinboundsamlconfigspconfig">Tenant<wbr>Inbound<wbr>Saml<wbr>Config<wbr>Sp<wbr>Config</a></code>
            </td>
            <td class="align-top">{{% md %}} SAML SP (Service Provider) configuration when the project acts as the relying party to receive and accept an
authentication assertion issued by a SAML identity provider.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">tenant</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The name of the tenant where this inbound SAML config resource exists
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
            <td class="align-top">display_<wbr>name</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} Human friendly display name.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">enabled</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} If this config allows users to sign in with the provider.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">idp_<wbr>config</td>
            <td class="align-top">
                
                <code><a href="#tenantinboundsamlconfigidpconfig">Dict[Tenant<wbr>Inbound<wbr>Saml<wbr>Config<wbr>Idp<wbr>Config]</a></code>
            </td>
            <td class="align-top">{{% md %}} SAML IdP configuration when the project acts as the relying party
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">name</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The name of the InboundSamlConfig resource. Must start with &#39;saml.&#39; and can only have alphanumeric characters, hyphens,
underscores or periods. The part after &#39;saml.&#39; must also start with a lowercase letter, end with an alphanumeric
character, and have at least 2 characters.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">project</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}}  {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">sp_<wbr>config</td>
            <td class="align-top">
                
                <code><a href="#tenantinboundsamlconfigspconfig">Dict[Tenant<wbr>Inbound<wbr>Saml<wbr>Config<wbr>Sp<wbr>Config]</a></code>
            </td>
            <td class="align-top">{{% md %}} SAML SP (Service Provider) configuration when the project acts as the relying party to receive and accept an
authentication assertion issued by a SAML identity provider.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">tenant</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The name of the tenant where this inbound SAML config resource exists
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}








## Look up an Existing TenantInboundSamlConfig Resource

{{< langchoose csharp nojavascript >}}

<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">pulumi.Input&lt;pulumi.ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/identityplatform/#TenantInboundSamlConfigState">TenantInboundSamlConfigState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/identityplatform/#TenantInboundSamlConfig">TenantInboundSamlConfig</a></span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>display_name=None<span class="p">, </span>enabled=None<span class="p">, </span>idp_config=None<span class="p">, </span>name=None<span class="p">, </span>project=None<span class="p">, </span>sp_config=None<span class="p">, </span>tenant=None<span class="p">, __props__=None);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetTenantInboundSamlConfig<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">pulumi.IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/identityplatform?tab=doc#TenantInboundSamlConfigState">TenantInboundSamlConfigState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/identityplatform?tab=doc#TenantInboundSamlConfig">TenantInboundSamlConfig</a></span>, error)</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Identityplatform.TenantInboundSamlConfig.html">TenantInboundSamlConfig</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Pulumi.Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Identityplatform.TenantInboundSamlConfigState.html">TenantInboundSamlConfigState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>

Get an existing TenantInboundSamlConfig resource's state with the given name, ID, and optional extra properties used to qualify the lookup.

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
            <td class="align-top">Display<wbr>Name</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Human friendly display name.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Enabled</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
If this config allows users to sign in with the provider.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Idp<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#tenantinboundsamlconfigidpconfig">Tenant<wbr>Inbound<wbr>Saml<wbr>Config<wbr>Idp<wbr>Config<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
SAML IdP configuration when the project acts as the relying party
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
The name of the InboundSamlConfig resource. Must start with &#39;saml.&#39; and can only have alphanumeric characters, hyphens,
underscores or periods. The part after &#39;saml.&#39; must also start with a lowercase letter, end with an alphanumeric
character, and have at least 2 characters.
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
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Sp<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#tenantinboundsamlconfigspconfig">Tenant<wbr>Inbound<wbr>Saml<wbr>Config<wbr>Sp<wbr>Config<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
SAML SP (Service Provider) configuration when the project acts as the relying party to receive and accept an
authentication assertion issued by a SAML identity provider.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Tenant</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The name of the tenant where this inbound SAML config resource exists
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
            <td class="align-top">Display<wbr>Name</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Human friendly display name.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Enabled</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
If this config allows users to sign in with the provider.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Idp<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#tenantinboundsamlconfigidpconfig">*Tenant<wbr>Inbound<wbr>Saml<wbr>Config<wbr>Idp<wbr>Config</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
SAML IdP configuration when the project acts as the relying party
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
The name of the InboundSamlConfig resource. Must start with &#39;saml.&#39; and can only have alphanumeric characters, hyphens,
underscores or periods. The part after &#39;saml.&#39; must also start with a lowercase letter, end with an alphanumeric
character, and have at least 2 characters.
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
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Sp<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#tenantinboundsamlconfigspconfig">*Tenant<wbr>Inbound<wbr>Saml<wbr>Config<wbr>Sp<wbr>Config</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
SAML SP (Service Provider) configuration when the project acts as the relying party to receive and accept an
authentication assertion issued by a SAML identity provider.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Tenant</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The name of the tenant where this inbound SAML config resource exists
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
            <td class="align-top">display<wbr>Name</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Human friendly display name.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">enabled</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
If this config allows users to sign in with the provider.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">idp<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#tenantinboundsamlconfigidpconfig">Tenant<wbr>Inbound<wbr>Saml<wbr>Config<wbr>Idp<wbr>Config?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
SAML IdP configuration when the project acts as the relying party
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
The name of the InboundSamlConfig resource. Must start with &#39;saml.&#39; and can only have alphanumeric characters, hyphens,
underscores or periods. The part after &#39;saml.&#39; must also start with a lowercase letter, end with an alphanumeric
character, and have at least 2 characters.
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
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">sp<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#tenantinboundsamlconfigspconfig">Tenant<wbr>Inbound<wbr>Saml<wbr>Config<wbr>Sp<wbr>Config?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
SAML SP (Service Provider) configuration when the project acts as the relying party to receive and accept an
authentication assertion issued by a SAML identity provider.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">tenant</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The name of the tenant where this inbound SAML config resource exists
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
            <td class="align-top">display_<wbr>name</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Human friendly display name.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">enabled</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
If this config allows users to sign in with the provider.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">idp_<wbr>config</td>
            <td class="align-top">
                
                <code><a href="#tenantinboundsamlconfigidpconfig">Dict[Tenant<wbr>Inbound<wbr>Saml<wbr>Config<wbr>Idp<wbr>Config]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
SAML IdP configuration when the project acts as the relying party
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
The name of the InboundSamlConfig resource. Must start with &#39;saml.&#39; and can only have alphanumeric characters, hyphens,
underscores or periods. The part after &#39;saml.&#39; must also start with a lowercase letter, end with an alphanumeric
character, and have at least 2 characters.
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
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">sp_<wbr>config</td>
            <td class="align-top">
                
                <code><a href="#tenantinboundsamlconfigspconfig">Dict[Tenant<wbr>Inbound<wbr>Saml<wbr>Config<wbr>Sp<wbr>Config]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
SAML SP (Service Provider) configuration when the project acts as the relying party to receive and accept an
authentication assertion issued by a SAML identity provider.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">tenant</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The name of the tenant where this inbound SAML config resource exists
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}










## Supporting Types

#### TenantInboundSamlConfigIdpConfig
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#TenantInboundSamlConfigIdpConfig">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#TenantInboundSamlConfigIdpConfig">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/identityplatform?tab=doc#TenantInboundSamlConfigIdpConfigArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/identityplatform?tab=doc#TenantInboundSamlConfigIdpConfigOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Identityplatform.TenantInboundSamlConfigIdpConfigArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Identityplatform.TenantInboundSamlConfigIdpConfig.html">output</a> API doc for this type.
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
            <td class="align-top">Idp<wbr>Certificates</td>
            <td class="align-top">
                
                <code><a href="#tenantinboundsamlconfigidpconfigidpcertificate">List&lt;Tenant<wbr>Inbound<wbr>Saml<wbr>Config<wbr>Idp<wbr>Config<wbr>Idp<wbr>Certificate<wbr>Args&gt;</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Idp<wbr>Entity<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Sign<wbr>Request</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Sso<wbr>Url</td>
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
            <td class="align-top">Idp<wbr>Certificates</td>
            <td class="align-top">
                
                <code><a href="#tenantinboundsamlconfigidpconfigidpcertificate">[]Tenant<wbr>Inbound<wbr>Saml<wbr>Config<wbr>Idp<wbr>Config<wbr>Idp<wbr>Certificate</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Idp<wbr>Entity<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Sign<wbr>Request</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Sso<wbr>Url</td>
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
            <td class="align-top">idp<wbr>Certificates</td>
            <td class="align-top">
                
                <code><a href="#tenantinboundsamlconfigidpconfigidpcertificate">Tenant<wbr>Inbound<wbr>Saml<wbr>Config<wbr>Idp<wbr>Config<wbr>Idp<wbr>Certificate[]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">idp<wbr>Entity<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">sign<wbr>Request</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">sso<wbr>Url</td>
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
            <td class="align-top">idp<wbr>Certificates</td>
            <td class="align-top">
                
                <code><a href="#tenantinboundsamlconfigidpconfigidpcertificate">List[Tenant<wbr>Inbound<wbr>Saml<wbr>Config<wbr>Idp<wbr>Config<wbr>Idp<wbr>Certificate]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">idp<wbr>Entity<wbr>Id</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">sign<wbr>Request</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">sso<wbr>Url</td>
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





#### TenantInboundSamlConfigIdpConfigIdpCertificate
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#TenantInboundSamlConfigIdpConfigIdpCertificate">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#TenantInboundSamlConfigIdpConfigIdpCertificate">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/identityplatform?tab=doc#TenantInboundSamlConfigIdpConfigIdpCertificateArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/identityplatform?tab=doc#TenantInboundSamlConfigIdpConfigIdpCertificateOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Identityplatform.TenantInboundSamlConfigIdpConfigIdpCertificateArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Identityplatform.TenantInboundSamlConfigIdpConfigIdpCertificate.html">output</a> API doc for this type.
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
            <td class="align-top">X509Certificate</td>
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
            <td class="align-top">X509Certificate</td>
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
            <td class="align-top">x509Certificate</td>
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
            <td class="align-top">x509Certificate</td>
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





#### TenantInboundSamlConfigSpConfig
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#TenantInboundSamlConfigSpConfig">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#TenantInboundSamlConfigSpConfig">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/identityplatform?tab=doc#TenantInboundSamlConfigSpConfigArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/identityplatform?tab=doc#TenantInboundSamlConfigSpConfigOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Identityplatform.TenantInboundSamlConfigSpConfigArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Identityplatform.TenantInboundSamlConfigSpConfig.html">output</a> API doc for this type.
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
            <td class="align-top">Callback<wbr>Uri</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Sp<wbr>Certificates</td>
            <td class="align-top">
                
                <code><a href="#tenantinboundsamlconfigspconfigspcertificate">List&lt;Tenant<wbr>Inbound<wbr>Saml<wbr>Config<wbr>Sp<wbr>Config<wbr>Sp<wbr>Certificate<wbr>Args&gt;?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Sp<wbr>Entity<wbr>Id</td>
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
            <td class="align-top">Callback<wbr>Uri</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Sp<wbr>Certificates</td>
            <td class="align-top">
                
                <code><a href="#tenantinboundsamlconfigspconfigspcertificate">[]Tenant<wbr>Inbound<wbr>Saml<wbr>Config<wbr>Sp<wbr>Config<wbr>Sp<wbr>Certificate</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Sp<wbr>Entity<wbr>Id</td>
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
            <td class="align-top">callback<wbr>Uri</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">sp<wbr>Certificates</td>
            <td class="align-top">
                
                <code><a href="#tenantinboundsamlconfigspconfigspcertificate">Tenant<wbr>Inbound<wbr>Saml<wbr>Config<wbr>Sp<wbr>Config<wbr>Sp<wbr>Certificate[]?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">sp<wbr>Entity<wbr>Id</td>
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
            <td class="align-top">callback<wbr>Uri</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">sp<wbr>Certificates</td>
            <td class="align-top">
                
                <code><a href="#tenantinboundsamlconfigspconfigspcertificate">List[Tenant<wbr>Inbound<wbr>Saml<wbr>Config<wbr>Sp<wbr>Config<wbr>Sp<wbr>Certificate]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">sp<wbr>Entity<wbr>Id</td>
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





#### TenantInboundSamlConfigSpConfigSpCertificate
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#TenantInboundSamlConfigSpConfigSpCertificate">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#TenantInboundSamlConfigSpConfigSpCertificate">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/identityplatform?tab=doc#TenantInboundSamlConfigSpConfigSpCertificateArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/identityplatform?tab=doc#TenantInboundSamlConfigSpConfigSpCertificateOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Identityplatform.TenantInboundSamlConfigSpConfigSpCertificateArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Identityplatform.TenantInboundSamlConfigSpConfigSpCertificate.html">output</a> API doc for this type.
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
            <td class="align-top">X509Certificate</td>
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
            <td class="align-top">X509Certificate</td>
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
            <td class="align-top">x509Certificate</td>
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
            <td class="align-top">x509Certificate</td>
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








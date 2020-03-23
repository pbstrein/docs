
---
title: "GetIAMPolicy"
block_external_search_index: true
---
<style>
table td p { margin-top: 0; margin-bottom: 0; }
</style>

Generates an IAM policy document that may be referenced by and applied to
other Google Cloud Platform resources, such as the `gcp.organizations.Project` resource.

**Note:** Several restrictions apply when setting IAM policies through this API.
See the [setIamPolicy docs](https://cloud.google.com/resource-manager/reference/rest/v1/projects/setIamPolicy)
for a list of these restrictions.

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as gcp from "@pulumi/gcp";

const admin = gcp.organizations.getIAMPolicy({
    auditConfigs: [{
        auditLogConfigs: [
            {
                exemptedMembers: ["user:you@domain.com"],
                logType: "DATA_READ",
            },
            {
                logType: "DATA_WRITE",
            },
            {
                logType: "ADMIN_READ",
            },
        ],
        service: "cloudkms.googleapis.com",
    }],
    bindings: [
        {
            members: ["serviceAccount:your-custom-sa@your-project.iam.gserviceaccount.com"],
            role: "roles/compute.instanceAdmin",
        },
        {
            members: ["user:alice@gmail.com"],
            role: "roles/storage.objectViewer",
        },
    ],
});
```

This data source is used to define IAM policies to apply to other resources.
Currently, defining a policy through a datasource and referencing that policy
from another resource is the only way to apply an IAM policy to a resource.

> This content is derived from https://github.com/terraform-providers/terraform-provider-google/blob/master/website/docs/d/google_iam_policy.html.markdown.





## Using GetIAMPolicy

{{< langchoose csharp nojavascript >}}


<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">function </span>getIAMPolicy<span class="p">(</span><span class="nx">args</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/organizations/#GetIAMPolicyArgs">GetIAMPolicyArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#InvokeOptions">pulumi.InvokeOptions</a></span><span class="p">): Promise&lt;<span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/organizations/#GetIAMPolicyResult">GetIAMPolicyResult</a></span>></span></code></pre></div>


<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">function </span> get_iam_policy(</span>audit_configs=None<span class="p">, </span>bindings=None<span class="p">, </span>opts=None<span class="p">)</span></code></pre></div>


<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>LookupIAMPolicy<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">args</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/organizations?tab=doc#LookupIAMPolicyArgs">LookupIAMPolicyArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#InvokeOption">pulumi.InvokeOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/organizations?tab=doc#LookupIAMPolicyResult">LookupIAMPolicyResult</a></span>, error)</span></code></pre></div>


<div class="highlight">
<pre class="chroma">
<code class="language-csharp" data-lang="csharp"><span class="k">public static class </span><span class="nx">GetIAMPolicy </span><span class="p">{</span>
    <span class="k">public static </span>Task&lt;<span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Organizations.GetIAMPolicyResult.html">GetIAMPolicyResult</a></span>> <span class="p">InvokeAsync(</span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Organizations.GetIAMPolicyArgs.html">GetIAMPolicyArgs</a></span> <span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/InvokeOptions.html">InvokeOptions</a></span>? <span class="nx">opts = null<span class="p">)</span>
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
            <td class="align-top">Audit<wbr>Configs</td>
            <td class="align-top">
                
                <code><a href="#getiampolicyauditconfig">List&lt;Get<wbr>IAMPolicy<wbr>Audit<wbr>Config<wbr>Args&gt;?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A nested configuration block that defines logging additional configuration for your project.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Bindings</td>
            <td class="align-top">
                
                <code><a href="#getiampolicybinding">List&lt;Get<wbr>IAMPolicy<wbr>Binding<wbr>Args&gt;?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A nested configuration block (described below)
defining a binding to be included in the policy document. Multiple
`binding` arguments are supported.
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
            <td class="align-top">Audit<wbr>Configs</td>
            <td class="align-top">
                
                <code><a href="#getiampolicyauditconfig">[]Get<wbr>IAMPolicy<wbr>Audit<wbr>Config</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A nested configuration block that defines logging additional configuration for your project.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Bindings</td>
            <td class="align-top">
                
                <code><a href="#getiampolicybinding">[]Get<wbr>IAMPolicy<wbr>Binding</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A nested configuration block (described below)
defining a binding to be included in the policy document. Multiple
`binding` arguments are supported.
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
            <td class="align-top">audit<wbr>Configs</td>
            <td class="align-top">
                
                <code><a href="#getiampolicyauditconfig">Get<wbr>IAMPolicy<wbr>Audit<wbr>Config[]?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A nested configuration block that defines logging additional configuration for your project.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">bindings</td>
            <td class="align-top">
                
                <code><a href="#getiampolicybinding">Get<wbr>IAMPolicy<wbr>Binding[]?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A nested configuration block (described below)
defining a binding to be included in the policy document. Multiple
`binding` arguments are supported.
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
            <td class="align-top">audit_<wbr>configs</td>
            <td class="align-top">
                
                <code><a href="#getiampolicyauditconfig">List[Get<wbr>IAMPolicy<wbr>Audit<wbr>Config]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A nested configuration block that defines logging additional configuration for your project.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">bindings</td>
            <td class="align-top">
                
                <code><a href="#getiampolicybinding">List[Get<wbr>IAMPolicy<wbr>Binding]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A nested configuration block (described below)
defining a binding to be included in the policy document. Multiple
`binding` arguments are supported.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}








## GetIAMPolicy Result

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
            <td class="align-top">Audit<wbr>Configs</td>
            <td class="align-top">
                
                <code><a href="#getiampolicyauditconfig">List&lt;Get<wbr>IAMPolicy<wbr>Audit<wbr>Config&gt;?</a></code>
            </td>
            <td class="align-top">{{% md %}}  {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Bindings</td>
            <td class="align-top">
                
                <code><a href="#getiampolicybinding">List&lt;Get<wbr>IAMPolicy<wbr>Binding&gt;?</a></code>
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
            <td class="align-top">Policy<wbr>Data</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The above bindings serialized in a format suitable for
referencing from a resource that supports IAM.
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
            <td class="align-top">Audit<wbr>Configs</td>
            <td class="align-top">
                
                <code><a href="#getiampolicyauditconfig">[]Get<wbr>IAMPolicy<wbr>Audit<wbr>Config</a></code>
            </td>
            <td class="align-top">{{% md %}}  {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Bindings</td>
            <td class="align-top">
                
                <code><a href="#getiampolicybinding">[]Get<wbr>IAMPolicy<wbr>Binding</a></code>
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
            <td class="align-top">Policy<wbr>Data</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The above bindings serialized in a format suitable for
referencing from a resource that supports IAM.
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
            <td class="align-top">audit<wbr>Configs</td>
            <td class="align-top">
                
                <code><a href="#getiampolicyauditconfig">Get<wbr>IAMPolicy<wbr>Audit<wbr>Config[]?</a></code>
            </td>
            <td class="align-top">{{% md %}}  {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">bindings</td>
            <td class="align-top">
                
                <code><a href="#getiampolicybinding">Get<wbr>IAMPolicy<wbr>Binding[]?</a></code>
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
            <td class="align-top">policy<wbr>Data</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The above bindings serialized in a format suitable for
referencing from a resource that supports IAM.
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
            <td class="align-top">audit_<wbr>configs</td>
            <td class="align-top">
                
                <code><a href="#getiampolicyauditconfig">List[Get<wbr>IAMPolicy<wbr>Audit<wbr>Config]</a></code>
            </td>
            <td class="align-top">{{% md %}}  {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">bindings</td>
            <td class="align-top">
                
                <code><a href="#getiampolicybinding">List[Get<wbr>IAMPolicy<wbr>Binding]</a></code>
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
            <td class="align-top">policy_<wbr>data</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The above bindings serialized in a format suitable for
referencing from a resource that supports IAM.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}








## Supporting Types

#### GetIAMPolicyAuditConfig
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#GetIAMPolicyAuditConfig">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#GetIAMPolicyAuditConfig">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/organizations?tab=doc#GetIAMPolicyAuditConfigArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/organizations?tab=doc#GetIAMPolicyAuditConfig">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Organizations.GetIAMPolicyAuditConfigArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Organizations.GetIAMPolicyAuditConfig.html">output</a> API doc for this type.
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
            <td class="align-top">Audit<wbr>Log<wbr>Configs</td>
            <td class="align-top">
                
                <code><a href="#getiampolicyauditconfigauditlogconfig">List&lt;Get<wbr>IAMPolicy<wbr>Audit<wbr>Config<wbr>Audit<wbr>Log<wbr>Config<wbr>Args&gt;</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
A nested block that defines the operations you&#39;d like to log.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Service</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Defines a service that will be enabled for audit logging. For example, `storage.googleapis.com`, `cloudsql.googleapis.com`. `allServices` is a special value that covers all services.
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
            <td class="align-top">Audit<wbr>Log<wbr>Configs</td>
            <td class="align-top">
                
                <code><a href="#getiampolicyauditconfigauditlogconfig">[]Get<wbr>IAMPolicy<wbr>Audit<wbr>Config<wbr>Audit<wbr>Log<wbr>Config</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
A nested block that defines the operations you&#39;d like to log.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Service</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Defines a service that will be enabled for audit logging. For example, `storage.googleapis.com`, `cloudsql.googleapis.com`. `allServices` is a special value that covers all services.
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
            <td class="align-top">audit<wbr>Log<wbr>Configs</td>
            <td class="align-top">
                
                <code><a href="#getiampolicyauditconfigauditlogconfig">Get<wbr>IAMPolicy<wbr>Audit<wbr>Config<wbr>Audit<wbr>Log<wbr>Config[]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
A nested block that defines the operations you&#39;d like to log.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">service</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Defines a service that will be enabled for audit logging. For example, `storage.googleapis.com`, `cloudsql.googleapis.com`. `allServices` is a special value that covers all services.
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
            <td class="align-top">audit_<wbr>log_<wbr>configs</td>
            <td class="align-top">
                
                <code><a href="#getiampolicyauditconfigauditlogconfig">List[Get<wbr>IAMPolicy<wbr>Audit<wbr>Config<wbr>Audit<wbr>Log<wbr>Config]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
A nested block that defines the operations you&#39;d like to log.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">service</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Defines a service that will be enabled for audit logging. For example, `storage.googleapis.com`, `cloudsql.googleapis.com`. `allServices` is a special value that covers all services.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}





#### GetIAMPolicyAuditConfigAuditLogConfig
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#GetIAMPolicyAuditConfigAuditLogConfig">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#GetIAMPolicyAuditConfigAuditLogConfig">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/organizations?tab=doc#GetIAMPolicyAuditConfigAuditLogConfigArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/organizations?tab=doc#GetIAMPolicyAuditConfigAuditLogConfig">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Organizations.GetIAMPolicyAuditConfigAuditLogConfigArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Organizations.GetIAMPolicyAuditConfigAuditLogConfig.html">output</a> API doc for this type.
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
            <td class="align-top">Exempted<wbr>Members</td>
            <td class="align-top">
                
                <code>List<string>?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Specifies the identities that are exempt from these types of logging operations. Follows the same format of the `members` array for `binding`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Log<wbr>Type</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Defines the logging level. `DATA_READ`, `DATA_WRITE` and `ADMIN_READ` capture different types of events. See [the audit configuration documentation](https://cloud.google.com/resource-manager/reference/rest/Shared.Types/AuditConfig) for more details.
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
            <td class="align-top">Exempted<wbr>Members</td>
            <td class="align-top">
                
                <code>[]string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Specifies the identities that are exempt from these types of logging operations. Follows the same format of the `members` array for `binding`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Log<wbr>Type</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Defines the logging level. `DATA_READ`, `DATA_WRITE` and `ADMIN_READ` capture different types of events. See [the audit configuration documentation](https://cloud.google.com/resource-manager/reference/rest/Shared.Types/AuditConfig) for more details.
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
            <td class="align-top">exempted<wbr>Members</td>
            <td class="align-top">
                
                <code>string[]?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Specifies the identities that are exempt from these types of logging operations. Follows the same format of the `members` array for `binding`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">log<wbr>Type</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Defines the logging level. `DATA_READ`, `DATA_WRITE` and `ADMIN_READ` capture different types of events. See [the audit configuration documentation](https://cloud.google.com/resource-manager/reference/rest/Shared.Types/AuditConfig) for more details.
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
            <td class="align-top">exempted<wbr>Members</td>
            <td class="align-top">
                
                <code>List[str]</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Specifies the identities that are exempt from these types of logging operations. Follows the same format of the `members` array for `binding`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">log<wbr>Type</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Defines the logging level. `DATA_READ`, `DATA_WRITE` and `ADMIN_READ` capture different types of events. See [the audit configuration documentation](https://cloud.google.com/resource-manager/reference/rest/Shared.Types/AuditConfig) for more details.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}





#### GetIAMPolicyBinding
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#GetIAMPolicyBinding">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#GetIAMPolicyBinding">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/organizations?tab=doc#GetIAMPolicyBindingArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/organizations?tab=doc#GetIAMPolicyBinding">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Organizations.GetIAMPolicyBindingArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Organizations.GetIAMPolicyBinding.html">output</a> API doc for this type.
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
            <td class="align-top">Condition</td>
            <td class="align-top">
                
                <code><a href="#getiampolicybindingcondition">Get<wbr>IAMPolicy<wbr>Binding<wbr>Condition<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Members</td>
            <td class="align-top">
                
                <code>List<string></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
An array of identities that will be granted the privilege in the `role`. For more details on format and restrictions see https://cloud.google.com/billing/reference/rest/v1/Policy#Binding
Each entry can have one of the following values:
* **allUsers**: A special identifier that represents anyone who is on the internet; with or without a Google account. It **can&#39;t** be used with the `gcp.organizations.Project` resource.
* **allAuthenticatedUsers**: A special identifier that represents anyone who is authenticated with a Google account or a service account. It **can&#39;t** be used with the `gcp.organizations.Project` resource.
* **user:{emailid}**: An email address that represents a specific Google account. For example, alice@gmail.com.
* **serviceAccount:{emailid}**: An email address that represents a service account. For example, my-other-app@appspot.gserviceaccount.com.
* **group:{emailid}**: An email address that represents a Google group. For example, admins@example.com.
* **domain:{domain}**: A G Suite domain (primary, instead of alias) name that represents all the users of that domain. For example, google.com or example.com.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Role</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The role/permission that will be granted to the members.
See the [IAM Roles](https://cloud.google.com/compute/docs/access/iam) documentation for a complete list of roles.
Note that custom roles must be of the format `[projects|organizations]/{parent-name}/roles/{role-name}`.
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
            <td class="align-top">Condition</td>
            <td class="align-top">
                
                <code><a href="#getiampolicybindingcondition">*Get<wbr>IAMPolicy<wbr>Binding<wbr>Condition</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Members</td>
            <td class="align-top">
                
                <code>[]string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
An array of identities that will be granted the privilege in the `role`. For more details on format and restrictions see https://cloud.google.com/billing/reference/rest/v1/Policy#Binding
Each entry can have one of the following values:
* **allUsers**: A special identifier that represents anyone who is on the internet; with or without a Google account. It **can&#39;t** be used with the `gcp.organizations.Project` resource.
* **allAuthenticatedUsers**: A special identifier that represents anyone who is authenticated with a Google account or a service account. It **can&#39;t** be used with the `gcp.organizations.Project` resource.
* **user:{emailid}**: An email address that represents a specific Google account. For example, alice@gmail.com.
* **serviceAccount:{emailid}**: An email address that represents a service account. For example, my-other-app@appspot.gserviceaccount.com.
* **group:{emailid}**: An email address that represents a Google group. For example, admins@example.com.
* **domain:{domain}**: A G Suite domain (primary, instead of alias) name that represents all the users of that domain. For example, google.com or example.com.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Role</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The role/permission that will be granted to the members.
See the [IAM Roles](https://cloud.google.com/compute/docs/access/iam) documentation for a complete list of roles.
Note that custom roles must be of the format `[projects|organizations]/{parent-name}/roles/{role-name}`.
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
            <td class="align-top">condition</td>
            <td class="align-top">
                
                <code><a href="#getiampolicybindingcondition">Get<wbr>IAMPolicy<wbr>Binding<wbr>Condition?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">members</td>
            <td class="align-top">
                
                <code>string[]</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
An array of identities that will be granted the privilege in the `role`. For more details on format and restrictions see https://cloud.google.com/billing/reference/rest/v1/Policy#Binding
Each entry can have one of the following values:
* **allUsers**: A special identifier that represents anyone who is on the internet; with or without a Google account. It **can&#39;t** be used with the `gcp.organizations.Project` resource.
* **allAuthenticatedUsers**: A special identifier that represents anyone who is authenticated with a Google account or a service account. It **can&#39;t** be used with the `gcp.organizations.Project` resource.
* **user:{emailid}**: An email address that represents a specific Google account. For example, alice@gmail.com.
* **serviceAccount:{emailid}**: An email address that represents a service account. For example, my-other-app@appspot.gserviceaccount.com.
* **group:{emailid}**: An email address that represents a Google group. For example, admins@example.com.
* **domain:{domain}**: A G Suite domain (primary, instead of alias) name that represents all the users of that domain. For example, google.com or example.com.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">role</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The role/permission that will be granted to the members.
See the [IAM Roles](https://cloud.google.com/compute/docs/access/iam) documentation for a complete list of roles.
Note that custom roles must be of the format `[projects|organizations]/{parent-name}/roles/{role-name}`.
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
            <td class="align-top">condition</td>
            <td class="align-top">
                
                <code><a href="#getiampolicybindingcondition">Dict[Get<wbr>IAMPolicy<wbr>Binding<wbr>Condition]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">members</td>
            <td class="align-top">
                
                <code>List[str]</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
An array of identities that will be granted the privilege in the `role`. For more details on format and restrictions see https://cloud.google.com/billing/reference/rest/v1/Policy#Binding
Each entry can have one of the following values:
* **allUsers**: A special identifier that represents anyone who is on the internet; with or without a Google account. It **can&#39;t** be used with the `gcp.organizations.Project` resource.
* **allAuthenticatedUsers**: A special identifier that represents anyone who is authenticated with a Google account or a service account. It **can&#39;t** be used with the `gcp.organizations.Project` resource.
* **user:{emailid}**: An email address that represents a specific Google account. For example, alice@gmail.com.
* **serviceAccount:{emailid}**: An email address that represents a service account. For example, my-other-app@appspot.gserviceaccount.com.
* **group:{emailid}**: An email address that represents a Google group. For example, admins@example.com.
* **domain:{domain}**: A G Suite domain (primary, instead of alias) name that represents all the users of that domain. For example, google.com or example.com.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">role</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The role/permission that will be granted to the members.
See the [IAM Roles](https://cloud.google.com/compute/docs/access/iam) documentation for a complete list of roles.
Note that custom roles must be of the format `[projects|organizations]/{parent-name}/roles/{role-name}`.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}





#### GetIAMPolicyBindingCondition
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#GetIAMPolicyBindingCondition">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#GetIAMPolicyBindingCondition">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/organizations?tab=doc#GetIAMPolicyBindingConditionArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/organizations?tab=doc#GetIAMPolicyBindingCondition">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Organizations.GetIAMPolicyBindingConditionArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Organizations.GetIAMPolicyBindingCondition.html">output</a> API doc for this type.
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
            <td class="align-top">Description</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Expression</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Title</td>
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
            <td class="align-top">Description</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Expression</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Title</td>
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
            <td class="align-top">description</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">expression</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">title</td>
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
            <td class="align-top">description</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">expression</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">title</td>
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









---
title: "AppEngineVersionIamPolicy"
block_external_search_index: true
---
<style>
table td p { margin-top: 0; margin-bottom: 0; }
</style>

Three different resources help you manage your IAM policy for Identity-Aware Proxy AppEngineVersion. Each of these resources serves a different use case:

* `gcp.iap.AppEngineVersionIamPolicy`: Authoritative. Sets the IAM policy for the appengineversion and replaces any existing policy already attached.
* `gcp.iap.AppEngineVersionIamBinding`: Authoritative for a given role. Updates the IAM policy to grant a role to a list of members. Other roles within the IAM policy for the appengineversion are preserved.
* `gcp.iap.AppEngineVersionIamMember`: Non-authoritative. Updates the IAM policy to grant a role to a new member. Other members for the role for the appengineversion are preserved.

> **Note:** `gcp.iap.AppEngineVersionIamPolicy` **cannot** be used in conjunction with `gcp.iap.AppEngineVersionIamBinding` and `gcp.iap.AppEngineVersionIamMember` or they will fight over what your policy should be.

> **Note:** `gcp.iap.AppEngineVersionIamBinding` resources **can be** used in conjunction with `gcp.iap.AppEngineVersionIamMember` resources **only if** they do not grant privilege to the same role.



## google\_iap\_app\_engine\_version\_iam\_binding

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as gcp from "@pulumi/gcp";

const editor = new gcp.iap.AppEngineVersionIamBinding("editor", {
    appId: google_app_engine_standard_app_version_version.project,
    members: ["user:jane@example.com"],
    project: google_app_engine_standard_app_version_version.project,
    role: "roles/iap.httpsResourceAccessor",
    service: google_app_engine_standard_app_version_version.service,
    versionId: google_app_engine_standard_app_version_version.versionId,
});
```

With IAM Conditions:

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as gcp from "@pulumi/gcp";

const editor = new gcp.iap.AppEngineVersionIamBinding("editor", {
    appId: google_app_engine_standard_app_version_version.project,
    condition: {
        description: "Expiring at midnight of 2019-12-31",
        expression: "request.time < timestamp(\"2020-01-01T00:00:00Z\")",
        title: "expires_after_2019_12_31",
    },
    members: ["user:jane@example.com"],
    project: google_app_engine_standard_app_version_version.project,
    role: "roles/iap.httpsResourceAccessor",
    service: google_app_engine_standard_app_version_version.service,
    versionId: google_app_engine_standard_app_version_version.versionId,
});
```
## google\_iap\_app\_engine\_version\_iam\_member

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as gcp from "@pulumi/gcp";

const editor = new gcp.iap.AppEngineVersionIamMember("editor", {
    appId: google_app_engine_standard_app_version_version.project,
    member: "user:jane@example.com",
    project: google_app_engine_standard_app_version_version.project,
    role: "roles/iap.httpsResourceAccessor",
    service: google_app_engine_standard_app_version_version.service,
    versionId: google_app_engine_standard_app_version_version.versionId,
});
```

With IAM Conditions:

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as gcp from "@pulumi/gcp";

const editor = new gcp.iap.AppEngineVersionIamMember("editor", {
    appId: google_app_engine_standard_app_version_version.project,
    condition: {
        description: "Expiring at midnight of 2019-12-31",
        expression: "request.time < timestamp(\"2020-01-01T00:00:00Z\")",
        title: "expires_after_2019_12_31",
    },
    member: "user:jane@example.com",
    project: google_app_engine_standard_app_version_version.project,
    role: "roles/iap.httpsResourceAccessor",
    service: google_app_engine_standard_app_version_version.service,
    versionId: google_app_engine_standard_app_version_version.versionId,
});
```

> This content is derived from https://github.com/terraform-providers/terraform-provider-google/blob/master/website/docs/r/iap_app_engine_version_iam.html.markdown.



## Create a AppEngineVersionIamPolicy Resource

{{< langchoose csharp nojavascript >}}

<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/iap/#AppEngineVersionIamPolicy">AppEngineVersionIamPolicy</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/iap/#AppEngineVersionIamPolicyArgs">AppEngineVersionIamPolicyArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">AppEngineVersionIamPolicy</span><span class="p">(resource_name, opts=None, </span>app_id=None<span class="p">, </span>policy_data=None<span class="p">, </span>project=None<span class="p">, </span>service=None<span class="p">, </span>version_id=None<span class="p">, __props__=None);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewAppEngineVersionIamPolicy<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/iap?tab=doc#AppEngineVersionIamPolicyArgs">AppEngineVersionIamPolicyArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/iap?tab=doc#AppEngineVersionIamPolicy">AppEngineVersionIamPolicy</a></span>, error)</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Iap.AppEngineVersionIamPolicy.html">AppEngineVersionIamPolicy</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Iap.AppEngineVersionIamPolicyArgs.html">AppEngineVersionIamPolicyArgs</a></span> <span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>

Creates a AppEngineVersionIamPolicy resource with the given unique name, arguments, and options.

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
            <td class="align-top">App<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Id of the App Engine application. Used to find the parent resource to bind the IAM policy to
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Policy<wbr>Data</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The policy data generated by
a `gcp.organizations.getIAMPolicy` data source.
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
If it is not provided, the project will be parsed from the identifier of the parent resource. If no project is provided in the parent identifier and no project is specified, the provider project is used.
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
Service id of the App Engine application Used to find the parent resource to bind the IAM policy to
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Version<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Version id of the App Engine application Used to find the parent resource to bind the IAM policy to
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
            <td class="align-top">{{% md %}} 
 (Required)
Id of the App Engine application. Used to find the parent resource to bind the IAM policy to
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Policy<wbr>Data</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The policy data generated by
a `gcp.organizations.getIAMPolicy` data source.
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
If it is not provided, the project will be parsed from the identifier of the parent resource. If no project is provided in the parent identifier and no project is specified, the provider project is used.
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
Service id of the App Engine application Used to find the parent resource to bind the IAM policy to
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Version<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Version id of the App Engine application Used to find the parent resource to bind the IAM policy to
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
            <td class="align-top">{{% md %}} 
 (Required)
Id of the App Engine application. Used to find the parent resource to bind the IAM policy to
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">policy<wbr>Data</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The policy data generated by
a `gcp.organizations.getIAMPolicy` data source.
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
If it is not provided, the project will be parsed from the identifier of the parent resource. If no project is provided in the parent identifier and no project is specified, the provider project is used.
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
Service id of the App Engine application Used to find the parent resource to bind the IAM policy to
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">version<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Version id of the App Engine application Used to find the parent resource to bind the IAM policy to
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
 (Required)
Id of the App Engine application. Used to find the parent resource to bind the IAM policy to
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">policy_<wbr>data</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The policy data generated by
a `gcp.organizations.getIAMPolicy` data source.
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
If it is not provided, the project will be parsed from the identifier of the parent resource. If no project is provided in the parent identifier and no project is specified, the provider project is used.
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
Service id of the App Engine application Used to find the parent resource to bind the IAM policy to
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">version_<wbr>id</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Version id of the App Engine application Used to find the parent resource to bind the IAM policy to
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}







## AppEngineVersionIamPolicy Output Properties

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
            <td class="align-top">{{% md %}} Id of the App Engine application. Used to find the parent resource to bind the IAM policy to
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Etag</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} (Computed) The etag of the IAM policy.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Policy<wbr>Data</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The policy data generated by
a `gcp.organizations.getIAMPolicy` data source.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Project</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The ID of the project in which the resource belongs.
If it is not provided, the project will be parsed from the identifier of the parent resource. If no project is provided in the parent identifier and no project is specified, the provider project is used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Service</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Service id of the App Engine application Used to find the parent resource to bind the IAM policy to
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Version<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Version id of the App Engine application Used to find the parent resource to bind the IAM policy to
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
            <td class="align-top">{{% md %}} Id of the App Engine application. Used to find the parent resource to bind the IAM policy to
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Etag</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} (Computed) The etag of the IAM policy.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Policy<wbr>Data</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The policy data generated by
a `gcp.organizations.getIAMPolicy` data source.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Project</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The ID of the project in which the resource belongs.
If it is not provided, the project will be parsed from the identifier of the parent resource. If no project is provided in the parent identifier and no project is specified, the provider project is used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Service</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Service id of the App Engine application Used to find the parent resource to bind the IAM policy to
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Version<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Version id of the App Engine application Used to find the parent resource to bind the IAM policy to
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
            <td class="align-top">{{% md %}} Id of the App Engine application. Used to find the parent resource to bind the IAM policy to
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">etag</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} (Computed) The etag of the IAM policy.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">policy<wbr>Data</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The policy data generated by
a `gcp.organizations.getIAMPolicy` data source.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">project</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The ID of the project in which the resource belongs.
If it is not provided, the project will be parsed from the identifier of the parent resource. If no project is provided in the parent identifier and no project is specified, the provider project is used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">service</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Service id of the App Engine application Used to find the parent resource to bind the IAM policy to
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">version<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Version id of the App Engine application Used to find the parent resource to bind the IAM policy to
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
            <td class="align-top">{{% md %}} Id of the App Engine application. Used to find the parent resource to bind the IAM policy to
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">etag</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} (Computed) The etag of the IAM policy.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">policy_<wbr>data</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The policy data generated by
a `gcp.organizations.getIAMPolicy` data source.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">project</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The ID of the project in which the resource belongs.
If it is not provided, the project will be parsed from the identifier of the parent resource. If no project is provided in the parent identifier and no project is specified, the provider project is used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">service</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} Service id of the App Engine application Used to find the parent resource to bind the IAM policy to
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">version_<wbr>id</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} Version id of the App Engine application Used to find the parent resource to bind the IAM policy to
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}








## Look up an Existing AppEngineVersionIamPolicy Resource

{{< langchoose csharp nojavascript >}}

<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">pulumi.Input&lt;pulumi.ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/iap/#AppEngineVersionIamPolicyState">AppEngineVersionIamPolicyState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/iap/#AppEngineVersionIamPolicy">AppEngineVersionIamPolicy</a></span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>app_id=None<span class="p">, </span>etag=None<span class="p">, </span>policy_data=None<span class="p">, </span>project=None<span class="p">, </span>service=None<span class="p">, </span>version_id=None<span class="p">, __props__=None);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetAppEngineVersionIamPolicy<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">pulumi.IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/iap?tab=doc#AppEngineVersionIamPolicyState">AppEngineVersionIamPolicyState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/iap?tab=doc#AppEngineVersionIamPolicy">AppEngineVersionIamPolicy</a></span>, error)</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Iap.AppEngineVersionIamPolicy.html">AppEngineVersionIamPolicy</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Pulumi.Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Iap.AppEngineVersionIamPolicyState.html">AppEngineVersionIamPolicyState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>

Get an existing AppEngineVersionIamPolicy resource's state with the given name, ID, and optional extra properties used to qualify the lookup.

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
Id of the App Engine application. Used to find the parent resource to bind the IAM policy to
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Etag</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
(Computed) The etag of the IAM policy.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Policy<wbr>Data</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The policy data generated by
a `gcp.organizations.getIAMPolicy` data source.
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
If it is not provided, the project will be parsed from the identifier of the parent resource. If no project is provided in the parent identifier and no project is specified, the provider project is used.
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
Service id of the App Engine application Used to find the parent resource to bind the IAM policy to
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
Version id of the App Engine application Used to find the parent resource to bind the IAM policy to
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
Id of the App Engine application. Used to find the parent resource to bind the IAM policy to
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Etag</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
(Computed) The etag of the IAM policy.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Policy<wbr>Data</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The policy data generated by
a `gcp.organizations.getIAMPolicy` data source.
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
If it is not provided, the project will be parsed from the identifier of the parent resource. If no project is provided in the parent identifier and no project is specified, the provider project is used.
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
Service id of the App Engine application Used to find the parent resource to bind the IAM policy to
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
Version id of the App Engine application Used to find the parent resource to bind the IAM policy to
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
Id of the App Engine application. Used to find the parent resource to bind the IAM policy to
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">etag</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
(Computed) The etag of the IAM policy.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">policy<wbr>Data</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The policy data generated by
a `gcp.organizations.getIAMPolicy` data source.
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
If it is not provided, the project will be parsed from the identifier of the parent resource. If no project is provided in the parent identifier and no project is specified, the provider project is used.
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
Service id of the App Engine application Used to find the parent resource to bind the IAM policy to
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
Version id of the App Engine application Used to find the parent resource to bind the IAM policy to
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
Id of the App Engine application. Used to find the parent resource to bind the IAM policy to
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">etag</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
(Computed) The etag of the IAM policy.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">policy_<wbr>data</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The policy data generated by
a `gcp.organizations.getIAMPolicy` data source.
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
If it is not provided, the project will be parsed from the identifier of the parent resource. If no project is provided in the parent identifier and no project is specified, the provider project is used.
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
Service id of the App Engine application Used to find the parent resource to bind the IAM policy to
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
Version id of the App Engine application Used to find the parent resource to bind the IAM policy to
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}










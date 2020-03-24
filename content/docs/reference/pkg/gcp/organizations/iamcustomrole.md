
---
title: "IAMCustomRole"
block_external_search_index: true
---
<style>
table td p { margin-top: 0; margin-bottom: 0; }
</style>

Allows management of a customized Cloud IAM organization role. For more information see
[the official documentation](https://cloud.google.com/iam/docs/understanding-custom-roles)
and
[API](https://cloud.google.com/iam/reference/rest/v1/organizations.roles).

> **Warning:** Note that custom roles in GCP have the concept of a soft-delete. There are two issues that may arise
 from this and how roles are propagated. 1) creating a role may involve undeleting and then updating a role with the
 same name, possibly causing confusing behavior between undelete and update. 2) A deleted role is permanently deleted
 after 7 days, but it can take up to 30 more days (i.e. between 7 and 37 days after deletion) before the role name is
 made available again. This means a deleted role that has been deleted for more than 7 days cannot be changed at all
 by the provider, and new roles cannot share that name.
 
## Example Usage

This snippet creates a customized IAM organization role.

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as gcp from "@pulumi/gcp";

const my_custom_role = new gcp.organizations.IAMCustomRole("my-custom-role", {
    description: "A description",
    orgId: "123456789",
    permissions: [
        "iam.roles.list",
        "iam.roles.create",
        "iam.roles.delete",
    ],
    roleId: "myCustomRole",
    title: "My Custom Role",
});
```

> This content is derived from https://github.com/terraform-providers/terraform-provider-google/blob/master/website/docs/r/google_organization_iam_custom_role.html.markdown.



## Create a IAMCustomRole Resource

{{< langchoose csharp nojavascript >}}

<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/organizations/#IAMCustomRole">IAMCustomRole</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/organizations/#IAMCustomRoleArgs">IAMCustomRoleArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">IAMCustomRole</span><span class="p">(resource_name, opts=None, </span>description=None<span class="p">, </span>org_id=None<span class="p">, </span>permissions=None<span class="p">, </span>role_id=None<span class="p">, </span>stage=None<span class="p">, </span>title=None<span class="p">, __props__=None);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewIAMCustomRole<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/organizations?tab=doc#IAMCustomRoleArgs">IAMCustomRoleArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/organizations?tab=doc#IAMCustomRole">IAMCustomRole</a></span>, error)</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Organizations.IAMCustomRole.html">IAMCustomRole</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Organizations.IAMCustomRoleArgs.html">IAMCustomRoleArgs</a></span> <span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>

Creates a IAMCustomRole resource with the given unique name, arguments, and options.

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
            <td class="align-top">Description</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A human-readable description for the role.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Org<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The numeric ID of the organization in which you want to create a custom role.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Permissions</td>
            <td class="align-top">
                
                <code>List<string></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The names of the permissions this role grants when bound in an IAM policy. At least one permission must be specified.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Role<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The role id to use for this role.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Stage</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The current launch stage of the role.
Defaults to `GA`.
List of possible stages is [here](https://cloud.google.com/iam/reference/rest/v1/organizations.roles#Role.RoleLaunchStage).
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
A human-readable title for the role.
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
A human-readable description for the role.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Org<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The numeric ID of the organization in which you want to create a custom role.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Permissions</td>
            <td class="align-top">
                
                <code>[]string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The names of the permissions this role grants when bound in an IAM policy. At least one permission must be specified.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Role<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The role id to use for this role.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Stage</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The current launch stage of the role.
Defaults to `GA`.
List of possible stages is [here](https://cloud.google.com/iam/reference/rest/v1/organizations.roles#Role.RoleLaunchStage).
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
A human-readable title for the role.
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
A human-readable description for the role.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">org<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The numeric ID of the organization in which you want to create a custom role.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">permissions</td>
            <td class="align-top">
                
                <code>string[]</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The names of the permissions this role grants when bound in an IAM policy. At least one permission must be specified.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">role<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The role id to use for this role.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">stage</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The current launch stage of the role.
Defaults to `GA`.
List of possible stages is [here](https://cloud.google.com/iam/reference/rest/v1/organizations.roles#Role.RoleLaunchStage).
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
A human-readable title for the role.
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
A human-readable description for the role.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">org_<wbr>id</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The numeric ID of the organization in which you want to create a custom role.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">permissions</td>
            <td class="align-top">
                
                <code>List[str]</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The names of the permissions this role grants when bound in an IAM policy. At least one permission must be specified.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">role_<wbr>id</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The role id to use for this role.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">stage</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The current launch stage of the role.
Defaults to `GA`.
List of possible stages is [here](https://cloud.google.com/iam/reference/rest/v1/organizations.roles#Role.RoleLaunchStage).
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
A human-readable title for the role.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}







## IAMCustomRole Output Properties

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
            <td class="align-top">Deleted</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} (Optional) The current deleted state of the role.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Description</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} A human-readable description for the role.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Org<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The numeric ID of the organization in which you want to create a custom role.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Permissions</td>
            <td class="align-top">
                
                <code>List<string></code>
            </td>
            <td class="align-top">{{% md %}} The names of the permissions this role grants when bound in an IAM policy. At least one permission must be specified.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Role<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The role id to use for this role.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Stage</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} The current launch stage of the role.
Defaults to `GA`.
List of possible stages is [here](https://cloud.google.com/iam/reference/rest/v1/organizations.roles#Role.RoleLaunchStage).
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Title</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} A human-readable title for the role.
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
            <td class="align-top">Deleted</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} (Optional) The current deleted state of the role.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Description</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} A human-readable description for the role.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Org<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The numeric ID of the organization in which you want to create a custom role.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Permissions</td>
            <td class="align-top">
                
                <code>[]string</code>
            </td>
            <td class="align-top">{{% md %}} The names of the permissions this role grants when bound in an IAM policy. At least one permission must be specified.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Role<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The role id to use for this role.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Stage</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} The current launch stage of the role.
Defaults to `GA`.
List of possible stages is [here](https://cloud.google.com/iam/reference/rest/v1/organizations.roles#Role.RoleLaunchStage).
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Title</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} A human-readable title for the role.
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
            <td class="align-top">deleted</td>
            <td class="align-top">
                
                <code>boolean</code>
            </td>
            <td class="align-top">{{% md %}} (Optional) The current deleted state of the role.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">description</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} A human-readable description for the role.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">org<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The numeric ID of the organization in which you want to create a custom role.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">permissions</td>
            <td class="align-top">
                
                <code>string[]</code>
            </td>
            <td class="align-top">{{% md %}} The names of the permissions this role grants when bound in an IAM policy. At least one permission must be specified.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">role<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The role id to use for this role.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">stage</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} The current launch stage of the role.
Defaults to `GA`.
List of possible stages is [here](https://cloud.google.com/iam/reference/rest/v1/organizations.roles#Role.RoleLaunchStage).
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">title</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} A human-readable title for the role.
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
            <td class="align-top">deleted</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} (Optional) The current deleted state of the role.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">description</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} A human-readable description for the role.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">org_<wbr>id</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The numeric ID of the organization in which you want to create a custom role.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">permissions</td>
            <td class="align-top">
                
                <code>List[str]</code>
            </td>
            <td class="align-top">{{% md %}} The names of the permissions this role grants when bound in an IAM policy. At least one permission must be specified.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">role_<wbr>id</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The role id to use for this role.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">stage</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The current launch stage of the role.
Defaults to `GA`.
List of possible stages is [here](https://cloud.google.com/iam/reference/rest/v1/organizations.roles#Role.RoleLaunchStage).
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">title</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} A human-readable title for the role.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}








## Look up an Existing IAMCustomRole Resource

{{< langchoose csharp nojavascript >}}

<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">pulumi.Input&lt;pulumi.ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/organizations/#IAMCustomRoleState">IAMCustomRoleState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/organizations/#IAMCustomRole">IAMCustomRole</a></span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>deleted=None<span class="p">, </span>description=None<span class="p">, </span>org_id=None<span class="p">, </span>permissions=None<span class="p">, </span>role_id=None<span class="p">, </span>stage=None<span class="p">, </span>title=None<span class="p">, __props__=None);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetIAMCustomRole<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">pulumi.IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/organizations?tab=doc#IAMCustomRoleState">IAMCustomRoleState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/organizations?tab=doc#IAMCustomRole">IAMCustomRole</a></span>, error)</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Organizations.IAMCustomRole.html">IAMCustomRole</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Pulumi.Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Organizations.IAMCustomRoleState.html">IAMCustomRoleState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>

Get an existing IAMCustomRole resource's state with the given name, ID, and optional extra properties used to qualify the lookup.

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
            <td class="align-top">Deleted</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
(Optional) The current deleted state of the role.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Description</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A human-readable description for the role.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Org<wbr>Id</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The numeric ID of the organization in which you want to create a custom role.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Permissions</td>
            <td class="align-top">
                
                <code>List<string>?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The names of the permissions this role grants when bound in an IAM policy. At least one permission must be specified.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Role<wbr>Id</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The role id to use for this role.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Stage</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The current launch stage of the role.
Defaults to `GA`.
List of possible stages is [here](https://cloud.google.com/iam/reference/rest/v1/organizations.roles#Role.RoleLaunchStage).
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Title</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A human-readable title for the role.
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
            <td class="align-top">Deleted</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
(Optional) The current deleted state of the role.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Description</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A human-readable description for the role.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Org<wbr>Id</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The numeric ID of the organization in which you want to create a custom role.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Permissions</td>
            <td class="align-top">
                
                <code>[]string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The names of the permissions this role grants when bound in an IAM policy. At least one permission must be specified.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Role<wbr>Id</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The role id to use for this role.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Stage</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The current launch stage of the role.
Defaults to `GA`.
List of possible stages is [here](https://cloud.google.com/iam/reference/rest/v1/organizations.roles#Role.RoleLaunchStage).
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Title</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A human-readable title for the role.
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
            <td class="align-top">deleted</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
(Optional) The current deleted state of the role.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">description</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A human-readable description for the role.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">org<wbr>Id</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The numeric ID of the organization in which you want to create a custom role.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">permissions</td>
            <td class="align-top">
                
                <code>string[]?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The names of the permissions this role grants when bound in an IAM policy. At least one permission must be specified.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">role<wbr>Id</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The role id to use for this role.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">stage</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The current launch stage of the role.
Defaults to `GA`.
List of possible stages is [here](https://cloud.google.com/iam/reference/rest/v1/organizations.roles#Role.RoleLaunchStage).
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">title</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A human-readable title for the role.
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
            <td class="align-top">deleted</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
(Optional) The current deleted state of the role.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">description</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A human-readable description for the role.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">org_<wbr>id</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The numeric ID of the organization in which you want to create a custom role.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">permissions</td>
            <td class="align-top">
                
                <code>List[str]</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The names of the permissions this role grants when bound in an IAM policy. At least one permission must be specified.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">role_<wbr>id</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The role id to use for this role.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">stage</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The current launch stage of the role.
Defaults to `GA`.
List of possible stages is [here](https://cloud.google.com/iam/reference/rest/v1/organizations.roles#Role.RoleLaunchStage).
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">title</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A human-readable title for the role.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}










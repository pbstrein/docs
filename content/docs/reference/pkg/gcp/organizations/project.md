
---
title: "Project"
block_external_search_index: true
---
<style>
table td p { margin-top: 0; margin-bottom: 0; }
</style>

Allows creation and management of a Google Cloud Platform project.

Projects created with this resource must be associated with an Organization.
See the [Organization documentation](https://cloud.google.com/resource-manager/docs/quickstarts) for more details.

The service account used to run this provider when creating a `gcp.organizations.Project`
resource must have `roles/resourcemanager.projectCreator`. See the
[Access Control for Organizations Using IAM](https://cloud.google.com/resource-manager/docs/access-control-org)
doc for more information.

> This content is derived from https://github.com/terraform-providers/terraform-provider-google/blob/master/website/docs/r/google_project.html.markdown.



## Create a Project Resource

{{< langchoose csharp nojavascript >}}

<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/organizations/#Project">Project</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/organizations/#ProjectArgs">ProjectArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">Project</span><span class="p">(resource_name, opts=None, </span>auto_create_network=None<span class="p">, </span>billing_account=None<span class="p">, </span>folder_id=None<span class="p">, </span>labels=None<span class="p">, </span>name=None<span class="p">, </span>org_id=None<span class="p">, </span>project_id=None<span class="p">, </span>skip_delete=None<span class="p">, __props__=None);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewProject<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/organizations?tab=doc#ProjectArgs">ProjectArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/organizations?tab=doc#Project">Project</a></span>, error)</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Organizations.Project.html">Project</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Organizations.ProjectArgs.html">ProjectArgs</a></span> <span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>

Creates a Project resource with the given unique name, arguments, and options.

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
            <td class="align-top">Auto<wbr>Create<wbr>Network</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Create the &#39;default&#39; network automatically.  Default `true`.
If set to `false`, the default network will be deleted.  Note that, for quota purposes, you
will still need to have 1 network slot available to create the project successfully, even if
you set `auto_create_network` to `false`, since the network will exist momentarily.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Billing<wbr>Account</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The alphanumeric ID of the billing account this project
belongs to. The user or service account performing this operation with the provider
must have Billing Account Administrator privileges (`roles/billing.admin`) in
the organization. See [Google Cloud Billing API Access Control](https://cloud.google.com/billing/v1/how-tos/access-control)
for more details.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Folder<wbr>Id</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The numeric ID of the folder this project should be
created under. Only one of `org_id` or `folder_id` may be
specified. If the `folder_id` is specified, then the project is
created under the specified folder. Changing this forces the
project to be migrated to the newly specified folder.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Labels</td>
            <td class="align-top">
                
                <code>Dictionary<string, string>?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A set of key/value label pairs to assign to the project.
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
The display name of the project.
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
The numeric ID of the organization this project belongs to.
Changing this forces a new project to be created.  Only one of
`org_id` or `folder_id` may be specified. If the `org_id` is
specified then the project is created at the top level. Changing
this forces the project to be migrated to the newly specified
organization.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Project<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The project ID. Changing this forces a new project to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Skip<wbr>Delete</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
If true, the resource can be deleted
without deleting the Project via the Google API.
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
            <td class="align-top">Auto<wbr>Create<wbr>Network</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Create the &#39;default&#39; network automatically.  Default `true`.
If set to `false`, the default network will be deleted.  Note that, for quota purposes, you
will still need to have 1 network slot available to create the project successfully, even if
you set `auto_create_network` to `false`, since the network will exist momentarily.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Billing<wbr>Account</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The alphanumeric ID of the billing account this project
belongs to. The user or service account performing this operation with the provider
must have Billing Account Administrator privileges (`roles/billing.admin`) in
the organization. See [Google Cloud Billing API Access Control](https://cloud.google.com/billing/v1/how-tos/access-control)
for more details.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Folder<wbr>Id</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The numeric ID of the folder this project should be
created under. Only one of `org_id` or `folder_id` may be
specified. If the `folder_id` is specified, then the project is
created under the specified folder. Changing this forces the
project to be migrated to the newly specified folder.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Labels</td>
            <td class="align-top">
                
                <code>map[string]string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A set of key/value label pairs to assign to the project.
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
The display name of the project.
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
The numeric ID of the organization this project belongs to.
Changing this forces a new project to be created.  Only one of
`org_id` or `folder_id` may be specified. If the `org_id` is
specified then the project is created at the top level. Changing
this forces the project to be migrated to the newly specified
organization.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Project<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The project ID. Changing this forces a new project to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Skip<wbr>Delete</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
If true, the resource can be deleted
without deleting the Project via the Google API.
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
            <td class="align-top">auto<wbr>Create<wbr>Network</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Create the &#39;default&#39; network automatically.  Default `true`.
If set to `false`, the default network will be deleted.  Note that, for quota purposes, you
will still need to have 1 network slot available to create the project successfully, even if
you set `auto_create_network` to `false`, since the network will exist momentarily.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">billing<wbr>Account</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The alphanumeric ID of the billing account this project
belongs to. The user or service account performing this operation with the provider
must have Billing Account Administrator privileges (`roles/billing.admin`) in
the organization. See [Google Cloud Billing API Access Control](https://cloud.google.com/billing/v1/how-tos/access-control)
for more details.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">folder<wbr>Id</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The numeric ID of the folder this project should be
created under. Only one of `org_id` or `folder_id` may be
specified. If the `folder_id` is specified, then the project is
created under the specified folder. Changing this forces the
project to be migrated to the newly specified folder.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">labels</td>
            <td class="align-top">
                
                <code>{[key: string]: string}?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A set of key/value label pairs to assign to the project.
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
The display name of the project.
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
The numeric ID of the organization this project belongs to.
Changing this forces a new project to be created.  Only one of
`org_id` or `folder_id` may be specified. If the `org_id` is
specified then the project is created at the top level. Changing
this forces the project to be migrated to the newly specified
organization.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">project<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The project ID. Changing this forces a new project to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">skip<wbr>Delete</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
If true, the resource can be deleted
without deleting the Project via the Google API.
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
            <td class="align-top">auto_<wbr>create_<wbr>network</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Create the &#39;default&#39; network automatically.  Default `true`.
If set to `false`, the default network will be deleted.  Note that, for quota purposes, you
will still need to have 1 network slot available to create the project successfully, even if
you set `auto_create_network` to `false`, since the network will exist momentarily.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">billing_<wbr>account</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The alphanumeric ID of the billing account this project
belongs to. The user or service account performing this operation with the provider
must have Billing Account Administrator privileges (`roles/billing.admin`) in
the organization. See [Google Cloud Billing API Access Control](https://cloud.google.com/billing/v1/how-tos/access-control)
for more details.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">folder_<wbr>id</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The numeric ID of the folder this project should be
created under. Only one of `org_id` or `folder_id` may be
specified. If the `folder_id` is specified, then the project is
created under the specified folder. Changing this forces the
project to be migrated to the newly specified folder.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">labels</td>
            <td class="align-top">
                
                <code>Dict[str, str]</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A set of key/value label pairs to assign to the project.
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
The display name of the project.
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
The numeric ID of the organization this project belongs to.
Changing this forces a new project to be created.  Only one of
`org_id` or `folder_id` may be specified. If the `org_id` is
specified then the project is created at the top level. Changing
this forces the project to be migrated to the newly specified
organization.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">project_<wbr>id</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The project ID. Changing this forces a new project to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">skip_<wbr>delete</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
If true, the resource can be deleted
without deleting the Project via the Google API.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}







## Project Output Properties

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
            <td class="align-top">Auto<wbr>Create<wbr>Network</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} Create the &#39;default&#39; network automatically.  Default `true`.
If set to `false`, the default network will be deleted.  Note that, for quota purposes, you
will still need to have 1 network slot available to create the project successfully, even if
you set `auto_create_network` to `false`, since the network will exist momentarily.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Billing<wbr>Account</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} The alphanumeric ID of the billing account this project
belongs to. The user or service account performing this operation with the provider
must have Billing Account Administrator privileges (`roles/billing.admin`) in
the organization. See [Google Cloud Billing API Access Control](https://cloud.google.com/billing/v1/how-tos/access-control)
for more details.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Folder<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The numeric ID of the folder this project should be
created under. Only one of `org_id` or `folder_id` may be
specified. If the `folder_id` is specified, then the project is
created under the specified folder. Changing this forces the
project to be migrated to the newly specified folder.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Labels</td>
            <td class="align-top">
                
                <code>Dictionary<string, string>?</code>
            </td>
            <td class="align-top">{{% md %}} A set of key/value label pairs to assign to the project.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The display name of the project.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Number</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The numeric identifier of the project.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Org<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The numeric ID of the organization this project belongs to.
Changing this forces a new project to be created.  Only one of
`org_id` or `folder_id` may be specified. If the `org_id` is
specified then the project is created at the top level. Changing
this forces the project to be migrated to the newly specified
organization.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Project<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The project ID. Changing this forces a new project to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Skip<wbr>Delete</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} If true, the resource can be deleted
without deleting the Project via the Google API.
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
            <td class="align-top">Auto<wbr>Create<wbr>Network</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} Create the &#39;default&#39; network automatically.  Default `true`.
If set to `false`, the default network will be deleted.  Note that, for quota purposes, you
will still need to have 1 network slot available to create the project successfully, even if
you set `auto_create_network` to `false`, since the network will exist momentarily.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Billing<wbr>Account</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} The alphanumeric ID of the billing account this project
belongs to. The user or service account performing this operation with the provider
must have Billing Account Administrator privileges (`roles/billing.admin`) in
the organization. See [Google Cloud Billing API Access Control](https://cloud.google.com/billing/v1/how-tos/access-control)
for more details.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Folder<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The numeric ID of the folder this project should be
created under. Only one of `org_id` or `folder_id` may be
specified. If the `folder_id` is specified, then the project is
created under the specified folder. Changing this forces the
project to be migrated to the newly specified folder.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Labels</td>
            <td class="align-top">
                
                <code>map[string]string</code>
            </td>
            <td class="align-top">{{% md %}} A set of key/value label pairs to assign to the project.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The display name of the project.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Number</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The numeric identifier of the project.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Org<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The numeric ID of the organization this project belongs to.
Changing this forces a new project to be created.  Only one of
`org_id` or `folder_id` may be specified. If the `org_id` is
specified then the project is created at the top level. Changing
this forces the project to be migrated to the newly specified
organization.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Project<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The project ID. Changing this forces a new project to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Skip<wbr>Delete</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} If true, the resource can be deleted
without deleting the Project via the Google API.
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
            <td class="align-top">auto<wbr>Create<wbr>Network</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} Create the &#39;default&#39; network automatically.  Default `true`.
If set to `false`, the default network will be deleted.  Note that, for quota purposes, you
will still need to have 1 network slot available to create the project successfully, even if
you set `auto_create_network` to `false`, since the network will exist momentarily.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">billing<wbr>Account</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} The alphanumeric ID of the billing account this project
belongs to. The user or service account performing this operation with the provider
must have Billing Account Administrator privileges (`roles/billing.admin`) in
the organization. See [Google Cloud Billing API Access Control](https://cloud.google.com/billing/v1/how-tos/access-control)
for more details.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">folder<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The numeric ID of the folder this project should be
created under. Only one of `org_id` or `folder_id` may be
specified. If the `folder_id` is specified, then the project is
created under the specified folder. Changing this forces the
project to be migrated to the newly specified folder.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">labels</td>
            <td class="align-top">
                
                <code>{[key: string]: string}?</code>
            </td>
            <td class="align-top">{{% md %}} A set of key/value label pairs to assign to the project.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The display name of the project.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">number</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The numeric identifier of the project.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">org<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The numeric ID of the organization this project belongs to.
Changing this forces a new project to be created.  Only one of
`org_id` or `folder_id` may be specified. If the `org_id` is
specified then the project is created at the top level. Changing
this forces the project to be migrated to the newly specified
organization.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">project<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The project ID. Changing this forces a new project to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">skip<wbr>Delete</td>
            <td class="align-top">
                
                <code>boolean</code>
            </td>
            <td class="align-top">{{% md %}} If true, the resource can be deleted
without deleting the Project via the Google API.
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
            <td class="align-top">auto_<wbr>create_<wbr>network</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} Create the &#39;default&#39; network automatically.  Default `true`.
If set to `false`, the default network will be deleted.  Note that, for quota purposes, you
will still need to have 1 network slot available to create the project successfully, even if
you set `auto_create_network` to `false`, since the network will exist momentarily.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">billing_<wbr>account</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The alphanumeric ID of the billing account this project
belongs to. The user or service account performing this operation with the provider
must have Billing Account Administrator privileges (`roles/billing.admin`) in
the organization. See [Google Cloud Billing API Access Control](https://cloud.google.com/billing/v1/how-tos/access-control)
for more details.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">folder_<wbr>id</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The numeric ID of the folder this project should be
created under. Only one of `org_id` or `folder_id` may be
specified. If the `folder_id` is specified, then the project is
created under the specified folder. Changing this forces the
project to be migrated to the newly specified folder.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">labels</td>
            <td class="align-top">
                
                <code>Dict[str, str]</code>
            </td>
            <td class="align-top">{{% md %}} A set of key/value label pairs to assign to the project.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">name</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The display name of the project.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">number</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The numeric identifier of the project.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">org_<wbr>id</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The numeric ID of the organization this project belongs to.
Changing this forces a new project to be created.  Only one of
`org_id` or `folder_id` may be specified. If the `org_id` is
specified then the project is created at the top level. Changing
this forces the project to be migrated to the newly specified
organization.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">project_<wbr>id</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The project ID. Changing this forces a new project to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">skip_<wbr>delete</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} If true, the resource can be deleted
without deleting the Project via the Google API.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}








## Look up an Existing Project Resource

{{< langchoose csharp nojavascript >}}

<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">pulumi.Input&lt;pulumi.ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/organizations/#ProjectState">ProjectState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/organizations/#Project">Project</a></span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>auto_create_network=None<span class="p">, </span>billing_account=None<span class="p">, </span>folder_id=None<span class="p">, </span>labels=None<span class="p">, </span>name=None<span class="p">, </span>number=None<span class="p">, </span>org_id=None<span class="p">, </span>project_id=None<span class="p">, </span>skip_delete=None<span class="p">, __props__=None);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetProject<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">pulumi.IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/organizations?tab=doc#ProjectState">ProjectState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/organizations?tab=doc#Project">Project</a></span>, error)</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Organizations.Project.html">Project</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Pulumi.Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Organizations.ProjectState.html">ProjectState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>

Get an existing Project resource's state with the given name, ID, and optional extra properties used to qualify the lookup.

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
            <td class="align-top">Auto<wbr>Create<wbr>Network</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Create the &#39;default&#39; network automatically.  Default `true`.
If set to `false`, the default network will be deleted.  Note that, for quota purposes, you
will still need to have 1 network slot available to create the project successfully, even if
you set `auto_create_network` to `false`, since the network will exist momentarily.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Billing<wbr>Account</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The alphanumeric ID of the billing account this project
belongs to. The user or service account performing this operation with the provider
must have Billing Account Administrator privileges (`roles/billing.admin`) in
the organization. See [Google Cloud Billing API Access Control](https://cloud.google.com/billing/v1/how-tos/access-control)
for more details.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Folder<wbr>Id</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The numeric ID of the folder this project should be
created under. Only one of `org_id` or `folder_id` may be
specified. If the `folder_id` is specified, then the project is
created under the specified folder. Changing this forces the
project to be migrated to the newly specified folder.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Labels</td>
            <td class="align-top">
                
                <code>Dictionary<string, string>?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A set of key/value label pairs to assign to the project.
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
The display name of the project.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Number</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The numeric identifier of the project.
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
The numeric ID of the organization this project belongs to.
Changing this forces a new project to be created.  Only one of
`org_id` or `folder_id` may be specified. If the `org_id` is
specified then the project is created at the top level. Changing
this forces the project to be migrated to the newly specified
organization.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Project<wbr>Id</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The project ID. Changing this forces a new project to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Skip<wbr>Delete</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
If true, the resource can be deleted
without deleting the Project via the Google API.
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
            <td class="align-top">Auto<wbr>Create<wbr>Network</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Create the &#39;default&#39; network automatically.  Default `true`.
If set to `false`, the default network will be deleted.  Note that, for quota purposes, you
will still need to have 1 network slot available to create the project successfully, even if
you set `auto_create_network` to `false`, since the network will exist momentarily.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Billing<wbr>Account</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The alphanumeric ID of the billing account this project
belongs to. The user or service account performing this operation with the provider
must have Billing Account Administrator privileges (`roles/billing.admin`) in
the organization. See [Google Cloud Billing API Access Control](https://cloud.google.com/billing/v1/how-tos/access-control)
for more details.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Folder<wbr>Id</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The numeric ID of the folder this project should be
created under. Only one of `org_id` or `folder_id` may be
specified. If the `folder_id` is specified, then the project is
created under the specified folder. Changing this forces the
project to be migrated to the newly specified folder.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Labels</td>
            <td class="align-top">
                
                <code>map[string]string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A set of key/value label pairs to assign to the project.
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
The display name of the project.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Number</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The numeric identifier of the project.
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
The numeric ID of the organization this project belongs to.
Changing this forces a new project to be created.  Only one of
`org_id` or `folder_id` may be specified. If the `org_id` is
specified then the project is created at the top level. Changing
this forces the project to be migrated to the newly specified
organization.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Project<wbr>Id</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The project ID. Changing this forces a new project to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Skip<wbr>Delete</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
If true, the resource can be deleted
without deleting the Project via the Google API.
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
            <td class="align-top">auto<wbr>Create<wbr>Network</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Create the &#39;default&#39; network automatically.  Default `true`.
If set to `false`, the default network will be deleted.  Note that, for quota purposes, you
will still need to have 1 network slot available to create the project successfully, even if
you set `auto_create_network` to `false`, since the network will exist momentarily.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">billing<wbr>Account</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The alphanumeric ID of the billing account this project
belongs to. The user or service account performing this operation with the provider
must have Billing Account Administrator privileges (`roles/billing.admin`) in
the organization. See [Google Cloud Billing API Access Control](https://cloud.google.com/billing/v1/how-tos/access-control)
for more details.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">folder<wbr>Id</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The numeric ID of the folder this project should be
created under. Only one of `org_id` or `folder_id` may be
specified. If the `folder_id` is specified, then the project is
created under the specified folder. Changing this forces the
project to be migrated to the newly specified folder.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">labels</td>
            <td class="align-top">
                
                <code>{[key: string]: string}?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A set of key/value label pairs to assign to the project.
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
The display name of the project.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">number</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The numeric identifier of the project.
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
The numeric ID of the organization this project belongs to.
Changing this forces a new project to be created.  Only one of
`org_id` or `folder_id` may be specified. If the `org_id` is
specified then the project is created at the top level. Changing
this forces the project to be migrated to the newly specified
organization.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">project<wbr>Id</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The project ID. Changing this forces a new project to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">skip<wbr>Delete</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
If true, the resource can be deleted
without deleting the Project via the Google API.
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
            <td class="align-top">auto_<wbr>create_<wbr>network</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Create the &#39;default&#39; network automatically.  Default `true`.
If set to `false`, the default network will be deleted.  Note that, for quota purposes, you
will still need to have 1 network slot available to create the project successfully, even if
you set `auto_create_network` to `false`, since the network will exist momentarily.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">billing_<wbr>account</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The alphanumeric ID of the billing account this project
belongs to. The user or service account performing this operation with the provider
must have Billing Account Administrator privileges (`roles/billing.admin`) in
the organization. See [Google Cloud Billing API Access Control](https://cloud.google.com/billing/v1/how-tos/access-control)
for more details.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">folder_<wbr>id</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The numeric ID of the folder this project should be
created under. Only one of `org_id` or `folder_id` may be
specified. If the `folder_id` is specified, then the project is
created under the specified folder. Changing this forces the
project to be migrated to the newly specified folder.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">labels</td>
            <td class="align-top">
                
                <code>Dict[str, str]</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A set of key/value label pairs to assign to the project.
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
The display name of the project.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">number</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The numeric identifier of the project.
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
The numeric ID of the organization this project belongs to.
Changing this forces a new project to be created.  Only one of
`org_id` or `folder_id` may be specified. If the `org_id` is
specified then the project is created at the top level. Changing
this forces the project to be migrated to the newly specified
organization.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">project_<wbr>id</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The project ID. Changing this forces a new project to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">skip_<wbr>delete</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
If true, the resource can be deleted
without deleting the Project via the Google API.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}










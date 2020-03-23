
---
title: "ObjectAccessControl"
block_external_search_index: true
---
<style>
table td p { margin-top: 0; margin-bottom: 0; }
</style>

The ObjectAccessControls resources represent the Access Control Lists
(ACLs) for objects within Google Cloud Storage. ACLs let you specify
who has access to your data and to what extent.

There are two roles that can be assigned to an entity:

READERs can get an object, though the acl property will not be revealed.
OWNERs are READERs, and they can get the acl property, update an object,
and call all objectAccessControls methods on the object. The owner of an
object is always an OWNER.
For more information, see Access Control, with the caveat that this API
uses READER and OWNER instead of READ and FULL_CONTROL.


To get more information about ObjectAccessControl, see:

* [API documentation](https://cloud.google.com/storage/docs/json_api/v1/objectAccessControls)
* How-to Guides
    * [Official Documentation](https://cloud.google.com/storage/docs/access-control/create-manage-lists)

> This content is derived from https://github.com/terraform-providers/terraform-provider-google/blob/master/website/docs/r/storage_object_access_control.html.markdown.



## Create a ObjectAccessControl Resource

{{< langchoose csharp nojavascript >}}

<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/storage/#ObjectAccessControl">ObjectAccessControl</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/storage/#ObjectAccessControlArgs">ObjectAccessControlArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">ObjectAccessControl</span><span class="p">(resource_name, opts=None, </span>bucket=None<span class="p">, </span>entity=None<span class="p">, </span>object=None<span class="p">, </span>role=None<span class="p">, __props__=None);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewObjectAccessControl<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/storage?tab=doc#ObjectAccessControlArgs">ObjectAccessControlArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/storage?tab=doc#ObjectAccessControl">ObjectAccessControl</a></span>, error)</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Storage.ObjectAccessControl.html">ObjectAccessControl</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Storage.ObjectAccessControlArgs.html">ObjectAccessControlArgs</a></span> <span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>

Creates a ObjectAccessControl resource with the given unique name, arguments, and options.

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
            <td class="align-top">Bucket</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The name of the bucket.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Entity</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The entity holding the permission, in one of the following forms: * user-{{userId}} * user-{{email}} (such as
&#34;user-liz@example.com&#34;) * group-{{groupId}} * group-{{email}} (such as &#34;group-example@googlegroups.com&#34;) *
domain-{{domain}} (such as &#34;domain-example.com&#34;) * project-team-{{projectId}} * allUsers * allAuthenticatedUsers
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Object</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The name of the object to apply the access control to.
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
The access permission for the entity.
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
            <td class="align-top">Bucket</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The name of the bucket.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Entity</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The entity holding the permission, in one of the following forms: * user-{{userId}} * user-{{email}} (such as
&#34;user-liz@example.com&#34;) * group-{{groupId}} * group-{{email}} (such as &#34;group-example@googlegroups.com&#34;) *
domain-{{domain}} (such as &#34;domain-example.com&#34;) * project-team-{{projectId}} * allUsers * allAuthenticatedUsers
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Object</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The name of the object to apply the access control to.
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
The access permission for the entity.
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
            <td class="align-top">bucket</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The name of the bucket.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">entity</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The entity holding the permission, in one of the following forms: * user-{{userId}} * user-{{email}} (such as
&#34;user-liz@example.com&#34;) * group-{{groupId}} * group-{{email}} (such as &#34;group-example@googlegroups.com&#34;) *
domain-{{domain}} (such as &#34;domain-example.com&#34;) * project-team-{{projectId}} * allUsers * allAuthenticatedUsers
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">object</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The name of the object to apply the access control to.
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
The access permission for the entity.
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
            <td class="align-top">bucket</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The name of the bucket.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">entity</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The entity holding the permission, in one of the following forms: * user-{{userId}} * user-{{email}} (such as
&#34;user-liz@example.com&#34;) * group-{{groupId}} * group-{{email}} (such as &#34;group-example@googlegroups.com&#34;) *
domain-{{domain}} (such as &#34;domain-example.com&#34;) * project-team-{{projectId}} * allUsers * allAuthenticatedUsers
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">object</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The name of the object to apply the access control to.
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
The access permission for the entity.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}







## ObjectAccessControl Output Properties

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
            <td class="align-top">Bucket</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The name of the bucket.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Domain</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The domain associated with the entity.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Email</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The email address associated with the entity.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Entity</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The entity holding the permission, in one of the following forms: * user-{{userId}} * user-{{email}} (such as
&#34;user-liz@example.com&#34;) * group-{{groupId}} * group-{{email}} (such as &#34;group-example@googlegroups.com&#34;) *
domain-{{domain}} (such as &#34;domain-example.com&#34;) * project-team-{{projectId}} * allUsers * allAuthenticatedUsers
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Entity<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The ID for the entity
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Generation</td>
            <td class="align-top">
                
                <code>int</code>
            </td>
            <td class="align-top">{{% md %}} The content generation of the object, if applied to an object.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Object</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The name of the object to apply the access control to.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Project<wbr>Team</td>
            <td class="align-top">
                
                <code><a href="#objectaccesscontrolprojectteam">Object<wbr>Access<wbr>Control<wbr>Project<wbr>Team</a></code>
            </td>
            <td class="align-top">{{% md %}} The project team associated with the entity
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Role</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The access permission for the entity.
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
            <td class="align-top">Bucket</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The name of the bucket.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Domain</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The domain associated with the entity.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Email</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The email address associated with the entity.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Entity</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The entity holding the permission, in one of the following forms: * user-{{userId}} * user-{{email}} (such as
&#34;user-liz@example.com&#34;) * group-{{groupId}} * group-{{email}} (such as &#34;group-example@googlegroups.com&#34;) *
domain-{{domain}} (such as &#34;domain-example.com&#34;) * project-team-{{projectId}} * allUsers * allAuthenticatedUsers
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Entity<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The ID for the entity
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Generation</td>
            <td class="align-top">
                
                <code>int</code>
            </td>
            <td class="align-top">{{% md %}} The content generation of the object, if applied to an object.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Object</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The name of the object to apply the access control to.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Project<wbr>Team</td>
            <td class="align-top">
                
                <code><a href="#objectaccesscontrolprojectteam">Object<wbr>Access<wbr>Control<wbr>Project<wbr>Team</a></code>
            </td>
            <td class="align-top">{{% md %}} The project team associated with the entity
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Role</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The access permission for the entity.
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
            <td class="align-top">bucket</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The name of the bucket.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">domain</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The domain associated with the entity.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">email</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The email address associated with the entity.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">entity</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The entity holding the permission, in one of the following forms: * user-{{userId}} * user-{{email}} (such as
&#34;user-liz@example.com&#34;) * group-{{groupId}} * group-{{email}} (such as &#34;group-example@googlegroups.com&#34;) *
domain-{{domain}} (such as &#34;domain-example.com&#34;) * project-team-{{projectId}} * allUsers * allAuthenticatedUsers
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">entity<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The ID for the entity
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">generation</td>
            <td class="align-top">
                
                <code>number</code>
            </td>
            <td class="align-top">{{% md %}} The content generation of the object, if applied to an object.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">object</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The name of the object to apply the access control to.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">project<wbr>Team</td>
            <td class="align-top">
                
                <code><a href="#objectaccesscontrolprojectteam">Object<wbr>Access<wbr>Control<wbr>Project<wbr>Team</a></code>
            </td>
            <td class="align-top">{{% md %}} The project team associated with the entity
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">role</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The access permission for the entity.
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
            <td class="align-top">bucket</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The name of the bucket.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">domain</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The domain associated with the entity.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">email</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The email address associated with the entity.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">entity</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The entity holding the permission, in one of the following forms: * user-{{userId}} * user-{{email}} (such as
&#34;user-liz@example.com&#34;) * group-{{groupId}} * group-{{email}} (such as &#34;group-example@googlegroups.com&#34;) *
domain-{{domain}} (such as &#34;domain-example.com&#34;) * project-team-{{projectId}} * allUsers * allAuthenticatedUsers
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">entity_<wbr>id</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The ID for the entity
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">generation</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} The content generation of the object, if applied to an object.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">object</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The name of the object to apply the access control to.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">project_<wbr>team</td>
            <td class="align-top">
                
                <code><a href="#objectaccesscontrolprojectteam">Dict[Object<wbr>Access<wbr>Control<wbr>Project<wbr>Team]</a></code>
            </td>
            <td class="align-top">{{% md %}} The project team associated with the entity
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">role</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The access permission for the entity.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}








## Look up an Existing ObjectAccessControl Resource

{{< langchoose csharp nojavascript >}}

<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">pulumi.Input&lt;pulumi.ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/storage/#ObjectAccessControlState">ObjectAccessControlState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/storage/#ObjectAccessControl">ObjectAccessControl</a></span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>bucket=None<span class="p">, </span>domain=None<span class="p">, </span>email=None<span class="p">, </span>entity=None<span class="p">, </span>entity_id=None<span class="p">, </span>generation=None<span class="p">, </span>object=None<span class="p">, </span>project_team=None<span class="p">, </span>role=None<span class="p">, __props__=None);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetObjectAccessControl<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">pulumi.IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/storage?tab=doc#ObjectAccessControlState">ObjectAccessControlState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/storage?tab=doc#ObjectAccessControl">ObjectAccessControl</a></span>, error)</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Storage.ObjectAccessControl.html">ObjectAccessControl</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Pulumi.Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Storage.ObjectAccessControlState.html">ObjectAccessControlState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>

Get an existing ObjectAccessControl resource's state with the given name, ID, and optional extra properties used to qualify the lookup.

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
            <td class="align-top">Bucket</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The name of the bucket.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Domain</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The domain associated with the entity.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Email</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The email address associated with the entity.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Entity</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The entity holding the permission, in one of the following forms: * user-{{userId}} * user-{{email}} (such as
&#34;user-liz@example.com&#34;) * group-{{groupId}} * group-{{email}} (such as &#34;group-example@googlegroups.com&#34;) *
domain-{{domain}} (such as &#34;domain-example.com&#34;) * project-team-{{projectId}} * allUsers * allAuthenticatedUsers
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Entity<wbr>Id</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID for the entity
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Generation</td>
            <td class="align-top">
                
                <code>int?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The content generation of the object, if applied to an object.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Object</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The name of the object to apply the access control to.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Project<wbr>Team</td>
            <td class="align-top">
                
                <code><a href="#objectaccesscontrolprojectteam">Object<wbr>Access<wbr>Control<wbr>Project<wbr>Team<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The project team associated with the entity
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Role</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The access permission for the entity.
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
            <td class="align-top">Bucket</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The name of the bucket.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Domain</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The domain associated with the entity.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Email</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The email address associated with the entity.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Entity</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The entity holding the permission, in one of the following forms: * user-{{userId}} * user-{{email}} (such as
&#34;user-liz@example.com&#34;) * group-{{groupId}} * group-{{email}} (such as &#34;group-example@googlegroups.com&#34;) *
domain-{{domain}} (such as &#34;domain-example.com&#34;) * project-team-{{projectId}} * allUsers * allAuthenticatedUsers
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Entity<wbr>Id</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID for the entity
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Generation</td>
            <td class="align-top">
                
                <code>*int</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The content generation of the object, if applied to an object.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Object</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The name of the object to apply the access control to.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Project<wbr>Team</td>
            <td class="align-top">
                
                <code><a href="#objectaccesscontrolprojectteam">*Object<wbr>Access<wbr>Control<wbr>Project<wbr>Team</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The project team associated with the entity
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Role</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The access permission for the entity.
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
            <td class="align-top">bucket</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The name of the bucket.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">domain</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The domain associated with the entity.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">email</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The email address associated with the entity.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">entity</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The entity holding the permission, in one of the following forms: * user-{{userId}} * user-{{email}} (such as
&#34;user-liz@example.com&#34;) * group-{{groupId}} * group-{{email}} (such as &#34;group-example@googlegroups.com&#34;) *
domain-{{domain}} (such as &#34;domain-example.com&#34;) * project-team-{{projectId}} * allUsers * allAuthenticatedUsers
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">entity<wbr>Id</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID for the entity
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">generation</td>
            <td class="align-top">
                
                <code>number?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The content generation of the object, if applied to an object.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">object</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The name of the object to apply the access control to.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">project<wbr>Team</td>
            <td class="align-top">
                
                <code><a href="#objectaccesscontrolprojectteam">Object<wbr>Access<wbr>Control<wbr>Project<wbr>Team?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The project team associated with the entity
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">role</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The access permission for the entity.
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
            <td class="align-top">bucket</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The name of the bucket.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">domain</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The domain associated with the entity.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">email</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The email address associated with the entity.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">entity</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The entity holding the permission, in one of the following forms: * user-{{userId}} * user-{{email}} (such as
&#34;user-liz@example.com&#34;) * group-{{groupId}} * group-{{email}} (such as &#34;group-example@googlegroups.com&#34;) *
domain-{{domain}} (such as &#34;domain-example.com&#34;) * project-team-{{projectId}} * allUsers * allAuthenticatedUsers
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">entity_<wbr>id</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The ID for the entity
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">generation</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The content generation of the object, if applied to an object.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">object</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The name of the object to apply the access control to.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">project_<wbr>team</td>
            <td class="align-top">
                
                <code><a href="#objectaccesscontrolprojectteam">Dict[Object<wbr>Access<wbr>Control<wbr>Project<wbr>Team]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The project team associated with the entity
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">role</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The access permission for the entity.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}










## Supporting Types

#### ObjectAccessControlProjectTeam
{{% lang nodejs %}}
> See the   <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#ObjectAccessControlProjectTeam">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the   <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/storage?tab=doc#ObjectAccessControlProjectTeamOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the   <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Storage.ObjectAccessControlProjectTeam.html">output</a> API doc for this type.
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
            <td class="align-top">Project<wbr>Number</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Team</td>
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
            <td class="align-top">Project<wbr>Number</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Team</td>
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
            <td class="align-top">project<wbr>Number</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">team</td>
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
            <td class="align-top">project<wbr>Number</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">team</td>
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








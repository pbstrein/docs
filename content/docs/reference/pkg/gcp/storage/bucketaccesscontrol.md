
---
title: "BucketAccessControl"
block_external_search_index: true
---
<style>
table td p { margin-top: 0; margin-bottom: 0; }
</style>

Bucket ACLs can be managed authoritatively using the
`storage_bucket_acl` resource. Do not use these two resources in conjunction to manage the same bucket.

The BucketAccessControls resource manages the Access Control List
(ACLs) for a single entity/role pairing on a bucket. ACLs let you specify who
has access to your data and to what extent.

There are three roles that can be assigned to an entity:

READERs can get the bucket, though no acl property will be returned, and
list the bucket's objects.  WRITERs are READERs, and they can insert
objects into the bucket and delete the bucket's objects.  OWNERs are
WRITERs, and they can get the acl property of a bucket, update a bucket,
and call all BucketAccessControls methods on the bucket.  For more
information, see Access Control, with the caveat that this API uses
READER, WRITER, and OWNER instead of READ, WRITE, and FULL_CONTROL.


To get more information about BucketAccessControl, see:

* [API documentation](https://cloud.google.com/storage/docs/json_api/v1/bucketAccessControls)
* How-to Guides
    * [Official Documentation](https://cloud.google.com/storage/docs/access-control/lists)

> This content is derived from https://github.com/terraform-providers/terraform-provider-google/blob/master/website/docs/r/storage_bucket_access_control.html.markdown.



## Create a BucketAccessControl Resource

{{< langchoose csharp nojavascript >}}

<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/storage/#BucketAccessControl">BucketAccessControl</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/storage/#BucketAccessControlArgs">BucketAccessControlArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">BucketAccessControl</span><span class="p">(resource_name, opts=None, </span>bucket=None<span class="p">, </span>entity=None<span class="p">, </span>role=None<span class="p">, __props__=None);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewBucketAccessControl<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/storage?tab=doc#BucketAccessControlArgs">BucketAccessControlArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/storage?tab=doc#BucketAccessControl">BucketAccessControl</a></span>, error)</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Storage.BucketAccessControl.html">BucketAccessControl</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Storage.BucketAccessControlArgs.html">BucketAccessControlArgs</a></span> <span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>

Creates a BucketAccessControl resource with the given unique name, arguments, and options.

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
The entity holding the permission, in one of the following forms: user-userId user-email group-groupId group-email
domain-domain project-team-projectId allUsers allAuthenticatedUsers Examples: The user liz@example.com would be
user-liz@example.com. The group example@googlegroups.com would be group-example@googlegroups.com. To refer to all
members of the Google Apps for Business domain example.com, the entity would be domain-example.com.
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
The entity holding the permission, in one of the following forms: user-userId user-email group-groupId group-email
domain-domain project-team-projectId allUsers allAuthenticatedUsers Examples: The user liz@example.com would be
user-liz@example.com. The group example@googlegroups.com would be group-example@googlegroups.com. To refer to all
members of the Google Apps for Business domain example.com, the entity would be domain-example.com.
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
The entity holding the permission, in one of the following forms: user-userId user-email group-groupId group-email
domain-domain project-team-projectId allUsers allAuthenticatedUsers Examples: The user liz@example.com would be
user-liz@example.com. The group example@googlegroups.com would be group-example@googlegroups.com. To refer to all
members of the Google Apps for Business domain example.com, the entity would be domain-example.com.
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
The entity holding the permission, in one of the following forms: user-userId user-email group-groupId group-email
domain-domain project-team-projectId allUsers allAuthenticatedUsers Examples: The user liz@example.com would be
user-liz@example.com. The group example@googlegroups.com would be group-example@googlegroups.com. To refer to all
members of the Google Apps for Business domain example.com, the entity would be domain-example.com.
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







## BucketAccessControl Output Properties

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
            <td class="align-top">{{% md %}} The entity holding the permission, in one of the following forms: user-userId user-email group-groupId group-email
domain-domain project-team-projectId allUsers allAuthenticatedUsers Examples: The user liz@example.com would be
user-liz@example.com. The group example@googlegroups.com would be group-example@googlegroups.com. To refer to all
members of the Google Apps for Business domain example.com, the entity would be domain-example.com.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Role</td>
            <td class="align-top">
                
                <code>string?</code>
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
            <td class="align-top">{{% md %}} The entity holding the permission, in one of the following forms: user-userId user-email group-groupId group-email
domain-domain project-team-projectId allUsers allAuthenticatedUsers Examples: The user liz@example.com would be
user-liz@example.com. The group example@googlegroups.com would be group-example@googlegroups.com. To refer to all
members of the Google Apps for Business domain example.com, the entity would be domain-example.com.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Role</td>
            <td class="align-top">
                
                <code>*string</code>
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
            <td class="align-top">{{% md %}} The entity holding the permission, in one of the following forms: user-userId user-email group-groupId group-email
domain-domain project-team-projectId allUsers allAuthenticatedUsers Examples: The user liz@example.com would be
user-liz@example.com. The group example@googlegroups.com would be group-example@googlegroups.com. To refer to all
members of the Google Apps for Business domain example.com, the entity would be domain-example.com.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">role</td>
            <td class="align-top">
                
                <code>string?</code>
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
            <td class="align-top">{{% md %}} The entity holding the permission, in one of the following forms: user-userId user-email group-groupId group-email
domain-domain project-team-projectId allUsers allAuthenticatedUsers Examples: The user liz@example.com would be
user-liz@example.com. The group example@googlegroups.com would be group-example@googlegroups.com. To refer to all
members of the Google Apps for Business domain example.com, the entity would be domain-example.com.
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








## Look up an Existing BucketAccessControl Resource

{{< langchoose csharp nojavascript >}}

<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">pulumi.Input&lt;pulumi.ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/storage/#BucketAccessControlState">BucketAccessControlState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/storage/#BucketAccessControl">BucketAccessControl</a></span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>bucket=None<span class="p">, </span>domain=None<span class="p">, </span>email=None<span class="p">, </span>entity=None<span class="p">, </span>role=None<span class="p">, __props__=None);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetBucketAccessControl<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">pulumi.IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/storage?tab=doc#BucketAccessControlState">BucketAccessControlState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/storage?tab=doc#BucketAccessControl">BucketAccessControl</a></span>, error)</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Storage.BucketAccessControl.html">BucketAccessControl</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Pulumi.Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Storage.BucketAccessControlState.html">BucketAccessControlState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>

Get an existing BucketAccessControl resource's state with the given name, ID, and optional extra properties used to qualify the lookup.

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
The entity holding the permission, in one of the following forms: user-userId user-email group-groupId group-email
domain-domain project-team-projectId allUsers allAuthenticatedUsers Examples: The user liz@example.com would be
user-liz@example.com. The group example@googlegroups.com would be group-example@googlegroups.com. To refer to all
members of the Google Apps for Business domain example.com, the entity would be domain-example.com.
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
The entity holding the permission, in one of the following forms: user-userId user-email group-groupId group-email
domain-domain project-team-projectId allUsers allAuthenticatedUsers Examples: The user liz@example.com would be
user-liz@example.com. The group example@googlegroups.com would be group-example@googlegroups.com. To refer to all
members of the Google Apps for Business domain example.com, the entity would be domain-example.com.
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
The entity holding the permission, in one of the following forms: user-userId user-email group-groupId group-email
domain-domain project-team-projectId allUsers allAuthenticatedUsers Examples: The user liz@example.com would be
user-liz@example.com. The group example@googlegroups.com would be group-example@googlegroups.com. To refer to all
members of the Google Apps for Business domain example.com, the entity would be domain-example.com.
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
The entity holding the permission, in one of the following forms: user-userId user-email group-groupId group-email
domain-domain project-team-projectId allUsers allAuthenticatedUsers Examples: The user liz@example.com would be
user-liz@example.com. The group example@googlegroups.com would be group-example@googlegroups.com. To refer to all
members of the Google Apps for Business domain example.com, the entity would be domain-example.com.
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










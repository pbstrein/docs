
---
title: "Lien"
block_external_search_index: true
---
<style>
table td p { margin-top: 0; margin-bottom: 0; }
</style>

A Lien represents an encumbrance on the actions that can be performed on a resource.



## Example Usage - Resource Manager Lien


```typescript
import * as pulumi from "@pulumi/pulumi";
import * as gcp from "@pulumi/gcp";

const project = new gcp.organizations.Project("project", {
    projectId: "staging-project",
});
const lien = new gcp.resourcemanager.Lien("lien", {
    origin: "machine-readable-explanation",
    parent: pulumi.interpolate`projects/${project.number}`,
    reason: "This project is an important environment",
    restrictions: ["resourcemanager.projects.delete"],
});
```

> This content is derived from https://github.com/terraform-providers/terraform-provider-google/blob/master/website/docs/r/resource_manager_lien.html.markdown.



## Create a Lien Resource

{{< langchoose csharp nojavascript >}}

<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/resourcemanager/#Lien">Lien</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/resourcemanager/#LienArgs">LienArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">Lien</span><span class="p">(resource_name, opts=None, </span>origin=None<span class="p">, </span>parent=None<span class="p">, </span>reason=None<span class="p">, </span>restrictions=None<span class="p">, __props__=None);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewLien<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/resourcemanager?tab=doc#LienArgs">LienArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/resourcemanager?tab=doc#Lien">Lien</a></span>, error)</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Resourcemanager.Lien.html">Lien</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Resourcemanager.LienArgs.html">LienArgs</a></span> <span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>

Creates a Lien resource with the given unique name, arguments, and options.

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
            <td class="align-top">Origin</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
A stable, user-visible/meaningful string identifying the origin of the Lien, intended to be inspected programmatically.
Maximum length of 200 characters.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Parent</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
A reference to the resource this Lien is attached to. The server will validate the parent against those for which Liens
are supported. Since a variety of objects can have Liens against them, you must provide the type prefix (e.g.
&#34;projects/my-project-name&#34;).
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Reason</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Concise user-visible strings indicating why an action cannot be performed on a resource. Maximum length of 200
characters.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Restrictions</td>
            <td class="align-top">
                
                <code>List<string></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The types of operations which should be blocked as a result of this Lien. Each value should correspond to an IAM
permission. The server will validate the permissions against those for which Liens are supported. An empty list is
meaningless and will be rejected. e.g. [&#39;resourcemanager.projects.delete&#39;]
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
            <td class="align-top">Origin</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
A stable, user-visible/meaningful string identifying the origin of the Lien, intended to be inspected programmatically.
Maximum length of 200 characters.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Parent</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
A reference to the resource this Lien is attached to. The server will validate the parent against those for which Liens
are supported. Since a variety of objects can have Liens against them, you must provide the type prefix (e.g.
&#34;projects/my-project-name&#34;).
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Reason</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Concise user-visible strings indicating why an action cannot be performed on a resource. Maximum length of 200
characters.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Restrictions</td>
            <td class="align-top">
                
                <code>[]string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The types of operations which should be blocked as a result of this Lien. Each value should correspond to an IAM
permission. The server will validate the permissions against those for which Liens are supported. An empty list is
meaningless and will be rejected. e.g. [&#39;resourcemanager.projects.delete&#39;]
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
            <td class="align-top">origin</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
A stable, user-visible/meaningful string identifying the origin of the Lien, intended to be inspected programmatically.
Maximum length of 200 characters.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">parent</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
A reference to the resource this Lien is attached to. The server will validate the parent against those for which Liens
are supported. Since a variety of objects can have Liens against them, you must provide the type prefix (e.g.
&#34;projects/my-project-name&#34;).
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">reason</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Concise user-visible strings indicating why an action cannot be performed on a resource. Maximum length of 200
characters.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">restrictions</td>
            <td class="align-top">
                
                <code>string[]</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The types of operations which should be blocked as a result of this Lien. Each value should correspond to an IAM
permission. The server will validate the permissions against those for which Liens are supported. An empty list is
meaningless and will be rejected. e.g. [&#39;resourcemanager.projects.delete&#39;]
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
            <td class="align-top">origin</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
A stable, user-visible/meaningful string identifying the origin of the Lien, intended to be inspected programmatically.
Maximum length of 200 characters.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">parent</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
A reference to the resource this Lien is attached to. The server will validate the parent against those for which Liens
are supported. Since a variety of objects can have Liens against them, you must provide the type prefix (e.g.
&#34;projects/my-project-name&#34;).
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">reason</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Concise user-visible strings indicating why an action cannot be performed on a resource. Maximum length of 200
characters.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">restrictions</td>
            <td class="align-top">
                
                <code>List[str]</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The types of operations which should be blocked as a result of this Lien. Each value should correspond to an IAM
permission. The server will validate the permissions against those for which Liens are supported. An empty list is
meaningless and will be rejected. e.g. [&#39;resourcemanager.projects.delete&#39;]
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}







## Lien Output Properties

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
            <td class="align-top">Create<wbr>Time</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Time of creation
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} A system-generated unique identifier for this Lien.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Origin</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} A stable, user-visible/meaningful string identifying the origin of the Lien, intended to be inspected programmatically.
Maximum length of 200 characters.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Parent</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} A reference to the resource this Lien is attached to. The server will validate the parent against those for which Liens
are supported. Since a variety of objects can have Liens against them, you must provide the type prefix (e.g.
&#34;projects/my-project-name&#34;).
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Reason</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Concise user-visible strings indicating why an action cannot be performed on a resource. Maximum length of 200
characters.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Restrictions</td>
            <td class="align-top">
                
                <code>List<string></code>
            </td>
            <td class="align-top">{{% md %}} The types of operations which should be blocked as a result of this Lien. Each value should correspond to an IAM
permission. The server will validate the permissions against those for which Liens are supported. An empty list is
meaningless and will be rejected. e.g. [&#39;resourcemanager.projects.delete&#39;]
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
            <td class="align-top">Create<wbr>Time</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Time of creation
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} A system-generated unique identifier for this Lien.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Origin</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} A stable, user-visible/meaningful string identifying the origin of the Lien, intended to be inspected programmatically.
Maximum length of 200 characters.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Parent</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} A reference to the resource this Lien is attached to. The server will validate the parent against those for which Liens
are supported. Since a variety of objects can have Liens against them, you must provide the type prefix (e.g.
&#34;projects/my-project-name&#34;).
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Reason</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Concise user-visible strings indicating why an action cannot be performed on a resource. Maximum length of 200
characters.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Restrictions</td>
            <td class="align-top">
                
                <code>[]string</code>
            </td>
            <td class="align-top">{{% md %}} The types of operations which should be blocked as a result of this Lien. Each value should correspond to an IAM
permission. The server will validate the permissions against those for which Liens are supported. An empty list is
meaningless and will be rejected. e.g. [&#39;resourcemanager.projects.delete&#39;]
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
            <td class="align-top">create<wbr>Time</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Time of creation
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} A system-generated unique identifier for this Lien.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">origin</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} A stable, user-visible/meaningful string identifying the origin of the Lien, intended to be inspected programmatically.
Maximum length of 200 characters.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">parent</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} A reference to the resource this Lien is attached to. The server will validate the parent against those for which Liens
are supported. Since a variety of objects can have Liens against them, you must provide the type prefix (e.g.
&#34;projects/my-project-name&#34;).
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">reason</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Concise user-visible strings indicating why an action cannot be performed on a resource. Maximum length of 200
characters.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">restrictions</td>
            <td class="align-top">
                
                <code>string[]</code>
            </td>
            <td class="align-top">{{% md %}} The types of operations which should be blocked as a result of this Lien. Each value should correspond to an IAM
permission. The server will validate the permissions against those for which Liens are supported. An empty list is
meaningless and will be rejected. e.g. [&#39;resourcemanager.projects.delete&#39;]
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
            <td class="align-top">create_<wbr>time</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} Time of creation
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">name</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} A system-generated unique identifier for this Lien.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">origin</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} A stable, user-visible/meaningful string identifying the origin of the Lien, intended to be inspected programmatically.
Maximum length of 200 characters.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">parent</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} A reference to the resource this Lien is attached to. The server will validate the parent against those for which Liens
are supported. Since a variety of objects can have Liens against them, you must provide the type prefix (e.g.
&#34;projects/my-project-name&#34;).
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">reason</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} Concise user-visible strings indicating why an action cannot be performed on a resource. Maximum length of 200
characters.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">restrictions</td>
            <td class="align-top">
                
                <code>List[str]</code>
            </td>
            <td class="align-top">{{% md %}} The types of operations which should be blocked as a result of this Lien. Each value should correspond to an IAM
permission. The server will validate the permissions against those for which Liens are supported. An empty list is
meaningless and will be rejected. e.g. [&#39;resourcemanager.projects.delete&#39;]
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}








## Look up an Existing Lien Resource

{{< langchoose csharp nojavascript >}}

<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">pulumi.Input&lt;pulumi.ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/resourcemanager/#LienState">LienState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/resourcemanager/#Lien">Lien</a></span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>create_time=None<span class="p">, </span>name=None<span class="p">, </span>origin=None<span class="p">, </span>parent=None<span class="p">, </span>reason=None<span class="p">, </span>restrictions=None<span class="p">, __props__=None);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetLien<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">pulumi.IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/resourcemanager?tab=doc#LienState">LienState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/resourcemanager?tab=doc#Lien">Lien</a></span>, error)</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Resourcemanager.Lien.html">Lien</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Pulumi.Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Resourcemanager.LienState.html">LienState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>

Get an existing Lien resource's state with the given name, ID, and optional extra properties used to qualify the lookup.

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
            <td class="align-top">Create<wbr>Time</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Time of creation
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
A system-generated unique identifier for this Lien.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Origin</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A stable, user-visible/meaningful string identifying the origin of the Lien, intended to be inspected programmatically.
Maximum length of 200 characters.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Parent</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A reference to the resource this Lien is attached to. The server will validate the parent against those for which Liens
are supported. Since a variety of objects can have Liens against them, you must provide the type prefix (e.g.
&#34;projects/my-project-name&#34;).
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Reason</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Concise user-visible strings indicating why an action cannot be performed on a resource. Maximum length of 200
characters.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Restrictions</td>
            <td class="align-top">
                
                <code>List<string>?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The types of operations which should be blocked as a result of this Lien. Each value should correspond to an IAM
permission. The server will validate the permissions against those for which Liens are supported. An empty list is
meaningless and will be rejected. e.g. [&#39;resourcemanager.projects.delete&#39;]
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
            <td class="align-top">Create<wbr>Time</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Time of creation
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
A system-generated unique identifier for this Lien.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Origin</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A stable, user-visible/meaningful string identifying the origin of the Lien, intended to be inspected programmatically.
Maximum length of 200 characters.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Parent</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A reference to the resource this Lien is attached to. The server will validate the parent against those for which Liens
are supported. Since a variety of objects can have Liens against them, you must provide the type prefix (e.g.
&#34;projects/my-project-name&#34;).
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Reason</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Concise user-visible strings indicating why an action cannot be performed on a resource. Maximum length of 200
characters.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Restrictions</td>
            <td class="align-top">
                
                <code>[]string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The types of operations which should be blocked as a result of this Lien. Each value should correspond to an IAM
permission. The server will validate the permissions against those for which Liens are supported. An empty list is
meaningless and will be rejected. e.g. [&#39;resourcemanager.projects.delete&#39;]
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
            <td class="align-top">create<wbr>Time</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Time of creation
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
A system-generated unique identifier for this Lien.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">origin</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A stable, user-visible/meaningful string identifying the origin of the Lien, intended to be inspected programmatically.
Maximum length of 200 characters.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">parent</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A reference to the resource this Lien is attached to. The server will validate the parent against those for which Liens
are supported. Since a variety of objects can have Liens against them, you must provide the type prefix (e.g.
&#34;projects/my-project-name&#34;).
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">reason</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Concise user-visible strings indicating why an action cannot be performed on a resource. Maximum length of 200
characters.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">restrictions</td>
            <td class="align-top">
                
                <code>string[]?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The types of operations which should be blocked as a result of this Lien. Each value should correspond to an IAM
permission. The server will validate the permissions against those for which Liens are supported. An empty list is
meaningless and will be rejected. e.g. [&#39;resourcemanager.projects.delete&#39;]
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
            <td class="align-top">create_<wbr>time</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Time of creation
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
A system-generated unique identifier for this Lien.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">origin</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A stable, user-visible/meaningful string identifying the origin of the Lien, intended to be inspected programmatically.
Maximum length of 200 characters.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">parent</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A reference to the resource this Lien is attached to. The server will validate the parent against those for which Liens
are supported. Since a variety of objects can have Liens against them, you must provide the type prefix (e.g.
&#34;projects/my-project-name&#34;).
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">reason</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Concise user-visible strings indicating why an action cannot be performed on a resource. Maximum length of 200
characters.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">restrictions</td>
            <td class="align-top">
                
                <code>List[str]</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The types of operations which should be blocked as a result of this Lien. Each value should correspond to an IAM
permission. The server will validate the permissions against those for which Liens are supported. An empty list is
meaningless and will be rejected. e.g. [&#39;resourcemanager.projects.delete&#39;]
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}










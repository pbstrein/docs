
---
title: "Note"
block_external_search_index: true
---
<style>
table td p { margin-top: 0; margin-bottom: 0; }
</style>




## Create a Note Resource

{{< langchoose csharp nojavascript >}}

<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/containeranalysis/#Note">Note</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/containeranalysis/#NoteArgs">NoteArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">Note</span><span class="p">(resource_name, opts=None, </span>attestation_authority=None<span class="p">, </span>name=None<span class="p">, </span>project=None<span class="p">, __props__=None);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewNote<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/containeranalysis?tab=doc#NoteArgs">NoteArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/containeranalysis?tab=doc#Note">Note</a></span>, error)</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Containeranalysis.Note.html">Note</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Containeranalysis.NoteArgs.html">NoteArgs</a></span> <span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>

Creates a Note resource with the given unique name, arguments, and options.

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
            <td class="align-top">Attestation<wbr>Authority</td>
            <td class="align-top">
                
                <code><a href="#noteattestationauthority">Note<wbr>Attestation<wbr>Authority<wbr>Args</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Note kind that represents a logical attestation &#34;role&#34; or &#34;authority&#34;. For example, an organization might have one
AttestationAuthority for &#34;QA&#34; and one for &#34;build&#34;. This Note is intended to act strictly as a grouping mechanism for the
attached Occurrences (Attestations). This grouping mechanism also provides a security boundary, since IAM ACLs gate the
ability for a principle to attach an Occurrence to a given Note. It also provides a single point of lookup to find all
attached Attestation Occurrences, even if they don&#39;t all live in the same project.
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
The name of the note.
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
            <td class="align-top">Attestation<wbr>Authority</td>
            <td class="align-top">
                
                <code><a href="#noteattestationauthority">Note<wbr>Attestation<wbr>Authority</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Note kind that represents a logical attestation &#34;role&#34; or &#34;authority&#34;. For example, an organization might have one
AttestationAuthority for &#34;QA&#34; and one for &#34;build&#34;. This Note is intended to act strictly as a grouping mechanism for the
attached Occurrences (Attestations). This grouping mechanism also provides a security boundary, since IAM ACLs gate the
ability for a principle to attach an Occurrence to a given Note. It also provides a single point of lookup to find all
attached Attestation Occurrences, even if they don&#39;t all live in the same project.
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
The name of the note.
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
            <td class="align-top">attestation<wbr>Authority</td>
            <td class="align-top">
                
                <code><a href="#noteattestationauthority">Note<wbr>Attestation<wbr>Authority</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Note kind that represents a logical attestation &#34;role&#34; or &#34;authority&#34;. For example, an organization might have one
AttestationAuthority for &#34;QA&#34; and one for &#34;build&#34;. This Note is intended to act strictly as a grouping mechanism for the
attached Occurrences (Attestations). This grouping mechanism also provides a security boundary, since IAM ACLs gate the
ability for a principle to attach an Occurrence to a given Note. It also provides a single point of lookup to find all
attached Attestation Occurrences, even if they don&#39;t all live in the same project.
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
The name of the note.
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
            <td class="align-top">attestation_<wbr>authority</td>
            <td class="align-top">
                
                <code><a href="#noteattestationauthority">Dict[Note<wbr>Attestation<wbr>Authority]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Note kind that represents a logical attestation &#34;role&#34; or &#34;authority&#34;. For example, an organization might have one
AttestationAuthority for &#34;QA&#34; and one for &#34;build&#34;. This Note is intended to act strictly as a grouping mechanism for the
attached Occurrences (Attestations). This grouping mechanism also provides a security boundary, since IAM ACLs gate the
ability for a principle to attach an Occurrence to a given Note. It also provides a single point of lookup to find all
attached Attestation Occurrences, even if they don&#39;t all live in the same project.
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
The name of the note.
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
    
    </tbody>
</table>


{{% /lang %}}







## Note Output Properties

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
            <td class="align-top">Attestation<wbr>Authority</td>
            <td class="align-top">
                
                <code><a href="#noteattestationauthority">Note<wbr>Attestation<wbr>Authority</a></code>
            </td>
            <td class="align-top">{{% md %}} Note kind that represents a logical attestation &#34;role&#34; or &#34;authority&#34;. For example, an organization might have one
AttestationAuthority for &#34;QA&#34; and one for &#34;build&#34;. This Note is intended to act strictly as a grouping mechanism for the
attached Occurrences (Attestations). This grouping mechanism also provides a security boundary, since IAM ACLs gate the
ability for a principle to attach an Occurrence to a given Note. It also provides a single point of lookup to find all
attached Attestation Occurrences, even if they don&#39;t all live in the same project.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The name of the note.
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
            <td class="align-top">Attestation<wbr>Authority</td>
            <td class="align-top">
                
                <code><a href="#noteattestationauthority">Note<wbr>Attestation<wbr>Authority</a></code>
            </td>
            <td class="align-top">{{% md %}} Note kind that represents a logical attestation &#34;role&#34; or &#34;authority&#34;. For example, an organization might have one
AttestationAuthority for &#34;QA&#34; and one for &#34;build&#34;. This Note is intended to act strictly as a grouping mechanism for the
attached Occurrences (Attestations). This grouping mechanism also provides a security boundary, since IAM ACLs gate the
ability for a principle to attach an Occurrence to a given Note. It also provides a single point of lookup to find all
attached Attestation Occurrences, even if they don&#39;t all live in the same project.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The name of the note.
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
            <td class="align-top">attestation<wbr>Authority</td>
            <td class="align-top">
                
                <code><a href="#noteattestationauthority">Note<wbr>Attestation<wbr>Authority</a></code>
            </td>
            <td class="align-top">{{% md %}} Note kind that represents a logical attestation &#34;role&#34; or &#34;authority&#34;. For example, an organization might have one
AttestationAuthority for &#34;QA&#34; and one for &#34;build&#34;. This Note is intended to act strictly as a grouping mechanism for the
attached Occurrences (Attestations). This grouping mechanism also provides a security boundary, since IAM ACLs gate the
ability for a principle to attach an Occurrence to a given Note. It also provides a single point of lookup to find all
attached Attestation Occurrences, even if they don&#39;t all live in the same project.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The name of the note.
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
            <td class="align-top">attestation_<wbr>authority</td>
            <td class="align-top">
                
                <code><a href="#noteattestationauthority">Dict[Note<wbr>Attestation<wbr>Authority]</a></code>
            </td>
            <td class="align-top">{{% md %}} Note kind that represents a logical attestation &#34;role&#34; or &#34;authority&#34;. For example, an organization might have one
AttestationAuthority for &#34;QA&#34; and one for &#34;build&#34;. This Note is intended to act strictly as a grouping mechanism for the
attached Occurrences (Attestations). This grouping mechanism also provides a security boundary, since IAM ACLs gate the
ability for a principle to attach an Occurrence to a given Note. It also provides a single point of lookup to find all
attached Attestation Occurrences, even if they don&#39;t all live in the same project.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">name</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The name of the note.
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
    
    </tbody>
</table>


{{% /lang %}}








## Look up an Existing Note Resource

{{< langchoose csharp nojavascript >}}

<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">pulumi.Input&lt;pulumi.ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/containeranalysis/#NoteState">NoteState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/containeranalysis/#Note">Note</a></span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>attestation_authority=None<span class="p">, </span>name=None<span class="p">, </span>project=None<span class="p">, __props__=None);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetNote<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">pulumi.IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/containeranalysis?tab=doc#NoteState">NoteState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/containeranalysis?tab=doc#Note">Note</a></span>, error)</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Containeranalysis.Note.html">Note</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Pulumi.Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Containeranalysis.NoteState.html">NoteState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>

Get an existing Note resource's state with the given name, ID, and optional extra properties used to qualify the lookup.

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
            <td class="align-top">Attestation<wbr>Authority</td>
            <td class="align-top">
                
                <code><a href="#noteattestationauthority">Note<wbr>Attestation<wbr>Authority<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Note kind that represents a logical attestation &#34;role&#34; or &#34;authority&#34;. For example, an organization might have one
AttestationAuthority for &#34;QA&#34; and one for &#34;build&#34;. This Note is intended to act strictly as a grouping mechanism for the
attached Occurrences (Attestations). This grouping mechanism also provides a security boundary, since IAM ACLs gate the
ability for a principle to attach an Occurrence to a given Note. It also provides a single point of lookup to find all
attached Attestation Occurrences, even if they don&#39;t all live in the same project.
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
The name of the note.
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
            <td class="align-top">Attestation<wbr>Authority</td>
            <td class="align-top">
                
                <code><a href="#noteattestationauthority">*Note<wbr>Attestation<wbr>Authority</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Note kind that represents a logical attestation &#34;role&#34; or &#34;authority&#34;. For example, an organization might have one
AttestationAuthority for &#34;QA&#34; and one for &#34;build&#34;. This Note is intended to act strictly as a grouping mechanism for the
attached Occurrences (Attestations). This grouping mechanism also provides a security boundary, since IAM ACLs gate the
ability for a principle to attach an Occurrence to a given Note. It also provides a single point of lookup to find all
attached Attestation Occurrences, even if they don&#39;t all live in the same project.
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
The name of the note.
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
            <td class="align-top">attestation<wbr>Authority</td>
            <td class="align-top">
                
                <code><a href="#noteattestationauthority">Note<wbr>Attestation<wbr>Authority?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Note kind that represents a logical attestation &#34;role&#34; or &#34;authority&#34;. For example, an organization might have one
AttestationAuthority for &#34;QA&#34; and one for &#34;build&#34;. This Note is intended to act strictly as a grouping mechanism for the
attached Occurrences (Attestations). This grouping mechanism also provides a security boundary, since IAM ACLs gate the
ability for a principle to attach an Occurrence to a given Note. It also provides a single point of lookup to find all
attached Attestation Occurrences, even if they don&#39;t all live in the same project.
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
The name of the note.
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
            <td class="align-top">attestation_<wbr>authority</td>
            <td class="align-top">
                
                <code><a href="#noteattestationauthority">Dict[Note<wbr>Attestation<wbr>Authority]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Note kind that represents a logical attestation &#34;role&#34; or &#34;authority&#34;. For example, an organization might have one
AttestationAuthority for &#34;QA&#34; and one for &#34;build&#34;. This Note is intended to act strictly as a grouping mechanism for the
attached Occurrences (Attestations). This grouping mechanism also provides a security boundary, since IAM ACLs gate the
ability for a principle to attach an Occurrence to a given Note. It also provides a single point of lookup to find all
attached Attestation Occurrences, even if they don&#39;t all live in the same project.
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
The name of the note.
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
    
    </tbody>
</table>


{{% /lang %}}










## Supporting Types

#### NoteAttestationAuthority
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#NoteAttestationAuthority">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#NoteAttestationAuthority">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/containeranalysis?tab=doc#NoteAttestationAuthorityArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/containeranalysis?tab=doc#NoteAttestationAuthorityOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Containeranalysis.NoteAttestationAuthorityArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Containeranalysis.NoteAttestationAuthority.html">output</a> API doc for this type.
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
            <td class="align-top">Hint</td>
            <td class="align-top">
                
                <code><a href="#noteattestationauthorityhint">Note<wbr>Attestation<wbr>Authority<wbr>Hint<wbr>Args</a></code>
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
            <td class="align-top">Hint</td>
            <td class="align-top">
                
                <code><a href="#noteattestationauthorityhint">Note<wbr>Attestation<wbr>Authority<wbr>Hint</a></code>
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
            <td class="align-top">hint</td>
            <td class="align-top">
                
                <code><a href="#noteattestationauthorityhint">Note<wbr>Attestation<wbr>Authority<wbr>Hint</a></code>
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
            <td class="align-top">hint</td>
            <td class="align-top">
                
                <code><a href="#noteattestationauthorityhint">Dict[Note<wbr>Attestation<wbr>Authority<wbr>Hint]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}





#### NoteAttestationAuthorityHint
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#NoteAttestationAuthorityHint">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#NoteAttestationAuthorityHint">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/containeranalysis?tab=doc#NoteAttestationAuthorityHintArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/containeranalysis?tab=doc#NoteAttestationAuthorityHintOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Containeranalysis.NoteAttestationAuthorityHintArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Containeranalysis.NoteAttestationAuthorityHint.html">output</a> API doc for this type.
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
            <td class="align-top">Human<wbr>Readable<wbr>Name</td>
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
            <td class="align-top">Human<wbr>Readable<wbr>Name</td>
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
            <td class="align-top">human<wbr>Readable<wbr>Name</td>
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
            <td class="align-top">human<wbr>Readable<wbr>Name</td>
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








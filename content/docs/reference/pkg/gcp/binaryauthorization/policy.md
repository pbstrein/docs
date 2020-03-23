
---
title: "Policy"
block_external_search_index: true
---
<style>
table td p { margin-top: 0; margin-bottom: 0; }
</style>




## Create a Policy Resource

{{< langchoose csharp nojavascript >}}

<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/binaryauthorization/#Policy">Policy</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/binaryauthorization/#PolicyArgs">PolicyArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">Policy</span><span class="p">(resource_name, opts=None, </span>admission_whitelist_patterns=None<span class="p">, </span>cluster_admission_rules=None<span class="p">, </span>default_admission_rule=None<span class="p">, </span>description=None<span class="p">, </span>global_policy_evaluation_mode=None<span class="p">, </span>project=None<span class="p">, __props__=None);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewPolicy<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/binaryauthorization?tab=doc#PolicyArgs">PolicyArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/binaryauthorization?tab=doc#Policy">Policy</a></span>, error)</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Binaryauthorization.Policy.html">Policy</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Binaryauthorization.PolicyArgs.html">PolicyArgs</a></span> <span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>

Creates a Policy resource with the given unique name, arguments, and options.

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
            <td class="align-top">Admission<wbr>Whitelist<wbr>Patterns</td>
            <td class="align-top">
                
                <code><a href="#policyadmissionwhitelistpattern">List&lt;Policy<wbr>Admission<wbr>Whitelist<wbr>Pattern<wbr>Args&gt;?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A whitelist of image patterns to exclude from admission rules. If an image&#39;s name matches a whitelist pattern, the
image&#39;s admission requests will always be permitted regardless of your admission rules.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Cluster<wbr>Admission<wbr>Rules</td>
            <td class="align-top">
                
                <code><a href="#policyclusteradmissionrule">List&lt;Policy<wbr>Cluster<wbr>Admission<wbr>Rule<wbr>Args&gt;?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Per-cluster admission rules. An admission rule specifies either that all container images used in a pod creation request
must be attested to by one or more attestors, that all pod creations will be allowed, or that all pod creations will be
denied. There can be at most one admission rule per cluster spec. Identifier format: &#39;{{location}}.{{clusterId}}&#39;. A
location is either a compute zone (e.g. &#39;us-central1-a&#39;) or a region (e.g. &#39;us-central1&#39;).
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Default<wbr>Admission<wbr>Rule</td>
            <td class="align-top">
                
                <code><a href="#policydefaultadmissionrule">Policy<wbr>Default<wbr>Admission<wbr>Rule<wbr>Args</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Default admission rule for a cluster without a per-cluster admission rule.
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
A descriptive comment.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Global<wbr>Policy<wbr>Evaluation<wbr>Mode</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Controls the evaluation of a Google-maintained global admission policy for common system-level images. Images not
covered by the global policy will be subject to the project admission policy.
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
            <td class="align-top">Admission<wbr>Whitelist<wbr>Patterns</td>
            <td class="align-top">
                
                <code><a href="#policyadmissionwhitelistpattern">[]Policy<wbr>Admission<wbr>Whitelist<wbr>Pattern</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A whitelist of image patterns to exclude from admission rules. If an image&#39;s name matches a whitelist pattern, the
image&#39;s admission requests will always be permitted regardless of your admission rules.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Cluster<wbr>Admission<wbr>Rules</td>
            <td class="align-top">
                
                <code><a href="#policyclusteradmissionrule">[]Policy<wbr>Cluster<wbr>Admission<wbr>Rule</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Per-cluster admission rules. An admission rule specifies either that all container images used in a pod creation request
must be attested to by one or more attestors, that all pod creations will be allowed, or that all pod creations will be
denied. There can be at most one admission rule per cluster spec. Identifier format: &#39;{{location}}.{{clusterId}}&#39;. A
location is either a compute zone (e.g. &#39;us-central1-a&#39;) or a region (e.g. &#39;us-central1&#39;).
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Default<wbr>Admission<wbr>Rule</td>
            <td class="align-top">
                
                <code><a href="#policydefaultadmissionrule">Policy<wbr>Default<wbr>Admission<wbr>Rule</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Default admission rule for a cluster without a per-cluster admission rule.
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
A descriptive comment.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Global<wbr>Policy<wbr>Evaluation<wbr>Mode</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Controls the evaluation of a Google-maintained global admission policy for common system-level images. Images not
covered by the global policy will be subject to the project admission policy.
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
            <td class="align-top">admission<wbr>Whitelist<wbr>Patterns</td>
            <td class="align-top">
                
                <code><a href="#policyadmissionwhitelistpattern">Policy<wbr>Admission<wbr>Whitelist<wbr>Pattern[]?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A whitelist of image patterns to exclude from admission rules. If an image&#39;s name matches a whitelist pattern, the
image&#39;s admission requests will always be permitted regardless of your admission rules.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">cluster<wbr>Admission<wbr>Rules</td>
            <td class="align-top">
                
                <code><a href="#policyclusteradmissionrule">Policy<wbr>Cluster<wbr>Admission<wbr>Rule[]?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Per-cluster admission rules. An admission rule specifies either that all container images used in a pod creation request
must be attested to by one or more attestors, that all pod creations will be allowed, or that all pod creations will be
denied. There can be at most one admission rule per cluster spec. Identifier format: &#39;{{location}}.{{clusterId}}&#39;. A
location is either a compute zone (e.g. &#39;us-central1-a&#39;) or a region (e.g. &#39;us-central1&#39;).
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">default<wbr>Admission<wbr>Rule</td>
            <td class="align-top">
                
                <code><a href="#policydefaultadmissionrule">Policy<wbr>Default<wbr>Admission<wbr>Rule</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Default admission rule for a cluster without a per-cluster admission rule.
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
A descriptive comment.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">global<wbr>Policy<wbr>Evaluation<wbr>Mode</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Controls the evaluation of a Google-maintained global admission policy for common system-level images. Images not
covered by the global policy will be subject to the project admission policy.
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
            <td class="align-top">admission_<wbr>whitelist_<wbr>patterns</td>
            <td class="align-top">
                
                <code><a href="#policyadmissionwhitelistpattern">List[Policy<wbr>Admission<wbr>Whitelist<wbr>Pattern]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A whitelist of image patterns to exclude from admission rules. If an image&#39;s name matches a whitelist pattern, the
image&#39;s admission requests will always be permitted regardless of your admission rules.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">cluster_<wbr>admission_<wbr>rules</td>
            <td class="align-top">
                
                <code><a href="#policyclusteradmissionrule">List[Policy<wbr>Cluster<wbr>Admission<wbr>Rule]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Per-cluster admission rules. An admission rule specifies either that all container images used in a pod creation request
must be attested to by one or more attestors, that all pod creations will be allowed, or that all pod creations will be
denied. There can be at most one admission rule per cluster spec. Identifier format: &#39;{{location}}.{{clusterId}}&#39;. A
location is either a compute zone (e.g. &#39;us-central1-a&#39;) or a region (e.g. &#39;us-central1&#39;).
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">default_<wbr>admission_<wbr>rule</td>
            <td class="align-top">
                
                <code><a href="#policydefaultadmissionrule">Dict[Policy<wbr>Default<wbr>Admission<wbr>Rule]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Default admission rule for a cluster without a per-cluster admission rule.
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
A descriptive comment.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">global_<wbr>policy_<wbr>evaluation_<wbr>mode</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Controls the evaluation of a Google-maintained global admission policy for common system-level images. Images not
covered by the global policy will be subject to the project admission policy.
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







## Policy Output Properties

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
            <td class="align-top">Admission<wbr>Whitelist<wbr>Patterns</td>
            <td class="align-top">
                
                <code><a href="#policyadmissionwhitelistpattern">List&lt;Policy<wbr>Admission<wbr>Whitelist<wbr>Pattern&gt;?</a></code>
            </td>
            <td class="align-top">{{% md %}} A whitelist of image patterns to exclude from admission rules. If an image&#39;s name matches a whitelist pattern, the
image&#39;s admission requests will always be permitted regardless of your admission rules.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Cluster<wbr>Admission<wbr>Rules</td>
            <td class="align-top">
                
                <code><a href="#policyclusteradmissionrule">List&lt;Policy<wbr>Cluster<wbr>Admission<wbr>Rule&gt;?</a></code>
            </td>
            <td class="align-top">{{% md %}} Per-cluster admission rules. An admission rule specifies either that all container images used in a pod creation request
must be attested to by one or more attestors, that all pod creations will be allowed, or that all pod creations will be
denied. There can be at most one admission rule per cluster spec. Identifier format: &#39;{{location}}.{{clusterId}}&#39;. A
location is either a compute zone (e.g. &#39;us-central1-a&#39;) or a region (e.g. &#39;us-central1&#39;).
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Default<wbr>Admission<wbr>Rule</td>
            <td class="align-top">
                
                <code><a href="#policydefaultadmissionrule">Policy<wbr>Default<wbr>Admission<wbr>Rule</a></code>
            </td>
            <td class="align-top">{{% md %}} Default admission rule for a cluster without a per-cluster admission rule.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Description</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} A descriptive comment.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Global<wbr>Policy<wbr>Evaluation<wbr>Mode</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Controls the evaluation of a Google-maintained global admission policy for common system-level images. Images not
covered by the global policy will be subject to the project admission policy.
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
            <td class="align-top">Admission<wbr>Whitelist<wbr>Patterns</td>
            <td class="align-top">
                
                <code><a href="#policyadmissionwhitelistpattern">[]Policy<wbr>Admission<wbr>Whitelist<wbr>Pattern</a></code>
            </td>
            <td class="align-top">{{% md %}} A whitelist of image patterns to exclude from admission rules. If an image&#39;s name matches a whitelist pattern, the
image&#39;s admission requests will always be permitted regardless of your admission rules.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Cluster<wbr>Admission<wbr>Rules</td>
            <td class="align-top">
                
                <code><a href="#policyclusteradmissionrule">[]Policy<wbr>Cluster<wbr>Admission<wbr>Rule</a></code>
            </td>
            <td class="align-top">{{% md %}} Per-cluster admission rules. An admission rule specifies either that all container images used in a pod creation request
must be attested to by one or more attestors, that all pod creations will be allowed, or that all pod creations will be
denied. There can be at most one admission rule per cluster spec. Identifier format: &#39;{{location}}.{{clusterId}}&#39;. A
location is either a compute zone (e.g. &#39;us-central1-a&#39;) or a region (e.g. &#39;us-central1&#39;).
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Default<wbr>Admission<wbr>Rule</td>
            <td class="align-top">
                
                <code><a href="#policydefaultadmissionrule">Policy<wbr>Default<wbr>Admission<wbr>Rule</a></code>
            </td>
            <td class="align-top">{{% md %}} Default admission rule for a cluster without a per-cluster admission rule.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Description</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} A descriptive comment.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Global<wbr>Policy<wbr>Evaluation<wbr>Mode</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Controls the evaluation of a Google-maintained global admission policy for common system-level images. Images not
covered by the global policy will be subject to the project admission policy.
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
            <td class="align-top">admission<wbr>Whitelist<wbr>Patterns</td>
            <td class="align-top">
                
                <code><a href="#policyadmissionwhitelistpattern">Policy<wbr>Admission<wbr>Whitelist<wbr>Pattern[]?</a></code>
            </td>
            <td class="align-top">{{% md %}} A whitelist of image patterns to exclude from admission rules. If an image&#39;s name matches a whitelist pattern, the
image&#39;s admission requests will always be permitted regardless of your admission rules.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">cluster<wbr>Admission<wbr>Rules</td>
            <td class="align-top">
                
                <code><a href="#policyclusteradmissionrule">Policy<wbr>Cluster<wbr>Admission<wbr>Rule[]?</a></code>
            </td>
            <td class="align-top">{{% md %}} Per-cluster admission rules. An admission rule specifies either that all container images used in a pod creation request
must be attested to by one or more attestors, that all pod creations will be allowed, or that all pod creations will be
denied. There can be at most one admission rule per cluster spec. Identifier format: &#39;{{location}}.{{clusterId}}&#39;. A
location is either a compute zone (e.g. &#39;us-central1-a&#39;) or a region (e.g. &#39;us-central1&#39;).
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">default<wbr>Admission<wbr>Rule</td>
            <td class="align-top">
                
                <code><a href="#policydefaultadmissionrule">Policy<wbr>Default<wbr>Admission<wbr>Rule</a></code>
            </td>
            <td class="align-top">{{% md %}} Default admission rule for a cluster without a per-cluster admission rule.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">description</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} A descriptive comment.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">global<wbr>Policy<wbr>Evaluation<wbr>Mode</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Controls the evaluation of a Google-maintained global admission policy for common system-level images. Images not
covered by the global policy will be subject to the project admission policy.
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
            <td class="align-top">admission_<wbr>whitelist_<wbr>patterns</td>
            <td class="align-top">
                
                <code><a href="#policyadmissionwhitelistpattern">List[Policy<wbr>Admission<wbr>Whitelist<wbr>Pattern]</a></code>
            </td>
            <td class="align-top">{{% md %}} A whitelist of image patterns to exclude from admission rules. If an image&#39;s name matches a whitelist pattern, the
image&#39;s admission requests will always be permitted regardless of your admission rules.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">cluster_<wbr>admission_<wbr>rules</td>
            <td class="align-top">
                
                <code><a href="#policyclusteradmissionrule">List[Policy<wbr>Cluster<wbr>Admission<wbr>Rule]</a></code>
            </td>
            <td class="align-top">{{% md %}} Per-cluster admission rules. An admission rule specifies either that all container images used in a pod creation request
must be attested to by one or more attestors, that all pod creations will be allowed, or that all pod creations will be
denied. There can be at most one admission rule per cluster spec. Identifier format: &#39;{{location}}.{{clusterId}}&#39;. A
location is either a compute zone (e.g. &#39;us-central1-a&#39;) or a region (e.g. &#39;us-central1&#39;).
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">default_<wbr>admission_<wbr>rule</td>
            <td class="align-top">
                
                <code><a href="#policydefaultadmissionrule">Dict[Policy<wbr>Default<wbr>Admission<wbr>Rule]</a></code>
            </td>
            <td class="align-top">{{% md %}} Default admission rule for a cluster without a per-cluster admission rule.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">description</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} A descriptive comment.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">global_<wbr>policy_<wbr>evaluation_<wbr>mode</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} Controls the evaluation of a Google-maintained global admission policy for common system-level images. Images not
covered by the global policy will be subject to the project admission policy.
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








## Look up an Existing Policy Resource

{{< langchoose csharp nojavascript >}}

<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">pulumi.Input&lt;pulumi.ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/binaryauthorization/#PolicyState">PolicyState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/binaryauthorization/#Policy">Policy</a></span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>admission_whitelist_patterns=None<span class="p">, </span>cluster_admission_rules=None<span class="p">, </span>default_admission_rule=None<span class="p">, </span>description=None<span class="p">, </span>global_policy_evaluation_mode=None<span class="p">, </span>project=None<span class="p">, __props__=None);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetPolicy<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">pulumi.IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/binaryauthorization?tab=doc#PolicyState">PolicyState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/binaryauthorization?tab=doc#Policy">Policy</a></span>, error)</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Binaryauthorization.Policy.html">Policy</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Pulumi.Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Binaryauthorization.PolicyState.html">PolicyState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>

Get an existing Policy resource's state with the given name, ID, and optional extra properties used to qualify the lookup.

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
            <td class="align-top">Admission<wbr>Whitelist<wbr>Patterns</td>
            <td class="align-top">
                
                <code><a href="#policyadmissionwhitelistpattern">List&lt;Policy<wbr>Admission<wbr>Whitelist<wbr>Pattern<wbr>Args&gt;?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A whitelist of image patterns to exclude from admission rules. If an image&#39;s name matches a whitelist pattern, the
image&#39;s admission requests will always be permitted regardless of your admission rules.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Cluster<wbr>Admission<wbr>Rules</td>
            <td class="align-top">
                
                <code><a href="#policyclusteradmissionrule">List&lt;Policy<wbr>Cluster<wbr>Admission<wbr>Rule<wbr>Args&gt;?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Per-cluster admission rules. An admission rule specifies either that all container images used in a pod creation request
must be attested to by one or more attestors, that all pod creations will be allowed, or that all pod creations will be
denied. There can be at most one admission rule per cluster spec. Identifier format: &#39;{{location}}.{{clusterId}}&#39;. A
location is either a compute zone (e.g. &#39;us-central1-a&#39;) or a region (e.g. &#39;us-central1&#39;).
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Default<wbr>Admission<wbr>Rule</td>
            <td class="align-top">
                
                <code><a href="#policydefaultadmissionrule">Policy<wbr>Default<wbr>Admission<wbr>Rule<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Default admission rule for a cluster without a per-cluster admission rule.
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
A descriptive comment.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Global<wbr>Policy<wbr>Evaluation<wbr>Mode</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Controls the evaluation of a Google-maintained global admission policy for common system-level images. Images not
covered by the global policy will be subject to the project admission policy.
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
            <td class="align-top">Admission<wbr>Whitelist<wbr>Patterns</td>
            <td class="align-top">
                
                <code><a href="#policyadmissionwhitelistpattern">[]Policy<wbr>Admission<wbr>Whitelist<wbr>Pattern</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A whitelist of image patterns to exclude from admission rules. If an image&#39;s name matches a whitelist pattern, the
image&#39;s admission requests will always be permitted regardless of your admission rules.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Cluster<wbr>Admission<wbr>Rules</td>
            <td class="align-top">
                
                <code><a href="#policyclusteradmissionrule">[]Policy<wbr>Cluster<wbr>Admission<wbr>Rule</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Per-cluster admission rules. An admission rule specifies either that all container images used in a pod creation request
must be attested to by one or more attestors, that all pod creations will be allowed, or that all pod creations will be
denied. There can be at most one admission rule per cluster spec. Identifier format: &#39;{{location}}.{{clusterId}}&#39;. A
location is either a compute zone (e.g. &#39;us-central1-a&#39;) or a region (e.g. &#39;us-central1&#39;).
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Default<wbr>Admission<wbr>Rule</td>
            <td class="align-top">
                
                <code><a href="#policydefaultadmissionrule">*Policy<wbr>Default<wbr>Admission<wbr>Rule</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Default admission rule for a cluster without a per-cluster admission rule.
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
A descriptive comment.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Global<wbr>Policy<wbr>Evaluation<wbr>Mode</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Controls the evaluation of a Google-maintained global admission policy for common system-level images. Images not
covered by the global policy will be subject to the project admission policy.
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
            <td class="align-top">admission<wbr>Whitelist<wbr>Patterns</td>
            <td class="align-top">
                
                <code><a href="#policyadmissionwhitelistpattern">Policy<wbr>Admission<wbr>Whitelist<wbr>Pattern[]?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A whitelist of image patterns to exclude from admission rules. If an image&#39;s name matches a whitelist pattern, the
image&#39;s admission requests will always be permitted regardless of your admission rules.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">cluster<wbr>Admission<wbr>Rules</td>
            <td class="align-top">
                
                <code><a href="#policyclusteradmissionrule">Policy<wbr>Cluster<wbr>Admission<wbr>Rule[]?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Per-cluster admission rules. An admission rule specifies either that all container images used in a pod creation request
must be attested to by one or more attestors, that all pod creations will be allowed, or that all pod creations will be
denied. There can be at most one admission rule per cluster spec. Identifier format: &#39;{{location}}.{{clusterId}}&#39;. A
location is either a compute zone (e.g. &#39;us-central1-a&#39;) or a region (e.g. &#39;us-central1&#39;).
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">default<wbr>Admission<wbr>Rule</td>
            <td class="align-top">
                
                <code><a href="#policydefaultadmissionrule">Policy<wbr>Default<wbr>Admission<wbr>Rule?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Default admission rule for a cluster without a per-cluster admission rule.
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
A descriptive comment.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">global<wbr>Policy<wbr>Evaluation<wbr>Mode</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Controls the evaluation of a Google-maintained global admission policy for common system-level images. Images not
covered by the global policy will be subject to the project admission policy.
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
            <td class="align-top">admission_<wbr>whitelist_<wbr>patterns</td>
            <td class="align-top">
                
                <code><a href="#policyadmissionwhitelistpattern">List[Policy<wbr>Admission<wbr>Whitelist<wbr>Pattern]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A whitelist of image patterns to exclude from admission rules. If an image&#39;s name matches a whitelist pattern, the
image&#39;s admission requests will always be permitted regardless of your admission rules.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">cluster_<wbr>admission_<wbr>rules</td>
            <td class="align-top">
                
                <code><a href="#policyclusteradmissionrule">List[Policy<wbr>Cluster<wbr>Admission<wbr>Rule]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Per-cluster admission rules. An admission rule specifies either that all container images used in a pod creation request
must be attested to by one or more attestors, that all pod creations will be allowed, or that all pod creations will be
denied. There can be at most one admission rule per cluster spec. Identifier format: &#39;{{location}}.{{clusterId}}&#39;. A
location is either a compute zone (e.g. &#39;us-central1-a&#39;) or a region (e.g. &#39;us-central1&#39;).
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">default_<wbr>admission_<wbr>rule</td>
            <td class="align-top">
                
                <code><a href="#policydefaultadmissionrule">Dict[Policy<wbr>Default<wbr>Admission<wbr>Rule]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Default admission rule for a cluster without a per-cluster admission rule.
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
A descriptive comment.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">global_<wbr>policy_<wbr>evaluation_<wbr>mode</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Controls the evaluation of a Google-maintained global admission policy for common system-level images. Images not
covered by the global policy will be subject to the project admission policy.
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

#### PolicyAdmissionWhitelistPattern
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#PolicyAdmissionWhitelistPattern">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#PolicyAdmissionWhitelistPattern">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/binaryauthorization?tab=doc#PolicyAdmissionWhitelistPatternArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/binaryauthorization?tab=doc#PolicyAdmissionWhitelistPatternOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Binaryauthorization.PolicyAdmissionWhitelistPatternArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Binaryauthorization.PolicyAdmissionWhitelistPattern.html">output</a> API doc for this type.
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
            <td class="align-top">Name<wbr>Pattern</td>
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
            <td class="align-top">Name<wbr>Pattern</td>
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
            <td class="align-top">name<wbr>Pattern</td>
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
            <td class="align-top">name<wbr>Pattern</td>
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





#### PolicyClusterAdmissionRule
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#PolicyClusterAdmissionRule">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#PolicyClusterAdmissionRule">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/binaryauthorization?tab=doc#PolicyClusterAdmissionRuleArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/binaryauthorization?tab=doc#PolicyClusterAdmissionRuleOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Binaryauthorization.PolicyClusterAdmissionRuleArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Binaryauthorization.PolicyClusterAdmissionRule.html">output</a> API doc for this type.
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
            <td class="align-top">Cluster</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Enforcement<wbr>Mode</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Evaluation<wbr>Mode</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Require<wbr>Attestations<wbr>Bies</td>
            <td class="align-top">
                
                <code>List<string>?</code>
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
            <td class="align-top">Cluster</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Enforcement<wbr>Mode</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Evaluation<wbr>Mode</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Require<wbr>Attestations<wbr>Bies</td>
            <td class="align-top">
                
                <code>[]string</code>
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
            <td class="align-top">cluster</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">enforcement<wbr>Mode</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">evaluation<wbr>Mode</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">require<wbr>Attestations<wbr>Bies</td>
            <td class="align-top">
                
                <code>string[]?</code>
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
            <td class="align-top">cluster</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">enforcement<wbr>Mode</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">evaluation<wbr>Mode</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">require<wbr>Attestations<wbr>Bies</td>
            <td class="align-top">
                
                <code>List[str]</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}





#### PolicyDefaultAdmissionRule
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#PolicyDefaultAdmissionRule">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#PolicyDefaultAdmissionRule">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/binaryauthorization?tab=doc#PolicyDefaultAdmissionRuleArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/binaryauthorization?tab=doc#PolicyDefaultAdmissionRuleOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Binaryauthorization.PolicyDefaultAdmissionRuleArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Binaryauthorization.PolicyDefaultAdmissionRule.html">output</a> API doc for this type.
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
            <td class="align-top">Enforcement<wbr>Mode</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Evaluation<wbr>Mode</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Require<wbr>Attestations<wbr>Bies</td>
            <td class="align-top">
                
                <code>List<string>?</code>
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
            <td class="align-top">Enforcement<wbr>Mode</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Evaluation<wbr>Mode</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Require<wbr>Attestations<wbr>Bies</td>
            <td class="align-top">
                
                <code>[]string</code>
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
            <td class="align-top">enforcement<wbr>Mode</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">evaluation<wbr>Mode</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">require<wbr>Attestations<wbr>Bies</td>
            <td class="align-top">
                
                <code>string[]?</code>
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
            <td class="align-top">enforcement<wbr>Mode</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">evaluation<wbr>Mode</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">require<wbr>Attestations<wbr>Bies</td>
            <td class="align-top">
                
                <code>List[str]</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}








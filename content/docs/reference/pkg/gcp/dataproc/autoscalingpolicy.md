
---
title: "AutoscalingPolicy"
block_external_search_index: true
---
<style>
table td p { margin-top: 0; margin-bottom: 0; }
</style>

Describes an autoscaling policy for Dataproc cluster autoscaler.

> This content is derived from https://github.com/terraform-providers/terraform-provider-google/blob/master/website/docs/r/dataproc_autoscaling_policy.html.markdown.



## Create a AutoscalingPolicy Resource

{{< langchoose csharp nojavascript >}}

<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/dataproc/#AutoscalingPolicy">AutoscalingPolicy</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/dataproc/#AutoscalingPolicyArgs">AutoscalingPolicyArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">AutoscalingPolicy</span><span class="p">(resource_name, opts=None, </span>basic_algorithm=None<span class="p">, </span>location=None<span class="p">, </span>policy_id=None<span class="p">, </span>project=None<span class="p">, </span>secondary_worker_config=None<span class="p">, </span>worker_config=None<span class="p">, __props__=None);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewAutoscalingPolicy<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/dataproc?tab=doc#AutoscalingPolicyArgs">AutoscalingPolicyArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/dataproc?tab=doc#AutoscalingPolicy">AutoscalingPolicy</a></span>, error)</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Dataproc.AutoscalingPolicy.html">AutoscalingPolicy</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Dataproc.AutoscalingPolicyArgs.html">AutoscalingPolicyArgs</a></span> <span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>

Creates a AutoscalingPolicy resource with the given unique name, arguments, and options.

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
            <td class="align-top">Basic<wbr>Algorithm</td>
            <td class="align-top">
                
                <code><a href="#autoscalingpolicybasicalgorithm">Autoscaling<wbr>Policy<wbr>Basic<wbr>Algorithm<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Basic algorithm for autoscaling.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Location</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The location where the autoscaling poicy should reside. The default value is &#39;global&#39;.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Policy<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The policy id. The id must contain only letters (a-z, A-Z), numbers (0-9), underscores (_), and hyphens (-). Cannot
begin or end with underscore or hyphen. Must consist of between 3 and 50 characters.
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
If it is not provided, the provider project is used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Secondary<wbr>Worker<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#autoscalingpolicysecondaryworkerconfig">Autoscaling<wbr>Policy<wbr>Secondary<wbr>Worker<wbr>Config<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Describes how the autoscaler will operate for secondary workers.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Worker<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#autoscalingpolicyworkerconfig">Autoscaling<wbr>Policy<wbr>Worker<wbr>Config<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Describes how the autoscaler will operate for primary workers.
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
            <td class="align-top">Basic<wbr>Algorithm</td>
            <td class="align-top">
                
                <code><a href="#autoscalingpolicybasicalgorithm">*Autoscaling<wbr>Policy<wbr>Basic<wbr>Algorithm</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Basic algorithm for autoscaling.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Location</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The location where the autoscaling poicy should reside. The default value is &#39;global&#39;.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Policy<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The policy id. The id must contain only letters (a-z, A-Z), numbers (0-9), underscores (_), and hyphens (-). Cannot
begin or end with underscore or hyphen. Must consist of between 3 and 50 characters.
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
If it is not provided, the provider project is used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Secondary<wbr>Worker<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#autoscalingpolicysecondaryworkerconfig">*Autoscaling<wbr>Policy<wbr>Secondary<wbr>Worker<wbr>Config</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Describes how the autoscaler will operate for secondary workers.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Worker<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#autoscalingpolicyworkerconfig">*Autoscaling<wbr>Policy<wbr>Worker<wbr>Config</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Describes how the autoscaler will operate for primary workers.
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
            <td class="align-top">basic<wbr>Algorithm</td>
            <td class="align-top">
                
                <code><a href="#autoscalingpolicybasicalgorithm">Autoscaling<wbr>Policy<wbr>Basic<wbr>Algorithm?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Basic algorithm for autoscaling.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">location</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The location where the autoscaling poicy should reside. The default value is &#39;global&#39;.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">policy<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The policy id. The id must contain only letters (a-z, A-Z), numbers (0-9), underscores (_), and hyphens (-). Cannot
begin or end with underscore or hyphen. Must consist of between 3 and 50 characters.
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
If it is not provided, the provider project is used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">secondary<wbr>Worker<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#autoscalingpolicysecondaryworkerconfig">Autoscaling<wbr>Policy<wbr>Secondary<wbr>Worker<wbr>Config?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Describes how the autoscaler will operate for secondary workers.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">worker<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#autoscalingpolicyworkerconfig">Autoscaling<wbr>Policy<wbr>Worker<wbr>Config?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Describes how the autoscaler will operate for primary workers.
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
            <td class="align-top">basic_<wbr>algorithm</td>
            <td class="align-top">
                
                <code><a href="#autoscalingpolicybasicalgorithm">Dict[Autoscaling<wbr>Policy<wbr>Basic<wbr>Algorithm]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Basic algorithm for autoscaling.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">location</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The location where the autoscaling poicy should reside. The default value is &#39;global&#39;.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">policy_<wbr>id</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The policy id. The id must contain only letters (a-z, A-Z), numbers (0-9), underscores (_), and hyphens (-). Cannot
begin or end with underscore or hyphen. Must consist of between 3 and 50 characters.
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
If it is not provided, the provider project is used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">secondary_<wbr>worker_<wbr>config</td>
            <td class="align-top">
                
                <code><a href="#autoscalingpolicysecondaryworkerconfig">Dict[Autoscaling<wbr>Policy<wbr>Secondary<wbr>Worker<wbr>Config]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Describes how the autoscaler will operate for secondary workers.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">worker_<wbr>config</td>
            <td class="align-top">
                
                <code><a href="#autoscalingpolicyworkerconfig">Dict[Autoscaling<wbr>Policy<wbr>Worker<wbr>Config]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Describes how the autoscaler will operate for primary workers.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}







## AutoscalingPolicy Output Properties

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
            <td class="align-top">Basic<wbr>Algorithm</td>
            <td class="align-top">
                
                <code><a href="#autoscalingpolicybasicalgorithm">Autoscaling<wbr>Policy<wbr>Basic<wbr>Algorithm?</a></code>
            </td>
            <td class="align-top">{{% md %}} Basic algorithm for autoscaling.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Location</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} The location where the autoscaling poicy should reside. The default value is &#39;global&#39;.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The &#34;resource name&#34; of the autoscaling policy.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Policy<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The policy id. The id must contain only letters (a-z, A-Z), numbers (0-9), underscores (_), and hyphens (-). Cannot
begin or end with underscore or hyphen. Must consist of between 3 and 50 characters.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Project</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The ID of the project in which the resource belongs.
If it is not provided, the provider project is used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Secondary<wbr>Worker<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#autoscalingpolicysecondaryworkerconfig">Autoscaling<wbr>Policy<wbr>Secondary<wbr>Worker<wbr>Config?</a></code>
            </td>
            <td class="align-top">{{% md %}} Describes how the autoscaler will operate for secondary workers.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Worker<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#autoscalingpolicyworkerconfig">Autoscaling<wbr>Policy<wbr>Worker<wbr>Config?</a></code>
            </td>
            <td class="align-top">{{% md %}} Describes how the autoscaler will operate for primary workers.
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
            <td class="align-top">Basic<wbr>Algorithm</td>
            <td class="align-top">
                
                <code><a href="#autoscalingpolicybasicalgorithm">*Autoscaling<wbr>Policy<wbr>Basic<wbr>Algorithm</a></code>
            </td>
            <td class="align-top">{{% md %}} Basic algorithm for autoscaling.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Location</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} The location where the autoscaling poicy should reside. The default value is &#39;global&#39;.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The &#34;resource name&#34; of the autoscaling policy.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Policy<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The policy id. The id must contain only letters (a-z, A-Z), numbers (0-9), underscores (_), and hyphens (-). Cannot
begin or end with underscore or hyphen. Must consist of between 3 and 50 characters.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Project</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The ID of the project in which the resource belongs.
If it is not provided, the provider project is used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Secondary<wbr>Worker<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#autoscalingpolicysecondaryworkerconfig">*Autoscaling<wbr>Policy<wbr>Secondary<wbr>Worker<wbr>Config</a></code>
            </td>
            <td class="align-top">{{% md %}} Describes how the autoscaler will operate for secondary workers.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Worker<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#autoscalingpolicyworkerconfig">*Autoscaling<wbr>Policy<wbr>Worker<wbr>Config</a></code>
            </td>
            <td class="align-top">{{% md %}} Describes how the autoscaler will operate for primary workers.
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
            <td class="align-top">basic<wbr>Algorithm</td>
            <td class="align-top">
                
                <code><a href="#autoscalingpolicybasicalgorithm">Autoscaling<wbr>Policy<wbr>Basic<wbr>Algorithm?</a></code>
            </td>
            <td class="align-top">{{% md %}} Basic algorithm for autoscaling.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">location</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} The location where the autoscaling poicy should reside. The default value is &#39;global&#39;.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The &#34;resource name&#34; of the autoscaling policy.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">policy<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The policy id. The id must contain only letters (a-z, A-Z), numbers (0-9), underscores (_), and hyphens (-). Cannot
begin or end with underscore or hyphen. Must consist of between 3 and 50 characters.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">project</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The ID of the project in which the resource belongs.
If it is not provided, the provider project is used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">secondary<wbr>Worker<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#autoscalingpolicysecondaryworkerconfig">Autoscaling<wbr>Policy<wbr>Secondary<wbr>Worker<wbr>Config?</a></code>
            </td>
            <td class="align-top">{{% md %}} Describes how the autoscaler will operate for secondary workers.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">worker<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#autoscalingpolicyworkerconfig">Autoscaling<wbr>Policy<wbr>Worker<wbr>Config?</a></code>
            </td>
            <td class="align-top">{{% md %}} Describes how the autoscaler will operate for primary workers.
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
            <td class="align-top">basic_<wbr>algorithm</td>
            <td class="align-top">
                
                <code><a href="#autoscalingpolicybasicalgorithm">Dict[Autoscaling<wbr>Policy<wbr>Basic<wbr>Algorithm]</a></code>
            </td>
            <td class="align-top">{{% md %}} Basic algorithm for autoscaling.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">location</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The location where the autoscaling poicy should reside. The default value is &#39;global&#39;.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">name</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The &#34;resource name&#34; of the autoscaling policy.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">policy_<wbr>id</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The policy id. The id must contain only letters (a-z, A-Z), numbers (0-9), underscores (_), and hyphens (-). Cannot
begin or end with underscore or hyphen. Must consist of between 3 and 50 characters.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">project</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The ID of the project in which the resource belongs.
If it is not provided, the provider project is used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">secondary_<wbr>worker_<wbr>config</td>
            <td class="align-top">
                
                <code><a href="#autoscalingpolicysecondaryworkerconfig">Dict[Autoscaling<wbr>Policy<wbr>Secondary<wbr>Worker<wbr>Config]</a></code>
            </td>
            <td class="align-top">{{% md %}} Describes how the autoscaler will operate for secondary workers.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">worker_<wbr>config</td>
            <td class="align-top">
                
                <code><a href="#autoscalingpolicyworkerconfig">Dict[Autoscaling<wbr>Policy<wbr>Worker<wbr>Config]</a></code>
            </td>
            <td class="align-top">{{% md %}} Describes how the autoscaler will operate for primary workers.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}








## Look up an Existing AutoscalingPolicy Resource

{{< langchoose csharp nojavascript >}}

<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">pulumi.Input&lt;pulumi.ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/dataproc/#AutoscalingPolicyState">AutoscalingPolicyState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/dataproc/#AutoscalingPolicy">AutoscalingPolicy</a></span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>basic_algorithm=None<span class="p">, </span>location=None<span class="p">, </span>name=None<span class="p">, </span>policy_id=None<span class="p">, </span>project=None<span class="p">, </span>secondary_worker_config=None<span class="p">, </span>worker_config=None<span class="p">, __props__=None);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetAutoscalingPolicy<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">pulumi.IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/dataproc?tab=doc#AutoscalingPolicyState">AutoscalingPolicyState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/dataproc?tab=doc#AutoscalingPolicy">AutoscalingPolicy</a></span>, error)</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Dataproc.AutoscalingPolicy.html">AutoscalingPolicy</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Pulumi.Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Dataproc.AutoscalingPolicyState.html">AutoscalingPolicyState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>

Get an existing AutoscalingPolicy resource's state with the given name, ID, and optional extra properties used to qualify the lookup.

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
            <td class="align-top">Basic<wbr>Algorithm</td>
            <td class="align-top">
                
                <code><a href="#autoscalingpolicybasicalgorithm">Autoscaling<wbr>Policy<wbr>Basic<wbr>Algorithm<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Basic algorithm for autoscaling.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Location</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The location where the autoscaling poicy should reside. The default value is &#39;global&#39;.
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
The &#34;resource name&#34; of the autoscaling policy.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Policy<wbr>Id</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The policy id. The id must contain only letters (a-z, A-Z), numbers (0-9), underscores (_), and hyphens (-). Cannot
begin or end with underscore or hyphen. Must consist of between 3 and 50 characters.
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
If it is not provided, the provider project is used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Secondary<wbr>Worker<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#autoscalingpolicysecondaryworkerconfig">Autoscaling<wbr>Policy<wbr>Secondary<wbr>Worker<wbr>Config<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Describes how the autoscaler will operate for secondary workers.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Worker<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#autoscalingpolicyworkerconfig">Autoscaling<wbr>Policy<wbr>Worker<wbr>Config<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Describes how the autoscaler will operate for primary workers.
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
            <td class="align-top">Basic<wbr>Algorithm</td>
            <td class="align-top">
                
                <code><a href="#autoscalingpolicybasicalgorithm">*Autoscaling<wbr>Policy<wbr>Basic<wbr>Algorithm</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Basic algorithm for autoscaling.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Location</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The location where the autoscaling poicy should reside. The default value is &#39;global&#39;.
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
The &#34;resource name&#34; of the autoscaling policy.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Policy<wbr>Id</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The policy id. The id must contain only letters (a-z, A-Z), numbers (0-9), underscores (_), and hyphens (-). Cannot
begin or end with underscore or hyphen. Must consist of between 3 and 50 characters.
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
If it is not provided, the provider project is used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Secondary<wbr>Worker<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#autoscalingpolicysecondaryworkerconfig">*Autoscaling<wbr>Policy<wbr>Secondary<wbr>Worker<wbr>Config</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Describes how the autoscaler will operate for secondary workers.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Worker<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#autoscalingpolicyworkerconfig">*Autoscaling<wbr>Policy<wbr>Worker<wbr>Config</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Describes how the autoscaler will operate for primary workers.
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
            <td class="align-top">basic<wbr>Algorithm</td>
            <td class="align-top">
                
                <code><a href="#autoscalingpolicybasicalgorithm">Autoscaling<wbr>Policy<wbr>Basic<wbr>Algorithm?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Basic algorithm for autoscaling.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">location</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The location where the autoscaling poicy should reside. The default value is &#39;global&#39;.
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
The &#34;resource name&#34; of the autoscaling policy.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">policy<wbr>Id</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The policy id. The id must contain only letters (a-z, A-Z), numbers (0-9), underscores (_), and hyphens (-). Cannot
begin or end with underscore or hyphen. Must consist of between 3 and 50 characters.
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
If it is not provided, the provider project is used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">secondary<wbr>Worker<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#autoscalingpolicysecondaryworkerconfig">Autoscaling<wbr>Policy<wbr>Secondary<wbr>Worker<wbr>Config?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Describes how the autoscaler will operate for secondary workers.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">worker<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#autoscalingpolicyworkerconfig">Autoscaling<wbr>Policy<wbr>Worker<wbr>Config?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Describes how the autoscaler will operate for primary workers.
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
            <td class="align-top">basic_<wbr>algorithm</td>
            <td class="align-top">
                
                <code><a href="#autoscalingpolicybasicalgorithm">Dict[Autoscaling<wbr>Policy<wbr>Basic<wbr>Algorithm]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Basic algorithm for autoscaling.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">location</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The location where the autoscaling poicy should reside. The default value is &#39;global&#39;.
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
The &#34;resource name&#34; of the autoscaling policy.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">policy_<wbr>id</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The policy id. The id must contain only letters (a-z, A-Z), numbers (0-9), underscores (_), and hyphens (-). Cannot
begin or end with underscore or hyphen. Must consist of between 3 and 50 characters.
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
If it is not provided, the provider project is used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">secondary_<wbr>worker_<wbr>config</td>
            <td class="align-top">
                
                <code><a href="#autoscalingpolicysecondaryworkerconfig">Dict[Autoscaling<wbr>Policy<wbr>Secondary<wbr>Worker<wbr>Config]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Describes how the autoscaler will operate for secondary workers.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">worker_<wbr>config</td>
            <td class="align-top">
                
                <code><a href="#autoscalingpolicyworkerconfig">Dict[Autoscaling<wbr>Policy<wbr>Worker<wbr>Config]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Describes how the autoscaler will operate for primary workers.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}










## Supporting Types

#### AutoscalingPolicyBasicAlgorithm
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#AutoscalingPolicyBasicAlgorithm">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#AutoscalingPolicyBasicAlgorithm">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/dataproc?tab=doc#AutoscalingPolicyBasicAlgorithmArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/dataproc?tab=doc#AutoscalingPolicyBasicAlgorithmOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Dataproc.AutoscalingPolicyBasicAlgorithmArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Dataproc.AutoscalingPolicyBasicAlgorithm.html">output</a> API doc for this type.
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
            <td class="align-top">Cooldown<wbr>Period</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Yarn<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#autoscalingpolicybasicalgorithmyarnconfig">Autoscaling<wbr>Policy<wbr>Basic<wbr>Algorithm<wbr>Yarn<wbr>Config<wbr>Args</a></code>
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
            <td class="align-top">Cooldown<wbr>Period</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Yarn<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#autoscalingpolicybasicalgorithmyarnconfig">Autoscaling<wbr>Policy<wbr>Basic<wbr>Algorithm<wbr>Yarn<wbr>Config</a></code>
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
            <td class="align-top">cooldown<wbr>Period</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">yarn<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#autoscalingpolicybasicalgorithmyarnconfig">Autoscaling<wbr>Policy<wbr>Basic<wbr>Algorithm<wbr>Yarn<wbr>Config</a></code>
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
            <td class="align-top">cooldown<wbr>Period</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">yarn<wbr>Config</td>
            <td class="align-top">
                
                <code><a href="#autoscalingpolicybasicalgorithmyarnconfig">Dict[Autoscaling<wbr>Policy<wbr>Basic<wbr>Algorithm<wbr>Yarn<wbr>Config]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}





#### AutoscalingPolicyBasicAlgorithmYarnConfig
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#AutoscalingPolicyBasicAlgorithmYarnConfig">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#AutoscalingPolicyBasicAlgorithmYarnConfig">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/dataproc?tab=doc#AutoscalingPolicyBasicAlgorithmYarnConfigArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/dataproc?tab=doc#AutoscalingPolicyBasicAlgorithmYarnConfigOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Dataproc.AutoscalingPolicyBasicAlgorithmYarnConfigArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Dataproc.AutoscalingPolicyBasicAlgorithmYarnConfig.html">output</a> API doc for this type.
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
            <td class="align-top">Graceful<wbr>Decommission<wbr>Timeout</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Scale<wbr>Down<wbr>Factor</td>
            <td class="align-top">
                
                <code>double</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Scale<wbr>Down<wbr>Min<wbr>Worker<wbr>Fraction</td>
            <td class="align-top">
                
                <code>double?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Scale<wbr>Up<wbr>Factor</td>
            <td class="align-top">
                
                <code>double</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Scale<wbr>Up<wbr>Min<wbr>Worker<wbr>Fraction</td>
            <td class="align-top">
                
                <code>double?</code>
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
            <td class="align-top">Graceful<wbr>Decommission<wbr>Timeout</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Scale<wbr>Down<wbr>Factor</td>
            <td class="align-top">
                
                <code>float64</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Scale<wbr>Down<wbr>Min<wbr>Worker<wbr>Fraction</td>
            <td class="align-top">
                
                <code>*float64</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Scale<wbr>Up<wbr>Factor</td>
            <td class="align-top">
                
                <code>float64</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Scale<wbr>Up<wbr>Min<wbr>Worker<wbr>Fraction</td>
            <td class="align-top">
                
                <code>*float64</code>
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
            <td class="align-top">graceful<wbr>Decommission<wbr>Timeout</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">scale<wbr>Down<wbr>Factor</td>
            <td class="align-top">
                
                <code>number</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">scale<wbr>Down<wbr>Min<wbr>Worker<wbr>Fraction</td>
            <td class="align-top">
                
                <code>number?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">scale<wbr>Up<wbr>Factor</td>
            <td class="align-top">
                
                <code>number</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">scale<wbr>Up<wbr>Min<wbr>Worker<wbr>Fraction</td>
            <td class="align-top">
                
                <code>number?</code>
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
            <td class="align-top">graceful<wbr>Decommission<wbr>Timeout</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">scale<wbr>Down<wbr>Factor</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">scale<wbr>Down<wbr>Min<wbr>Worker<wbr>Fraction</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">scale<wbr>Up<wbr>Factor</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">scale<wbr>Up<wbr>Min<wbr>Worker<wbr>Fraction</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}





#### AutoscalingPolicySecondaryWorkerConfig
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#AutoscalingPolicySecondaryWorkerConfig">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#AutoscalingPolicySecondaryWorkerConfig">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/dataproc?tab=doc#AutoscalingPolicySecondaryWorkerConfigArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/dataproc?tab=doc#AutoscalingPolicySecondaryWorkerConfigOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Dataproc.AutoscalingPolicySecondaryWorkerConfigArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Dataproc.AutoscalingPolicySecondaryWorkerConfig.html">output</a> API doc for this type.
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
            <td class="align-top">Max<wbr>Instances</td>
            <td class="align-top">
                
                <code>int?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Min<wbr>Instances</td>
            <td class="align-top">
                
                <code>int?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Weight</td>
            <td class="align-top">
                
                <code>int?</code>
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
            <td class="align-top">Max<wbr>Instances</td>
            <td class="align-top">
                
                <code>*int</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Min<wbr>Instances</td>
            <td class="align-top">
                
                <code>*int</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Weight</td>
            <td class="align-top">
                
                <code>*int</code>
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
            <td class="align-top">max<wbr>Instances</td>
            <td class="align-top">
                
                <code>number?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">min<wbr>Instances</td>
            <td class="align-top">
                
                <code>number?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">weight</td>
            <td class="align-top">
                
                <code>number?</code>
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
            <td class="align-top">max_<wbr>instances</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">min<wbr>Instances</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">weight</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}





#### AutoscalingPolicyWorkerConfig
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#AutoscalingPolicyWorkerConfig">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#AutoscalingPolicyWorkerConfig">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/dataproc?tab=doc#AutoscalingPolicyWorkerConfigArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/dataproc?tab=doc#AutoscalingPolicyWorkerConfigOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Dataproc.AutoscalingPolicyWorkerConfigArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Dataproc.AutoscalingPolicyWorkerConfig.html">output</a> API doc for this type.
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
            <td class="align-top">Max<wbr>Instances</td>
            <td class="align-top">
                
                <code>int</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Min<wbr>Instances</td>
            <td class="align-top">
                
                <code>int?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Weight</td>
            <td class="align-top">
                
                <code>int?</code>
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
            <td class="align-top">Max<wbr>Instances</td>
            <td class="align-top">
                
                <code>int</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Min<wbr>Instances</td>
            <td class="align-top">
                
                <code>*int</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Weight</td>
            <td class="align-top">
                
                <code>*int</code>
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
            <td class="align-top">max<wbr>Instances</td>
            <td class="align-top">
                
                <code>number</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">min<wbr>Instances</td>
            <td class="align-top">
                
                <code>number?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">weight</td>
            <td class="align-top">
                
                <code>number?</code>
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
            <td class="align-top">max_<wbr>instances</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">min<wbr>Instances</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">weight</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}









---
title: "Deployment"
block_external_search_index: true
---
<style>
table td p { margin-top: 0; margin-bottom: 0; }
</style>




## Create a Deployment Resource

{{< langchoose csharp nojavascript >}}

<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/deploymentmanager/#Deployment">Deployment</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/deploymentmanager/#DeploymentArgs">DeploymentArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">Deployment</span><span class="p">(resource_name, opts=None, </span>create_policy=None<span class="p">, </span>delete_policy=None<span class="p">, </span>description=None<span class="p">, </span>labels=None<span class="p">, </span>name=None<span class="p">, </span>preview=None<span class="p">, </span>project=None<span class="p">, </span>target=None<span class="p">, __props__=None);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewDeployment<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/deploymentmanager?tab=doc#DeploymentArgs">DeploymentArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/deploymentmanager?tab=doc#Deployment">Deployment</a></span>, error)</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Deploymentmanager.Deployment.html">Deployment</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Deploymentmanager.DeploymentArgs.html">DeploymentArgs</a></span> <span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>

Creates a Deployment resource with the given unique name, arguments, and options.

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
            <td class="align-top">Create<wbr>Policy</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Set the policy to use for creating new resources. Only used on create and update. Valid values are &#39;CREATE_OR_ACQUIRE&#39;
(default) or &#39;ACQUIRE&#39;. If set to &#39;ACQUIRE&#39; and resources do not already exist, the deployment will fail. Note that
updating this field does not actually affect the deployment, just how it is updated.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Delete<wbr>Policy</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Set the policy to use for deleting new resources on update/delete. Valid values are &#39;DELETE&#39; (default) or &#39;ABANDON&#39;. If
&#39;DELETE&#39;, resource is deleted after removal from Deployment Manager. If &#39;ABANDON&#39;, the resource is only removed from
Deployment Manager and is not actually deleted. Note that updating this field does not actually change the deployment,
just how it is updated.
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
Optional user-provided description of deployment.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Labels</td>
            <td class="align-top">
                
                <code><a href="#deploymentlabel">List&lt;Deployment<wbr>Label<wbr>Args&gt;?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Key-value pairs to apply to this labels.
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
Unique name for the deployment
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Preview</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
If set to true, a deployment is created with &#34;shell&#34; resources that are not actually instantiated. This allows you to
preview a deployment. It can be updated to false to actually deploy with real resources. ~&gt;**NOTE**: Deployment Manager
does not allow update of a deployment in preview (unless updating to preview=false). Thus, Terraform will force-recreate
deployments if either preview is updated to true or if other fields are updated while preview is true.
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
    
        <tr>
            <td class="align-top">Target</td>
            <td class="align-top">
                
                <code><a href="#deploymenttarget">Deployment<wbr>Target<wbr>Args</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Parameters that define your deployment, including the deployment configuration and relevant templates.
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
            <td class="align-top">Create<wbr>Policy</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Set the policy to use for creating new resources. Only used on create and update. Valid values are &#39;CREATE_OR_ACQUIRE&#39;
(default) or &#39;ACQUIRE&#39;. If set to &#39;ACQUIRE&#39; and resources do not already exist, the deployment will fail. Note that
updating this field does not actually affect the deployment, just how it is updated.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Delete<wbr>Policy</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Set the policy to use for deleting new resources on update/delete. Valid values are &#39;DELETE&#39; (default) or &#39;ABANDON&#39;. If
&#39;DELETE&#39;, resource is deleted after removal from Deployment Manager. If &#39;ABANDON&#39;, the resource is only removed from
Deployment Manager and is not actually deleted. Note that updating this field does not actually change the deployment,
just how it is updated.
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
Optional user-provided description of deployment.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Labels</td>
            <td class="align-top">
                
                <code><a href="#deploymentlabel">[]Deployment<wbr>Label</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Key-value pairs to apply to this labels.
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
Unique name for the deployment
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Preview</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
If set to true, a deployment is created with &#34;shell&#34; resources that are not actually instantiated. This allows you to
preview a deployment. It can be updated to false to actually deploy with real resources. ~&gt;**NOTE**: Deployment Manager
does not allow update of a deployment in preview (unless updating to preview=false). Thus, Terraform will force-recreate
deployments if either preview is updated to true or if other fields are updated while preview is true.
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
    
        <tr>
            <td class="align-top">Target</td>
            <td class="align-top">
                
                <code><a href="#deploymenttarget">Deployment<wbr>Target</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Parameters that define your deployment, including the deployment configuration and relevant templates.
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
            <td class="align-top">create<wbr>Policy</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Set the policy to use for creating new resources. Only used on create and update. Valid values are &#39;CREATE_OR_ACQUIRE&#39;
(default) or &#39;ACQUIRE&#39;. If set to &#39;ACQUIRE&#39; and resources do not already exist, the deployment will fail. Note that
updating this field does not actually affect the deployment, just how it is updated.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">delete<wbr>Policy</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Set the policy to use for deleting new resources on update/delete. Valid values are &#39;DELETE&#39; (default) or &#39;ABANDON&#39;. If
&#39;DELETE&#39;, resource is deleted after removal from Deployment Manager. If &#39;ABANDON&#39;, the resource is only removed from
Deployment Manager and is not actually deleted. Note that updating this field does not actually change the deployment,
just how it is updated.
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
Optional user-provided description of deployment.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">labels</td>
            <td class="align-top">
                
                <code><a href="#deploymentlabel">Deployment<wbr>Label[]?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Key-value pairs to apply to this labels.
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
Unique name for the deployment
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">preview</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
If set to true, a deployment is created with &#34;shell&#34; resources that are not actually instantiated. This allows you to
preview a deployment. It can be updated to false to actually deploy with real resources. ~&gt;**NOTE**: Deployment Manager
does not allow update of a deployment in preview (unless updating to preview=false). Thus, Terraform will force-recreate
deployments if either preview is updated to true or if other fields are updated while preview is true.
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
    
        <tr>
            <td class="align-top">target</td>
            <td class="align-top">
                
                <code><a href="#deploymenttarget">Deployment<wbr>Target</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Parameters that define your deployment, including the deployment configuration and relevant templates.
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
            <td class="align-top">create_<wbr>policy</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Set the policy to use for creating new resources. Only used on create and update. Valid values are &#39;CREATE_OR_ACQUIRE&#39;
(default) or &#39;ACQUIRE&#39;. If set to &#39;ACQUIRE&#39; and resources do not already exist, the deployment will fail. Note that
updating this field does not actually affect the deployment, just how it is updated.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">delete_<wbr>policy</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Set the policy to use for deleting new resources on update/delete. Valid values are &#39;DELETE&#39; (default) or &#39;ABANDON&#39;. If
&#39;DELETE&#39;, resource is deleted after removal from Deployment Manager. If &#39;ABANDON&#39;, the resource is only removed from
Deployment Manager and is not actually deleted. Note that updating this field does not actually change the deployment,
just how it is updated.
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
Optional user-provided description of deployment.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">labels</td>
            <td class="align-top">
                
                <code><a href="#deploymentlabel">List[Deployment<wbr>Label]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Key-value pairs to apply to this labels.
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
Unique name for the deployment
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">preview</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
If set to true, a deployment is created with &#34;shell&#34; resources that are not actually instantiated. This allows you to
preview a deployment. It can be updated to false to actually deploy with real resources. ~&gt;**NOTE**: Deployment Manager
does not allow update of a deployment in preview (unless updating to preview=false). Thus, Terraform will force-recreate
deployments if either preview is updated to true or if other fields are updated while preview is true.
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
    
        <tr>
            <td class="align-top">target</td>
            <td class="align-top">
                
                <code><a href="#deploymenttarget">Dict[Deployment<wbr>Target]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Parameters that define your deployment, including the deployment configuration and relevant templates.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}







## Deployment Output Properties

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
            <td class="align-top">Create<wbr>Policy</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} Set the policy to use for creating new resources. Only used on create and update. Valid values are &#39;CREATE_OR_ACQUIRE&#39;
(default) or &#39;ACQUIRE&#39;. If set to &#39;ACQUIRE&#39; and resources do not already exist, the deployment will fail. Note that
updating this field does not actually affect the deployment, just how it is updated.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Delete<wbr>Policy</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} Set the policy to use for deleting new resources on update/delete. Valid values are &#39;DELETE&#39; (default) or &#39;ABANDON&#39;. If
&#39;DELETE&#39;, resource is deleted after removal from Deployment Manager. If &#39;ABANDON&#39;, the resource is only removed from
Deployment Manager and is not actually deleted. Note that updating this field does not actually change the deployment,
just how it is updated.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Deployment<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Unique identifier for deployment. Output only.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Description</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} Optional user-provided description of deployment.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Labels</td>
            <td class="align-top">
                
                <code><a href="#deploymentlabel">List&lt;Deployment<wbr>Label&gt;?</a></code>
            </td>
            <td class="align-top">{{% md %}} Key-value pairs to apply to this labels.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Manifest</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Output only. URL of the manifest representing the last manifest that was successfully deployed.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Unique name for the deployment
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Preview</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} If set to true, a deployment is created with &#34;shell&#34; resources that are not actually instantiated. This allows you to
preview a deployment. It can be updated to false to actually deploy with real resources. ~&gt;**NOTE**: Deployment Manager
does not allow update of a deployment in preview (unless updating to preview=false). Thus, Terraform will force-recreate
deployments if either preview is updated to true or if other fields are updated while preview is true.
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
    
        <tr>
            <td class="align-top">Self<wbr>Link</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Output only. Server defined URL for the resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Target</td>
            <td class="align-top">
                
                <code><a href="#deploymenttarget">Deployment<wbr>Target</a></code>
            </td>
            <td class="align-top">{{% md %}} Parameters that define your deployment, including the deployment configuration and relevant templates.
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
            <td class="align-top">Create<wbr>Policy</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} Set the policy to use for creating new resources. Only used on create and update. Valid values are &#39;CREATE_OR_ACQUIRE&#39;
(default) or &#39;ACQUIRE&#39;. If set to &#39;ACQUIRE&#39; and resources do not already exist, the deployment will fail. Note that
updating this field does not actually affect the deployment, just how it is updated.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Delete<wbr>Policy</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} Set the policy to use for deleting new resources on update/delete. Valid values are &#39;DELETE&#39; (default) or &#39;ABANDON&#39;. If
&#39;DELETE&#39;, resource is deleted after removal from Deployment Manager. If &#39;ABANDON&#39;, the resource is only removed from
Deployment Manager and is not actually deleted. Note that updating this field does not actually change the deployment,
just how it is updated.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Deployment<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Unique identifier for deployment. Output only.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Description</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} Optional user-provided description of deployment.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Labels</td>
            <td class="align-top">
                
                <code><a href="#deploymentlabel">[]Deployment<wbr>Label</a></code>
            </td>
            <td class="align-top">{{% md %}} Key-value pairs to apply to this labels.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Manifest</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Output only. URL of the manifest representing the last manifest that was successfully deployed.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Unique name for the deployment
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Preview</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} If set to true, a deployment is created with &#34;shell&#34; resources that are not actually instantiated. This allows you to
preview a deployment. It can be updated to false to actually deploy with real resources. ~&gt;**NOTE**: Deployment Manager
does not allow update of a deployment in preview (unless updating to preview=false). Thus, Terraform will force-recreate
deployments if either preview is updated to true or if other fields are updated while preview is true.
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
    
        <tr>
            <td class="align-top">Self<wbr>Link</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Output only. Server defined URL for the resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Target</td>
            <td class="align-top">
                
                <code><a href="#deploymenttarget">Deployment<wbr>Target</a></code>
            </td>
            <td class="align-top">{{% md %}} Parameters that define your deployment, including the deployment configuration and relevant templates.
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
            <td class="align-top">create<wbr>Policy</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} Set the policy to use for creating new resources. Only used on create and update. Valid values are &#39;CREATE_OR_ACQUIRE&#39;
(default) or &#39;ACQUIRE&#39;. If set to &#39;ACQUIRE&#39; and resources do not already exist, the deployment will fail. Note that
updating this field does not actually affect the deployment, just how it is updated.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">delete<wbr>Policy</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} Set the policy to use for deleting new resources on update/delete. Valid values are &#39;DELETE&#39; (default) or &#39;ABANDON&#39;. If
&#39;DELETE&#39;, resource is deleted after removal from Deployment Manager. If &#39;ABANDON&#39;, the resource is only removed from
Deployment Manager and is not actually deleted. Note that updating this field does not actually change the deployment,
just how it is updated.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">deployment<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Unique identifier for deployment. Output only.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">description</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} Optional user-provided description of deployment.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">labels</td>
            <td class="align-top">
                
                <code><a href="#deploymentlabel">Deployment<wbr>Label[]?</a></code>
            </td>
            <td class="align-top">{{% md %}} Key-value pairs to apply to this labels.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">manifest</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Output only. URL of the manifest representing the last manifest that was successfully deployed.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Unique name for the deployment
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">preview</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} If set to true, a deployment is created with &#34;shell&#34; resources that are not actually instantiated. This allows you to
preview a deployment. It can be updated to false to actually deploy with real resources. ~&gt;**NOTE**: Deployment Manager
does not allow update of a deployment in preview (unless updating to preview=false). Thus, Terraform will force-recreate
deployments if either preview is updated to true or if other fields are updated while preview is true.
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
    
        <tr>
            <td class="align-top">self<wbr>Link</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Output only. Server defined URL for the resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">target</td>
            <td class="align-top">
                
                <code><a href="#deploymenttarget">Deployment<wbr>Target</a></code>
            </td>
            <td class="align-top">{{% md %}} Parameters that define your deployment, including the deployment configuration and relevant templates.
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
            <td class="align-top">create_<wbr>policy</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} Set the policy to use for creating new resources. Only used on create and update. Valid values are &#39;CREATE_OR_ACQUIRE&#39;
(default) or &#39;ACQUIRE&#39;. If set to &#39;ACQUIRE&#39; and resources do not already exist, the deployment will fail. Note that
updating this field does not actually affect the deployment, just how it is updated.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">delete_<wbr>policy</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} Set the policy to use for deleting new resources on update/delete. Valid values are &#39;DELETE&#39; (default) or &#39;ABANDON&#39;. If
&#39;DELETE&#39;, resource is deleted after removal from Deployment Manager. If &#39;ABANDON&#39;, the resource is only removed from
Deployment Manager and is not actually deleted. Note that updating this field does not actually change the deployment,
just how it is updated.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">deployment_<wbr>id</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} Unique identifier for deployment. Output only.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">description</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} Optional user-provided description of deployment.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">labels</td>
            <td class="align-top">
                
                <code><a href="#deploymentlabel">List[Deployment<wbr>Label]</a></code>
            </td>
            <td class="align-top">{{% md %}} Key-value pairs to apply to this labels.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">manifest</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} Output only. URL of the manifest representing the last manifest that was successfully deployed.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">name</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} Unique name for the deployment
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">preview</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} If set to true, a deployment is created with &#34;shell&#34; resources that are not actually instantiated. This allows you to
preview a deployment. It can be updated to false to actually deploy with real resources. ~&gt;**NOTE**: Deployment Manager
does not allow update of a deployment in preview (unless updating to preview=false). Thus, Terraform will force-recreate
deployments if either preview is updated to true or if other fields are updated while preview is true.
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
    
        <tr>
            <td class="align-top">self_<wbr>link</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} Output only. Server defined URL for the resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">target</td>
            <td class="align-top">
                
                <code><a href="#deploymenttarget">Dict[Deployment<wbr>Target]</a></code>
            </td>
            <td class="align-top">{{% md %}} Parameters that define your deployment, including the deployment configuration and relevant templates.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}








## Look up an Existing Deployment Resource

{{< langchoose csharp nojavascript >}}

<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">pulumi.Input&lt;pulumi.ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/deploymentmanager/#DeploymentState">DeploymentState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/deploymentmanager/#Deployment">Deployment</a></span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>create_policy=None<span class="p">, </span>delete_policy=None<span class="p">, </span>deployment_id=None<span class="p">, </span>description=None<span class="p">, </span>labels=None<span class="p">, </span>manifest=None<span class="p">, </span>name=None<span class="p">, </span>preview=None<span class="p">, </span>project=None<span class="p">, </span>self_link=None<span class="p">, </span>target=None<span class="p">, __props__=None);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetDeployment<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">pulumi.IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/deploymentmanager?tab=doc#DeploymentState">DeploymentState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/deploymentmanager?tab=doc#Deployment">Deployment</a></span>, error)</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Deploymentmanager.Deployment.html">Deployment</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Pulumi.Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Deploymentmanager.DeploymentState.html">DeploymentState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>

Get an existing Deployment resource's state with the given name, ID, and optional extra properties used to qualify the lookup.

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
            <td class="align-top">Create<wbr>Policy</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Set the policy to use for creating new resources. Only used on create and update. Valid values are &#39;CREATE_OR_ACQUIRE&#39;
(default) or &#39;ACQUIRE&#39;. If set to &#39;ACQUIRE&#39; and resources do not already exist, the deployment will fail. Note that
updating this field does not actually affect the deployment, just how it is updated.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Delete<wbr>Policy</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Set the policy to use for deleting new resources on update/delete. Valid values are &#39;DELETE&#39; (default) or &#39;ABANDON&#39;. If
&#39;DELETE&#39;, resource is deleted after removal from Deployment Manager. If &#39;ABANDON&#39;, the resource is only removed from
Deployment Manager and is not actually deleted. Note that updating this field does not actually change the deployment,
just how it is updated.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Deployment<wbr>Id</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Unique identifier for deployment. Output only.
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
Optional user-provided description of deployment.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Labels</td>
            <td class="align-top">
                
                <code><a href="#deploymentlabel">List&lt;Deployment<wbr>Label<wbr>Args&gt;?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Key-value pairs to apply to this labels.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Manifest</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Output only. URL of the manifest representing the last manifest that was successfully deployed.
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
Unique name for the deployment
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Preview</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
If set to true, a deployment is created with &#34;shell&#34; resources that are not actually instantiated. This allows you to
preview a deployment. It can be updated to false to actually deploy with real resources. ~&gt;**NOTE**: Deployment Manager
does not allow update of a deployment in preview (unless updating to preview=false). Thus, Terraform will force-recreate
deployments if either preview is updated to true or if other fields are updated while preview is true.
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
    
        <tr>
            <td class="align-top">Self<wbr>Link</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Output only. Server defined URL for the resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Target</td>
            <td class="align-top">
                
                <code><a href="#deploymenttarget">Deployment<wbr>Target<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Parameters that define your deployment, including the deployment configuration and relevant templates.
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
            <td class="align-top">Create<wbr>Policy</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Set the policy to use for creating new resources. Only used on create and update. Valid values are &#39;CREATE_OR_ACQUIRE&#39;
(default) or &#39;ACQUIRE&#39;. If set to &#39;ACQUIRE&#39; and resources do not already exist, the deployment will fail. Note that
updating this field does not actually affect the deployment, just how it is updated.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Delete<wbr>Policy</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Set the policy to use for deleting new resources on update/delete. Valid values are &#39;DELETE&#39; (default) or &#39;ABANDON&#39;. If
&#39;DELETE&#39;, resource is deleted after removal from Deployment Manager. If &#39;ABANDON&#39;, the resource is only removed from
Deployment Manager and is not actually deleted. Note that updating this field does not actually change the deployment,
just how it is updated.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Deployment<wbr>Id</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Unique identifier for deployment. Output only.
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
Optional user-provided description of deployment.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Labels</td>
            <td class="align-top">
                
                <code><a href="#deploymentlabel">[]Deployment<wbr>Label</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Key-value pairs to apply to this labels.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Manifest</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Output only. URL of the manifest representing the last manifest that was successfully deployed.
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
Unique name for the deployment
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Preview</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
If set to true, a deployment is created with &#34;shell&#34; resources that are not actually instantiated. This allows you to
preview a deployment. It can be updated to false to actually deploy with real resources. ~&gt;**NOTE**: Deployment Manager
does not allow update of a deployment in preview (unless updating to preview=false). Thus, Terraform will force-recreate
deployments if either preview is updated to true or if other fields are updated while preview is true.
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
    
        <tr>
            <td class="align-top">Self<wbr>Link</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Output only. Server defined URL for the resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Target</td>
            <td class="align-top">
                
                <code><a href="#deploymenttarget">*Deployment<wbr>Target</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Parameters that define your deployment, including the deployment configuration and relevant templates.
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
            <td class="align-top">create<wbr>Policy</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Set the policy to use for creating new resources. Only used on create and update. Valid values are &#39;CREATE_OR_ACQUIRE&#39;
(default) or &#39;ACQUIRE&#39;. If set to &#39;ACQUIRE&#39; and resources do not already exist, the deployment will fail. Note that
updating this field does not actually affect the deployment, just how it is updated.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">delete<wbr>Policy</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Set the policy to use for deleting new resources on update/delete. Valid values are &#39;DELETE&#39; (default) or &#39;ABANDON&#39;. If
&#39;DELETE&#39;, resource is deleted after removal from Deployment Manager. If &#39;ABANDON&#39;, the resource is only removed from
Deployment Manager and is not actually deleted. Note that updating this field does not actually change the deployment,
just how it is updated.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">deployment<wbr>Id</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Unique identifier for deployment. Output only.
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
Optional user-provided description of deployment.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">labels</td>
            <td class="align-top">
                
                <code><a href="#deploymentlabel">Deployment<wbr>Label[]?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Key-value pairs to apply to this labels.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">manifest</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Output only. URL of the manifest representing the last manifest that was successfully deployed.
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
Unique name for the deployment
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">preview</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
If set to true, a deployment is created with &#34;shell&#34; resources that are not actually instantiated. This allows you to
preview a deployment. It can be updated to false to actually deploy with real resources. ~&gt;**NOTE**: Deployment Manager
does not allow update of a deployment in preview (unless updating to preview=false). Thus, Terraform will force-recreate
deployments if either preview is updated to true or if other fields are updated while preview is true.
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
    
        <tr>
            <td class="align-top">self<wbr>Link</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Output only. Server defined URL for the resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">target</td>
            <td class="align-top">
                
                <code><a href="#deploymenttarget">Deployment<wbr>Target?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Parameters that define your deployment, including the deployment configuration and relevant templates.
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
            <td class="align-top">create_<wbr>policy</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Set the policy to use for creating new resources. Only used on create and update. Valid values are &#39;CREATE_OR_ACQUIRE&#39;
(default) or &#39;ACQUIRE&#39;. If set to &#39;ACQUIRE&#39; and resources do not already exist, the deployment will fail. Note that
updating this field does not actually affect the deployment, just how it is updated.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">delete_<wbr>policy</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Set the policy to use for deleting new resources on update/delete. Valid values are &#39;DELETE&#39; (default) or &#39;ABANDON&#39;. If
&#39;DELETE&#39;, resource is deleted after removal from Deployment Manager. If &#39;ABANDON&#39;, the resource is only removed from
Deployment Manager and is not actually deleted. Note that updating this field does not actually change the deployment,
just how it is updated.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">deployment_<wbr>id</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Unique identifier for deployment. Output only.
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
Optional user-provided description of deployment.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">labels</td>
            <td class="align-top">
                
                <code><a href="#deploymentlabel">List[Deployment<wbr>Label]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Key-value pairs to apply to this labels.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">manifest</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Output only. URL of the manifest representing the last manifest that was successfully deployed.
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
Unique name for the deployment
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">preview</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
If set to true, a deployment is created with &#34;shell&#34; resources that are not actually instantiated. This allows you to
preview a deployment. It can be updated to false to actually deploy with real resources. ~&gt;**NOTE**: Deployment Manager
does not allow update of a deployment in preview (unless updating to preview=false). Thus, Terraform will force-recreate
deployments if either preview is updated to true or if other fields are updated while preview is true.
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
    
        <tr>
            <td class="align-top">self_<wbr>link</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Output only. Server defined URL for the resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">target</td>
            <td class="align-top">
                
                <code><a href="#deploymenttarget">Dict[Deployment<wbr>Target]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Parameters that define your deployment, including the deployment configuration and relevant templates.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}










## Supporting Types

#### DeploymentLabel
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#DeploymentLabel">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#DeploymentLabel">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/deploymentmanager?tab=doc#DeploymentLabelArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/deploymentmanager?tab=doc#DeploymentLabelOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Deploymentmanager.DeploymentLabelArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Deploymentmanager.DeploymentLabel.html">output</a> API doc for this type.
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
            <td class="align-top">Key</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Value</td>
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
            <td class="align-top">Key</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Value</td>
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
            <td class="align-top">key</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">value</td>
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
            <td class="align-top">key</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">value</td>
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





#### DeploymentTarget
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#DeploymentTarget">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#DeploymentTarget">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/deploymentmanager?tab=doc#DeploymentTargetArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/deploymentmanager?tab=doc#DeploymentTargetOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Deploymentmanager.DeploymentTargetArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Deploymentmanager.DeploymentTarget.html">output</a> API doc for this type.
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
            <td class="align-top">Config</td>
            <td class="align-top">
                
                <code><a href="#deploymenttargetconfig">Deployment<wbr>Target<wbr>Config<wbr>Args</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Imports</td>
            <td class="align-top">
                
                <code><a href="#deploymenttargetimport">List&lt;Deployment<wbr>Target<wbr>Import<wbr>Args&gt;?</a></code>
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
            <td class="align-top">Config</td>
            <td class="align-top">
                
                <code><a href="#deploymenttargetconfig">Deployment<wbr>Target<wbr>Config</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Imports</td>
            <td class="align-top">
                
                <code><a href="#deploymenttargetimport">[]Deployment<wbr>Target<wbr>Import</a></code>
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
            <td class="align-top">config</td>
            <td class="align-top">
                
                <code><a href="#deploymenttargetconfig">Deployment<wbr>Target<wbr>Config</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">imports</td>
            <td class="align-top">
                
                <code><a href="#deploymenttargetimport">Deployment<wbr>Target<wbr>Import[]?</a></code>
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
            <td class="align-top">config</td>
            <td class="align-top">
                
                <code><a href="#deploymenttargetconfig">Dict[Deployment<wbr>Target<wbr>Config]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">imports</td>
            <td class="align-top">
                
                <code><a href="#deploymenttargetimport">List[Deployment<wbr>Target<wbr>Import]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}





#### DeploymentTargetConfig
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#DeploymentTargetConfig">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#DeploymentTargetConfig">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/deploymentmanager?tab=doc#DeploymentTargetConfigArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/deploymentmanager?tab=doc#DeploymentTargetConfigOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Deploymentmanager.DeploymentTargetConfigArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Deploymentmanager.DeploymentTargetConfig.html">output</a> API doc for this type.
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
            <td class="align-top">Content</td>
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
            <td class="align-top">Content</td>
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
            <td class="align-top">content</td>
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
            <td class="align-top">content</td>
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





#### DeploymentTargetImport
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#DeploymentTargetImport">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#DeploymentTargetImport">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/deploymentmanager?tab=doc#DeploymentTargetImportArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/deploymentmanager?tab=doc#DeploymentTargetImportOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Deploymentmanager.DeploymentTargetImportArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Deploymentmanager.DeploymentTargetImport.html">output</a> API doc for this type.
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
            <td class="align-top">Content</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
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
            <td class="align-top">Content</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
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
            <td class="align-top">content</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
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
            <td class="align-top">content</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
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
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}








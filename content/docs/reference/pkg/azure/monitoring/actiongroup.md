
---
title: "ActionGroup"
block_external_search_index: true
---
<style>
table td p { margin-top: 0; margin-bottom: 0; }
</style>

Manages an Action Group within Azure Monitor.

> This content is derived from https://github.com/terraform-providers/terraform-provider-azurerm/blob/master/website/docs/r/monitor_action_group.html.markdown.



## Create a ActionGroup Resource

{{< langchoose csharp nojavascript >}}

<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/azure/monitoring/#ActionGroup">ActionGroup</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/azure/monitoring/#ActionGroupArgs">ActionGroupArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">ActionGroup</span><span class="p">(resource_name, opts=None, </span>arm_role_receivers=None<span class="p">, </span>automation_runbook_receivers=None<span class="p">, </span>azure_app_push_receivers=None<span class="p">, </span>azure_function_receivers=None<span class="p">, </span>email_receivers=None<span class="p">, </span>enabled=None<span class="p">, </span>itsm_receivers=None<span class="p">, </span>logic_app_receivers=None<span class="p">, </span>name=None<span class="p">, </span>resource_group_name=None<span class="p">, </span>short_name=None<span class="p">, </span>sms_receivers=None<span class="p">, </span>tags=None<span class="p">, </span>voice_receivers=None<span class="p">, </span>webhook_receivers=None<span class="p">, __props__=None);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewActionGroup<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/monitoring?tab=doc#ActionGroupArgs">ActionGroupArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/monitoring?tab=doc#ActionGroup">ActionGroup</a></span>, error)</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Monitoring.ActionGroup.html">ActionGroup</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Monitoring.ActionGroupArgs.html">ActionGroupArgs</a></span> <span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>

Creates a ActionGroup resource with the given unique name, arguments, and options.

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
            <td class="align-top">Arm<wbr>Role<wbr>Receivers</td>
            <td class="align-top">
                
                <code><a href="#actiongrouparmrolereceiver">List&lt;Action<wbr>Group<wbr>Arm<wbr>Role<wbr>Receiver<wbr>Args&gt;?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `arm_role_receiver` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Automation<wbr>Runbook<wbr>Receivers</td>
            <td class="align-top">
                
                <code><a href="#actiongroupautomationrunbookreceiver">List&lt;Action<wbr>Group<wbr>Automation<wbr>Runbook<wbr>Receiver<wbr>Args&gt;?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `automation_runbook_receiver` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Azure<wbr>App<wbr>Push<wbr>Receivers</td>
            <td class="align-top">
                
                <code><a href="#actiongroupazureapppushreceiver">List&lt;Action<wbr>Group<wbr>Azure<wbr>App<wbr>Push<wbr>Receiver<wbr>Args&gt;?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `azure_app_push_receiver` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Azure<wbr>Function<wbr>Receivers</td>
            <td class="align-top">
                
                <code><a href="#actiongroupazurefunctionreceiver">List&lt;Action<wbr>Group<wbr>Azure<wbr>Function<wbr>Receiver<wbr>Args&gt;?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `azure_function_receiver` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Email<wbr>Receivers</td>
            <td class="align-top">
                
                <code><a href="#actiongroupemailreceiver">List&lt;Action<wbr>Group<wbr>Email<wbr>Receiver<wbr>Args&gt;?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `email_receiver` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Enabled</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Whether this action group is enabled. If an action group is not enabled, then none of its receivers will receive communications. Defaults to `true`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Itsm<wbr>Receivers</td>
            <td class="align-top">
                
                <code><a href="#actiongroupitsmreceiver">List&lt;Action<wbr>Group<wbr>Itsm<wbr>Receiver<wbr>Args&gt;?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `itsm_receiver` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Logic<wbr>App<wbr>Receivers</td>
            <td class="align-top">
                
                <code><a href="#actiongrouplogicappreceiver">List&lt;Action<wbr>Group<wbr>Logic<wbr>App<wbr>Receiver<wbr>Args&gt;?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `logic_app_receiver` blocks as defined below.
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
The name of the webhook receiver. Names must be unique (case-insensitive) across all receivers within an action group.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Resource<wbr>Group<wbr>Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The name of the resource group in which to create the Action Group instance.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Short<wbr>Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The short name of the action group. This will be used in SMS messages.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Sms<wbr>Receivers</td>
            <td class="align-top">
                
                <code><a href="#actiongroupsmsreceiver">List&lt;Action<wbr>Group<wbr>Sms<wbr>Receiver<wbr>Args&gt;?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `sms_receiver` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Tags</td>
            <td class="align-top">
                
                <code>Dictionary<string, string>?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A mapping of tags to assign to the resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Voice<wbr>Receivers</td>
            <td class="align-top">
                
                <code><a href="#actiongroupvoicereceiver">List&lt;Action<wbr>Group<wbr>Voice<wbr>Receiver<wbr>Args&gt;?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `voice_receiver` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Webhook<wbr>Receivers</td>
            <td class="align-top">
                
                <code><a href="#actiongroupwebhookreceiver">List&lt;Action<wbr>Group<wbr>Webhook<wbr>Receiver<wbr>Args&gt;?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `webhook_receiver` blocks as defined below.
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
            <td class="align-top">Arm<wbr>Role<wbr>Receivers</td>
            <td class="align-top">
                
                <code><a href="#actiongrouparmrolereceiver">[]Action<wbr>Group<wbr>Arm<wbr>Role<wbr>Receiver</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `arm_role_receiver` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Automation<wbr>Runbook<wbr>Receivers</td>
            <td class="align-top">
                
                <code><a href="#actiongroupautomationrunbookreceiver">[]Action<wbr>Group<wbr>Automation<wbr>Runbook<wbr>Receiver</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `automation_runbook_receiver` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Azure<wbr>App<wbr>Push<wbr>Receivers</td>
            <td class="align-top">
                
                <code><a href="#actiongroupazureapppushreceiver">[]Action<wbr>Group<wbr>Azure<wbr>App<wbr>Push<wbr>Receiver</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `azure_app_push_receiver` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Azure<wbr>Function<wbr>Receivers</td>
            <td class="align-top">
                
                <code><a href="#actiongroupazurefunctionreceiver">[]Action<wbr>Group<wbr>Azure<wbr>Function<wbr>Receiver</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `azure_function_receiver` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Email<wbr>Receivers</td>
            <td class="align-top">
                
                <code><a href="#actiongroupemailreceiver">[]Action<wbr>Group<wbr>Email<wbr>Receiver</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `email_receiver` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Enabled</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Whether this action group is enabled. If an action group is not enabled, then none of its receivers will receive communications. Defaults to `true`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Itsm<wbr>Receivers</td>
            <td class="align-top">
                
                <code><a href="#actiongroupitsmreceiver">[]Action<wbr>Group<wbr>Itsm<wbr>Receiver</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `itsm_receiver` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Logic<wbr>App<wbr>Receivers</td>
            <td class="align-top">
                
                <code><a href="#actiongrouplogicappreceiver">[]Action<wbr>Group<wbr>Logic<wbr>App<wbr>Receiver</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `logic_app_receiver` blocks as defined below.
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
The name of the webhook receiver. Names must be unique (case-insensitive) across all receivers within an action group.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Resource<wbr>Group<wbr>Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The name of the resource group in which to create the Action Group instance.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Short<wbr>Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The short name of the action group. This will be used in SMS messages.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Sms<wbr>Receivers</td>
            <td class="align-top">
                
                <code><a href="#actiongroupsmsreceiver">[]Action<wbr>Group<wbr>Sms<wbr>Receiver</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `sms_receiver` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Tags</td>
            <td class="align-top">
                
                <code>map[string]string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A mapping of tags to assign to the resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Voice<wbr>Receivers</td>
            <td class="align-top">
                
                <code><a href="#actiongroupvoicereceiver">[]Action<wbr>Group<wbr>Voice<wbr>Receiver</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `voice_receiver` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Webhook<wbr>Receivers</td>
            <td class="align-top">
                
                <code><a href="#actiongroupwebhookreceiver">[]Action<wbr>Group<wbr>Webhook<wbr>Receiver</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `webhook_receiver` blocks as defined below.
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
            <td class="align-top">arm<wbr>Role<wbr>Receivers</td>
            <td class="align-top">
                
                <code><a href="#actiongrouparmrolereceiver">Action<wbr>Group<wbr>Arm<wbr>Role<wbr>Receiver[]?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `arm_role_receiver` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">automation<wbr>Runbook<wbr>Receivers</td>
            <td class="align-top">
                
                <code><a href="#actiongroupautomationrunbookreceiver">Action<wbr>Group<wbr>Automation<wbr>Runbook<wbr>Receiver[]?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `automation_runbook_receiver` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">azure<wbr>App<wbr>Push<wbr>Receivers</td>
            <td class="align-top">
                
                <code><a href="#actiongroupazureapppushreceiver">Action<wbr>Group<wbr>Azure<wbr>App<wbr>Push<wbr>Receiver[]?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `azure_app_push_receiver` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">azure<wbr>Function<wbr>Receivers</td>
            <td class="align-top">
                
                <code><a href="#actiongroupazurefunctionreceiver">Action<wbr>Group<wbr>Azure<wbr>Function<wbr>Receiver[]?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `azure_function_receiver` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">email<wbr>Receivers</td>
            <td class="align-top">
                
                <code><a href="#actiongroupemailreceiver">Action<wbr>Group<wbr>Email<wbr>Receiver[]?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `email_receiver` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">enabled</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Whether this action group is enabled. If an action group is not enabled, then none of its receivers will receive communications. Defaults to `true`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">itsm<wbr>Receivers</td>
            <td class="align-top">
                
                <code><a href="#actiongroupitsmreceiver">Action<wbr>Group<wbr>Itsm<wbr>Receiver[]?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `itsm_receiver` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">logic<wbr>App<wbr>Receivers</td>
            <td class="align-top">
                
                <code><a href="#actiongrouplogicappreceiver">Action<wbr>Group<wbr>Logic<wbr>App<wbr>Receiver[]?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `logic_app_receiver` blocks as defined below.
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
The name of the webhook receiver. Names must be unique (case-insensitive) across all receivers within an action group.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">resource<wbr>Group<wbr>Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The name of the resource group in which to create the Action Group instance.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">short<wbr>Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The short name of the action group. This will be used in SMS messages.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">sms<wbr>Receivers</td>
            <td class="align-top">
                
                <code><a href="#actiongroupsmsreceiver">Action<wbr>Group<wbr>Sms<wbr>Receiver[]?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `sms_receiver` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">tags</td>
            <td class="align-top">
                
                <code>{[key: string]: string}?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A mapping of tags to assign to the resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">voice<wbr>Receivers</td>
            <td class="align-top">
                
                <code><a href="#actiongroupvoicereceiver">Action<wbr>Group<wbr>Voice<wbr>Receiver[]?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `voice_receiver` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">webhook<wbr>Receivers</td>
            <td class="align-top">
                
                <code><a href="#actiongroupwebhookreceiver">Action<wbr>Group<wbr>Webhook<wbr>Receiver[]?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `webhook_receiver` blocks as defined below.
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
            <td class="align-top">arm_<wbr>role_<wbr>receivers</td>
            <td class="align-top">
                
                <code><a href="#actiongrouparmrolereceiver">List[Action<wbr>Group<wbr>Arm<wbr>Role<wbr>Receiver]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `arm_role_receiver` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">automation_<wbr>runbook_<wbr>receivers</td>
            <td class="align-top">
                
                <code><a href="#actiongroupautomationrunbookreceiver">List[Action<wbr>Group<wbr>Automation<wbr>Runbook<wbr>Receiver]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `automation_runbook_receiver` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">azure_<wbr>app_<wbr>push_<wbr>receivers</td>
            <td class="align-top">
                
                <code><a href="#actiongroupazureapppushreceiver">List[Action<wbr>Group<wbr>Azure<wbr>App<wbr>Push<wbr>Receiver]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `azure_app_push_receiver` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">azure_<wbr>function_<wbr>receivers</td>
            <td class="align-top">
                
                <code><a href="#actiongroupazurefunctionreceiver">List[Action<wbr>Group<wbr>Azure<wbr>Function<wbr>Receiver]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `azure_function_receiver` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">email_<wbr>receivers</td>
            <td class="align-top">
                
                <code><a href="#actiongroupemailreceiver">List[Action<wbr>Group<wbr>Email<wbr>Receiver]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `email_receiver` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">enabled</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Whether this action group is enabled. If an action group is not enabled, then none of its receivers will receive communications. Defaults to `true`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">itsm_<wbr>receivers</td>
            <td class="align-top">
                
                <code><a href="#actiongroupitsmreceiver">List[Action<wbr>Group<wbr>Itsm<wbr>Receiver]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `itsm_receiver` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">logic_<wbr>app_<wbr>receivers</td>
            <td class="align-top">
                
                <code><a href="#actiongrouplogicappreceiver">List[Action<wbr>Group<wbr>Logic<wbr>App<wbr>Receiver]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `logic_app_receiver` blocks as defined below.
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
The name of the webhook receiver. Names must be unique (case-insensitive) across all receivers within an action group.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">resource_<wbr>group_<wbr>name</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The name of the resource group in which to create the Action Group instance.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">short_<wbr>name</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The short name of the action group. This will be used in SMS messages.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">sms_<wbr>receivers</td>
            <td class="align-top">
                
                <code><a href="#actiongroupsmsreceiver">List[Action<wbr>Group<wbr>Sms<wbr>Receiver]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `sms_receiver` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">tags</td>
            <td class="align-top">
                
                <code>Dict[str, str]</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A mapping of tags to assign to the resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">voice_<wbr>receivers</td>
            <td class="align-top">
                
                <code><a href="#actiongroupvoicereceiver">List[Action<wbr>Group<wbr>Voice<wbr>Receiver]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `voice_receiver` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">webhook_<wbr>receivers</td>
            <td class="align-top">
                
                <code><a href="#actiongroupwebhookreceiver">List[Action<wbr>Group<wbr>Webhook<wbr>Receiver]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `webhook_receiver` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}







## ActionGroup Output Properties

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
            <td class="align-top">Arm<wbr>Role<wbr>Receivers</td>
            <td class="align-top">
                
                <code><a href="#actiongrouparmrolereceiver">List&lt;Action<wbr>Group<wbr>Arm<wbr>Role<wbr>Receiver&gt;?</a></code>
            </td>
            <td class="align-top">{{% md %}} One or more `arm_role_receiver` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Automation<wbr>Runbook<wbr>Receivers</td>
            <td class="align-top">
                
                <code><a href="#actiongroupautomationrunbookreceiver">List&lt;Action<wbr>Group<wbr>Automation<wbr>Runbook<wbr>Receiver&gt;?</a></code>
            </td>
            <td class="align-top">{{% md %}} One or more `automation_runbook_receiver` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Azure<wbr>App<wbr>Push<wbr>Receivers</td>
            <td class="align-top">
                
                <code><a href="#actiongroupazureapppushreceiver">List&lt;Action<wbr>Group<wbr>Azure<wbr>App<wbr>Push<wbr>Receiver&gt;?</a></code>
            </td>
            <td class="align-top">{{% md %}} One or more `azure_app_push_receiver` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Azure<wbr>Function<wbr>Receivers</td>
            <td class="align-top">
                
                <code><a href="#actiongroupazurefunctionreceiver">List&lt;Action<wbr>Group<wbr>Azure<wbr>Function<wbr>Receiver&gt;?</a></code>
            </td>
            <td class="align-top">{{% md %}} One or more `azure_function_receiver` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Email<wbr>Receivers</td>
            <td class="align-top">
                
                <code><a href="#actiongroupemailreceiver">List&lt;Action<wbr>Group<wbr>Email<wbr>Receiver&gt;?</a></code>
            </td>
            <td class="align-top">{{% md %}} One or more `email_receiver` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Enabled</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} Whether this action group is enabled. If an action group is not enabled, then none of its receivers will receive communications. Defaults to `true`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Itsm<wbr>Receivers</td>
            <td class="align-top">
                
                <code><a href="#actiongroupitsmreceiver">List&lt;Action<wbr>Group<wbr>Itsm<wbr>Receiver&gt;?</a></code>
            </td>
            <td class="align-top">{{% md %}} One or more `itsm_receiver` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Logic<wbr>App<wbr>Receivers</td>
            <td class="align-top">
                
                <code><a href="#actiongrouplogicappreceiver">List&lt;Action<wbr>Group<wbr>Logic<wbr>App<wbr>Receiver&gt;?</a></code>
            </td>
            <td class="align-top">{{% md %}} One or more `logic_app_receiver` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The name of the webhook receiver. Names must be unique (case-insensitive) across all receivers within an action group.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Resource<wbr>Group<wbr>Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The name of the resource group in which to create the Action Group instance.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Short<wbr>Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The short name of the action group. This will be used in SMS messages.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Sms<wbr>Receivers</td>
            <td class="align-top">
                
                <code><a href="#actiongroupsmsreceiver">List&lt;Action<wbr>Group<wbr>Sms<wbr>Receiver&gt;?</a></code>
            </td>
            <td class="align-top">{{% md %}} One or more `sms_receiver` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Tags</td>
            <td class="align-top">
                
                <code>Dictionary<string, string>?</code>
            </td>
            <td class="align-top">{{% md %}} A mapping of tags to assign to the resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Voice<wbr>Receivers</td>
            <td class="align-top">
                
                <code><a href="#actiongroupvoicereceiver">List&lt;Action<wbr>Group<wbr>Voice<wbr>Receiver&gt;?</a></code>
            </td>
            <td class="align-top">{{% md %}} One or more `voice_receiver` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Webhook<wbr>Receivers</td>
            <td class="align-top">
                
                <code><a href="#actiongroupwebhookreceiver">List&lt;Action<wbr>Group<wbr>Webhook<wbr>Receiver&gt;?</a></code>
            </td>
            <td class="align-top">{{% md %}} One or more `webhook_receiver` blocks as defined below.
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
            <td class="align-top">Arm<wbr>Role<wbr>Receivers</td>
            <td class="align-top">
                
                <code><a href="#actiongrouparmrolereceiver">[]Action<wbr>Group<wbr>Arm<wbr>Role<wbr>Receiver</a></code>
            </td>
            <td class="align-top">{{% md %}} One or more `arm_role_receiver` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Automation<wbr>Runbook<wbr>Receivers</td>
            <td class="align-top">
                
                <code><a href="#actiongroupautomationrunbookreceiver">[]Action<wbr>Group<wbr>Automation<wbr>Runbook<wbr>Receiver</a></code>
            </td>
            <td class="align-top">{{% md %}} One or more `automation_runbook_receiver` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Azure<wbr>App<wbr>Push<wbr>Receivers</td>
            <td class="align-top">
                
                <code><a href="#actiongroupazureapppushreceiver">[]Action<wbr>Group<wbr>Azure<wbr>App<wbr>Push<wbr>Receiver</a></code>
            </td>
            <td class="align-top">{{% md %}} One or more `azure_app_push_receiver` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Azure<wbr>Function<wbr>Receivers</td>
            <td class="align-top">
                
                <code><a href="#actiongroupazurefunctionreceiver">[]Action<wbr>Group<wbr>Azure<wbr>Function<wbr>Receiver</a></code>
            </td>
            <td class="align-top">{{% md %}} One or more `azure_function_receiver` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Email<wbr>Receivers</td>
            <td class="align-top">
                
                <code><a href="#actiongroupemailreceiver">[]Action<wbr>Group<wbr>Email<wbr>Receiver</a></code>
            </td>
            <td class="align-top">{{% md %}} One or more `email_receiver` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Enabled</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} Whether this action group is enabled. If an action group is not enabled, then none of its receivers will receive communications. Defaults to `true`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Itsm<wbr>Receivers</td>
            <td class="align-top">
                
                <code><a href="#actiongroupitsmreceiver">[]Action<wbr>Group<wbr>Itsm<wbr>Receiver</a></code>
            </td>
            <td class="align-top">{{% md %}} One or more `itsm_receiver` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Logic<wbr>App<wbr>Receivers</td>
            <td class="align-top">
                
                <code><a href="#actiongrouplogicappreceiver">[]Action<wbr>Group<wbr>Logic<wbr>App<wbr>Receiver</a></code>
            </td>
            <td class="align-top">{{% md %}} One or more `logic_app_receiver` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The name of the webhook receiver. Names must be unique (case-insensitive) across all receivers within an action group.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Resource<wbr>Group<wbr>Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The name of the resource group in which to create the Action Group instance.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Short<wbr>Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The short name of the action group. This will be used in SMS messages.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Sms<wbr>Receivers</td>
            <td class="align-top">
                
                <code><a href="#actiongroupsmsreceiver">[]Action<wbr>Group<wbr>Sms<wbr>Receiver</a></code>
            </td>
            <td class="align-top">{{% md %}} One or more `sms_receiver` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Tags</td>
            <td class="align-top">
                
                <code>map[string]string</code>
            </td>
            <td class="align-top">{{% md %}} A mapping of tags to assign to the resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Voice<wbr>Receivers</td>
            <td class="align-top">
                
                <code><a href="#actiongroupvoicereceiver">[]Action<wbr>Group<wbr>Voice<wbr>Receiver</a></code>
            </td>
            <td class="align-top">{{% md %}} One or more `voice_receiver` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Webhook<wbr>Receivers</td>
            <td class="align-top">
                
                <code><a href="#actiongroupwebhookreceiver">[]Action<wbr>Group<wbr>Webhook<wbr>Receiver</a></code>
            </td>
            <td class="align-top">{{% md %}} One or more `webhook_receiver` blocks as defined below.
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
            <td class="align-top">arm<wbr>Role<wbr>Receivers</td>
            <td class="align-top">
                
                <code><a href="#actiongrouparmrolereceiver">Action<wbr>Group<wbr>Arm<wbr>Role<wbr>Receiver[]?</a></code>
            </td>
            <td class="align-top">{{% md %}} One or more `arm_role_receiver` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">automation<wbr>Runbook<wbr>Receivers</td>
            <td class="align-top">
                
                <code><a href="#actiongroupautomationrunbookreceiver">Action<wbr>Group<wbr>Automation<wbr>Runbook<wbr>Receiver[]?</a></code>
            </td>
            <td class="align-top">{{% md %}} One or more `automation_runbook_receiver` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">azure<wbr>App<wbr>Push<wbr>Receivers</td>
            <td class="align-top">
                
                <code><a href="#actiongroupazureapppushreceiver">Action<wbr>Group<wbr>Azure<wbr>App<wbr>Push<wbr>Receiver[]?</a></code>
            </td>
            <td class="align-top">{{% md %}} One or more `azure_app_push_receiver` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">azure<wbr>Function<wbr>Receivers</td>
            <td class="align-top">
                
                <code><a href="#actiongroupazurefunctionreceiver">Action<wbr>Group<wbr>Azure<wbr>Function<wbr>Receiver[]?</a></code>
            </td>
            <td class="align-top">{{% md %}} One or more `azure_function_receiver` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">email<wbr>Receivers</td>
            <td class="align-top">
                
                <code><a href="#actiongroupemailreceiver">Action<wbr>Group<wbr>Email<wbr>Receiver[]?</a></code>
            </td>
            <td class="align-top">{{% md %}} One or more `email_receiver` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">enabled</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} Whether this action group is enabled. If an action group is not enabled, then none of its receivers will receive communications. Defaults to `true`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">itsm<wbr>Receivers</td>
            <td class="align-top">
                
                <code><a href="#actiongroupitsmreceiver">Action<wbr>Group<wbr>Itsm<wbr>Receiver[]?</a></code>
            </td>
            <td class="align-top">{{% md %}} One or more `itsm_receiver` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">logic<wbr>App<wbr>Receivers</td>
            <td class="align-top">
                
                <code><a href="#actiongrouplogicappreceiver">Action<wbr>Group<wbr>Logic<wbr>App<wbr>Receiver[]?</a></code>
            </td>
            <td class="align-top">{{% md %}} One or more `logic_app_receiver` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The name of the webhook receiver. Names must be unique (case-insensitive) across all receivers within an action group.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">resource<wbr>Group<wbr>Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The name of the resource group in which to create the Action Group instance.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">short<wbr>Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The short name of the action group. This will be used in SMS messages.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">sms<wbr>Receivers</td>
            <td class="align-top">
                
                <code><a href="#actiongroupsmsreceiver">Action<wbr>Group<wbr>Sms<wbr>Receiver[]?</a></code>
            </td>
            <td class="align-top">{{% md %}} One or more `sms_receiver` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">tags</td>
            <td class="align-top">
                
                <code>{[key: string]: string}?</code>
            </td>
            <td class="align-top">{{% md %}} A mapping of tags to assign to the resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">voice<wbr>Receivers</td>
            <td class="align-top">
                
                <code><a href="#actiongroupvoicereceiver">Action<wbr>Group<wbr>Voice<wbr>Receiver[]?</a></code>
            </td>
            <td class="align-top">{{% md %}} One or more `voice_receiver` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">webhook<wbr>Receivers</td>
            <td class="align-top">
                
                <code><a href="#actiongroupwebhookreceiver">Action<wbr>Group<wbr>Webhook<wbr>Receiver[]?</a></code>
            </td>
            <td class="align-top">{{% md %}} One or more `webhook_receiver` blocks as defined below.
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
            <td class="align-top">arm_<wbr>role_<wbr>receivers</td>
            <td class="align-top">
                
                <code><a href="#actiongrouparmrolereceiver">List[Action<wbr>Group<wbr>Arm<wbr>Role<wbr>Receiver]</a></code>
            </td>
            <td class="align-top">{{% md %}} One or more `arm_role_receiver` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">automation_<wbr>runbook_<wbr>receivers</td>
            <td class="align-top">
                
                <code><a href="#actiongroupautomationrunbookreceiver">List[Action<wbr>Group<wbr>Automation<wbr>Runbook<wbr>Receiver]</a></code>
            </td>
            <td class="align-top">{{% md %}} One or more `automation_runbook_receiver` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">azure_<wbr>app_<wbr>push_<wbr>receivers</td>
            <td class="align-top">
                
                <code><a href="#actiongroupazureapppushreceiver">List[Action<wbr>Group<wbr>Azure<wbr>App<wbr>Push<wbr>Receiver]</a></code>
            </td>
            <td class="align-top">{{% md %}} One or more `azure_app_push_receiver` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">azure_<wbr>function_<wbr>receivers</td>
            <td class="align-top">
                
                <code><a href="#actiongroupazurefunctionreceiver">List[Action<wbr>Group<wbr>Azure<wbr>Function<wbr>Receiver]</a></code>
            </td>
            <td class="align-top">{{% md %}} One or more `azure_function_receiver` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">email_<wbr>receivers</td>
            <td class="align-top">
                
                <code><a href="#actiongroupemailreceiver">List[Action<wbr>Group<wbr>Email<wbr>Receiver]</a></code>
            </td>
            <td class="align-top">{{% md %}} One or more `email_receiver` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">enabled</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} Whether this action group is enabled. If an action group is not enabled, then none of its receivers will receive communications. Defaults to `true`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">itsm_<wbr>receivers</td>
            <td class="align-top">
                
                <code><a href="#actiongroupitsmreceiver">List[Action<wbr>Group<wbr>Itsm<wbr>Receiver]</a></code>
            </td>
            <td class="align-top">{{% md %}} One or more `itsm_receiver` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">logic_<wbr>app_<wbr>receivers</td>
            <td class="align-top">
                
                <code><a href="#actiongrouplogicappreceiver">List[Action<wbr>Group<wbr>Logic<wbr>App<wbr>Receiver]</a></code>
            </td>
            <td class="align-top">{{% md %}} One or more `logic_app_receiver` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">name</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The name of the webhook receiver. Names must be unique (case-insensitive) across all receivers within an action group.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">resource_<wbr>group_<wbr>name</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The name of the resource group in which to create the Action Group instance.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">short_<wbr>name</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The short name of the action group. This will be used in SMS messages.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">sms_<wbr>receivers</td>
            <td class="align-top">
                
                <code><a href="#actiongroupsmsreceiver">List[Action<wbr>Group<wbr>Sms<wbr>Receiver]</a></code>
            </td>
            <td class="align-top">{{% md %}} One or more `sms_receiver` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">tags</td>
            <td class="align-top">
                
                <code>Dict[str, str]</code>
            </td>
            <td class="align-top">{{% md %}} A mapping of tags to assign to the resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">voice_<wbr>receivers</td>
            <td class="align-top">
                
                <code><a href="#actiongroupvoicereceiver">List[Action<wbr>Group<wbr>Voice<wbr>Receiver]</a></code>
            </td>
            <td class="align-top">{{% md %}} One or more `voice_receiver` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">webhook_<wbr>receivers</td>
            <td class="align-top">
                
                <code><a href="#actiongroupwebhookreceiver">List[Action<wbr>Group<wbr>Webhook<wbr>Receiver]</a></code>
            </td>
            <td class="align-top">{{% md %}} One or more `webhook_receiver` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}








## Look up an Existing ActionGroup Resource

{{< langchoose csharp nojavascript >}}

<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">pulumi.Input&lt;pulumi.ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/azure/monitoring/#ActionGroupState">ActionGroupState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/azure/monitoring/#ActionGroup">ActionGroup</a></span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>arm_role_receivers=None<span class="p">, </span>automation_runbook_receivers=None<span class="p">, </span>azure_app_push_receivers=None<span class="p">, </span>azure_function_receivers=None<span class="p">, </span>email_receivers=None<span class="p">, </span>enabled=None<span class="p">, </span>itsm_receivers=None<span class="p">, </span>logic_app_receivers=None<span class="p">, </span>name=None<span class="p">, </span>resource_group_name=None<span class="p">, </span>short_name=None<span class="p">, </span>sms_receivers=None<span class="p">, </span>tags=None<span class="p">, </span>voice_receivers=None<span class="p">, </span>webhook_receivers=None<span class="p">, __props__=None);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetActionGroup<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">pulumi.IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/monitoring?tab=doc#ActionGroupState">ActionGroupState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/monitoring?tab=doc#ActionGroup">ActionGroup</a></span>, error)</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Monitoring.ActionGroup.html">ActionGroup</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Pulumi.Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Monitoring.ActionGroupState.html">ActionGroupState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>

Get an existing ActionGroup resource's state with the given name, ID, and optional extra properties used to qualify the lookup.

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
            <td class="align-top">Arm<wbr>Role<wbr>Receivers</td>
            <td class="align-top">
                
                <code><a href="#actiongrouparmrolereceiver">List&lt;Action<wbr>Group<wbr>Arm<wbr>Role<wbr>Receiver<wbr>Args&gt;?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `arm_role_receiver` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Automation<wbr>Runbook<wbr>Receivers</td>
            <td class="align-top">
                
                <code><a href="#actiongroupautomationrunbookreceiver">List&lt;Action<wbr>Group<wbr>Automation<wbr>Runbook<wbr>Receiver<wbr>Args&gt;?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `automation_runbook_receiver` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Azure<wbr>App<wbr>Push<wbr>Receivers</td>
            <td class="align-top">
                
                <code><a href="#actiongroupazureapppushreceiver">List&lt;Action<wbr>Group<wbr>Azure<wbr>App<wbr>Push<wbr>Receiver<wbr>Args&gt;?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `azure_app_push_receiver` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Azure<wbr>Function<wbr>Receivers</td>
            <td class="align-top">
                
                <code><a href="#actiongroupazurefunctionreceiver">List&lt;Action<wbr>Group<wbr>Azure<wbr>Function<wbr>Receiver<wbr>Args&gt;?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `azure_function_receiver` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Email<wbr>Receivers</td>
            <td class="align-top">
                
                <code><a href="#actiongroupemailreceiver">List&lt;Action<wbr>Group<wbr>Email<wbr>Receiver<wbr>Args&gt;?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `email_receiver` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Enabled</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Whether this action group is enabled. If an action group is not enabled, then none of its receivers will receive communications. Defaults to `true`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Itsm<wbr>Receivers</td>
            <td class="align-top">
                
                <code><a href="#actiongroupitsmreceiver">List&lt;Action<wbr>Group<wbr>Itsm<wbr>Receiver<wbr>Args&gt;?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `itsm_receiver` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Logic<wbr>App<wbr>Receivers</td>
            <td class="align-top">
                
                <code><a href="#actiongrouplogicappreceiver">List&lt;Action<wbr>Group<wbr>Logic<wbr>App<wbr>Receiver<wbr>Args&gt;?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `logic_app_receiver` blocks as defined below.
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
The name of the webhook receiver. Names must be unique (case-insensitive) across all receivers within an action group.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Resource<wbr>Group<wbr>Name</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The name of the resource group in which to create the Action Group instance.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Short<wbr>Name</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The short name of the action group. This will be used in SMS messages.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Sms<wbr>Receivers</td>
            <td class="align-top">
                
                <code><a href="#actiongroupsmsreceiver">List&lt;Action<wbr>Group<wbr>Sms<wbr>Receiver<wbr>Args&gt;?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `sms_receiver` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Tags</td>
            <td class="align-top">
                
                <code>Dictionary<string, string>?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A mapping of tags to assign to the resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Voice<wbr>Receivers</td>
            <td class="align-top">
                
                <code><a href="#actiongroupvoicereceiver">List&lt;Action<wbr>Group<wbr>Voice<wbr>Receiver<wbr>Args&gt;?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `voice_receiver` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Webhook<wbr>Receivers</td>
            <td class="align-top">
                
                <code><a href="#actiongroupwebhookreceiver">List&lt;Action<wbr>Group<wbr>Webhook<wbr>Receiver<wbr>Args&gt;?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `webhook_receiver` blocks as defined below.
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
            <td class="align-top">Arm<wbr>Role<wbr>Receivers</td>
            <td class="align-top">
                
                <code><a href="#actiongrouparmrolereceiver">[]Action<wbr>Group<wbr>Arm<wbr>Role<wbr>Receiver</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `arm_role_receiver` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Automation<wbr>Runbook<wbr>Receivers</td>
            <td class="align-top">
                
                <code><a href="#actiongroupautomationrunbookreceiver">[]Action<wbr>Group<wbr>Automation<wbr>Runbook<wbr>Receiver</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `automation_runbook_receiver` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Azure<wbr>App<wbr>Push<wbr>Receivers</td>
            <td class="align-top">
                
                <code><a href="#actiongroupazureapppushreceiver">[]Action<wbr>Group<wbr>Azure<wbr>App<wbr>Push<wbr>Receiver</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `azure_app_push_receiver` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Azure<wbr>Function<wbr>Receivers</td>
            <td class="align-top">
                
                <code><a href="#actiongroupazurefunctionreceiver">[]Action<wbr>Group<wbr>Azure<wbr>Function<wbr>Receiver</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `azure_function_receiver` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Email<wbr>Receivers</td>
            <td class="align-top">
                
                <code><a href="#actiongroupemailreceiver">[]Action<wbr>Group<wbr>Email<wbr>Receiver</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `email_receiver` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Enabled</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Whether this action group is enabled. If an action group is not enabled, then none of its receivers will receive communications. Defaults to `true`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Itsm<wbr>Receivers</td>
            <td class="align-top">
                
                <code><a href="#actiongroupitsmreceiver">[]Action<wbr>Group<wbr>Itsm<wbr>Receiver</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `itsm_receiver` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Logic<wbr>App<wbr>Receivers</td>
            <td class="align-top">
                
                <code><a href="#actiongrouplogicappreceiver">[]Action<wbr>Group<wbr>Logic<wbr>App<wbr>Receiver</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `logic_app_receiver` blocks as defined below.
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
The name of the webhook receiver. Names must be unique (case-insensitive) across all receivers within an action group.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Resource<wbr>Group<wbr>Name</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The name of the resource group in which to create the Action Group instance.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Short<wbr>Name</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The short name of the action group. This will be used in SMS messages.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Sms<wbr>Receivers</td>
            <td class="align-top">
                
                <code><a href="#actiongroupsmsreceiver">[]Action<wbr>Group<wbr>Sms<wbr>Receiver</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `sms_receiver` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Tags</td>
            <td class="align-top">
                
                <code>map[string]string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A mapping of tags to assign to the resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Voice<wbr>Receivers</td>
            <td class="align-top">
                
                <code><a href="#actiongroupvoicereceiver">[]Action<wbr>Group<wbr>Voice<wbr>Receiver</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `voice_receiver` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Webhook<wbr>Receivers</td>
            <td class="align-top">
                
                <code><a href="#actiongroupwebhookreceiver">[]Action<wbr>Group<wbr>Webhook<wbr>Receiver</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `webhook_receiver` blocks as defined below.
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
            <td class="align-top">arm<wbr>Role<wbr>Receivers</td>
            <td class="align-top">
                
                <code><a href="#actiongrouparmrolereceiver">Action<wbr>Group<wbr>Arm<wbr>Role<wbr>Receiver[]?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `arm_role_receiver` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">automation<wbr>Runbook<wbr>Receivers</td>
            <td class="align-top">
                
                <code><a href="#actiongroupautomationrunbookreceiver">Action<wbr>Group<wbr>Automation<wbr>Runbook<wbr>Receiver[]?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `automation_runbook_receiver` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">azure<wbr>App<wbr>Push<wbr>Receivers</td>
            <td class="align-top">
                
                <code><a href="#actiongroupazureapppushreceiver">Action<wbr>Group<wbr>Azure<wbr>App<wbr>Push<wbr>Receiver[]?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `azure_app_push_receiver` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">azure<wbr>Function<wbr>Receivers</td>
            <td class="align-top">
                
                <code><a href="#actiongroupazurefunctionreceiver">Action<wbr>Group<wbr>Azure<wbr>Function<wbr>Receiver[]?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `azure_function_receiver` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">email<wbr>Receivers</td>
            <td class="align-top">
                
                <code><a href="#actiongroupemailreceiver">Action<wbr>Group<wbr>Email<wbr>Receiver[]?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `email_receiver` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">enabled</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Whether this action group is enabled. If an action group is not enabled, then none of its receivers will receive communications. Defaults to `true`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">itsm<wbr>Receivers</td>
            <td class="align-top">
                
                <code><a href="#actiongroupitsmreceiver">Action<wbr>Group<wbr>Itsm<wbr>Receiver[]?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `itsm_receiver` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">logic<wbr>App<wbr>Receivers</td>
            <td class="align-top">
                
                <code><a href="#actiongrouplogicappreceiver">Action<wbr>Group<wbr>Logic<wbr>App<wbr>Receiver[]?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `logic_app_receiver` blocks as defined below.
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
The name of the webhook receiver. Names must be unique (case-insensitive) across all receivers within an action group.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">resource<wbr>Group<wbr>Name</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The name of the resource group in which to create the Action Group instance.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">short<wbr>Name</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The short name of the action group. This will be used in SMS messages.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">sms<wbr>Receivers</td>
            <td class="align-top">
                
                <code><a href="#actiongroupsmsreceiver">Action<wbr>Group<wbr>Sms<wbr>Receiver[]?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `sms_receiver` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">tags</td>
            <td class="align-top">
                
                <code>{[key: string]: string}?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A mapping of tags to assign to the resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">voice<wbr>Receivers</td>
            <td class="align-top">
                
                <code><a href="#actiongroupvoicereceiver">Action<wbr>Group<wbr>Voice<wbr>Receiver[]?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `voice_receiver` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">webhook<wbr>Receivers</td>
            <td class="align-top">
                
                <code><a href="#actiongroupwebhookreceiver">Action<wbr>Group<wbr>Webhook<wbr>Receiver[]?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `webhook_receiver` blocks as defined below.
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
            <td class="align-top">arm_<wbr>role_<wbr>receivers</td>
            <td class="align-top">
                
                <code><a href="#actiongrouparmrolereceiver">List[Action<wbr>Group<wbr>Arm<wbr>Role<wbr>Receiver]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `arm_role_receiver` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">automation_<wbr>runbook_<wbr>receivers</td>
            <td class="align-top">
                
                <code><a href="#actiongroupautomationrunbookreceiver">List[Action<wbr>Group<wbr>Automation<wbr>Runbook<wbr>Receiver]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `automation_runbook_receiver` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">azure_<wbr>app_<wbr>push_<wbr>receivers</td>
            <td class="align-top">
                
                <code><a href="#actiongroupazureapppushreceiver">List[Action<wbr>Group<wbr>Azure<wbr>App<wbr>Push<wbr>Receiver]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `azure_app_push_receiver` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">azure_<wbr>function_<wbr>receivers</td>
            <td class="align-top">
                
                <code><a href="#actiongroupazurefunctionreceiver">List[Action<wbr>Group<wbr>Azure<wbr>Function<wbr>Receiver]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `azure_function_receiver` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">email_<wbr>receivers</td>
            <td class="align-top">
                
                <code><a href="#actiongroupemailreceiver">List[Action<wbr>Group<wbr>Email<wbr>Receiver]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `email_receiver` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">enabled</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Whether this action group is enabled. If an action group is not enabled, then none of its receivers will receive communications. Defaults to `true`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">itsm_<wbr>receivers</td>
            <td class="align-top">
                
                <code><a href="#actiongroupitsmreceiver">List[Action<wbr>Group<wbr>Itsm<wbr>Receiver]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `itsm_receiver` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">logic_<wbr>app_<wbr>receivers</td>
            <td class="align-top">
                
                <code><a href="#actiongrouplogicappreceiver">List[Action<wbr>Group<wbr>Logic<wbr>App<wbr>Receiver]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `logic_app_receiver` blocks as defined below.
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
The name of the webhook receiver. Names must be unique (case-insensitive) across all receivers within an action group.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">resource_<wbr>group_<wbr>name</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The name of the resource group in which to create the Action Group instance.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">short_<wbr>name</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The short name of the action group. This will be used in SMS messages.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">sms_<wbr>receivers</td>
            <td class="align-top">
                
                <code><a href="#actiongroupsmsreceiver">List[Action<wbr>Group<wbr>Sms<wbr>Receiver]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `sms_receiver` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">tags</td>
            <td class="align-top">
                
                <code>Dict[str, str]</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A mapping of tags to assign to the resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">voice_<wbr>receivers</td>
            <td class="align-top">
                
                <code><a href="#actiongroupvoicereceiver">List[Action<wbr>Group<wbr>Voice<wbr>Receiver]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `voice_receiver` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">webhook_<wbr>receivers</td>
            <td class="align-top">
                
                <code><a href="#actiongroupwebhookreceiver">List[Action<wbr>Group<wbr>Webhook<wbr>Receiver]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `webhook_receiver` blocks as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}










## Supporting Types

#### ActionGroupArmRoleReceiver
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/input/#ActionGroupArmRoleReceiver">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/output/#ActionGroupArmRoleReceiver">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/monitoring?tab=doc#ActionGroupArmRoleReceiverArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/monitoring?tab=doc#ActionGroupArmRoleReceiverOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Monitoring.ActionGroupArmRoleReceiverArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Monitoring.ActionGroupArmRoleReceiver.html">output</a> API doc for this type.
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
            <td class="align-top">Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The name of the webhook receiver. Names must be unique (case-insensitive) across all receivers within an action group.
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
The arm role id.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Use<wbr>Common<wbr>Alert<wbr>Schema</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Enables or disables the common alert schema.
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
            <td class="align-top">Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The name of the webhook receiver. Names must be unique (case-insensitive) across all receivers within an action group.
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
The arm role id.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Use<wbr>Common<wbr>Alert<wbr>Schema</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Enables or disables the common alert schema.
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
            <td class="align-top">name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The name of the webhook receiver. Names must be unique (case-insensitive) across all receivers within an action group.
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
The arm role id.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">use<wbr>Common<wbr>Alert<wbr>Schema</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Enables or disables the common alert schema.
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
            <td class="align-top">name</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The name of the webhook receiver. Names must be unique (case-insensitive) across all receivers within an action group.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">role<wbr>Id</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The arm role id.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">use<wbr>Common<wbr>Alert<wbr>Schema</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Enables or disables the common alert schema.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}





#### ActionGroupAutomationRunbookReceiver
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/input/#ActionGroupAutomationRunbookReceiver">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/output/#ActionGroupAutomationRunbookReceiver">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/monitoring?tab=doc#ActionGroupAutomationRunbookReceiverArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/monitoring?tab=doc#ActionGroupAutomationRunbookReceiverOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Monitoring.ActionGroupAutomationRunbookReceiverArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Monitoring.ActionGroupAutomationRunbookReceiver.html">output</a> API doc for this type.
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
            <td class="align-top">Automation<wbr>Account<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The automation account ID which holds this runbook and authenticates to Azure resources.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Is<wbr>Global<wbr>Runbook</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Indicates whether this instance is global runbook.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The name of the webhook receiver. Names must be unique (case-insensitive) across all receivers within an action group.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Runbook<wbr>Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The name for this runbook.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Service<wbr>Uri</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The URI where webhooks should be sent.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Use<wbr>Common<wbr>Alert<wbr>Schema</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Enables or disables the common alert schema.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Webhook<wbr>Resource<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The resource id for webhook linked to this runbook.
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
            <td class="align-top">Automation<wbr>Account<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The automation account ID which holds this runbook and authenticates to Azure resources.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Is<wbr>Global<wbr>Runbook</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Indicates whether this instance is global runbook.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The name of the webhook receiver. Names must be unique (case-insensitive) across all receivers within an action group.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Runbook<wbr>Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The name for this runbook.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Service<wbr>Uri</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The URI where webhooks should be sent.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Use<wbr>Common<wbr>Alert<wbr>Schema</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Enables or disables the common alert schema.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Webhook<wbr>Resource<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The resource id for webhook linked to this runbook.
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
            <td class="align-top">automation<wbr>Account<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The automation account ID which holds this runbook and authenticates to Azure resources.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">is<wbr>Global<wbr>Runbook</td>
            <td class="align-top">
                
                <code>boolean</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Indicates whether this instance is global runbook.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The name of the webhook receiver. Names must be unique (case-insensitive) across all receivers within an action group.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">runbook<wbr>Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The name for this runbook.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">service<wbr>Uri</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The URI where webhooks should be sent.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">use<wbr>Common<wbr>Alert<wbr>Schema</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Enables or disables the common alert schema.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">webhook<wbr>Resource<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The resource id for webhook linked to this runbook.
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
            <td class="align-top">automation<wbr>Account<wbr>Id</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The automation account ID which holds this runbook and authenticates to Azure resources.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">is<wbr>Global<wbr>Runbook</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
Indicates whether this instance is global runbook.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">name</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The name of the webhook receiver. Names must be unique (case-insensitive) across all receivers within an action group.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">runbook_<wbr>name</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The name for this runbook.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">service_<wbr>uri</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The URI where webhooks should be sent.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">use<wbr>Common<wbr>Alert<wbr>Schema</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Enables or disables the common alert schema.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">webhook<wbr>Resource<wbr>Id</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The resource id for webhook linked to this runbook.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}





#### ActionGroupAzureAppPushReceiver
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/input/#ActionGroupAzureAppPushReceiver">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/output/#ActionGroupAzureAppPushReceiver">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/monitoring?tab=doc#ActionGroupAzureAppPushReceiverArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/monitoring?tab=doc#ActionGroupAzureAppPushReceiverOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Monitoring.ActionGroupAzureAppPushReceiverArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Monitoring.ActionGroupAzureAppPushReceiver.html">output</a> API doc for this type.
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
            <td class="align-top">Email<wbr>Address</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The email address of this receiver.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The name of the webhook receiver. Names must be unique (case-insensitive) across all receivers within an action group.
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
            <td class="align-top">Email<wbr>Address</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The email address of this receiver.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The name of the webhook receiver. Names must be unique (case-insensitive) across all receivers within an action group.
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
            <td class="align-top">email<wbr>Address</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The email address of this receiver.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The name of the webhook receiver. Names must be unique (case-insensitive) across all receivers within an action group.
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
            <td class="align-top">email_<wbr>address</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The email address of this receiver.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">name</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The name of the webhook receiver. Names must be unique (case-insensitive) across all receivers within an action group.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}





#### ActionGroupAzureFunctionReceiver
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/input/#ActionGroupAzureFunctionReceiver">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/output/#ActionGroupAzureFunctionReceiver">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/monitoring?tab=doc#ActionGroupAzureFunctionReceiverArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/monitoring?tab=doc#ActionGroupAzureFunctionReceiverOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Monitoring.ActionGroupAzureFunctionReceiverArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Monitoring.ActionGroupAzureFunctionReceiver.html">output</a> API doc for this type.
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
            <td class="align-top">Function<wbr>App<wbr>Resource<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Function<wbr>Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The function name in the function app.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Http<wbr>Trigger<wbr>Url</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The http trigger url where http request sent to.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The name of the webhook receiver. Names must be unique (case-insensitive) across all receivers within an action group.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Use<wbr>Common<wbr>Alert<wbr>Schema</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Enables or disables the common alert schema.
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
            <td class="align-top">Function<wbr>App<wbr>Resource<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Function<wbr>Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The function name in the function app.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Http<wbr>Trigger<wbr>Url</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The http trigger url where http request sent to.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The name of the webhook receiver. Names must be unique (case-insensitive) across all receivers within an action group.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Use<wbr>Common<wbr>Alert<wbr>Schema</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Enables or disables the common alert schema.
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
            <td class="align-top">function<wbr>App<wbr>Resource<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">function<wbr>Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The function name in the function app.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">http<wbr>Trigger<wbr>Url</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The http trigger url where http request sent to.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The name of the webhook receiver. Names must be unique (case-insensitive) across all receivers within an action group.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">use<wbr>Common<wbr>Alert<wbr>Schema</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Enables or disables the common alert schema.
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
            <td class="align-top">function<wbr>App<wbr>Resource<wbr>Id</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">function<wbr>Name</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The function name in the function app.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">http<wbr>Trigger<wbr>Url</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The http trigger url where http request sent to.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">name</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The name of the webhook receiver. Names must be unique (case-insensitive) across all receivers within an action group.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">use<wbr>Common<wbr>Alert<wbr>Schema</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Enables or disables the common alert schema.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}





#### ActionGroupEmailReceiver
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/input/#ActionGroupEmailReceiver">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/output/#ActionGroupEmailReceiver">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/monitoring?tab=doc#ActionGroupEmailReceiverArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/monitoring?tab=doc#ActionGroupEmailReceiverOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Monitoring.ActionGroupEmailReceiverArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Monitoring.ActionGroupEmailReceiver.html">output</a> API doc for this type.
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
            <td class="align-top">Email<wbr>Address</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The email address of this receiver.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The name of the webhook receiver. Names must be unique (case-insensitive) across all receivers within an action group.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Use<wbr>Common<wbr>Alert<wbr>Schema</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Enables or disables the common alert schema.
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
            <td class="align-top">Email<wbr>Address</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The email address of this receiver.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The name of the webhook receiver. Names must be unique (case-insensitive) across all receivers within an action group.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Use<wbr>Common<wbr>Alert<wbr>Schema</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Enables or disables the common alert schema.
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
            <td class="align-top">email<wbr>Address</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The email address of this receiver.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The name of the webhook receiver. Names must be unique (case-insensitive) across all receivers within an action group.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">use<wbr>Common<wbr>Alert<wbr>Schema</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Enables or disables the common alert schema.
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
            <td class="align-top">email_<wbr>address</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The email address of this receiver.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">name</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The name of the webhook receiver. Names must be unique (case-insensitive) across all receivers within an action group.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">use<wbr>Common<wbr>Alert<wbr>Schema</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Enables or disables the common alert schema.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}





#### ActionGroupItsmReceiver
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/input/#ActionGroupItsmReceiver">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/output/#ActionGroupItsmReceiver">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/monitoring?tab=doc#ActionGroupItsmReceiverArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/monitoring?tab=doc#ActionGroupItsmReceiverOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Monitoring.ActionGroupItsmReceiverArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Monitoring.ActionGroupItsmReceiver.html">output</a> API doc for this type.
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
            <td class="align-top">Connection<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The unique connection identifier of the ITSM connection.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The name of the webhook receiver. Names must be unique (case-insensitive) across all receivers within an action group.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Region</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The region of the workspace.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Ticket<wbr>Configuration</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
A JSON blob for the configurations of the ITSM action. CreateMultipleWorkItems option will be part of this blob as well.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Workspace<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The Azure Log Analytics workspace ID where this connection is defined.
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
            <td class="align-top">Connection<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The unique connection identifier of the ITSM connection.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The name of the webhook receiver. Names must be unique (case-insensitive) across all receivers within an action group.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Region</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The region of the workspace.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Ticket<wbr>Configuration</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
A JSON blob for the configurations of the ITSM action. CreateMultipleWorkItems option will be part of this blob as well.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Workspace<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The Azure Log Analytics workspace ID where this connection is defined.
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
            <td class="align-top">connection<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The unique connection identifier of the ITSM connection.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The name of the webhook receiver. Names must be unique (case-insensitive) across all receivers within an action group.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">region</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The region of the workspace.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">ticket<wbr>Configuration</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
A JSON blob for the configurations of the ITSM action. CreateMultipleWorkItems option will be part of this blob as well.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">workspace<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The Azure Log Analytics workspace ID where this connection is defined.
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
            <td class="align-top">connection<wbr>Id</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The unique connection identifier of the ITSM connection.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">name</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The name of the webhook receiver. Names must be unique (case-insensitive) across all receivers within an action group.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">region</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The region of the workspace.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">ticket<wbr>Configuration</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
A JSON blob for the configurations of the ITSM action. CreateMultipleWorkItems option will be part of this blob as well.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">workspace_<wbr>id</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The Azure Log Analytics workspace ID where this connection is defined.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}





#### ActionGroupLogicAppReceiver
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/input/#ActionGroupLogicAppReceiver">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/output/#ActionGroupLogicAppReceiver">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/monitoring?tab=doc#ActionGroupLogicAppReceiverArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/monitoring?tab=doc#ActionGroupLogicAppReceiverOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Monitoring.ActionGroupLogicAppReceiverArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Monitoring.ActionGroupLogicAppReceiver.html">output</a> API doc for this type.
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
            <td class="align-top">Callback<wbr>Url</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The callback url where http request sent to.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The name of the webhook receiver. Names must be unique (case-insensitive) across all receivers within an action group.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Resource<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The Azure resource ID of the logic app.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Use<wbr>Common<wbr>Alert<wbr>Schema</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Enables or disables the common alert schema.
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
            <td class="align-top">Callback<wbr>Url</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The callback url where http request sent to.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The name of the webhook receiver. Names must be unique (case-insensitive) across all receivers within an action group.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Resource<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The Azure resource ID of the logic app.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Use<wbr>Common<wbr>Alert<wbr>Schema</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Enables or disables the common alert schema.
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
            <td class="align-top">callback<wbr>Url</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The callback url where http request sent to.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The name of the webhook receiver. Names must be unique (case-insensitive) across all receivers within an action group.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">resource<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The Azure resource ID of the logic app.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">use<wbr>Common<wbr>Alert<wbr>Schema</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Enables or disables the common alert schema.
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
            <td class="align-top">callback<wbr>Url</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The callback url where http request sent to.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">name</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The name of the webhook receiver. Names must be unique (case-insensitive) across all receivers within an action group.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">resource_<wbr>id</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The Azure resource ID of the logic app.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">use<wbr>Common<wbr>Alert<wbr>Schema</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Enables or disables the common alert schema.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}





#### ActionGroupSmsReceiver
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/input/#ActionGroupSmsReceiver">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/output/#ActionGroupSmsReceiver">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/monitoring?tab=doc#ActionGroupSmsReceiverArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/monitoring?tab=doc#ActionGroupSmsReceiverOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Monitoring.ActionGroupSmsReceiverArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Monitoring.ActionGroupSmsReceiver.html">output</a> API doc for this type.
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
            <td class="align-top">Country<wbr>Code</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The country code of the voice receiver.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The name of the webhook receiver. Names must be unique (case-insensitive) across all receivers within an action group.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Phone<wbr>Number</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The phone number of the voice receiver.
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
            <td class="align-top">Country<wbr>Code</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The country code of the voice receiver.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The name of the webhook receiver. Names must be unique (case-insensitive) across all receivers within an action group.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Phone<wbr>Number</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The phone number of the voice receiver.
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
            <td class="align-top">country<wbr>Code</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The country code of the voice receiver.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The name of the webhook receiver. Names must be unique (case-insensitive) across all receivers within an action group.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">phone<wbr>Number</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The phone number of the voice receiver.
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
            <td class="align-top">country<wbr>Code</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The country code of the voice receiver.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">name</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The name of the webhook receiver. Names must be unique (case-insensitive) across all receivers within an action group.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">phone<wbr>Number</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The phone number of the voice receiver.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}





#### ActionGroupVoiceReceiver
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/input/#ActionGroupVoiceReceiver">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/output/#ActionGroupVoiceReceiver">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/monitoring?tab=doc#ActionGroupVoiceReceiverArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/monitoring?tab=doc#ActionGroupVoiceReceiverOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Monitoring.ActionGroupVoiceReceiverArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Monitoring.ActionGroupVoiceReceiver.html">output</a> API doc for this type.
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
            <td class="align-top">Country<wbr>Code</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The country code of the voice receiver.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The name of the webhook receiver. Names must be unique (case-insensitive) across all receivers within an action group.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Phone<wbr>Number</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The phone number of the voice receiver.
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
            <td class="align-top">Country<wbr>Code</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The country code of the voice receiver.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The name of the webhook receiver. Names must be unique (case-insensitive) across all receivers within an action group.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Phone<wbr>Number</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The phone number of the voice receiver.
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
            <td class="align-top">country<wbr>Code</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The country code of the voice receiver.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The name of the webhook receiver. Names must be unique (case-insensitive) across all receivers within an action group.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">phone<wbr>Number</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The phone number of the voice receiver.
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
            <td class="align-top">country<wbr>Code</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The country code of the voice receiver.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">name</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The name of the webhook receiver. Names must be unique (case-insensitive) across all receivers within an action group.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">phone<wbr>Number</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The phone number of the voice receiver.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}





#### ActionGroupWebhookReceiver
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/input/#ActionGroupWebhookReceiver">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/output/#ActionGroupWebhookReceiver">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/monitoring?tab=doc#ActionGroupWebhookReceiverArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/monitoring?tab=doc#ActionGroupWebhookReceiverOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Monitoring.ActionGroupWebhookReceiverArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Monitoring.ActionGroupWebhookReceiver.html">output</a> API doc for this type.
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
            <td class="align-top">Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The name of the webhook receiver. Names must be unique (case-insensitive) across all receivers within an action group.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Service<wbr>Uri</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The URI where webhooks should be sent.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Use<wbr>Common<wbr>Alert<wbr>Schema</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Enables or disables the common alert schema.
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
            <td class="align-top">Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The name of the webhook receiver. Names must be unique (case-insensitive) across all receivers within an action group.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Service<wbr>Uri</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The URI where webhooks should be sent.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Use<wbr>Common<wbr>Alert<wbr>Schema</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Enables or disables the common alert schema.
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
            <td class="align-top">name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The name of the webhook receiver. Names must be unique (case-insensitive) across all receivers within an action group.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">service<wbr>Uri</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The URI where webhooks should be sent.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">use<wbr>Common<wbr>Alert<wbr>Schema</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Enables or disables the common alert schema.
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
            <td class="align-top">name</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The name of the webhook receiver. Names must be unique (case-insensitive) across all receivers within an action group.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">service_<wbr>uri</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The URI where webhooks should be sent.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">use<wbr>Common<wbr>Alert<wbr>Schema</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Enables or disables the common alert schema.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}








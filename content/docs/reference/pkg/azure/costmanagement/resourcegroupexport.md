
---
title: "ResourceGroupExport"
block_external_search_index: true
---
<style>
table td p { margin-top: 0; margin-bottom: 0; }
</style>

Manages an Azure Cost Management Export for a Resource Group.

> This content is derived from https://github.com/terraform-providers/terraform-provider-azurerm/blob/master/website/docs/r/cost_management_export_resource_group.html.markdown.



## Create a ResourceGroupExport Resource

{{< langchoose csharp nojavascript >}}

<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/azure/costmanagement/#ResourceGroupExport">ResourceGroupExport</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/azure/costmanagement/#ResourceGroupExportArgs">ResourceGroupExportArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">ResourceGroupExport</span><span class="p">(resource_name, opts=None, </span>active=None<span class="p">, </span>delivery_info=None<span class="p">, </span>name=None<span class="p">, </span>query=None<span class="p">, </span>recurrence_period_end=None<span class="p">, </span>recurrence_period_start=None<span class="p">, </span>recurrence_type=None<span class="p">, </span>resource_group_id=None<span class="p">, __props__=None);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewResourceGroupExport<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/costmanagement?tab=doc#ResourceGroupExportArgs">ResourceGroupExportArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/costmanagement?tab=doc#ResourceGroupExport">ResourceGroupExport</a></span>, error)</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Costmanagement.ResourceGroupExport.html">ResourceGroupExport</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Costmanagement.ResourceGroupExportArgs.html">ResourceGroupExportArgs</a></span> <span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>

Creates a ResourceGroupExport resource with the given unique name, arguments, and options.

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
            <td class="align-top">Active</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Is the cost management export active? Default is `true`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Delivery<wbr>Info</td>
            <td class="align-top">
                
                <code><a href="#resourcegroupexportdeliveryinfo">Resource<wbr>Group<wbr>Export<wbr>Delivery<wbr>Info<wbr>Args</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
A `delivery_info` block as defined below.
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
Specifies the name of the Cost Management Export. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Query</td>
            <td class="align-top">
                
                <code><a href="#resourcegroupexportquery">Resource<wbr>Group<wbr>Export<wbr>Query<wbr>Args</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
A `query` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Recurrence<wbr>Period<wbr>End</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The date the export will stop capturing information. 
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Recurrence<wbr>Period<wbr>Start</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The date the export will start capturing information.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Recurrence<wbr>Type</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
How often the requested information will be exported. Valid values include `Annually`, `Daily`, `Monthly`, `Weekly`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Resource<wbr>Group<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The id of the resource group in which to export information.
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
            <td class="align-top">Active</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Is the cost management export active? Default is `true`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Delivery<wbr>Info</td>
            <td class="align-top">
                
                <code><a href="#resourcegroupexportdeliveryinfo">Resource<wbr>Group<wbr>Export<wbr>Delivery<wbr>Info</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
A `delivery_info` block as defined below.
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
Specifies the name of the Cost Management Export. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Query</td>
            <td class="align-top">
                
                <code><a href="#resourcegroupexportquery">Resource<wbr>Group<wbr>Export<wbr>Query</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
A `query` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Recurrence<wbr>Period<wbr>End</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The date the export will stop capturing information. 
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Recurrence<wbr>Period<wbr>Start</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The date the export will start capturing information.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Recurrence<wbr>Type</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
How often the requested information will be exported. Valid values include `Annually`, `Daily`, `Monthly`, `Weekly`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Resource<wbr>Group<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The id of the resource group in which to export information.
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
            <td class="align-top">active</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Is the cost management export active? Default is `true`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">delivery<wbr>Info</td>
            <td class="align-top">
                
                <code><a href="#resourcegroupexportdeliveryinfo">Resource<wbr>Group<wbr>Export<wbr>Delivery<wbr>Info</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
A `delivery_info` block as defined below.
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
Specifies the name of the Cost Management Export. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">query</td>
            <td class="align-top">
                
                <code><a href="#resourcegroupexportquery">Resource<wbr>Group<wbr>Export<wbr>Query</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
A `query` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">recurrence<wbr>Period<wbr>End</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The date the export will stop capturing information. 
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">recurrence<wbr>Period<wbr>Start</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The date the export will start capturing information.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">recurrence<wbr>Type</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
How often the requested information will be exported. Valid values include `Annually`, `Daily`, `Monthly`, `Weekly`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">resource<wbr>Group<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The id of the resource group in which to export information.
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
            <td class="align-top">active</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Is the cost management export active? Default is `true`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">delivery_<wbr>info</td>
            <td class="align-top">
                
                <code><a href="#resourcegroupexportdeliveryinfo">Dict[Resource<wbr>Group<wbr>Export<wbr>Delivery<wbr>Info]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
A `delivery_info` block as defined below.
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
Specifies the name of the Cost Management Export. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">query</td>
            <td class="align-top">
                
                <code><a href="#resourcegroupexportquery">Dict[Resource<wbr>Group<wbr>Export<wbr>Query]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
A `query` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">recurrence_<wbr>period_<wbr>end</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The date the export will stop capturing information. 
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">recurrence_<wbr>period_<wbr>start</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The date the export will start capturing information.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">recurrence_<wbr>type</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
How often the requested information will be exported. Valid values include `Annually`, `Daily`, `Monthly`, `Weekly`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">resource_<wbr>group_<wbr>id</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The id of the resource group in which to export information.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}







## ResourceGroupExport Output Properties

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
            <td class="align-top">Active</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} Is the cost management export active? Default is `true`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Delivery<wbr>Info</td>
            <td class="align-top">
                
                <code><a href="#resourcegroupexportdeliveryinfo">Resource<wbr>Group<wbr>Export<wbr>Delivery<wbr>Info</a></code>
            </td>
            <td class="align-top">{{% md %}} A `delivery_info` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Specifies the name of the Cost Management Export. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Query</td>
            <td class="align-top">
                
                <code><a href="#resourcegroupexportquery">Resource<wbr>Group<wbr>Export<wbr>Query</a></code>
            </td>
            <td class="align-top">{{% md %}} A `query` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Recurrence<wbr>Period<wbr>End</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The date the export will stop capturing information. 
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Recurrence<wbr>Period<wbr>Start</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The date the export will start capturing information.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Recurrence<wbr>Type</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} How often the requested information will be exported. Valid values include `Annually`, `Daily`, `Monthly`, `Weekly`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Resource<wbr>Group<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The id of the resource group in which to export information.
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
            <td class="align-top">Active</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} Is the cost management export active? Default is `true`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Delivery<wbr>Info</td>
            <td class="align-top">
                
                <code><a href="#resourcegroupexportdeliveryinfo">Resource<wbr>Group<wbr>Export<wbr>Delivery<wbr>Info</a></code>
            </td>
            <td class="align-top">{{% md %}} A `delivery_info` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Specifies the name of the Cost Management Export. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Query</td>
            <td class="align-top">
                
                <code><a href="#resourcegroupexportquery">Resource<wbr>Group<wbr>Export<wbr>Query</a></code>
            </td>
            <td class="align-top">{{% md %}} A `query` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Recurrence<wbr>Period<wbr>End</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The date the export will stop capturing information. 
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Recurrence<wbr>Period<wbr>Start</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The date the export will start capturing information.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Recurrence<wbr>Type</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} How often the requested information will be exported. Valid values include `Annually`, `Daily`, `Monthly`, `Weekly`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Resource<wbr>Group<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The id of the resource group in which to export information.
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
            <td class="align-top">active</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} Is the cost management export active? Default is `true`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">delivery<wbr>Info</td>
            <td class="align-top">
                
                <code><a href="#resourcegroupexportdeliveryinfo">Resource<wbr>Group<wbr>Export<wbr>Delivery<wbr>Info</a></code>
            </td>
            <td class="align-top">{{% md %}} A `delivery_info` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Specifies the name of the Cost Management Export. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">query</td>
            <td class="align-top">
                
                <code><a href="#resourcegroupexportquery">Resource<wbr>Group<wbr>Export<wbr>Query</a></code>
            </td>
            <td class="align-top">{{% md %}} A `query` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">recurrence<wbr>Period<wbr>End</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The date the export will stop capturing information. 
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">recurrence<wbr>Period<wbr>Start</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The date the export will start capturing information.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">recurrence<wbr>Type</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} How often the requested information will be exported. Valid values include `Annually`, `Daily`, `Monthly`, `Weekly`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">resource<wbr>Group<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The id of the resource group in which to export information.
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
            <td class="align-top">active</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} Is the cost management export active? Default is `true`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">delivery_<wbr>info</td>
            <td class="align-top">
                
                <code><a href="#resourcegroupexportdeliveryinfo">Dict[Resource<wbr>Group<wbr>Export<wbr>Delivery<wbr>Info]</a></code>
            </td>
            <td class="align-top">{{% md %}} A `delivery_info` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">name</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} Specifies the name of the Cost Management Export. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">query</td>
            <td class="align-top">
                
                <code><a href="#resourcegroupexportquery">Dict[Resource<wbr>Group<wbr>Export<wbr>Query]</a></code>
            </td>
            <td class="align-top">{{% md %}} A `query` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">recurrence_<wbr>period_<wbr>end</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The date the export will stop capturing information. 
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">recurrence_<wbr>period_<wbr>start</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The date the export will start capturing information.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">recurrence_<wbr>type</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} How often the requested information will be exported. Valid values include `Annually`, `Daily`, `Monthly`, `Weekly`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">resource_<wbr>group_<wbr>id</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The id of the resource group in which to export information.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}








## Look up an Existing ResourceGroupExport Resource

{{< langchoose csharp nojavascript >}}

<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">pulumi.Input&lt;pulumi.ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/azure/costmanagement/#ResourceGroupExportState">ResourceGroupExportState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/azure/costmanagement/#ResourceGroupExport">ResourceGroupExport</a></span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>active=None<span class="p">, </span>delivery_info=None<span class="p">, </span>name=None<span class="p">, </span>query=None<span class="p">, </span>recurrence_period_end=None<span class="p">, </span>recurrence_period_start=None<span class="p">, </span>recurrence_type=None<span class="p">, </span>resource_group_id=None<span class="p">, __props__=None);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetResourceGroupExport<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">pulumi.IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/costmanagement?tab=doc#ResourceGroupExportState">ResourceGroupExportState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/costmanagement?tab=doc#ResourceGroupExport">ResourceGroupExport</a></span>, error)</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Costmanagement.ResourceGroupExport.html">ResourceGroupExport</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Pulumi.Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Costmanagement.ResourceGroupExportState.html">ResourceGroupExportState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>

Get an existing ResourceGroupExport resource's state with the given name, ID, and optional extra properties used to qualify the lookup.

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
            <td class="align-top">Active</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Is the cost management export active? Default is `true`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Delivery<wbr>Info</td>
            <td class="align-top">
                
                <code><a href="#resourcegroupexportdeliveryinfo">Resource<wbr>Group<wbr>Export<wbr>Delivery<wbr>Info<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `delivery_info` block as defined below.
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
Specifies the name of the Cost Management Export. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Query</td>
            <td class="align-top">
                
                <code><a href="#resourcegroupexportquery">Resource<wbr>Group<wbr>Export<wbr>Query<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `query` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Recurrence<wbr>Period<wbr>End</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The date the export will stop capturing information. 
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Recurrence<wbr>Period<wbr>Start</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The date the export will start capturing information.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Recurrence<wbr>Type</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
How often the requested information will be exported. Valid values include `Annually`, `Daily`, `Monthly`, `Weekly`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Resource<wbr>Group<wbr>Id</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The id of the resource group in which to export information.
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
            <td class="align-top">Active</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Is the cost management export active? Default is `true`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Delivery<wbr>Info</td>
            <td class="align-top">
                
                <code><a href="#resourcegroupexportdeliveryinfo">*Resource<wbr>Group<wbr>Export<wbr>Delivery<wbr>Info</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `delivery_info` block as defined below.
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
Specifies the name of the Cost Management Export. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Query</td>
            <td class="align-top">
                
                <code><a href="#resourcegroupexportquery">*Resource<wbr>Group<wbr>Export<wbr>Query</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `query` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Recurrence<wbr>Period<wbr>End</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The date the export will stop capturing information. 
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Recurrence<wbr>Period<wbr>Start</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The date the export will start capturing information.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Recurrence<wbr>Type</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
How often the requested information will be exported. Valid values include `Annually`, `Daily`, `Monthly`, `Weekly`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Resource<wbr>Group<wbr>Id</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The id of the resource group in which to export information.
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
            <td class="align-top">active</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Is the cost management export active? Default is `true`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">delivery<wbr>Info</td>
            <td class="align-top">
                
                <code><a href="#resourcegroupexportdeliveryinfo">Resource<wbr>Group<wbr>Export<wbr>Delivery<wbr>Info?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `delivery_info` block as defined below.
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
Specifies the name of the Cost Management Export. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">query</td>
            <td class="align-top">
                
                <code><a href="#resourcegroupexportquery">Resource<wbr>Group<wbr>Export<wbr>Query?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `query` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">recurrence<wbr>Period<wbr>End</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The date the export will stop capturing information. 
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">recurrence<wbr>Period<wbr>Start</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The date the export will start capturing information.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">recurrence<wbr>Type</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
How often the requested information will be exported. Valid values include `Annually`, `Daily`, `Monthly`, `Weekly`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">resource<wbr>Group<wbr>Id</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The id of the resource group in which to export information.
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
            <td class="align-top">active</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Is the cost management export active? Default is `true`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">delivery_<wbr>info</td>
            <td class="align-top">
                
                <code><a href="#resourcegroupexportdeliveryinfo">Dict[Resource<wbr>Group<wbr>Export<wbr>Delivery<wbr>Info]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `delivery_info` block as defined below.
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
Specifies the name of the Cost Management Export. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">query</td>
            <td class="align-top">
                
                <code><a href="#resourcegroupexportquery">Dict[Resource<wbr>Group<wbr>Export<wbr>Query]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A `query` block as defined below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">recurrence_<wbr>period_<wbr>end</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The date the export will stop capturing information. 
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">recurrence_<wbr>period_<wbr>start</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The date the export will start capturing information.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">recurrence_<wbr>type</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
How often the requested information will be exported. Valid values include `Annually`, `Daily`, `Monthly`, `Weekly`.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">resource_<wbr>group_<wbr>id</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The id of the resource group in which to export information.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}










## Supporting Types

#### ResourceGroupExportDeliveryInfo
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/input/#ResourceGroupExportDeliveryInfo">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/output/#ResourceGroupExportDeliveryInfo">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/costmanagement?tab=doc#ResourceGroupExportDeliveryInfoArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/costmanagement?tab=doc#ResourceGroupExportDeliveryInfoOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Costmanagement.ResourceGroupExportDeliveryInfoArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Costmanagement.ResourceGroupExportDeliveryInfo.html">output</a> API doc for this type.
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
            <td class="align-top">Container<wbr>Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Root<wbr>Folder<wbr>Path</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Storage<wbr>Account<wbr>Id</td>
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
            <td class="align-top">Container<wbr>Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Root<wbr>Folder<wbr>Path</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Storage<wbr>Account<wbr>Id</td>
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
            <td class="align-top">container<wbr>Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">root<wbr>Folder<wbr>Path</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">storage<wbr>Account<wbr>Id</td>
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
            <td class="align-top">container_<wbr>name</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">root<wbr>Folder<wbr>Path</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">storage_<wbr>account_<wbr>id</td>
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





#### ResourceGroupExportQuery
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/input/#ResourceGroupExportQuery">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/output/#ResourceGroupExportQuery">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/costmanagement?tab=doc#ResourceGroupExportQueryArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/costmanagement?tab=doc#ResourceGroupExportQueryOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Costmanagement.ResourceGroupExportQueryArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Costmanagement.ResourceGroupExportQuery.html">output</a> API doc for this type.
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
            <td class="align-top">Time<wbr>Frame</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Type</td>
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
            <td class="align-top">Time<wbr>Frame</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Type</td>
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
            <td class="align-top">time<wbr>Frame</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">type</td>
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
            <td class="align-top">time<wbr>Frame</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">type</td>
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








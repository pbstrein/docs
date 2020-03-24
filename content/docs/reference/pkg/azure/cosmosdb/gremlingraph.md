
---
title: "GremlinGraph"
block_external_search_index: true
---
<style>
table td p { margin-top: 0; margin-bottom: 0; }
</style>

Manages a Gremlin Graph within a Cosmos DB Account.

> This content is derived from https://github.com/terraform-providers/terraform-provider-azurerm/blob/master/website/docs/r/cosmosdb_gremlin_graph.html.markdown.



## Create a GremlinGraph Resource

{{< langchoose csharp nojavascript >}}

<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/azure/cosmosdb/#GremlinGraph">GremlinGraph</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/azure/cosmosdb/#GremlinGraphArgs">GremlinGraphArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">GremlinGraph</span><span class="p">(resource_name, opts=None, </span>account_name=None<span class="p">, </span>conflict_resolution_policies=None<span class="p">, </span>database_name=None<span class="p">, </span>index_policies=None<span class="p">, </span>name=None<span class="p">, </span>partition_key_path=None<span class="p">, </span>resource_group_name=None<span class="p">, </span>throughput=None<span class="p">, </span>unique_keys=None<span class="p">, __props__=None);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewGremlinGraph<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/cosmosdb?tab=doc#GremlinGraphArgs">GremlinGraphArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/cosmosdb?tab=doc#GremlinGraph">GremlinGraph</a></span>, error)</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Cosmosdb.GremlinGraph.html">GremlinGraph</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Cosmosdb.GremlinGraphArgs.html">GremlinGraphArgs</a></span> <span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>

Creates a GremlinGraph resource with the given unique name, arguments, and options.

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
            <td class="align-top">Account<wbr>Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The name of the CosmosDB Account to create the Gremlin Graph within. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Conflict<wbr>Resolution<wbr>Policies</td>
            <td class="align-top">
                
                <code><a href="#gremlingraphconflictresolutionpolicy">List&lt;Gremlin<wbr>Graph<wbr>Conflict<wbr>Resolution<wbr>Policy<wbr>Args&gt;</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The conflict resolution policy for the graph. One or more `conflict_resolution_policy` blocks as defined below. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Database<wbr>Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The name of the Cosmos DB Graph Database in which the Cosmos DB Gremlin Graph is created. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Index<wbr>Policies</td>
            <td class="align-top">
                
                <code><a href="#gremlingraphindexpolicy">List&lt;Gremlin<wbr>Graph<wbr>Index<wbr>Policy<wbr>Args&gt;</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The configuration of the indexing policy. One or more `index_policy` blocks as defined below. Changing this forces a new resource to be created.
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
Specifies the name of the Cosmos DB Gremlin Graph. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Partition<wbr>Key<wbr>Path</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Define a partition key. Changing this forces a new resource to be created.
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
The name of the resource group in which the Cosmos DB Gremlin Graph is created. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Throughput</td>
            <td class="align-top">
                
                <code>int?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The throughput of the Gremlin database (RU/s). Must be set in increments of `100`. The minimum value is `400`. This must be set upon database creation otherwise it cannot be updated without a manual resource destroy-apply.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Unique<wbr>Keys</td>
            <td class="align-top">
                
                <code><a href="#gremlingraphuniquekey">List&lt;Gremlin<wbr>Graph<wbr>Unique<wbr>Key<wbr>Args&gt;?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `unique_key` blocks as defined below. Changing this forces a new resource to be created.
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
            <td class="align-top">Account<wbr>Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The name of the CosmosDB Account to create the Gremlin Graph within. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Conflict<wbr>Resolution<wbr>Policies</td>
            <td class="align-top">
                
                <code><a href="#gremlingraphconflictresolutionpolicy">[]Gremlin<wbr>Graph<wbr>Conflict<wbr>Resolution<wbr>Policy</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The conflict resolution policy for the graph. One or more `conflict_resolution_policy` blocks as defined below. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Database<wbr>Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The name of the Cosmos DB Graph Database in which the Cosmos DB Gremlin Graph is created. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Index<wbr>Policies</td>
            <td class="align-top">
                
                <code><a href="#gremlingraphindexpolicy">[]Gremlin<wbr>Graph<wbr>Index<wbr>Policy</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The configuration of the indexing policy. One or more `index_policy` blocks as defined below. Changing this forces a new resource to be created.
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
Specifies the name of the Cosmos DB Gremlin Graph. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Partition<wbr>Key<wbr>Path</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Define a partition key. Changing this forces a new resource to be created.
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
The name of the resource group in which the Cosmos DB Gremlin Graph is created. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Throughput</td>
            <td class="align-top">
                
                <code>*int</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The throughput of the Gremlin database (RU/s). Must be set in increments of `100`. The minimum value is `400`. This must be set upon database creation otherwise it cannot be updated without a manual resource destroy-apply.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Unique<wbr>Keys</td>
            <td class="align-top">
                
                <code><a href="#gremlingraphuniquekey">[]Gremlin<wbr>Graph<wbr>Unique<wbr>Key</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `unique_key` blocks as defined below. Changing this forces a new resource to be created.
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
            <td class="align-top">account<wbr>Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The name of the CosmosDB Account to create the Gremlin Graph within. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">conflict<wbr>Resolution<wbr>Policies</td>
            <td class="align-top">
                
                <code><a href="#gremlingraphconflictresolutionpolicy">Gremlin<wbr>Graph<wbr>Conflict<wbr>Resolution<wbr>Policy[]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The conflict resolution policy for the graph. One or more `conflict_resolution_policy` blocks as defined below. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">database<wbr>Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The name of the Cosmos DB Graph Database in which the Cosmos DB Gremlin Graph is created. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">index<wbr>Policies</td>
            <td class="align-top">
                
                <code><a href="#gremlingraphindexpolicy">Gremlin<wbr>Graph<wbr>Index<wbr>Policy[]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The configuration of the indexing policy. One or more `index_policy` blocks as defined below. Changing this forces a new resource to be created.
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
Specifies the name of the Cosmos DB Gremlin Graph. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">partition<wbr>Key<wbr>Path</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Define a partition key. Changing this forces a new resource to be created.
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
The name of the resource group in which the Cosmos DB Gremlin Graph is created. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">throughput</td>
            <td class="align-top">
                
                <code>number?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The throughput of the Gremlin database (RU/s). Must be set in increments of `100`. The minimum value is `400`. This must be set upon database creation otherwise it cannot be updated without a manual resource destroy-apply.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">unique<wbr>Keys</td>
            <td class="align-top">
                
                <code><a href="#gremlingraphuniquekey">Gremlin<wbr>Graph<wbr>Unique<wbr>Key[]?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `unique_key` blocks as defined below. Changing this forces a new resource to be created.
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
            <td class="align-top">account_<wbr>name</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The name of the CosmosDB Account to create the Gremlin Graph within. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">conflict_<wbr>resolution_<wbr>policies</td>
            <td class="align-top">
                
                <code><a href="#gremlingraphconflictresolutionpolicy">List[Gremlin<wbr>Graph<wbr>Conflict<wbr>Resolution<wbr>Policy]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The conflict resolution policy for the graph. One or more `conflict_resolution_policy` blocks as defined below. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">database_<wbr>name</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The name of the Cosmos DB Graph Database in which the Cosmos DB Gremlin Graph is created. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">index_<wbr>policies</td>
            <td class="align-top">
                
                <code><a href="#gremlingraphindexpolicy">List[Gremlin<wbr>Graph<wbr>Index<wbr>Policy]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The configuration of the indexing policy. One or more `index_policy` blocks as defined below. Changing this forces a new resource to be created.
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
Specifies the name of the Cosmos DB Gremlin Graph. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">partition_<wbr>key_<wbr>path</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Define a partition key. Changing this forces a new resource to be created.
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
The name of the resource group in which the Cosmos DB Gremlin Graph is created. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">throughput</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The throughput of the Gremlin database (RU/s). Must be set in increments of `100`. The minimum value is `400`. This must be set upon database creation otherwise it cannot be updated without a manual resource destroy-apply.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">unique_<wbr>keys</td>
            <td class="align-top">
                
                <code><a href="#gremlingraphuniquekey">List[Gremlin<wbr>Graph<wbr>Unique<wbr>Key]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `unique_key` blocks as defined below. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}







## GremlinGraph Output Properties

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
            <td class="align-top">Account<wbr>Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The name of the CosmosDB Account to create the Gremlin Graph within. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Conflict<wbr>Resolution<wbr>Policies</td>
            <td class="align-top">
                
                <code><a href="#gremlingraphconflictresolutionpolicy">List&lt;Gremlin<wbr>Graph<wbr>Conflict<wbr>Resolution<wbr>Policy&gt;</a></code>
            </td>
            <td class="align-top">{{% md %}} The conflict resolution policy for the graph. One or more `conflict_resolution_policy` blocks as defined below. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Database<wbr>Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The name of the Cosmos DB Graph Database in which the Cosmos DB Gremlin Graph is created. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Index<wbr>Policies</td>
            <td class="align-top">
                
                <code><a href="#gremlingraphindexpolicy">List&lt;Gremlin<wbr>Graph<wbr>Index<wbr>Policy&gt;</a></code>
            </td>
            <td class="align-top">{{% md %}} The configuration of the indexing policy. One or more `index_policy` blocks as defined below. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Specifies the name of the Cosmos DB Gremlin Graph. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Partition<wbr>Key<wbr>Path</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} Define a partition key. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Resource<wbr>Group<wbr>Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The name of the resource group in which the Cosmos DB Gremlin Graph is created. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Throughput</td>
            <td class="align-top">
                
                <code>int</code>
            </td>
            <td class="align-top">{{% md %}} The throughput of the Gremlin database (RU/s). Must be set in increments of `100`. The minimum value is `400`. This must be set upon database creation otherwise it cannot be updated without a manual resource destroy-apply.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Unique<wbr>Keys</td>
            <td class="align-top">
                
                <code><a href="#gremlingraphuniquekey">List&lt;Gremlin<wbr>Graph<wbr>Unique<wbr>Key&gt;?</a></code>
            </td>
            <td class="align-top">{{% md %}} One or more `unique_key` blocks as defined below. Changing this forces a new resource to be created.
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
            <td class="align-top">Account<wbr>Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The name of the CosmosDB Account to create the Gremlin Graph within. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Conflict<wbr>Resolution<wbr>Policies</td>
            <td class="align-top">
                
                <code><a href="#gremlingraphconflictresolutionpolicy">[]Gremlin<wbr>Graph<wbr>Conflict<wbr>Resolution<wbr>Policy</a></code>
            </td>
            <td class="align-top">{{% md %}} The conflict resolution policy for the graph. One or more `conflict_resolution_policy` blocks as defined below. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Database<wbr>Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The name of the Cosmos DB Graph Database in which the Cosmos DB Gremlin Graph is created. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Index<wbr>Policies</td>
            <td class="align-top">
                
                <code><a href="#gremlingraphindexpolicy">[]Gremlin<wbr>Graph<wbr>Index<wbr>Policy</a></code>
            </td>
            <td class="align-top">{{% md %}} The configuration of the indexing policy. One or more `index_policy` blocks as defined below. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Specifies the name of the Cosmos DB Gremlin Graph. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Partition<wbr>Key<wbr>Path</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} Define a partition key. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Resource<wbr>Group<wbr>Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The name of the resource group in which the Cosmos DB Gremlin Graph is created. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Throughput</td>
            <td class="align-top">
                
                <code>int</code>
            </td>
            <td class="align-top">{{% md %}} The throughput of the Gremlin database (RU/s). Must be set in increments of `100`. The minimum value is `400`. This must be set upon database creation otherwise it cannot be updated without a manual resource destroy-apply.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Unique<wbr>Keys</td>
            <td class="align-top">
                
                <code><a href="#gremlingraphuniquekey">[]Gremlin<wbr>Graph<wbr>Unique<wbr>Key</a></code>
            </td>
            <td class="align-top">{{% md %}} One or more `unique_key` blocks as defined below. Changing this forces a new resource to be created.
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
            <td class="align-top">account<wbr>Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The name of the CosmosDB Account to create the Gremlin Graph within. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">conflict<wbr>Resolution<wbr>Policies</td>
            <td class="align-top">
                
                <code><a href="#gremlingraphconflictresolutionpolicy">Gremlin<wbr>Graph<wbr>Conflict<wbr>Resolution<wbr>Policy[]</a></code>
            </td>
            <td class="align-top">{{% md %}} The conflict resolution policy for the graph. One or more `conflict_resolution_policy` blocks as defined below. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">database<wbr>Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The name of the Cosmos DB Graph Database in which the Cosmos DB Gremlin Graph is created. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">index<wbr>Policies</td>
            <td class="align-top">
                
                <code><a href="#gremlingraphindexpolicy">Gremlin<wbr>Graph<wbr>Index<wbr>Policy[]</a></code>
            </td>
            <td class="align-top">{{% md %}} The configuration of the indexing policy. One or more `index_policy` blocks as defined below. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Specifies the name of the Cosmos DB Gremlin Graph. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">partition<wbr>Key<wbr>Path</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} Define a partition key. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">resource<wbr>Group<wbr>Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The name of the resource group in which the Cosmos DB Gremlin Graph is created. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">throughput</td>
            <td class="align-top">
                
                <code>number</code>
            </td>
            <td class="align-top">{{% md %}} The throughput of the Gremlin database (RU/s). Must be set in increments of `100`. The minimum value is `400`. This must be set upon database creation otherwise it cannot be updated without a manual resource destroy-apply.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">unique<wbr>Keys</td>
            <td class="align-top">
                
                <code><a href="#gremlingraphuniquekey">Gremlin<wbr>Graph<wbr>Unique<wbr>Key[]?</a></code>
            </td>
            <td class="align-top">{{% md %}} One or more `unique_key` blocks as defined below. Changing this forces a new resource to be created.
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
            <td class="align-top">account_<wbr>name</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The name of the CosmosDB Account to create the Gremlin Graph within. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">conflict_<wbr>resolution_<wbr>policies</td>
            <td class="align-top">
                
                <code><a href="#gremlingraphconflictresolutionpolicy">List[Gremlin<wbr>Graph<wbr>Conflict<wbr>Resolution<wbr>Policy]</a></code>
            </td>
            <td class="align-top">{{% md %}} The conflict resolution policy for the graph. One or more `conflict_resolution_policy` blocks as defined below. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">database_<wbr>name</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The name of the Cosmos DB Graph Database in which the Cosmos DB Gremlin Graph is created. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">index_<wbr>policies</td>
            <td class="align-top">
                
                <code><a href="#gremlingraphindexpolicy">List[Gremlin<wbr>Graph<wbr>Index<wbr>Policy]</a></code>
            </td>
            <td class="align-top">{{% md %}} The configuration of the indexing policy. One or more `index_policy` blocks as defined below. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">name</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} Specifies the name of the Cosmos DB Gremlin Graph. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">partition_<wbr>key_<wbr>path</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} Define a partition key. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">resource_<wbr>group_<wbr>name</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The name of the resource group in which the Cosmos DB Gremlin Graph is created. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">throughput</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} The throughput of the Gremlin database (RU/s). Must be set in increments of `100`. The minimum value is `400`. This must be set upon database creation otherwise it cannot be updated without a manual resource destroy-apply.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">unique_<wbr>keys</td>
            <td class="align-top">
                
                <code><a href="#gremlingraphuniquekey">List[Gremlin<wbr>Graph<wbr>Unique<wbr>Key]</a></code>
            </td>
            <td class="align-top">{{% md %}} One or more `unique_key` blocks as defined below. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}








## Look up an Existing GremlinGraph Resource

{{< langchoose csharp nojavascript >}}

<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">pulumi.Input&lt;pulumi.ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/azure/cosmosdb/#GremlinGraphState">GremlinGraphState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/azure/cosmosdb/#GremlinGraph">GremlinGraph</a></span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>account_name=None<span class="p">, </span>conflict_resolution_policies=None<span class="p">, </span>database_name=None<span class="p">, </span>index_policies=None<span class="p">, </span>name=None<span class="p">, </span>partition_key_path=None<span class="p">, </span>resource_group_name=None<span class="p">, </span>throughput=None<span class="p">, </span>unique_keys=None<span class="p">, __props__=None);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetGremlinGraph<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">pulumi.IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/cosmosdb?tab=doc#GremlinGraphState">GremlinGraphState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/cosmosdb?tab=doc#GremlinGraph">GremlinGraph</a></span>, error)</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Cosmosdb.GremlinGraph.html">GremlinGraph</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Pulumi.Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Cosmosdb.GremlinGraphState.html">GremlinGraphState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>

Get an existing GremlinGraph resource's state with the given name, ID, and optional extra properties used to qualify the lookup.

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
            <td class="align-top">Account<wbr>Name</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The name of the CosmosDB Account to create the Gremlin Graph within. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Conflict<wbr>Resolution<wbr>Policies</td>
            <td class="align-top">
                
                <code><a href="#gremlingraphconflictresolutionpolicy">List&lt;Gremlin<wbr>Graph<wbr>Conflict<wbr>Resolution<wbr>Policy<wbr>Args&gt;?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The conflict resolution policy for the graph. One or more `conflict_resolution_policy` blocks as defined below. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Database<wbr>Name</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The name of the Cosmos DB Graph Database in which the Cosmos DB Gremlin Graph is created. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Index<wbr>Policies</td>
            <td class="align-top">
                
                <code><a href="#gremlingraphindexpolicy">List&lt;Gremlin<wbr>Graph<wbr>Index<wbr>Policy<wbr>Args&gt;?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The configuration of the indexing policy. One or more `index_policy` blocks as defined below. Changing this forces a new resource to be created.
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
Specifies the name of the Cosmos DB Gremlin Graph. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Partition<wbr>Key<wbr>Path</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Define a partition key. Changing this forces a new resource to be created.
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
The name of the resource group in which the Cosmos DB Gremlin Graph is created. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Throughput</td>
            <td class="align-top">
                
                <code>int?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The throughput of the Gremlin database (RU/s). Must be set in increments of `100`. The minimum value is `400`. This must be set upon database creation otherwise it cannot be updated without a manual resource destroy-apply.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Unique<wbr>Keys</td>
            <td class="align-top">
                
                <code><a href="#gremlingraphuniquekey">List&lt;Gremlin<wbr>Graph<wbr>Unique<wbr>Key<wbr>Args&gt;?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `unique_key` blocks as defined below. Changing this forces a new resource to be created.
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
            <td class="align-top">Account<wbr>Name</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The name of the CosmosDB Account to create the Gremlin Graph within. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Conflict<wbr>Resolution<wbr>Policies</td>
            <td class="align-top">
                
                <code><a href="#gremlingraphconflictresolutionpolicy">[]Gremlin<wbr>Graph<wbr>Conflict<wbr>Resolution<wbr>Policy</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The conflict resolution policy for the graph. One or more `conflict_resolution_policy` blocks as defined below. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Database<wbr>Name</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The name of the Cosmos DB Graph Database in which the Cosmos DB Gremlin Graph is created. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Index<wbr>Policies</td>
            <td class="align-top">
                
                <code><a href="#gremlingraphindexpolicy">[]Gremlin<wbr>Graph<wbr>Index<wbr>Policy</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The configuration of the indexing policy. One or more `index_policy` blocks as defined below. Changing this forces a new resource to be created.
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
Specifies the name of the Cosmos DB Gremlin Graph. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Partition<wbr>Key<wbr>Path</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Define a partition key. Changing this forces a new resource to be created.
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
The name of the resource group in which the Cosmos DB Gremlin Graph is created. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Throughput</td>
            <td class="align-top">
                
                <code>*int</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The throughput of the Gremlin database (RU/s). Must be set in increments of `100`. The minimum value is `400`. This must be set upon database creation otherwise it cannot be updated without a manual resource destroy-apply.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Unique<wbr>Keys</td>
            <td class="align-top">
                
                <code><a href="#gremlingraphuniquekey">[]Gremlin<wbr>Graph<wbr>Unique<wbr>Key</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `unique_key` blocks as defined below. Changing this forces a new resource to be created.
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
            <td class="align-top">account<wbr>Name</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The name of the CosmosDB Account to create the Gremlin Graph within. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">conflict<wbr>Resolution<wbr>Policies</td>
            <td class="align-top">
                
                <code><a href="#gremlingraphconflictresolutionpolicy">Gremlin<wbr>Graph<wbr>Conflict<wbr>Resolution<wbr>Policy[]?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The conflict resolution policy for the graph. One or more `conflict_resolution_policy` blocks as defined below. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">database<wbr>Name</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The name of the Cosmos DB Graph Database in which the Cosmos DB Gremlin Graph is created. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">index<wbr>Policies</td>
            <td class="align-top">
                
                <code><a href="#gremlingraphindexpolicy">Gremlin<wbr>Graph<wbr>Index<wbr>Policy[]?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The configuration of the indexing policy. One or more `index_policy` blocks as defined below. Changing this forces a new resource to be created.
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
Specifies the name of the Cosmos DB Gremlin Graph. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">partition<wbr>Key<wbr>Path</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Define a partition key. Changing this forces a new resource to be created.
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
The name of the resource group in which the Cosmos DB Gremlin Graph is created. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">throughput</td>
            <td class="align-top">
                
                <code>number?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The throughput of the Gremlin database (RU/s). Must be set in increments of `100`. The minimum value is `400`. This must be set upon database creation otherwise it cannot be updated without a manual resource destroy-apply.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">unique<wbr>Keys</td>
            <td class="align-top">
                
                <code><a href="#gremlingraphuniquekey">Gremlin<wbr>Graph<wbr>Unique<wbr>Key[]?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `unique_key` blocks as defined below. Changing this forces a new resource to be created.
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
            <td class="align-top">account_<wbr>name</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The name of the CosmosDB Account to create the Gremlin Graph within. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">conflict_<wbr>resolution_<wbr>policies</td>
            <td class="align-top">
                
                <code><a href="#gremlingraphconflictresolutionpolicy">List[Gremlin<wbr>Graph<wbr>Conflict<wbr>Resolution<wbr>Policy]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The conflict resolution policy for the graph. One or more `conflict_resolution_policy` blocks as defined below. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">database_<wbr>name</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The name of the Cosmos DB Graph Database in which the Cosmos DB Gremlin Graph is created. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">index_<wbr>policies</td>
            <td class="align-top">
                
                <code><a href="#gremlingraphindexpolicy">List[Gremlin<wbr>Graph<wbr>Index<wbr>Policy]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The configuration of the indexing policy. One or more `index_policy` blocks as defined below. Changing this forces a new resource to be created.
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
Specifies the name of the Cosmos DB Gremlin Graph. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">partition_<wbr>key_<wbr>path</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Define a partition key. Changing this forces a new resource to be created.
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
The name of the resource group in which the Cosmos DB Gremlin Graph is created. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">throughput</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The throughput of the Gremlin database (RU/s). Must be set in increments of `100`. The minimum value is `400`. This must be set upon database creation otherwise it cannot be updated without a manual resource destroy-apply.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">unique_<wbr>keys</td>
            <td class="align-top">
                
                <code><a href="#gremlingraphuniquekey">List[Gremlin<wbr>Graph<wbr>Unique<wbr>Key]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
One or more `unique_key` blocks as defined below. Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}










## Supporting Types

#### GremlinGraphConflictResolutionPolicy
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/input/#GremlinGraphConflictResolutionPolicy">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/output/#GremlinGraphConflictResolutionPolicy">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/cosmosdb?tab=doc#GremlinGraphConflictResolutionPolicyArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/cosmosdb?tab=doc#GremlinGraphConflictResolutionPolicyOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Cosmosdb.GremlinGraphConflictResolutionPolicyArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Cosmosdb.GremlinGraphConflictResolutionPolicy.html">output</a> API doc for this type.
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
            <td class="align-top">Conflict<wbr>Resolution<wbr>Path</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Conflict<wbr>Resolution<wbr>Procedure</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Mode</td>
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
            <td class="align-top">Conflict<wbr>Resolution<wbr>Path</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Conflict<wbr>Resolution<wbr>Procedure</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Mode</td>
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
            <td class="align-top">conflict<wbr>Resolution<wbr>Path</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">conflict<wbr>Resolution<wbr>Procedure</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">mode</td>
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
            <td class="align-top">conflict<wbr>Resolution<wbr>Path</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">conflict<wbr>Resolution<wbr>Procedure</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">mode</td>
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





#### GremlinGraphIndexPolicy
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/input/#GremlinGraphIndexPolicy">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/output/#GremlinGraphIndexPolicy">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/cosmosdb?tab=doc#GremlinGraphIndexPolicyArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/cosmosdb?tab=doc#GremlinGraphIndexPolicyOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Cosmosdb.GremlinGraphIndexPolicyArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Cosmosdb.GremlinGraphIndexPolicy.html">output</a> API doc for this type.
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
            <td class="align-top">Automatic</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Excluded<wbr>Paths</td>
            <td class="align-top">
                
                <code>List<string>?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Included<wbr>Paths</td>
            <td class="align-top">
                
                <code>List<string>?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Indexing<wbr>Mode</td>
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
            <td class="align-top">Automatic</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Excluded<wbr>Paths</td>
            <td class="align-top">
                
                <code>[]string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Included<wbr>Paths</td>
            <td class="align-top">
                
                <code>[]string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Indexing<wbr>Mode</td>
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
            <td class="align-top">automatic</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">excluded<wbr>Paths</td>
            <td class="align-top">
                
                <code>string[]?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">included<wbr>Paths</td>
            <td class="align-top">
                
                <code>string[]?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">indexing<wbr>Mode</td>
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
            <td class="align-top">automatic</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">excluded<wbr>Paths</td>
            <td class="align-top">
                
                <code>List[str]</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">included<wbr>Paths</td>
            <td class="align-top">
                
                <code>List[str]</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">indexing<wbr>Mode</td>
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





#### GremlinGraphUniqueKey
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/input/#GremlinGraphUniqueKey">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/azure/types/output/#GremlinGraphUniqueKey">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/cosmosdb?tab=doc#GremlinGraphUniqueKeyArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-azure/sdk/go/azure/cosmosdb?tab=doc#GremlinGraphUniqueKeyOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Cosmosdb.GremlinGraphUniqueKeyArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Azure/Pulumi.Azure.Cosmosdb.GremlinGraphUniqueKey.html">output</a> API doc for this type.
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
            <td class="align-top">Paths</td>
            <td class="align-top">
                
                <code>List<string></code>
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
            <td class="align-top">Paths</td>
            <td class="align-top">
                
                <code>[]string</code>
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
            <td class="align-top">paths</td>
            <td class="align-top">
                
                <code>string[]</code>
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
            <td class="align-top">paths</td>
            <td class="align-top">
                
                <code>List[str]</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}








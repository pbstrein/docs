
---
title: "Table"
block_external_search_index: true
---
<style>
table td p { margin-top: 0; margin-bottom: 0; }
</style>

Creates a table resource in a dataset for Google BigQuery. For more information see
[the official documentation](https://cloud.google.com/bigquery/docs/) and
[API](https://cloud.google.com/bigquery/docs/reference/rest/v2/tables).

> This content is derived from https://github.com/terraform-providers/terraform-provider-google/blob/master/website/docs/r/bigquery_table.html.markdown.



## Create a Table Resource

{{< langchoose csharp nojavascript >}}

<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/bigquery/#Table">Table</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/bigquery/#TableArgs">TableArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">Table</span><span class="p">(resource_name, opts=None, </span>clusterings=None<span class="p">, </span>dataset_id=None<span class="p">, </span>description=None<span class="p">, </span>encryption_configuration=None<span class="p">, </span>expiration_time=None<span class="p">, </span>external_data_configuration=None<span class="p">, </span>friendly_name=None<span class="p">, </span>labels=None<span class="p">, </span>project=None<span class="p">, </span>range_partitioning=None<span class="p">, </span>schema=None<span class="p">, </span>table_id=None<span class="p">, </span>time_partitioning=None<span class="p">, </span>view=None<span class="p">, __props__=None);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewTable<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/bigquery?tab=doc#TableArgs">TableArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/bigquery?tab=doc#Table">Table</a></span>, error)</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Bigquery.Table.html">Table</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Bigquery.TableArgs.html">TableArgs</a></span> <span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>

Creates a Table resource with the given unique name, arguments, and options.

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
            <td class="align-top">Clusterings</td>
            <td class="align-top">
                
                <code>List<string>?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Specifies column names to use for data clustering.
Up to four top-level columns are allowed, and should be specified in
descending priority order.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Dataset<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The dataset ID to create the table in.
Changing this forces a new resource to be created.
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
The field description.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Encryption<wbr>Configuration</td>
            <td class="align-top">
                
                <code><a href="#tableencryptionconfiguration">Table<wbr>Encryption<wbr>Configuration<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Specifies how the table should be encrypted.
If left blank, the table will be encrypted with a Google-managed key; that process
is transparent to the user.  Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Expiration<wbr>Time</td>
            <td class="align-top">
                
                <code>int?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The time when this table expires, in
milliseconds since the epoch. If not present, the table will persist
indefinitely. Expired tables will be deleted and their storage
reclaimed.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">External<wbr>Data<wbr>Configuration</td>
            <td class="align-top">
                
                <code><a href="#tableexternaldataconfiguration">Table<wbr>External<wbr>Data<wbr>Configuration<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Describes the data format,
location, and other properties of a table stored outside of BigQuery.
By defining these properties, the data source can then be queried as
if it were a standard BigQuery table. Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Friendly<wbr>Name</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A descriptive name for the table.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Labels</td>
            <td class="align-top">
                
                <code>Dictionary<string, string>?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A mapping of labels to assign to the resource.
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
The ID of the project in which the resource belongs. If it
is not provided, the provider project is used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Range<wbr>Partitioning</td>
            <td class="align-top">
                
                <code><a href="#tablerangepartitioning">Table<wbr>Range<wbr>Partitioning<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
If specified, configures range-based
partitioning for this table. Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Schema</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A JSON schema for the table. Schema is required
for CSV and JSON formats and is disallowed for Google Cloud
Bigtable, Cloud Datastore backups, and Avro formats when using
external tables. For more information see the
[BigQuery API documentation](https://cloud.google.com/bigquery/docs/reference/rest/v2/tables#resource).
~&gt;**NOTE**: Because this field expects a JSON string, any changes to the
string will create a diff, even if the JSON itself hasn&#39;t changed.
If the API returns a different value for the same schema, e.g. it
switched the order of values or replaced `STRUCT` field type with `RECORD`
field type, we currently cannot suppress the recurring diff this causes.
As a workaround, we recommend using the schema as returned by the API.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Table<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
A unique ID for the resource.
Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Time<wbr>Partitioning</td>
            <td class="align-top">
                
                <code><a href="#tabletimepartitioning">Table<wbr>Time<wbr>Partitioning<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
If specified, configures time-based
partitioning for this table. Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">View</td>
            <td class="align-top">
                
                <code><a href="#tableview">Table<wbr>View<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
If specified, configures this table as a view.
Structure is documented below.
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
            <td class="align-top">Clusterings</td>
            <td class="align-top">
                
                <code>[]string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Specifies column names to use for data clustering.
Up to four top-level columns are allowed, and should be specified in
descending priority order.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Dataset<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The dataset ID to create the table in.
Changing this forces a new resource to be created.
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
The field description.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Encryption<wbr>Configuration</td>
            <td class="align-top">
                
                <code><a href="#tableencryptionconfiguration">*Table<wbr>Encryption<wbr>Configuration</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Specifies how the table should be encrypted.
If left blank, the table will be encrypted with a Google-managed key; that process
is transparent to the user.  Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Expiration<wbr>Time</td>
            <td class="align-top">
                
                <code>*int</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The time when this table expires, in
milliseconds since the epoch. If not present, the table will persist
indefinitely. Expired tables will be deleted and their storage
reclaimed.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">External<wbr>Data<wbr>Configuration</td>
            <td class="align-top">
                
                <code><a href="#tableexternaldataconfiguration">*Table<wbr>External<wbr>Data<wbr>Configuration</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Describes the data format,
location, and other properties of a table stored outside of BigQuery.
By defining these properties, the data source can then be queried as
if it were a standard BigQuery table. Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Friendly<wbr>Name</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A descriptive name for the table.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Labels</td>
            <td class="align-top">
                
                <code>map[string]string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A mapping of labels to assign to the resource.
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
The ID of the project in which the resource belongs. If it
is not provided, the provider project is used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Range<wbr>Partitioning</td>
            <td class="align-top">
                
                <code><a href="#tablerangepartitioning">*Table<wbr>Range<wbr>Partitioning</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
If specified, configures range-based
partitioning for this table. Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Schema</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A JSON schema for the table. Schema is required
for CSV and JSON formats and is disallowed for Google Cloud
Bigtable, Cloud Datastore backups, and Avro formats when using
external tables. For more information see the
[BigQuery API documentation](https://cloud.google.com/bigquery/docs/reference/rest/v2/tables#resource).
~&gt;**NOTE**: Because this field expects a JSON string, any changes to the
string will create a diff, even if the JSON itself hasn&#39;t changed.
If the API returns a different value for the same schema, e.g. it
switched the order of values or replaced `STRUCT` field type with `RECORD`
field type, we currently cannot suppress the recurring diff this causes.
As a workaround, we recommend using the schema as returned by the API.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Table<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
A unique ID for the resource.
Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Time<wbr>Partitioning</td>
            <td class="align-top">
                
                <code><a href="#tabletimepartitioning">*Table<wbr>Time<wbr>Partitioning</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
If specified, configures time-based
partitioning for this table. Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">View</td>
            <td class="align-top">
                
                <code><a href="#tableview">*Table<wbr>View</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
If specified, configures this table as a view.
Structure is documented below.
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
            <td class="align-top">clusterings</td>
            <td class="align-top">
                
                <code>string[]?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Specifies column names to use for data clustering.
Up to four top-level columns are allowed, and should be specified in
descending priority order.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">dataset<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The dataset ID to create the table in.
Changing this forces a new resource to be created.
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
The field description.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">encryption<wbr>Configuration</td>
            <td class="align-top">
                
                <code><a href="#tableencryptionconfiguration">Table<wbr>Encryption<wbr>Configuration?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Specifies how the table should be encrypted.
If left blank, the table will be encrypted with a Google-managed key; that process
is transparent to the user.  Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">expiration<wbr>Time</td>
            <td class="align-top">
                
                <code>number?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The time when this table expires, in
milliseconds since the epoch. If not present, the table will persist
indefinitely. Expired tables will be deleted and their storage
reclaimed.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">external<wbr>Data<wbr>Configuration</td>
            <td class="align-top">
                
                <code><a href="#tableexternaldataconfiguration">Table<wbr>External<wbr>Data<wbr>Configuration?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Describes the data format,
location, and other properties of a table stored outside of BigQuery.
By defining these properties, the data source can then be queried as
if it were a standard BigQuery table. Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">friendly<wbr>Name</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A descriptive name for the table.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">labels</td>
            <td class="align-top">
                
                <code>{[key: string]: string}?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A mapping of labels to assign to the resource.
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
The ID of the project in which the resource belongs. If it
is not provided, the provider project is used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">range<wbr>Partitioning</td>
            <td class="align-top">
                
                <code><a href="#tablerangepartitioning">Table<wbr>Range<wbr>Partitioning?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
If specified, configures range-based
partitioning for this table. Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">schema</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A JSON schema for the table. Schema is required
for CSV and JSON formats and is disallowed for Google Cloud
Bigtable, Cloud Datastore backups, and Avro formats when using
external tables. For more information see the
[BigQuery API documentation](https://cloud.google.com/bigquery/docs/reference/rest/v2/tables#resource).
~&gt;**NOTE**: Because this field expects a JSON string, any changes to the
string will create a diff, even if the JSON itself hasn&#39;t changed.
If the API returns a different value for the same schema, e.g. it
switched the order of values or replaced `STRUCT` field type with `RECORD`
field type, we currently cannot suppress the recurring diff this causes.
As a workaround, we recommend using the schema as returned by the API.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">table<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
A unique ID for the resource.
Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">time<wbr>Partitioning</td>
            <td class="align-top">
                
                <code><a href="#tabletimepartitioning">Table<wbr>Time<wbr>Partitioning?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
If specified, configures time-based
partitioning for this table. Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">view</td>
            <td class="align-top">
                
                <code><a href="#tableview">Table<wbr>View?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
If specified, configures this table as a view.
Structure is documented below.
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
            <td class="align-top">clusterings</td>
            <td class="align-top">
                
                <code>List[str]</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Specifies column names to use for data clustering.
Up to four top-level columns are allowed, and should be specified in
descending priority order.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">dataset_<wbr>id</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The dataset ID to create the table in.
Changing this forces a new resource to be created.
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
The field description.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">encryption_<wbr>configuration</td>
            <td class="align-top">
                
                <code><a href="#tableencryptionconfiguration">Dict[Table<wbr>Encryption<wbr>Configuration]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Specifies how the table should be encrypted.
If left blank, the table will be encrypted with a Google-managed key; that process
is transparent to the user.  Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">expiration_<wbr>time</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The time when this table expires, in
milliseconds since the epoch. If not present, the table will persist
indefinitely. Expired tables will be deleted and their storage
reclaimed.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">external_<wbr>data_<wbr>configuration</td>
            <td class="align-top">
                
                <code><a href="#tableexternaldataconfiguration">Dict[Table<wbr>External<wbr>Data<wbr>Configuration]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Describes the data format,
location, and other properties of a table stored outside of BigQuery.
By defining these properties, the data source can then be queried as
if it were a standard BigQuery table. Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">friendly_<wbr>name</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A descriptive name for the table.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">labels</td>
            <td class="align-top">
                
                <code>Dict[str, str]</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A mapping of labels to assign to the resource.
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
The ID of the project in which the resource belongs. If it
is not provided, the provider project is used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">range_<wbr>partitioning</td>
            <td class="align-top">
                
                <code><a href="#tablerangepartitioning">Dict[Table<wbr>Range<wbr>Partitioning]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
If specified, configures range-based
partitioning for this table. Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">schema</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A JSON schema for the table. Schema is required
for CSV and JSON formats and is disallowed for Google Cloud
Bigtable, Cloud Datastore backups, and Avro formats when using
external tables. For more information see the
[BigQuery API documentation](https://cloud.google.com/bigquery/docs/reference/rest/v2/tables#resource).
~&gt;**NOTE**: Because this field expects a JSON string, any changes to the
string will create a diff, even if the JSON itself hasn&#39;t changed.
If the API returns a different value for the same schema, e.g. it
switched the order of values or replaced `STRUCT` field type with `RECORD`
field type, we currently cannot suppress the recurring diff this causes.
As a workaround, we recommend using the schema as returned by the API.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">table_<wbr>id</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
A unique ID for the resource.
Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">time_<wbr>partitioning</td>
            <td class="align-top">
                
                <code><a href="#tabletimepartitioning">Dict[Table<wbr>Time<wbr>Partitioning]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
If specified, configures time-based
partitioning for this table. Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">view</td>
            <td class="align-top">
                
                <code><a href="#tableview">Dict[Table<wbr>View]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
If specified, configures this table as a view.
Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}







## Table Output Properties

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
            <td class="align-top">Clusterings</td>
            <td class="align-top">
                
                <code>List<string>?</code>
            </td>
            <td class="align-top">{{% md %}} Specifies column names to use for data clustering.
Up to four top-level columns are allowed, and should be specified in
descending priority order.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Creation<wbr>Time</td>
            <td class="align-top">
                
                <code>int</code>
            </td>
            <td class="align-top">{{% md %}} The time when this table was created, in milliseconds since the epoch.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Dataset<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The dataset ID to create the table in.
Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Description</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} The field description.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Encryption<wbr>Configuration</td>
            <td class="align-top">
                
                <code><a href="#tableencryptionconfiguration">Table<wbr>Encryption<wbr>Configuration?</a></code>
            </td>
            <td class="align-top">{{% md %}} Specifies how the table should be encrypted.
If left blank, the table will be encrypted with a Google-managed key; that process
is transparent to the user.  Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Etag</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} A hash of the resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Expiration<wbr>Time</td>
            <td class="align-top">
                
                <code>int</code>
            </td>
            <td class="align-top">{{% md %}} The time when this table expires, in
milliseconds since the epoch. If not present, the table will persist
indefinitely. Expired tables will be deleted and their storage
reclaimed.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">External<wbr>Data<wbr>Configuration</td>
            <td class="align-top">
                
                <code><a href="#tableexternaldataconfiguration">Table<wbr>External<wbr>Data<wbr>Configuration?</a></code>
            </td>
            <td class="align-top">{{% md %}} Describes the data format,
location, and other properties of a table stored outside of BigQuery.
By defining these properties, the data source can then be queried as
if it were a standard BigQuery table. Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Friendly<wbr>Name</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} A descriptive name for the table.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Labels</td>
            <td class="align-top">
                
                <code>Dictionary<string, string>?</code>
            </td>
            <td class="align-top">{{% md %}} A mapping of labels to assign to the resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Last<wbr>Modified<wbr>Time</td>
            <td class="align-top">
                
                <code>int</code>
            </td>
            <td class="align-top">{{% md %}} The time when this table was last modified, in milliseconds since the epoch.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Location</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The geographic location where the table resides. This value is inherited from the dataset.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Num<wbr>Bytes</td>
            <td class="align-top">
                
                <code>int</code>
            </td>
            <td class="align-top">{{% md %}} The size of this table in bytes, excluding any data in the streaming buffer.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Num<wbr>Long<wbr>Term<wbr>Bytes</td>
            <td class="align-top">
                
                <code>int</code>
            </td>
            <td class="align-top">{{% md %}} The number of bytes in the table that are considered &#34;long-term storage&#34;.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Num<wbr>Rows</td>
            <td class="align-top">
                
                <code>int</code>
            </td>
            <td class="align-top">{{% md %}} The number of rows of data in this table, excluding any data in the streaming buffer.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Project</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The ID of the project in which the resource belongs. If it
is not provided, the provider project is used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Range<wbr>Partitioning</td>
            <td class="align-top">
                
                <code><a href="#tablerangepartitioning">Table<wbr>Range<wbr>Partitioning?</a></code>
            </td>
            <td class="align-top">{{% md %}} If specified, configures range-based
partitioning for this table. Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Schema</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} A JSON schema for the table. Schema is required
for CSV and JSON formats and is disallowed for Google Cloud
Bigtable, Cloud Datastore backups, and Avro formats when using
external tables. For more information see the
[BigQuery API documentation](https://cloud.google.com/bigquery/docs/reference/rest/v2/tables#resource).
~&gt;**NOTE**: Because this field expects a JSON string, any changes to the
string will create a diff, even if the JSON itself hasn&#39;t changed.
If the API returns a different value for the same schema, e.g. it
switched the order of values or replaced `STRUCT` field type with `RECORD`
field type, we currently cannot suppress the recurring diff this causes.
As a workaround, we recommend using the schema as returned by the API.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Self<wbr>Link</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The URI of the created resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Table<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} A unique ID for the resource.
Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Time<wbr>Partitioning</td>
            <td class="align-top">
                
                <code><a href="#tabletimepartitioning">Table<wbr>Time<wbr>Partitioning?</a></code>
            </td>
            <td class="align-top">{{% md %}} If specified, configures time-based
partitioning for this table. Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Type</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Describes the table type.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">View</td>
            <td class="align-top">
                
                <code><a href="#tableview">Table<wbr>View?</a></code>
            </td>
            <td class="align-top">{{% md %}} If specified, configures this table as a view.
Structure is documented below.
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
            <td class="align-top">Clusterings</td>
            <td class="align-top">
                
                <code>[]string</code>
            </td>
            <td class="align-top">{{% md %}} Specifies column names to use for data clustering.
Up to four top-level columns are allowed, and should be specified in
descending priority order.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Creation<wbr>Time</td>
            <td class="align-top">
                
                <code>int</code>
            </td>
            <td class="align-top">{{% md %}} The time when this table was created, in milliseconds since the epoch.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Dataset<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The dataset ID to create the table in.
Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Description</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} The field description.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Encryption<wbr>Configuration</td>
            <td class="align-top">
                
                <code><a href="#tableencryptionconfiguration">*Table<wbr>Encryption<wbr>Configuration</a></code>
            </td>
            <td class="align-top">{{% md %}} Specifies how the table should be encrypted.
If left blank, the table will be encrypted with a Google-managed key; that process
is transparent to the user.  Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Etag</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} A hash of the resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Expiration<wbr>Time</td>
            <td class="align-top">
                
                <code>int</code>
            </td>
            <td class="align-top">{{% md %}} The time when this table expires, in
milliseconds since the epoch. If not present, the table will persist
indefinitely. Expired tables will be deleted and their storage
reclaimed.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">External<wbr>Data<wbr>Configuration</td>
            <td class="align-top">
                
                <code><a href="#tableexternaldataconfiguration">*Table<wbr>External<wbr>Data<wbr>Configuration</a></code>
            </td>
            <td class="align-top">{{% md %}} Describes the data format,
location, and other properties of a table stored outside of BigQuery.
By defining these properties, the data source can then be queried as
if it were a standard BigQuery table. Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Friendly<wbr>Name</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} A descriptive name for the table.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Labels</td>
            <td class="align-top">
                
                <code>map[string]string</code>
            </td>
            <td class="align-top">{{% md %}} A mapping of labels to assign to the resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Last<wbr>Modified<wbr>Time</td>
            <td class="align-top">
                
                <code>int</code>
            </td>
            <td class="align-top">{{% md %}} The time when this table was last modified, in milliseconds since the epoch.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Location</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The geographic location where the table resides. This value is inherited from the dataset.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Num<wbr>Bytes</td>
            <td class="align-top">
                
                <code>int</code>
            </td>
            <td class="align-top">{{% md %}} The size of this table in bytes, excluding any data in the streaming buffer.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Num<wbr>Long<wbr>Term<wbr>Bytes</td>
            <td class="align-top">
                
                <code>int</code>
            </td>
            <td class="align-top">{{% md %}} The number of bytes in the table that are considered &#34;long-term storage&#34;.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Num<wbr>Rows</td>
            <td class="align-top">
                
                <code>int</code>
            </td>
            <td class="align-top">{{% md %}} The number of rows of data in this table, excluding any data in the streaming buffer.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Project</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The ID of the project in which the resource belongs. If it
is not provided, the provider project is used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Range<wbr>Partitioning</td>
            <td class="align-top">
                
                <code><a href="#tablerangepartitioning">*Table<wbr>Range<wbr>Partitioning</a></code>
            </td>
            <td class="align-top">{{% md %}} If specified, configures range-based
partitioning for this table. Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Schema</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} A JSON schema for the table. Schema is required
for CSV and JSON formats and is disallowed for Google Cloud
Bigtable, Cloud Datastore backups, and Avro formats when using
external tables. For more information see the
[BigQuery API documentation](https://cloud.google.com/bigquery/docs/reference/rest/v2/tables#resource).
~&gt;**NOTE**: Because this field expects a JSON string, any changes to the
string will create a diff, even if the JSON itself hasn&#39;t changed.
If the API returns a different value for the same schema, e.g. it
switched the order of values or replaced `STRUCT` field type with `RECORD`
field type, we currently cannot suppress the recurring diff this causes.
As a workaround, we recommend using the schema as returned by the API.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Self<wbr>Link</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The URI of the created resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Table<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} A unique ID for the resource.
Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Time<wbr>Partitioning</td>
            <td class="align-top">
                
                <code><a href="#tabletimepartitioning">*Table<wbr>Time<wbr>Partitioning</a></code>
            </td>
            <td class="align-top">{{% md %}} If specified, configures time-based
partitioning for this table. Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Type</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Describes the table type.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">View</td>
            <td class="align-top">
                
                <code><a href="#tableview">*Table<wbr>View</a></code>
            </td>
            <td class="align-top">{{% md %}} If specified, configures this table as a view.
Structure is documented below.
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
            <td class="align-top">clusterings</td>
            <td class="align-top">
                
                <code>string[]?</code>
            </td>
            <td class="align-top">{{% md %}} Specifies column names to use for data clustering.
Up to four top-level columns are allowed, and should be specified in
descending priority order.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">creation<wbr>Time</td>
            <td class="align-top">
                
                <code>number</code>
            </td>
            <td class="align-top">{{% md %}} The time when this table was created, in milliseconds since the epoch.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">dataset<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The dataset ID to create the table in.
Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">description</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} The field description.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">encryption<wbr>Configuration</td>
            <td class="align-top">
                
                <code><a href="#tableencryptionconfiguration">Table<wbr>Encryption<wbr>Configuration?</a></code>
            </td>
            <td class="align-top">{{% md %}} Specifies how the table should be encrypted.
If left blank, the table will be encrypted with a Google-managed key; that process
is transparent to the user.  Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">etag</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} A hash of the resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">expiration<wbr>Time</td>
            <td class="align-top">
                
                <code>number</code>
            </td>
            <td class="align-top">{{% md %}} The time when this table expires, in
milliseconds since the epoch. If not present, the table will persist
indefinitely. Expired tables will be deleted and their storage
reclaimed.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">external<wbr>Data<wbr>Configuration</td>
            <td class="align-top">
                
                <code><a href="#tableexternaldataconfiguration">Table<wbr>External<wbr>Data<wbr>Configuration?</a></code>
            </td>
            <td class="align-top">{{% md %}} Describes the data format,
location, and other properties of a table stored outside of BigQuery.
By defining these properties, the data source can then be queried as
if it were a standard BigQuery table. Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">friendly<wbr>Name</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} A descriptive name for the table.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">labels</td>
            <td class="align-top">
                
                <code>{[key: string]: string}?</code>
            </td>
            <td class="align-top">{{% md %}} A mapping of labels to assign to the resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">last<wbr>Modified<wbr>Time</td>
            <td class="align-top">
                
                <code>number</code>
            </td>
            <td class="align-top">{{% md %}} The time when this table was last modified, in milliseconds since the epoch.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">location</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The geographic location where the table resides. This value is inherited from the dataset.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">num<wbr>Bytes</td>
            <td class="align-top">
                
                <code>number</code>
            </td>
            <td class="align-top">{{% md %}} The size of this table in bytes, excluding any data in the streaming buffer.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">num<wbr>Long<wbr>Term<wbr>Bytes</td>
            <td class="align-top">
                
                <code>number</code>
            </td>
            <td class="align-top">{{% md %}} The number of bytes in the table that are considered &#34;long-term storage&#34;.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">num<wbr>Rows</td>
            <td class="align-top">
                
                <code>number</code>
            </td>
            <td class="align-top">{{% md %}} The number of rows of data in this table, excluding any data in the streaming buffer.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">project</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The ID of the project in which the resource belongs. If it
is not provided, the provider project is used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">range<wbr>Partitioning</td>
            <td class="align-top">
                
                <code><a href="#tablerangepartitioning">Table<wbr>Range<wbr>Partitioning?</a></code>
            </td>
            <td class="align-top">{{% md %}} If specified, configures range-based
partitioning for this table. Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">schema</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} A JSON schema for the table. Schema is required
for CSV and JSON formats and is disallowed for Google Cloud
Bigtable, Cloud Datastore backups, and Avro formats when using
external tables. For more information see the
[BigQuery API documentation](https://cloud.google.com/bigquery/docs/reference/rest/v2/tables#resource).
~&gt;**NOTE**: Because this field expects a JSON string, any changes to the
string will create a diff, even if the JSON itself hasn&#39;t changed.
If the API returns a different value for the same schema, e.g. it
switched the order of values or replaced `STRUCT` field type with `RECORD`
field type, we currently cannot suppress the recurring diff this causes.
As a workaround, we recommend using the schema as returned by the API.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">self<wbr>Link</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The URI of the created resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">table<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} A unique ID for the resource.
Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">time<wbr>Partitioning</td>
            <td class="align-top">
                
                <code><a href="#tabletimepartitioning">Table<wbr>Time<wbr>Partitioning?</a></code>
            </td>
            <td class="align-top">{{% md %}} If specified, configures time-based
partitioning for this table. Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">type</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} Describes the table type.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">view</td>
            <td class="align-top">
                
                <code><a href="#tableview">Table<wbr>View?</a></code>
            </td>
            <td class="align-top">{{% md %}} If specified, configures this table as a view.
Structure is documented below.
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
            <td class="align-top">clusterings</td>
            <td class="align-top">
                
                <code>List[str]</code>
            </td>
            <td class="align-top">{{% md %}} Specifies column names to use for data clustering.
Up to four top-level columns are allowed, and should be specified in
descending priority order.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">creation_<wbr>time</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} The time when this table was created, in milliseconds since the epoch.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">dataset_<wbr>id</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The dataset ID to create the table in.
Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">description</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The field description.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">encryption_<wbr>configuration</td>
            <td class="align-top">
                
                <code><a href="#tableencryptionconfiguration">Dict[Table<wbr>Encryption<wbr>Configuration]</a></code>
            </td>
            <td class="align-top">{{% md %}} Specifies how the table should be encrypted.
If left blank, the table will be encrypted with a Google-managed key; that process
is transparent to the user.  Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">etag</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} A hash of the resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">expiration_<wbr>time</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} The time when this table expires, in
milliseconds since the epoch. If not present, the table will persist
indefinitely. Expired tables will be deleted and their storage
reclaimed.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">external_<wbr>data_<wbr>configuration</td>
            <td class="align-top">
                
                <code><a href="#tableexternaldataconfiguration">Dict[Table<wbr>External<wbr>Data<wbr>Configuration]</a></code>
            </td>
            <td class="align-top">{{% md %}} Describes the data format,
location, and other properties of a table stored outside of BigQuery.
By defining these properties, the data source can then be queried as
if it were a standard BigQuery table. Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">friendly_<wbr>name</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} A descriptive name for the table.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">labels</td>
            <td class="align-top">
                
                <code>Dict[str, str]</code>
            </td>
            <td class="align-top">{{% md %}} A mapping of labels to assign to the resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">last_<wbr>modified_<wbr>time</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} The time when this table was last modified, in milliseconds since the epoch.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">location</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The geographic location where the table resides. This value is inherited from the dataset.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">num_<wbr>bytes</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} The size of this table in bytes, excluding any data in the streaming buffer.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">num_<wbr>long_<wbr>term_<wbr>bytes</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} The number of bytes in the table that are considered &#34;long-term storage&#34;.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">num_<wbr>rows</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} The number of rows of data in this table, excluding any data in the streaming buffer.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">project</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The ID of the project in which the resource belongs. If it
is not provided, the provider project is used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">range_<wbr>partitioning</td>
            <td class="align-top">
                
                <code><a href="#tablerangepartitioning">Dict[Table<wbr>Range<wbr>Partitioning]</a></code>
            </td>
            <td class="align-top">{{% md %}} If specified, configures range-based
partitioning for this table. Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">schema</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} A JSON schema for the table. Schema is required
for CSV and JSON formats and is disallowed for Google Cloud
Bigtable, Cloud Datastore backups, and Avro formats when using
external tables. For more information see the
[BigQuery API documentation](https://cloud.google.com/bigquery/docs/reference/rest/v2/tables#resource).
~&gt;**NOTE**: Because this field expects a JSON string, any changes to the
string will create a diff, even if the JSON itself hasn&#39;t changed.
If the API returns a different value for the same schema, e.g. it
switched the order of values or replaced `STRUCT` field type with `RECORD`
field type, we currently cannot suppress the recurring diff this causes.
As a workaround, we recommend using the schema as returned by the API.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">self_<wbr>link</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The URI of the created resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">table_<wbr>id</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} A unique ID for the resource.
Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">time_<wbr>partitioning</td>
            <td class="align-top">
                
                <code><a href="#tabletimepartitioning">Dict[Table<wbr>Time<wbr>Partitioning]</a></code>
            </td>
            <td class="align-top">{{% md %}} If specified, configures time-based
partitioning for this table. Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">type</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} Describes the table type.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">view</td>
            <td class="align-top">
                
                <code><a href="#tableview">Dict[Table<wbr>View]</a></code>
            </td>
            <td class="align-top">{{% md %}} If specified, configures this table as a view.
Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}








## Look up an Existing Table Resource

{{< langchoose csharp nojavascript >}}

<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">pulumi.Input&lt;pulumi.ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/bigquery/#TableState">TableState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/bigquery/#Table">Table</a></span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>clusterings=None<span class="p">, </span>creation_time=None<span class="p">, </span>dataset_id=None<span class="p">, </span>description=None<span class="p">, </span>encryption_configuration=None<span class="p">, </span>etag=None<span class="p">, </span>expiration_time=None<span class="p">, </span>external_data_configuration=None<span class="p">, </span>friendly_name=None<span class="p">, </span>labels=None<span class="p">, </span>last_modified_time=None<span class="p">, </span>location=None<span class="p">, </span>num_bytes=None<span class="p">, </span>num_long_term_bytes=None<span class="p">, </span>num_rows=None<span class="p">, </span>project=None<span class="p">, </span>range_partitioning=None<span class="p">, </span>schema=None<span class="p">, </span>self_link=None<span class="p">, </span>table_id=None<span class="p">, </span>time_partitioning=None<span class="p">, </span>type=None<span class="p">, </span>view=None<span class="p">, __props__=None);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetTable<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">pulumi.IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/bigquery?tab=doc#TableState">TableState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/bigquery?tab=doc#Table">Table</a></span>, error)</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Bigquery.Table.html">Table</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Pulumi.Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Bigquery.TableState.html">TableState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>

Get an existing Table resource's state with the given name, ID, and optional extra properties used to qualify the lookup.

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
            <td class="align-top">Clusterings</td>
            <td class="align-top">
                
                <code>List<string>?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Specifies column names to use for data clustering.
Up to four top-level columns are allowed, and should be specified in
descending priority order.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Creation<wbr>Time</td>
            <td class="align-top">
                
                <code>int?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The time when this table was created, in milliseconds since the epoch.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Dataset<wbr>Id</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The dataset ID to create the table in.
Changing this forces a new resource to be created.
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
The field description.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Encryption<wbr>Configuration</td>
            <td class="align-top">
                
                <code><a href="#tableencryptionconfiguration">Table<wbr>Encryption<wbr>Configuration<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Specifies how the table should be encrypted.
If left blank, the table will be encrypted with a Google-managed key; that process
is transparent to the user.  Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Etag</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A hash of the resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Expiration<wbr>Time</td>
            <td class="align-top">
                
                <code>int?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The time when this table expires, in
milliseconds since the epoch. If not present, the table will persist
indefinitely. Expired tables will be deleted and their storage
reclaimed.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">External<wbr>Data<wbr>Configuration</td>
            <td class="align-top">
                
                <code><a href="#tableexternaldataconfiguration">Table<wbr>External<wbr>Data<wbr>Configuration<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Describes the data format,
location, and other properties of a table stored outside of BigQuery.
By defining these properties, the data source can then be queried as
if it were a standard BigQuery table. Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Friendly<wbr>Name</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A descriptive name for the table.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Labels</td>
            <td class="align-top">
                
                <code>Dictionary<string, string>?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A mapping of labels to assign to the resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Last<wbr>Modified<wbr>Time</td>
            <td class="align-top">
                
                <code>int?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The time when this table was last modified, in milliseconds since the epoch.
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
The geographic location where the table resides. This value is inherited from the dataset.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Num<wbr>Bytes</td>
            <td class="align-top">
                
                <code>int?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The size of this table in bytes, excluding any data in the streaming buffer.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Num<wbr>Long<wbr>Term<wbr>Bytes</td>
            <td class="align-top">
                
                <code>int?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The number of bytes in the table that are considered &#34;long-term storage&#34;.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Num<wbr>Rows</td>
            <td class="align-top">
                
                <code>int?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The number of rows of data in this table, excluding any data in the streaming buffer.
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
The ID of the project in which the resource belongs. If it
is not provided, the provider project is used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Range<wbr>Partitioning</td>
            <td class="align-top">
                
                <code><a href="#tablerangepartitioning">Table<wbr>Range<wbr>Partitioning<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
If specified, configures range-based
partitioning for this table. Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Schema</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A JSON schema for the table. Schema is required
for CSV and JSON formats and is disallowed for Google Cloud
Bigtable, Cloud Datastore backups, and Avro formats when using
external tables. For more information see the
[BigQuery API documentation](https://cloud.google.com/bigquery/docs/reference/rest/v2/tables#resource).
~&gt;**NOTE**: Because this field expects a JSON string, any changes to the
string will create a diff, even if the JSON itself hasn&#39;t changed.
If the API returns a different value for the same schema, e.g. it
switched the order of values or replaced `STRUCT` field type with `RECORD`
field type, we currently cannot suppress the recurring diff this causes.
As a workaround, we recommend using the schema as returned by the API.
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
The URI of the created resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Table<wbr>Id</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A unique ID for the resource.
Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Time<wbr>Partitioning</td>
            <td class="align-top">
                
                <code><a href="#tabletimepartitioning">Table<wbr>Time<wbr>Partitioning<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
If specified, configures time-based
partitioning for this table. Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Type</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Describes the table type.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">View</td>
            <td class="align-top">
                
                <code><a href="#tableview">Table<wbr>View<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
If specified, configures this table as a view.
Structure is documented below.
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
            <td class="align-top">Clusterings</td>
            <td class="align-top">
                
                <code>[]string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Specifies column names to use for data clustering.
Up to four top-level columns are allowed, and should be specified in
descending priority order.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Creation<wbr>Time</td>
            <td class="align-top">
                
                <code>*int</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The time when this table was created, in milliseconds since the epoch.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Dataset<wbr>Id</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The dataset ID to create the table in.
Changing this forces a new resource to be created.
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
The field description.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Encryption<wbr>Configuration</td>
            <td class="align-top">
                
                <code><a href="#tableencryptionconfiguration">*Table<wbr>Encryption<wbr>Configuration</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Specifies how the table should be encrypted.
If left blank, the table will be encrypted with a Google-managed key; that process
is transparent to the user.  Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Etag</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A hash of the resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Expiration<wbr>Time</td>
            <td class="align-top">
                
                <code>*int</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The time when this table expires, in
milliseconds since the epoch. If not present, the table will persist
indefinitely. Expired tables will be deleted and their storage
reclaimed.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">External<wbr>Data<wbr>Configuration</td>
            <td class="align-top">
                
                <code><a href="#tableexternaldataconfiguration">*Table<wbr>External<wbr>Data<wbr>Configuration</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Describes the data format,
location, and other properties of a table stored outside of BigQuery.
By defining these properties, the data source can then be queried as
if it were a standard BigQuery table. Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Friendly<wbr>Name</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A descriptive name for the table.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Labels</td>
            <td class="align-top">
                
                <code>map[string]string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A mapping of labels to assign to the resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Last<wbr>Modified<wbr>Time</td>
            <td class="align-top">
                
                <code>*int</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The time when this table was last modified, in milliseconds since the epoch.
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
The geographic location where the table resides. This value is inherited from the dataset.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Num<wbr>Bytes</td>
            <td class="align-top">
                
                <code>*int</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The size of this table in bytes, excluding any data in the streaming buffer.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Num<wbr>Long<wbr>Term<wbr>Bytes</td>
            <td class="align-top">
                
                <code>*int</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The number of bytes in the table that are considered &#34;long-term storage&#34;.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Num<wbr>Rows</td>
            <td class="align-top">
                
                <code>*int</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The number of rows of data in this table, excluding any data in the streaming buffer.
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
The ID of the project in which the resource belongs. If it
is not provided, the provider project is used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Range<wbr>Partitioning</td>
            <td class="align-top">
                
                <code><a href="#tablerangepartitioning">*Table<wbr>Range<wbr>Partitioning</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
If specified, configures range-based
partitioning for this table. Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Schema</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A JSON schema for the table. Schema is required
for CSV and JSON formats and is disallowed for Google Cloud
Bigtable, Cloud Datastore backups, and Avro formats when using
external tables. For more information see the
[BigQuery API documentation](https://cloud.google.com/bigquery/docs/reference/rest/v2/tables#resource).
~&gt;**NOTE**: Because this field expects a JSON string, any changes to the
string will create a diff, even if the JSON itself hasn&#39;t changed.
If the API returns a different value for the same schema, e.g. it
switched the order of values or replaced `STRUCT` field type with `RECORD`
field type, we currently cannot suppress the recurring diff this causes.
As a workaround, we recommend using the schema as returned by the API.
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
The URI of the created resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Table<wbr>Id</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A unique ID for the resource.
Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Time<wbr>Partitioning</td>
            <td class="align-top">
                
                <code><a href="#tabletimepartitioning">*Table<wbr>Time<wbr>Partitioning</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
If specified, configures time-based
partitioning for this table. Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Type</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Describes the table type.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">View</td>
            <td class="align-top">
                
                <code><a href="#tableview">*Table<wbr>View</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
If specified, configures this table as a view.
Structure is documented below.
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
            <td class="align-top">clusterings</td>
            <td class="align-top">
                
                <code>string[]?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Specifies column names to use for data clustering.
Up to four top-level columns are allowed, and should be specified in
descending priority order.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">creation<wbr>Time</td>
            <td class="align-top">
                
                <code>number?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The time when this table was created, in milliseconds since the epoch.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">dataset<wbr>Id</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The dataset ID to create the table in.
Changing this forces a new resource to be created.
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
The field description.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">encryption<wbr>Configuration</td>
            <td class="align-top">
                
                <code><a href="#tableencryptionconfiguration">Table<wbr>Encryption<wbr>Configuration?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Specifies how the table should be encrypted.
If left blank, the table will be encrypted with a Google-managed key; that process
is transparent to the user.  Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">etag</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A hash of the resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">expiration<wbr>Time</td>
            <td class="align-top">
                
                <code>number?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The time when this table expires, in
milliseconds since the epoch. If not present, the table will persist
indefinitely. Expired tables will be deleted and their storage
reclaimed.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">external<wbr>Data<wbr>Configuration</td>
            <td class="align-top">
                
                <code><a href="#tableexternaldataconfiguration">Table<wbr>External<wbr>Data<wbr>Configuration?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Describes the data format,
location, and other properties of a table stored outside of BigQuery.
By defining these properties, the data source can then be queried as
if it were a standard BigQuery table. Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">friendly<wbr>Name</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A descriptive name for the table.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">labels</td>
            <td class="align-top">
                
                <code>{[key: string]: string}?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A mapping of labels to assign to the resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">last<wbr>Modified<wbr>Time</td>
            <td class="align-top">
                
                <code>number?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The time when this table was last modified, in milliseconds since the epoch.
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
The geographic location where the table resides. This value is inherited from the dataset.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">num<wbr>Bytes</td>
            <td class="align-top">
                
                <code>number?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The size of this table in bytes, excluding any data in the streaming buffer.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">num<wbr>Long<wbr>Term<wbr>Bytes</td>
            <td class="align-top">
                
                <code>number?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The number of bytes in the table that are considered &#34;long-term storage&#34;.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">num<wbr>Rows</td>
            <td class="align-top">
                
                <code>number?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The number of rows of data in this table, excluding any data in the streaming buffer.
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
The ID of the project in which the resource belongs. If it
is not provided, the provider project is used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">range<wbr>Partitioning</td>
            <td class="align-top">
                
                <code><a href="#tablerangepartitioning">Table<wbr>Range<wbr>Partitioning?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
If specified, configures range-based
partitioning for this table. Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">schema</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A JSON schema for the table. Schema is required
for CSV and JSON formats and is disallowed for Google Cloud
Bigtable, Cloud Datastore backups, and Avro formats when using
external tables. For more information see the
[BigQuery API documentation](https://cloud.google.com/bigquery/docs/reference/rest/v2/tables#resource).
~&gt;**NOTE**: Because this field expects a JSON string, any changes to the
string will create a diff, even if the JSON itself hasn&#39;t changed.
If the API returns a different value for the same schema, e.g. it
switched the order of values or replaced `STRUCT` field type with `RECORD`
field type, we currently cannot suppress the recurring diff this causes.
As a workaround, we recommend using the schema as returned by the API.
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
The URI of the created resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">table<wbr>Id</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A unique ID for the resource.
Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">time<wbr>Partitioning</td>
            <td class="align-top">
                
                <code><a href="#tabletimepartitioning">Table<wbr>Time<wbr>Partitioning?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
If specified, configures time-based
partitioning for this table. Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">type</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Describes the table type.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">view</td>
            <td class="align-top">
                
                <code><a href="#tableview">Table<wbr>View?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
If specified, configures this table as a view.
Structure is documented below.
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
            <td class="align-top">clusterings</td>
            <td class="align-top">
                
                <code>List[str]</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Specifies column names to use for data clustering.
Up to four top-level columns are allowed, and should be specified in
descending priority order.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">creation_<wbr>time</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The time when this table was created, in milliseconds since the epoch.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">dataset_<wbr>id</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The dataset ID to create the table in.
Changing this forces a new resource to be created.
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
The field description.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">encryption_<wbr>configuration</td>
            <td class="align-top">
                
                <code><a href="#tableencryptionconfiguration">Dict[Table<wbr>Encryption<wbr>Configuration]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Specifies how the table should be encrypted.
If left blank, the table will be encrypted with a Google-managed key; that process
is transparent to the user.  Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">etag</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A hash of the resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">expiration_<wbr>time</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The time when this table expires, in
milliseconds since the epoch. If not present, the table will persist
indefinitely. Expired tables will be deleted and their storage
reclaimed.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">external_<wbr>data_<wbr>configuration</td>
            <td class="align-top">
                
                <code><a href="#tableexternaldataconfiguration">Dict[Table<wbr>External<wbr>Data<wbr>Configuration]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Describes the data format,
location, and other properties of a table stored outside of BigQuery.
By defining these properties, the data source can then be queried as
if it were a standard BigQuery table. Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">friendly_<wbr>name</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A descriptive name for the table.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">labels</td>
            <td class="align-top">
                
                <code>Dict[str, str]</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A mapping of labels to assign to the resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">last_<wbr>modified_<wbr>time</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The time when this table was last modified, in milliseconds since the epoch.
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
The geographic location where the table resides. This value is inherited from the dataset.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">num_<wbr>bytes</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The size of this table in bytes, excluding any data in the streaming buffer.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">num_<wbr>long_<wbr>term_<wbr>bytes</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The number of bytes in the table that are considered &#34;long-term storage&#34;.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">num_<wbr>rows</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The number of rows of data in this table, excluding any data in the streaming buffer.
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
The ID of the project in which the resource belongs. If it
is not provided, the provider project is used.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">range_<wbr>partitioning</td>
            <td class="align-top">
                
                <code><a href="#tablerangepartitioning">Dict[Table<wbr>Range<wbr>Partitioning]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
If specified, configures range-based
partitioning for this table. Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">schema</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A JSON schema for the table. Schema is required
for CSV and JSON formats and is disallowed for Google Cloud
Bigtable, Cloud Datastore backups, and Avro formats when using
external tables. For more information see the
[BigQuery API documentation](https://cloud.google.com/bigquery/docs/reference/rest/v2/tables#resource).
~&gt;**NOTE**: Because this field expects a JSON string, any changes to the
string will create a diff, even if the JSON itself hasn&#39;t changed.
If the API returns a different value for the same schema, e.g. it
switched the order of values or replaced `STRUCT` field type with `RECORD`
field type, we currently cannot suppress the recurring diff this causes.
As a workaround, we recommend using the schema as returned by the API.
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
The URI of the created resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">table_<wbr>id</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A unique ID for the resource.
Changing this forces a new resource to be created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">time_<wbr>partitioning</td>
            <td class="align-top">
                
                <code><a href="#tabletimepartitioning">Dict[Table<wbr>Time<wbr>Partitioning]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
If specified, configures time-based
partitioning for this table. Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">type</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Describes the table type.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">view</td>
            <td class="align-top">
                
                <code><a href="#tableview">Dict[Table<wbr>View]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
If specified, configures this table as a view.
Structure is documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}










## Supporting Types

#### TableEncryptionConfiguration
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#TableEncryptionConfiguration">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#TableEncryptionConfiguration">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/bigquery?tab=doc#TableEncryptionConfigurationArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/bigquery?tab=doc#TableEncryptionConfigurationOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Bigquery.TableEncryptionConfigurationArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Bigquery.TableEncryptionConfiguration.html">output</a> API doc for this type.
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
            <td class="align-top">Kms<wbr>Key<wbr>Name</td>
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
            <td class="align-top">Kms<wbr>Key<wbr>Name</td>
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
            <td class="align-top">kms<wbr>Key<wbr>Name</td>
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
            <td class="align-top">kms_<wbr>key_<wbr>name</td>
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





#### TableExternalDataConfiguration
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#TableExternalDataConfiguration">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#TableExternalDataConfiguration">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/bigquery?tab=doc#TableExternalDataConfigurationArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/bigquery?tab=doc#TableExternalDataConfigurationOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Bigquery.TableExternalDataConfigurationArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Bigquery.TableExternalDataConfiguration.html">output</a> API doc for this type.
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
            <td class="align-top">Autodetect</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Compression</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Csv<wbr>Options</td>
            <td class="align-top">
                
                <code><a href="#tableexternaldataconfigurationcsvoptions">Table<wbr>External<wbr>Data<wbr>Configuration<wbr>Csv<wbr>Options<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Google<wbr>Sheets<wbr>Options</td>
            <td class="align-top">
                
                <code><a href="#tableexternaldataconfigurationgooglesheetsoptions">Table<wbr>External<wbr>Data<wbr>Configuration<wbr>Google<wbr>Sheets<wbr>Options<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Ignore<wbr>Unknown<wbr>Values</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Max<wbr>Bad<wbr>Records</td>
            <td class="align-top">
                
                <code>int?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Source<wbr>Format</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Source<wbr>Uris</td>
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
            <td class="align-top">Autodetect</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Compression</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Csv<wbr>Options</td>
            <td class="align-top">
                
                <code><a href="#tableexternaldataconfigurationcsvoptions">*Table<wbr>External<wbr>Data<wbr>Configuration<wbr>Csv<wbr>Options</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Google<wbr>Sheets<wbr>Options</td>
            <td class="align-top">
                
                <code><a href="#tableexternaldataconfigurationgooglesheetsoptions">*Table<wbr>External<wbr>Data<wbr>Configuration<wbr>Google<wbr>Sheets<wbr>Options</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Ignore<wbr>Unknown<wbr>Values</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Max<wbr>Bad<wbr>Records</td>
            <td class="align-top">
                
                <code>*int</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Source<wbr>Format</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Source<wbr>Uris</td>
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
            <td class="align-top">autodetect</td>
            <td class="align-top">
                
                <code>boolean</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">compression</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">csv<wbr>Options</td>
            <td class="align-top">
                
                <code><a href="#tableexternaldataconfigurationcsvoptions">Table<wbr>External<wbr>Data<wbr>Configuration<wbr>Csv<wbr>Options?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">google<wbr>Sheets<wbr>Options</td>
            <td class="align-top">
                
                <code><a href="#tableexternaldataconfigurationgooglesheetsoptions">Table<wbr>External<wbr>Data<wbr>Configuration<wbr>Google<wbr>Sheets<wbr>Options?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">ignore<wbr>Unknown<wbr>Values</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">max<wbr>Bad<wbr>Records</td>
            <td class="align-top">
                
                <code>number?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">source<wbr>Format</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">source<wbr>Uris</td>
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
            <td class="align-top">autodetect</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">compression</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">csv<wbr>Options</td>
            <td class="align-top">
                
                <code><a href="#tableexternaldataconfigurationcsvoptions">Dict[Table<wbr>External<wbr>Data<wbr>Configuration<wbr>Csv<wbr>Options]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">google<wbr>Sheets<wbr>Options</td>
            <td class="align-top">
                
                <code><a href="#tableexternaldataconfigurationgooglesheetsoptions">Dict[Table<wbr>External<wbr>Data<wbr>Configuration<wbr>Google<wbr>Sheets<wbr>Options]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">ignore<wbr>Unknown<wbr>Values</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">max<wbr>Bad<wbr>Records</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">source<wbr>Format</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">source<wbr>Uris</td>
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





#### TableExternalDataConfigurationCsvOptions
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#TableExternalDataConfigurationCsvOptions">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#TableExternalDataConfigurationCsvOptions">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/bigquery?tab=doc#TableExternalDataConfigurationCsvOptionsArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/bigquery?tab=doc#TableExternalDataConfigurationCsvOptionsOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Bigquery.TableExternalDataConfigurationCsvOptionsArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Bigquery.TableExternalDataConfigurationCsvOptions.html">output</a> API doc for this type.
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
            <td class="align-top">Allow<wbr>Jagged<wbr>Rows</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Allow<wbr>Quoted<wbr>Newlines</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Encoding</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Field<wbr>Delimiter</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Quote</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Skip<wbr>Leading<wbr>Rows</td>
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
            <td class="align-top">Allow<wbr>Jagged<wbr>Rows</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Allow<wbr>Quoted<wbr>Newlines</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Encoding</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Field<wbr>Delimiter</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Quote</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Skip<wbr>Leading<wbr>Rows</td>
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
            <td class="align-top">allow<wbr>Jagged<wbr>Rows</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">allow<wbr>Quoted<wbr>Newlines</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">encoding</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">field<wbr>Delimiter</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">quote</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">skip<wbr>Leading<wbr>Rows</td>
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
            <td class="align-top">allow<wbr>Jagged<wbr>Rows</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">allow<wbr>Quoted<wbr>Newlines</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">encoding</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">field<wbr>Delimiter</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">quote</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">skip<wbr>Leading<wbr>Rows</td>
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





#### TableExternalDataConfigurationGoogleSheetsOptions
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#TableExternalDataConfigurationGoogleSheetsOptions">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#TableExternalDataConfigurationGoogleSheetsOptions">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/bigquery?tab=doc#TableExternalDataConfigurationGoogleSheetsOptionsArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/bigquery?tab=doc#TableExternalDataConfigurationGoogleSheetsOptionsOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Bigquery.TableExternalDataConfigurationGoogleSheetsOptionsArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Bigquery.TableExternalDataConfigurationGoogleSheetsOptions.html">output</a> API doc for this type.
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
            <td class="align-top">Range</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Skip<wbr>Leading<wbr>Rows</td>
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
            <td class="align-top">Range</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Skip<wbr>Leading<wbr>Rows</td>
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
            <td class="align-top">range</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">skip<wbr>Leading<wbr>Rows</td>
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
            <td class="align-top">range</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">skip<wbr>Leading<wbr>Rows</td>
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





#### TableRangePartitioning
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#TableRangePartitioning">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#TableRangePartitioning">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/bigquery?tab=doc#TableRangePartitioningArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/bigquery?tab=doc#TableRangePartitioningOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Bigquery.TableRangePartitioningArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Bigquery.TableRangePartitioning.html">output</a> API doc for this type.
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
            <td class="align-top">Field</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Range</td>
            <td class="align-top">
                
                <code><a href="#tablerangepartitioningrange">Table<wbr>Range<wbr>Partitioning<wbr>Range<wbr>Args</a></code>
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
            <td class="align-top">Field</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Range</td>
            <td class="align-top">
                
                <code><a href="#tablerangepartitioningrange">Table<wbr>Range<wbr>Partitioning<wbr>Range</a></code>
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
            <td class="align-top">field</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">range</td>
            <td class="align-top">
                
                <code><a href="#tablerangepartitioningrange">Table<wbr>Range<wbr>Partitioning<wbr>Range</a></code>
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
            <td class="align-top">field</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">range</td>
            <td class="align-top">
                
                <code><a href="#tablerangepartitioningrange">Dict[Table<wbr>Range<wbr>Partitioning<wbr>Range]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}





#### TableRangePartitioningRange
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#TableRangePartitioningRange">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#TableRangePartitioningRange">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/bigquery?tab=doc#TableRangePartitioningRangeArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/bigquery?tab=doc#TableRangePartitioningRangeOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Bigquery.TableRangePartitioningRangeArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Bigquery.TableRangePartitioningRange.html">output</a> API doc for this type.
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
            <td class="align-top">End</td>
            <td class="align-top">
                
                <code>int</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Interval</td>
            <td class="align-top">
                
                <code>int</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Start</td>
            <td class="align-top">
                
                <code>int</code>
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
            <td class="align-top">End</td>
            <td class="align-top">
                
                <code>int</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Interval</td>
            <td class="align-top">
                
                <code>int</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Start</td>
            <td class="align-top">
                
                <code>int</code>
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
            <td class="align-top">end</td>
            <td class="align-top">
                
                <code>number</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">interval</td>
            <td class="align-top">
                
                <code>number</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">start</td>
            <td class="align-top">
                
                <code>number</code>
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
            <td class="align-top">end</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">interval</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">start</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}





#### TableTimePartitioning
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#TableTimePartitioning">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#TableTimePartitioning">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/bigquery?tab=doc#TableTimePartitioningArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/bigquery?tab=doc#TableTimePartitioningOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Bigquery.TableTimePartitioningArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Bigquery.TableTimePartitioning.html">output</a> API doc for this type.
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
            <td class="align-top">Expiration<wbr>Ms</td>
            <td class="align-top">
                
                <code>int?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Field</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Require<wbr>Partition<wbr>Filter</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
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
Describes the table type.
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
            <td class="align-top">Expiration<wbr>Ms</td>
            <td class="align-top">
                
                <code>*int</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Field</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Require<wbr>Partition<wbr>Filter</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
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
Describes the table type.
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
            <td class="align-top">expiration<wbr>Ms</td>
            <td class="align-top">
                
                <code>number?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">field</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">require<wbr>Partition<wbr>Filter</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
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
Describes the table type.
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
            <td class="align-top">expiration<wbr>Ms</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">field</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">require<wbr>Partition<wbr>Filter</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
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
Describes the table type.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}





#### TableView
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#TableView">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#TableView">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/bigquery?tab=doc#TableViewArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/bigquery?tab=doc#TableViewOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Bigquery.TableViewArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Bigquery.TableView.html">output</a> API doc for this type.
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
            <td class="align-top">Query</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Use<wbr>Legacy<wbr>Sql</td>
            <td class="align-top">
                
                <code>bool?</code>
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
            <td class="align-top">Query</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Use<wbr>Legacy<wbr>Sql</td>
            <td class="align-top">
                
                <code>*bool</code>
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
            <td class="align-top">query</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">use<wbr>Legacy<wbr>Sql</td>
            <td class="align-top">
                
                <code>boolean?</code>
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
            <td class="align-top">query</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">use<wbr>Legacy<wbr>Sql</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}








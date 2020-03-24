
---
title: "FolderSink"
block_external_search_index: true
---
<style>
table td p { margin-top: 0; margin-bottom: 0; }
</style>

Manages a folder-level logging sink. For more information see
[the official documentation](https://cloud.google.com/logging/docs/) and
[Exporting Logs in the API](https://cloud.google.com/logging/docs/api/tasks/exporting-logs).

Note that you must have the "Logs Configuration Writer" IAM role (`roles/logging.configWriter`)
granted to the credentials used with this provider.

> This content is derived from https://github.com/terraform-providers/terraform-provider-google/blob/master/website/docs/r/logging_folder_sink.html.markdown.



## Create a FolderSink Resource

{{< langchoose csharp nojavascript >}}

<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/logging/#FolderSink">FolderSink</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/logging/#FolderSinkArgs">FolderSinkArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">FolderSink</span><span class="p">(resource_name, opts=None, </span>bigquery_options=None<span class="p">, </span>destination=None<span class="p">, </span>filter=None<span class="p">, </span>folder=None<span class="p">, </span>include_children=None<span class="p">, </span>name=None<span class="p">, __props__=None);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewFolderSink<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/logging?tab=doc#FolderSinkArgs">FolderSinkArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/logging?tab=doc#FolderSink">FolderSink</a></span>, error)</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Logging.FolderSink.html">FolderSink</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Logging.FolderSinkArgs.html">FolderSinkArgs</a></span> <span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>

Creates a FolderSink resource with the given unique name, arguments, and options.

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
            <td class="align-top">Bigquery<wbr>Options</td>
            <td class="align-top">
                
                <code><a href="#foldersinkbigqueryoptions">Folder<wbr>Sink<wbr>Bigquery<wbr>Options<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Options that affect sinks exporting data to BigQuery. Structure documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Destination</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The destination of the sink (or, in other words, where logs are written to). Can be a
Cloud Storage bucket, a PubSub topic, or a BigQuery dataset. Examples:
```typescript
import * as pulumi from &#34;@pulumi/pulumi&#34;;
```
The writer associated with the sink must have access to write to the above resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Filter</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The filter to apply when exporting logs. Only log entries that match the filter are exported.
See [Advanced Log Filters](https://cloud.google.com/logging/docs/view/advanced_filters) for information on how to
write a filter.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Folder</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The folder to be exported to the sink. Note that either [FOLDER_ID] or &#34;folders/[FOLDER_ID]&#34; is
accepted.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Include<wbr>Children</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Whether or not to include children folders in the sink export. If true, logs
associated with child projects are also exported; otherwise only logs relating to the provided folder are included.
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
The name of the logging sink.
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
            <td class="align-top">Bigquery<wbr>Options</td>
            <td class="align-top">
                
                <code><a href="#foldersinkbigqueryoptions">*Folder<wbr>Sink<wbr>Bigquery<wbr>Options</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Options that affect sinks exporting data to BigQuery. Structure documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Destination</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The destination of the sink (or, in other words, where logs are written to). Can be a
Cloud Storage bucket, a PubSub topic, or a BigQuery dataset. Examples:
```typescript
import * as pulumi from &#34;@pulumi/pulumi&#34;;
```
The writer associated with the sink must have access to write to the above resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Filter</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The filter to apply when exporting logs. Only log entries that match the filter are exported.
See [Advanced Log Filters](https://cloud.google.com/logging/docs/view/advanced_filters) for information on how to
write a filter.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Folder</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The folder to be exported to the sink. Note that either [FOLDER_ID] or &#34;folders/[FOLDER_ID]&#34; is
accepted.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Include<wbr>Children</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Whether or not to include children folders in the sink export. If true, logs
associated with child projects are also exported; otherwise only logs relating to the provided folder are included.
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
The name of the logging sink.
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
            <td class="align-top">bigquery<wbr>Options</td>
            <td class="align-top">
                
                <code><a href="#foldersinkbigqueryoptions">Folder<wbr>Sink<wbr>Bigquery<wbr>Options?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Options that affect sinks exporting data to BigQuery. Structure documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">destination</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The destination of the sink (or, in other words, where logs are written to). Can be a
Cloud Storage bucket, a PubSub topic, or a BigQuery dataset. Examples:
```typescript
import * as pulumi from &#34;@pulumi/pulumi&#34;;
```
The writer associated with the sink must have access to write to the above resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">filter</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The filter to apply when exporting logs. Only log entries that match the filter are exported.
See [Advanced Log Filters](https://cloud.google.com/logging/docs/view/advanced_filters) for information on how to
write a filter.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">folder</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The folder to be exported to the sink. Note that either [FOLDER_ID] or &#34;folders/[FOLDER_ID]&#34; is
accepted.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">include<wbr>Children</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Whether or not to include children folders in the sink export. If true, logs
associated with child projects are also exported; otherwise only logs relating to the provided folder are included.
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
The name of the logging sink.
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
            <td class="align-top">bigquery_<wbr>options</td>
            <td class="align-top">
                
                <code><a href="#foldersinkbigqueryoptions">Dict[Folder<wbr>Sink<wbr>Bigquery<wbr>Options]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Options that affect sinks exporting data to BigQuery. Structure documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">destination</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The destination of the sink (or, in other words, where logs are written to). Can be a
Cloud Storage bucket, a PubSub topic, or a BigQuery dataset. Examples:
```typescript
import * as pulumi from &#34;@pulumi/pulumi&#34;;
```
The writer associated with the sink must have access to write to the above resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">filter</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The filter to apply when exporting logs. Only log entries that match the filter are exported.
See [Advanced Log Filters](https://cloud.google.com/logging/docs/view/advanced_filters) for information on how to
write a filter.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">folder</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The folder to be exported to the sink. Note that either [FOLDER_ID] or &#34;folders/[FOLDER_ID]&#34; is
accepted.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">include_<wbr>children</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Whether or not to include children folders in the sink export. If true, logs
associated with child projects are also exported; otherwise only logs relating to the provided folder are included.
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
The name of the logging sink.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}







## FolderSink Output Properties

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
            <td class="align-top">Bigquery<wbr>Options</td>
            <td class="align-top">
                
                <code><a href="#foldersinkbigqueryoptions">Folder<wbr>Sink<wbr>Bigquery<wbr>Options</a></code>
            </td>
            <td class="align-top">{{% md %}} Options that affect sinks exporting data to BigQuery. Structure documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Destination</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The destination of the sink (or, in other words, where logs are written to). Can be a
Cloud Storage bucket, a PubSub topic, or a BigQuery dataset. Examples:
```typescript
import * as pulumi from &#34;@pulumi/pulumi&#34;;
```
The writer associated with the sink must have access to write to the above resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Filter</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} The filter to apply when exporting logs. Only log entries that match the filter are exported.
See [Advanced Log Filters](https://cloud.google.com/logging/docs/view/advanced_filters) for information on how to
write a filter.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Folder</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The folder to be exported to the sink. Note that either [FOLDER_ID] or &#34;folders/[FOLDER_ID]&#34; is
accepted.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Include<wbr>Children</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} Whether or not to include children folders in the sink export. If true, logs
associated with child projects are also exported; otherwise only logs relating to the provided folder are included.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The name of the logging sink.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Writer<wbr>Identity</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The identity associated with this sink. This identity must be granted write access to the
configured `destination`.
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
            <td class="align-top">Bigquery<wbr>Options</td>
            <td class="align-top">
                
                <code><a href="#foldersinkbigqueryoptions">Folder<wbr>Sink<wbr>Bigquery<wbr>Options</a></code>
            </td>
            <td class="align-top">{{% md %}} Options that affect sinks exporting data to BigQuery. Structure documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Destination</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The destination of the sink (or, in other words, where logs are written to). Can be a
Cloud Storage bucket, a PubSub topic, or a BigQuery dataset. Examples:
```typescript
import * as pulumi from &#34;@pulumi/pulumi&#34;;
```
The writer associated with the sink must have access to write to the above resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Filter</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} The filter to apply when exporting logs. Only log entries that match the filter are exported.
See [Advanced Log Filters](https://cloud.google.com/logging/docs/view/advanced_filters) for information on how to
write a filter.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Folder</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The folder to be exported to the sink. Note that either [FOLDER_ID] or &#34;folders/[FOLDER_ID]&#34; is
accepted.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Include<wbr>Children</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} Whether or not to include children folders in the sink export. If true, logs
associated with child projects are also exported; otherwise only logs relating to the provided folder are included.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The name of the logging sink.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Writer<wbr>Identity</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The identity associated with this sink. This identity must be granted write access to the
configured `destination`.
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
            <td class="align-top">bigquery<wbr>Options</td>
            <td class="align-top">
                
                <code><a href="#foldersinkbigqueryoptions">Folder<wbr>Sink<wbr>Bigquery<wbr>Options</a></code>
            </td>
            <td class="align-top">{{% md %}} Options that affect sinks exporting data to BigQuery. Structure documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">destination</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The destination of the sink (or, in other words, where logs are written to). Can be a
Cloud Storage bucket, a PubSub topic, or a BigQuery dataset. Examples:
```typescript
import * as pulumi from &#34;@pulumi/pulumi&#34;;
```
The writer associated with the sink must have access to write to the above resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">filter</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} The filter to apply when exporting logs. Only log entries that match the filter are exported.
See [Advanced Log Filters](https://cloud.google.com/logging/docs/view/advanced_filters) for information on how to
write a filter.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">folder</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The folder to be exported to the sink. Note that either [FOLDER_ID] or &#34;folders/[FOLDER_ID]&#34; is
accepted.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">include<wbr>Children</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} Whether or not to include children folders in the sink export. If true, logs
associated with child projects are also exported; otherwise only logs relating to the provided folder are included.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The name of the logging sink.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">writer<wbr>Identity</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The identity associated with this sink. This identity must be granted write access to the
configured `destination`.
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
            <td class="align-top">bigquery_<wbr>options</td>
            <td class="align-top">
                
                <code><a href="#foldersinkbigqueryoptions">Dict[Folder<wbr>Sink<wbr>Bigquery<wbr>Options]</a></code>
            </td>
            <td class="align-top">{{% md %}} Options that affect sinks exporting data to BigQuery. Structure documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">destination</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The destination of the sink (or, in other words, where logs are written to). Can be a
Cloud Storage bucket, a PubSub topic, or a BigQuery dataset. Examples:
```typescript
import * as pulumi from &#34;@pulumi/pulumi&#34;;
```
The writer associated with the sink must have access to write to the above resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">filter</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The filter to apply when exporting logs. Only log entries that match the filter are exported.
See [Advanced Log Filters](https://cloud.google.com/logging/docs/view/advanced_filters) for information on how to
write a filter.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">folder</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The folder to be exported to the sink. Note that either [FOLDER_ID] or &#34;folders/[FOLDER_ID]&#34; is
accepted.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">include_<wbr>children</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} Whether or not to include children folders in the sink export. If true, logs
associated with child projects are also exported; otherwise only logs relating to the provided folder are included.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">name</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The name of the logging sink.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">writer_<wbr>identity</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The identity associated with this sink. This identity must be granted write access to the
configured `destination`.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}








## Look up an Existing FolderSink Resource

{{< langchoose csharp nojavascript >}}

<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">pulumi.Input&lt;pulumi.ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/logging/#FolderSinkState">FolderSinkState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/logging/#FolderSink">FolderSink</a></span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>bigquery_options=None<span class="p">, </span>destination=None<span class="p">, </span>filter=None<span class="p">, </span>folder=None<span class="p">, </span>include_children=None<span class="p">, </span>name=None<span class="p">, </span>writer_identity=None<span class="p">, __props__=None);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetFolderSink<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">pulumi.IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/logging?tab=doc#FolderSinkState">FolderSinkState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/logging?tab=doc#FolderSink">FolderSink</a></span>, error)</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Logging.FolderSink.html">FolderSink</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Pulumi.Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Logging.FolderSinkState.html">FolderSinkState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>

Get an existing FolderSink resource's state with the given name, ID, and optional extra properties used to qualify the lookup.

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
            <td class="align-top">Bigquery<wbr>Options</td>
            <td class="align-top">
                
                <code><a href="#foldersinkbigqueryoptions">Folder<wbr>Sink<wbr>Bigquery<wbr>Options<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Options that affect sinks exporting data to BigQuery. Structure documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Destination</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The destination of the sink (or, in other words, where logs are written to). Can be a
Cloud Storage bucket, a PubSub topic, or a BigQuery dataset. Examples:
```typescript
import * as pulumi from &#34;@pulumi/pulumi&#34;;
```
The writer associated with the sink must have access to write to the above resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Filter</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The filter to apply when exporting logs. Only log entries that match the filter are exported.
See [Advanced Log Filters](https://cloud.google.com/logging/docs/view/advanced_filters) for information on how to
write a filter.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Folder</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The folder to be exported to the sink. Note that either [FOLDER_ID] or &#34;folders/[FOLDER_ID]&#34; is
accepted.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Include<wbr>Children</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Whether or not to include children folders in the sink export. If true, logs
associated with child projects are also exported; otherwise only logs relating to the provided folder are included.
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
The name of the logging sink.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Writer<wbr>Identity</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The identity associated with this sink. This identity must be granted write access to the
configured `destination`.
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
            <td class="align-top">Bigquery<wbr>Options</td>
            <td class="align-top">
                
                <code><a href="#foldersinkbigqueryoptions">*Folder<wbr>Sink<wbr>Bigquery<wbr>Options</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Options that affect sinks exporting data to BigQuery. Structure documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Destination</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The destination of the sink (or, in other words, where logs are written to). Can be a
Cloud Storage bucket, a PubSub topic, or a BigQuery dataset. Examples:
```typescript
import * as pulumi from &#34;@pulumi/pulumi&#34;;
```
The writer associated with the sink must have access to write to the above resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Filter</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The filter to apply when exporting logs. Only log entries that match the filter are exported.
See [Advanced Log Filters](https://cloud.google.com/logging/docs/view/advanced_filters) for information on how to
write a filter.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Folder</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The folder to be exported to the sink. Note that either [FOLDER_ID] or &#34;folders/[FOLDER_ID]&#34; is
accepted.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Include<wbr>Children</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Whether or not to include children folders in the sink export. If true, logs
associated with child projects are also exported; otherwise only logs relating to the provided folder are included.
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
The name of the logging sink.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Writer<wbr>Identity</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The identity associated with this sink. This identity must be granted write access to the
configured `destination`.
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
            <td class="align-top">bigquery<wbr>Options</td>
            <td class="align-top">
                
                <code><a href="#foldersinkbigqueryoptions">Folder<wbr>Sink<wbr>Bigquery<wbr>Options?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Options that affect sinks exporting data to BigQuery. Structure documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">destination</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The destination of the sink (or, in other words, where logs are written to). Can be a
Cloud Storage bucket, a PubSub topic, or a BigQuery dataset. Examples:
```typescript
import * as pulumi from &#34;@pulumi/pulumi&#34;;
```
The writer associated with the sink must have access to write to the above resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">filter</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The filter to apply when exporting logs. Only log entries that match the filter are exported.
See [Advanced Log Filters](https://cloud.google.com/logging/docs/view/advanced_filters) for information on how to
write a filter.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">folder</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The folder to be exported to the sink. Note that either [FOLDER_ID] or &#34;folders/[FOLDER_ID]&#34; is
accepted.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">include<wbr>Children</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Whether or not to include children folders in the sink export. If true, logs
associated with child projects are also exported; otherwise only logs relating to the provided folder are included.
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
The name of the logging sink.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">writer<wbr>Identity</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The identity associated with this sink. This identity must be granted write access to the
configured `destination`.
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
            <td class="align-top">bigquery_<wbr>options</td>
            <td class="align-top">
                
                <code><a href="#foldersinkbigqueryoptions">Dict[Folder<wbr>Sink<wbr>Bigquery<wbr>Options]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Options that affect sinks exporting data to BigQuery. Structure documented below.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">destination</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The destination of the sink (or, in other words, where logs are written to). Can be a
Cloud Storage bucket, a PubSub topic, or a BigQuery dataset. Examples:
```typescript
import * as pulumi from &#34;@pulumi/pulumi&#34;;
```
The writer associated with the sink must have access to write to the above resource.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">filter</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The filter to apply when exporting logs. Only log entries that match the filter are exported.
See [Advanced Log Filters](https://cloud.google.com/logging/docs/view/advanced_filters) for information on how to
write a filter.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">folder</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The folder to be exported to the sink. Note that either [FOLDER_ID] or &#34;folders/[FOLDER_ID]&#34; is
accepted.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">include_<wbr>children</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Whether or not to include children folders in the sink export. If true, logs
associated with child projects are also exported; otherwise only logs relating to the provided folder are included.
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
The name of the logging sink.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">writer_<wbr>identity</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The identity associated with this sink. This identity must be granted write access to the
configured `destination`.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}










## Supporting Types

#### FolderSinkBigqueryOptions
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#FolderSinkBigqueryOptions">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#FolderSinkBigqueryOptions">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/logging?tab=doc#FolderSinkBigqueryOptionsArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/logging?tab=doc#FolderSinkBigqueryOptionsOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Logging.FolderSinkBigqueryOptionsArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Logging.FolderSinkBigqueryOptions.html">output</a> API doc for this type.
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
            <td class="align-top">Use<wbr>Partitioned<wbr>Tables</td>
            <td class="align-top">
                
                <code>bool</code>
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
            <td class="align-top">Use<wbr>Partitioned<wbr>Tables</td>
            <td class="align-top">
                
                <code>bool</code>
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
            <td class="align-top">use<wbr>Partitioned<wbr>Tables</td>
            <td class="align-top">
                
                <code>boolean</code>
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
            <td class="align-top">use<wbr>Partitioned<wbr>Tables</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}








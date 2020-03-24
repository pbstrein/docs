
---
title: "DataTransferConfig"
block_external_search_index: true
---
<style>
table td p { margin-top: 0; margin-bottom: 0; }
</style>

Represents a data transfer configuration. A transfer configuration
contains all metadata needed to perform a data transfer.


To get more information about Config, see:

* [API documentation](https://cloud.google.com/bigquery/docs/reference/datatransfer/rest/v1/projects.locations.transferConfigs/create)
* How-to Guides
    * [Official Documentation](https://cloud.google.com/bigquery/docs/reference/datatransfer/rest/)

> This content is derived from https://github.com/terraform-providers/terraform-provider-google/blob/master/website/docs/r/bigquery_data_transfer_config.html.markdown.



## Create a DataTransferConfig Resource

{{< langchoose csharp nojavascript >}}

<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/bigquery/#DataTransferConfig">DataTransferConfig</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/bigquery/#DataTransferConfigArgs">DataTransferConfigArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">DataTransferConfig</span><span class="p">(resource_name, opts=None, </span>data_refresh_window_days=None<span class="p">, </span>data_source_id=None<span class="p">, </span>destination_dataset_id=None<span class="p">, </span>disabled=None<span class="p">, </span>display_name=None<span class="p">, </span>location=None<span class="p">, </span>params=None<span class="p">, </span>project=None<span class="p">, </span>schedule=None<span class="p">, __props__=None);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewDataTransferConfig<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/bigquery?tab=doc#DataTransferConfigArgs">DataTransferConfigArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/bigquery?tab=doc#DataTransferConfig">DataTransferConfig</a></span>, error)</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Bigquery.DataTransferConfig.html">DataTransferConfig</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Bigquery.DataTransferConfigArgs.html">DataTransferConfigArgs</a></span> <span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>

Creates a DataTransferConfig resource with the given unique name, arguments, and options.

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
            <td class="align-top">Data<wbr>Refresh<wbr>Window<wbr>Days</td>
            <td class="align-top">
                
                <code>int?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The number of days to look back to automatically refresh the data. For example, if dataRefreshWindowDays = 10, then
every day BigQuery reingests data for [today-10, today-1], rather than ingesting data for just [today-1]. Only valid if
the data source supports the feature. Set the value to 0 to use the default value.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Data<wbr>Source<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The data source id. Cannot be changed once the transfer config is created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Destination<wbr>Dataset<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The BigQuery target dataset id.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Disabled</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
When set to true, no runs are scheduled for a given transfer.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Display<wbr>Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The user specified display name for the transfer config.
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
The geographic location where the transfer config should reside. Examples: US, EU, asia-northeast1. The default value is
US.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Params</td>
            <td class="align-top">
                
                <code>Dictionary<string, string></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
These parameters are specific to each data source.
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
            <td class="align-top">Schedule</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Data transfer schedule. If the data source does not support a custom schedule, this should be empty. If it is empty, the
default value for the data source will be used. The specified times are in UTC. Examples of valid format: 1st,3rd monday
of month 15:30, every wed,fri of jan, jun 13:15, and first sunday of quarter 00:00. See more explanation about the
format here: https://cloud.google.com/appengine/docs/flexible/python/scheduling-jobs-with-cron-yaml#the_schedule_format
NOTE: the granularity should be at least 8 hours, or less frequent.
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
            <td class="align-top">Data<wbr>Refresh<wbr>Window<wbr>Days</td>
            <td class="align-top">
                
                <code>*int</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The number of days to look back to automatically refresh the data. For example, if dataRefreshWindowDays = 10, then
every day BigQuery reingests data for [today-10, today-1], rather than ingesting data for just [today-1]. Only valid if
the data source supports the feature. Set the value to 0 to use the default value.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Data<wbr>Source<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The data source id. Cannot be changed once the transfer config is created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Destination<wbr>Dataset<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The BigQuery target dataset id.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Disabled</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
When set to true, no runs are scheduled for a given transfer.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Display<wbr>Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The user specified display name for the transfer config.
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
The geographic location where the transfer config should reside. Examples: US, EU, asia-northeast1. The default value is
US.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Params</td>
            <td class="align-top">
                
                <code>map[string]string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
These parameters are specific to each data source.
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
            <td class="align-top">Schedule</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Data transfer schedule. If the data source does not support a custom schedule, this should be empty. If it is empty, the
default value for the data source will be used. The specified times are in UTC. Examples of valid format: 1st,3rd monday
of month 15:30, every wed,fri of jan, jun 13:15, and first sunday of quarter 00:00. See more explanation about the
format here: https://cloud.google.com/appengine/docs/flexible/python/scheduling-jobs-with-cron-yaml#the_schedule_format
NOTE: the granularity should be at least 8 hours, or less frequent.
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
            <td class="align-top">data<wbr>Refresh<wbr>Window<wbr>Days</td>
            <td class="align-top">
                
                <code>number?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The number of days to look back to automatically refresh the data. For example, if dataRefreshWindowDays = 10, then
every day BigQuery reingests data for [today-10, today-1], rather than ingesting data for just [today-1]. Only valid if
the data source supports the feature. Set the value to 0 to use the default value.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">data<wbr>Source<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The data source id. Cannot be changed once the transfer config is created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">destination<wbr>Dataset<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The BigQuery target dataset id.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">disabled</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
When set to true, no runs are scheduled for a given transfer.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">display<wbr>Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The user specified display name for the transfer config.
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
The geographic location where the transfer config should reside. Examples: US, EU, asia-northeast1. The default value is
US.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">params</td>
            <td class="align-top">
                
                <code>{[key: string]: string}</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
These parameters are specific to each data source.
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
            <td class="align-top">schedule</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Data transfer schedule. If the data source does not support a custom schedule, this should be empty. If it is empty, the
default value for the data source will be used. The specified times are in UTC. Examples of valid format: 1st,3rd monday
of month 15:30, every wed,fri of jan, jun 13:15, and first sunday of quarter 00:00. See more explanation about the
format here: https://cloud.google.com/appengine/docs/flexible/python/scheduling-jobs-with-cron-yaml#the_schedule_format
NOTE: the granularity should be at least 8 hours, or less frequent.
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
            <td class="align-top">data_<wbr>refresh_<wbr>window_<wbr>days</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The number of days to look back to automatically refresh the data. For example, if dataRefreshWindowDays = 10, then
every day BigQuery reingests data for [today-10, today-1], rather than ingesting data for just [today-1]. Only valid if
the data source supports the feature. Set the value to 0 to use the default value.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">data_<wbr>source_<wbr>id</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The data source id. Cannot be changed once the transfer config is created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">destination_<wbr>dataset_<wbr>id</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The BigQuery target dataset id.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">disabled</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
When set to true, no runs are scheduled for a given transfer.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">display_<wbr>name</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The user specified display name for the transfer config.
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
The geographic location where the transfer config should reside. Examples: US, EU, asia-northeast1. The default value is
US.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">params</td>
            <td class="align-top">
                
                <code>Dict[str, str]</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
These parameters are specific to each data source.
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
            <td class="align-top">schedule</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Data transfer schedule. If the data source does not support a custom schedule, this should be empty. If it is empty, the
default value for the data source will be used. The specified times are in UTC. Examples of valid format: 1st,3rd monday
of month 15:30, every wed,fri of jan, jun 13:15, and first sunday of quarter 00:00. See more explanation about the
format here: https://cloud.google.com/appengine/docs/flexible/python/scheduling-jobs-with-cron-yaml#the_schedule_format
NOTE: the granularity should be at least 8 hours, or less frequent.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}







## DataTransferConfig Output Properties

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
            <td class="align-top">Data<wbr>Refresh<wbr>Window<wbr>Days</td>
            <td class="align-top">
                
                <code>int?</code>
            </td>
            <td class="align-top">{{% md %}} The number of days to look back to automatically refresh the data. For example, if dataRefreshWindowDays = 10, then
every day BigQuery reingests data for [today-10, today-1], rather than ingesting data for just [today-1]. Only valid if
the data source supports the feature. Set the value to 0 to use the default value.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Data<wbr>Source<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The data source id. Cannot be changed once the transfer config is created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Destination<wbr>Dataset<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The BigQuery target dataset id.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Disabled</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} When set to true, no runs are scheduled for a given transfer.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Display<wbr>Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The user specified display name for the transfer config.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Location</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} The geographic location where the transfer config should reside. Examples: US, EU, asia-northeast1. The default value is
US.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The resource name of the transfer config. Transfer config names have the form
projects/{projectId}/locations/{location}/transferConfigs/{configId}. Where configId is usually a uuid, but this is not
required. The name is ignored when creating a transfer config.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Params</td>
            <td class="align-top">
                
                <code>Dictionary<string, string></code>
            </td>
            <td class="align-top">{{% md %}} These parameters are specific to each data source.
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
            <td class="align-top">Schedule</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} Data transfer schedule. If the data source does not support a custom schedule, this should be empty. If it is empty, the
default value for the data source will be used. The specified times are in UTC. Examples of valid format: 1st,3rd monday
of month 15:30, every wed,fri of jan, jun 13:15, and first sunday of quarter 00:00. See more explanation about the
format here: https://cloud.google.com/appengine/docs/flexible/python/scheduling-jobs-with-cron-yaml#the_schedule_format
NOTE: the granularity should be at least 8 hours, or less frequent.
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
            <td class="align-top">Data<wbr>Refresh<wbr>Window<wbr>Days</td>
            <td class="align-top">
                
                <code>*int</code>
            </td>
            <td class="align-top">{{% md %}} The number of days to look back to automatically refresh the data. For example, if dataRefreshWindowDays = 10, then
every day BigQuery reingests data for [today-10, today-1], rather than ingesting data for just [today-1]. Only valid if
the data source supports the feature. Set the value to 0 to use the default value.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Data<wbr>Source<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The data source id. Cannot be changed once the transfer config is created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Destination<wbr>Dataset<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The BigQuery target dataset id.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Disabled</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} When set to true, no runs are scheduled for a given transfer.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Display<wbr>Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The user specified display name for the transfer config.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Location</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} The geographic location where the transfer config should reside. Examples: US, EU, asia-northeast1. The default value is
US.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The resource name of the transfer config. Transfer config names have the form
projects/{projectId}/locations/{location}/transferConfigs/{configId}. Where configId is usually a uuid, but this is not
required. The name is ignored when creating a transfer config.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Params</td>
            <td class="align-top">
                
                <code>map[string]string</code>
            </td>
            <td class="align-top">{{% md %}} These parameters are specific to each data source.
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
            <td class="align-top">Schedule</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} Data transfer schedule. If the data source does not support a custom schedule, this should be empty. If it is empty, the
default value for the data source will be used. The specified times are in UTC. Examples of valid format: 1st,3rd monday
of month 15:30, every wed,fri of jan, jun 13:15, and first sunday of quarter 00:00. See more explanation about the
format here: https://cloud.google.com/appengine/docs/flexible/python/scheduling-jobs-with-cron-yaml#the_schedule_format
NOTE: the granularity should be at least 8 hours, or less frequent.
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
            <td class="align-top">data<wbr>Refresh<wbr>Window<wbr>Days</td>
            <td class="align-top">
                
                <code>number?</code>
            </td>
            <td class="align-top">{{% md %}} The number of days to look back to automatically refresh the data. For example, if dataRefreshWindowDays = 10, then
every day BigQuery reingests data for [today-10, today-1], rather than ingesting data for just [today-1]. Only valid if
the data source supports the feature. Set the value to 0 to use the default value.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">data<wbr>Source<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The data source id. Cannot be changed once the transfer config is created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">destination<wbr>Dataset<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The BigQuery target dataset id.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">disabled</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} When set to true, no runs are scheduled for a given transfer.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">display<wbr>Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The user specified display name for the transfer config.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">location</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} The geographic location where the transfer config should reside. Examples: US, EU, asia-northeast1. The default value is
US.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The resource name of the transfer config. Transfer config names have the form
projects/{projectId}/locations/{location}/transferConfigs/{configId}. Where configId is usually a uuid, but this is not
required. The name is ignored when creating a transfer config.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">params</td>
            <td class="align-top">
                
                <code>{[key: string]: string}</code>
            </td>
            <td class="align-top">{{% md %}} These parameters are specific to each data source.
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
            <td class="align-top">schedule</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} Data transfer schedule. If the data source does not support a custom schedule, this should be empty. If it is empty, the
default value for the data source will be used. The specified times are in UTC. Examples of valid format: 1st,3rd monday
of month 15:30, every wed,fri of jan, jun 13:15, and first sunday of quarter 00:00. See more explanation about the
format here: https://cloud.google.com/appengine/docs/flexible/python/scheduling-jobs-with-cron-yaml#the_schedule_format
NOTE: the granularity should be at least 8 hours, or less frequent.
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
            <td class="align-top">data_<wbr>refresh_<wbr>window_<wbr>days</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} The number of days to look back to automatically refresh the data. For example, if dataRefreshWindowDays = 10, then
every day BigQuery reingests data for [today-10, today-1], rather than ingesting data for just [today-1]. Only valid if
the data source supports the feature. Set the value to 0 to use the default value.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">data_<wbr>source_<wbr>id</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The data source id. Cannot be changed once the transfer config is created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">destination_<wbr>dataset_<wbr>id</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The BigQuery target dataset id.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">disabled</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} When set to true, no runs are scheduled for a given transfer.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">display_<wbr>name</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The user specified display name for the transfer config.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">location</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The geographic location where the transfer config should reside. Examples: US, EU, asia-northeast1. The default value is
US.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">name</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The resource name of the transfer config. Transfer config names have the form
projects/{projectId}/locations/{location}/transferConfigs/{configId}. Where configId is usually a uuid, but this is not
required. The name is ignored when creating a transfer config.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">params</td>
            <td class="align-top">
                
                <code>Dict[str, str]</code>
            </td>
            <td class="align-top">{{% md %}} These parameters are specific to each data source.
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
            <td class="align-top">schedule</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} Data transfer schedule. If the data source does not support a custom schedule, this should be empty. If it is empty, the
default value for the data source will be used. The specified times are in UTC. Examples of valid format: 1st,3rd monday
of month 15:30, every wed,fri of jan, jun 13:15, and first sunday of quarter 00:00. See more explanation about the
format here: https://cloud.google.com/appengine/docs/flexible/python/scheduling-jobs-with-cron-yaml#the_schedule_format
NOTE: the granularity should be at least 8 hours, or less frequent.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}








## Look up an Existing DataTransferConfig Resource

{{< langchoose csharp nojavascript >}}

<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">pulumi.Input&lt;pulumi.ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/bigquery/#DataTransferConfigState">DataTransferConfigState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/bigquery/#DataTransferConfig">DataTransferConfig</a></span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>data_refresh_window_days=None<span class="p">, </span>data_source_id=None<span class="p">, </span>destination_dataset_id=None<span class="p">, </span>disabled=None<span class="p">, </span>display_name=None<span class="p">, </span>location=None<span class="p">, </span>name=None<span class="p">, </span>params=None<span class="p">, </span>project=None<span class="p">, </span>schedule=None<span class="p">, __props__=None);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetDataTransferConfig<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">pulumi.IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/bigquery?tab=doc#DataTransferConfigState">DataTransferConfigState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/bigquery?tab=doc#DataTransferConfig">DataTransferConfig</a></span>, error)</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Bigquery.DataTransferConfig.html">DataTransferConfig</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Pulumi.Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Bigquery.DataTransferConfigState.html">DataTransferConfigState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>

Get an existing DataTransferConfig resource's state with the given name, ID, and optional extra properties used to qualify the lookup.

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
            <td class="align-top">Data<wbr>Refresh<wbr>Window<wbr>Days</td>
            <td class="align-top">
                
                <code>int?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The number of days to look back to automatically refresh the data. For example, if dataRefreshWindowDays = 10, then
every day BigQuery reingests data for [today-10, today-1], rather than ingesting data for just [today-1]. Only valid if
the data source supports the feature. Set the value to 0 to use the default value.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Data<wbr>Source<wbr>Id</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The data source id. Cannot be changed once the transfer config is created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Destination<wbr>Dataset<wbr>Id</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The BigQuery target dataset id.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Disabled</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
When set to true, no runs are scheduled for a given transfer.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Display<wbr>Name</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The user specified display name for the transfer config.
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
The geographic location where the transfer config should reside. Examples: US, EU, asia-northeast1. The default value is
US.
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
The resource name of the transfer config. Transfer config names have the form
projects/{projectId}/locations/{location}/transferConfigs/{configId}. Where configId is usually a uuid, but this is not
required. The name is ignored when creating a transfer config.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Params</td>
            <td class="align-top">
                
                <code>Dictionary<string, string>?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
These parameters are specific to each data source.
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
            <td class="align-top">Schedule</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Data transfer schedule. If the data source does not support a custom schedule, this should be empty. If it is empty, the
default value for the data source will be used. The specified times are in UTC. Examples of valid format: 1st,3rd monday
of month 15:30, every wed,fri of jan, jun 13:15, and first sunday of quarter 00:00. See more explanation about the
format here: https://cloud.google.com/appengine/docs/flexible/python/scheduling-jobs-with-cron-yaml#the_schedule_format
NOTE: the granularity should be at least 8 hours, or less frequent.
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
            <td class="align-top">Data<wbr>Refresh<wbr>Window<wbr>Days</td>
            <td class="align-top">
                
                <code>*int</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The number of days to look back to automatically refresh the data. For example, if dataRefreshWindowDays = 10, then
every day BigQuery reingests data for [today-10, today-1], rather than ingesting data for just [today-1]. Only valid if
the data source supports the feature. Set the value to 0 to use the default value.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Data<wbr>Source<wbr>Id</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The data source id. Cannot be changed once the transfer config is created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Destination<wbr>Dataset<wbr>Id</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The BigQuery target dataset id.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Disabled</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
When set to true, no runs are scheduled for a given transfer.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Display<wbr>Name</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The user specified display name for the transfer config.
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
The geographic location where the transfer config should reside. Examples: US, EU, asia-northeast1. The default value is
US.
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
The resource name of the transfer config. Transfer config names have the form
projects/{projectId}/locations/{location}/transferConfigs/{configId}. Where configId is usually a uuid, but this is not
required. The name is ignored when creating a transfer config.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Params</td>
            <td class="align-top">
                
                <code>map[string]string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
These parameters are specific to each data source.
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
            <td class="align-top">Schedule</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Data transfer schedule. If the data source does not support a custom schedule, this should be empty. If it is empty, the
default value for the data source will be used. The specified times are in UTC. Examples of valid format: 1st,3rd monday
of month 15:30, every wed,fri of jan, jun 13:15, and first sunday of quarter 00:00. See more explanation about the
format here: https://cloud.google.com/appengine/docs/flexible/python/scheduling-jobs-with-cron-yaml#the_schedule_format
NOTE: the granularity should be at least 8 hours, or less frequent.
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
            <td class="align-top">data<wbr>Refresh<wbr>Window<wbr>Days</td>
            <td class="align-top">
                
                <code>number?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The number of days to look back to automatically refresh the data. For example, if dataRefreshWindowDays = 10, then
every day BigQuery reingests data for [today-10, today-1], rather than ingesting data for just [today-1]. Only valid if
the data source supports the feature. Set the value to 0 to use the default value.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">data<wbr>Source<wbr>Id</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The data source id. Cannot be changed once the transfer config is created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">destination<wbr>Dataset<wbr>Id</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The BigQuery target dataset id.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">disabled</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
When set to true, no runs are scheduled for a given transfer.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">display<wbr>Name</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The user specified display name for the transfer config.
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
The geographic location where the transfer config should reside. Examples: US, EU, asia-northeast1. The default value is
US.
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
The resource name of the transfer config. Transfer config names have the form
projects/{projectId}/locations/{location}/transferConfigs/{configId}. Where configId is usually a uuid, but this is not
required. The name is ignored when creating a transfer config.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">params</td>
            <td class="align-top">
                
                <code>{[key: string]: string}?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
These parameters are specific to each data source.
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
            <td class="align-top">schedule</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Data transfer schedule. If the data source does not support a custom schedule, this should be empty. If it is empty, the
default value for the data source will be used. The specified times are in UTC. Examples of valid format: 1st,3rd monday
of month 15:30, every wed,fri of jan, jun 13:15, and first sunday of quarter 00:00. See more explanation about the
format here: https://cloud.google.com/appengine/docs/flexible/python/scheduling-jobs-with-cron-yaml#the_schedule_format
NOTE: the granularity should be at least 8 hours, or less frequent.
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
            <td class="align-top">data_<wbr>refresh_<wbr>window_<wbr>days</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The number of days to look back to automatically refresh the data. For example, if dataRefreshWindowDays = 10, then
every day BigQuery reingests data for [today-10, today-1], rather than ingesting data for just [today-1]. Only valid if
the data source supports the feature. Set the value to 0 to use the default value.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">data_<wbr>source_<wbr>id</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The data source id. Cannot be changed once the transfer config is created.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">destination_<wbr>dataset_<wbr>id</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The BigQuery target dataset id.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">disabled</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
When set to true, no runs are scheduled for a given transfer.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">display_<wbr>name</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The user specified display name for the transfer config.
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
The geographic location where the transfer config should reside. Examples: US, EU, asia-northeast1. The default value is
US.
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
The resource name of the transfer config. Transfer config names have the form
projects/{projectId}/locations/{location}/transferConfigs/{configId}. Where configId is usually a uuid, but this is not
required. The name is ignored when creating a transfer config.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">params</td>
            <td class="align-top">
                
                <code>Dict[str, str]</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
These parameters are specific to each data source.
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
            <td class="align-top">schedule</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
Data transfer schedule. If the data source does not support a custom schedule, this should be empty. If it is empty, the
default value for the data source will be used. The specified times are in UTC. Examples of valid format: 1st,3rd monday
of month 15:30, every wed,fri of jan, jun 13:15, and first sunday of quarter 00:00. See more explanation about the
format here: https://cloud.google.com/appengine/docs/flexible/python/scheduling-jobs-with-cron-yaml#the_schedule_format
NOTE: the granularity should be at least 8 hours, or less frequent.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}










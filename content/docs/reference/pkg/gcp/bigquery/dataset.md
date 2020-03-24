
---
title: "Dataset"
block_external_search_index: true
---
<style>
table td p { margin-top: 0; margin-bottom: 0; }
</style>

Datasets allow you to organize and control access to your tables.

> This content is derived from https://github.com/terraform-providers/terraform-provider-google/blob/master/website/docs/r/bigquery_dataset.html.markdown.



## Create a Dataset Resource

{{< langchoose csharp nojavascript >}}

<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/bigquery/#Dataset">Dataset</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/bigquery/#DatasetArgs">DatasetArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">Dataset</span><span class="p">(resource_name, opts=None, </span>accesses=None<span class="p">, </span>dataset_id=None<span class="p">, </span>default_encryption_configuration=None<span class="p">, </span>default_partition_expiration_ms=None<span class="p">, </span>default_table_expiration_ms=None<span class="p">, </span>delete_contents_on_destroy=None<span class="p">, </span>description=None<span class="p">, </span>friendly_name=None<span class="p">, </span>labels=None<span class="p">, </span>location=None<span class="p">, </span>project=None<span class="p">, __props__=None);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewDataset<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/bigquery?tab=doc#DatasetArgs">DatasetArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/bigquery?tab=doc#Dataset">Dataset</a></span>, error)</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Bigquery.Dataset.html">Dataset</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Bigquery.DatasetArgs.html">DatasetArgs</a></span> <span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>

Creates a Dataset resource with the given unique name, arguments, and options.

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
            <td class="align-top">Accesses</td>
            <td class="align-top">
                
                <code><a href="#datasetaccess">List&lt;Dataset<wbr>Access<wbr>Args&gt;?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
An array of objects that define dataset access for one or more entities.
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
A unique ID for this dataset, without the project name. The ID must contain only letters (a-z, A-Z), numbers (0-9), or
underscores (_). The maximum length is 1,024 characters.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Default<wbr>Encryption<wbr>Configuration</td>
            <td class="align-top">
                
                <code><a href="#datasetdefaultencryptionconfiguration">Dataset<wbr>Default<wbr>Encryption<wbr>Configuration<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The default encryption key for all tables in the dataset. Once this property is set, all newly-created partitioned
tables in the dataset will have encryption key set to this value, unless table creation request (or query) overrides the
key.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Default<wbr>Partition<wbr>Expiration<wbr>Ms</td>
            <td class="align-top">
                
                <code>int?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The default partition expiration for all partitioned tables in the dataset, in milliseconds. Once this property is set,
all newly-created partitioned tables in the dataset will have an &#39;expirationMs&#39; property in the &#39;timePartitioning&#39;
settings set to this value, and changing the value will only affect new tables, not existing ones. The storage in a
partition will have an expiration time of its partition time plus this value. Setting this property overrides the use of
&#39;defaultTableExpirationMs&#39; for partitioned tables: only one of &#39;defaultTableExpirationMs&#39; and
&#39;defaultPartitionExpirationMs&#39; will be used for any new partitioned table. If you provide an explicit
&#39;timePartitioning.expirationMs&#39; when creating or updating a partitioned table, that value takes precedence over the
default partition expiration time indicated by this property.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Default<wbr>Table<wbr>Expiration<wbr>Ms</td>
            <td class="align-top">
                
                <code>int?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The default lifetime of all tables in the dataset, in milliseconds. The minimum value is 3600000 milliseconds (one
hour). Once this property is set, all newly-created tables in the dataset will have an &#39;expirationTime&#39; property set to
the creation time plus the value in this property, and changing the value will only affect new tables, not existing
ones. When the &#39;expirationTime&#39; for a given table is reached, that table will be deleted automatically. If a table&#39;s
&#39;expirationTime&#39; is modified or removed before the table expires, or if you provide an explicit &#39;expirationTime&#39; when
creating a table, that value takes precedence over the default expiration time indicated by this property.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Delete<wbr>Contents<wbr>On<wbr>Destroy</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
If set to `true`, delete all the tables in the
dataset when destroying the resource; otherwise,
destroying the resource will fail if tables are present.
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
A user-friendly description of the dataset
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
A descriptive name for the dataset
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
The labels associated with this dataset. You can use these to organize and group your datasets
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
The geographic location where the dataset should reside. See [official
docs](https://cloud.google.com/bigquery/docs/dataset-locations). There are two types of locations, regional or
multi-regional. A regional location is a specific geographic place, such as Tokyo, and a multi-regional location is a
large geographic area, such as the United States, that contains at least two geographic places. Possible regional values
include: &#39;asia-east1&#39;, &#39;asia-northeast1&#39;, &#39;asia-southeast1&#39;, &#39;australia-southeast1&#39;, &#39;europe-north1&#39;, &#39;europe-west2&#39; and
&#39;us-east4&#39;. Possible multi-regional values: &#39;EU&#39; and &#39;US&#39;. The default value is multi-regional location &#39;US&#39;. Changing
this forces a new resource to be created.
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
            <td class="align-top">Accesses</td>
            <td class="align-top">
                
                <code><a href="#datasetaccess">[]Dataset<wbr>Access</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
An array of objects that define dataset access for one or more entities.
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
A unique ID for this dataset, without the project name. The ID must contain only letters (a-z, A-Z), numbers (0-9), or
underscores (_). The maximum length is 1,024 characters.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Default<wbr>Encryption<wbr>Configuration</td>
            <td class="align-top">
                
                <code><a href="#datasetdefaultencryptionconfiguration">*Dataset<wbr>Default<wbr>Encryption<wbr>Configuration</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The default encryption key for all tables in the dataset. Once this property is set, all newly-created partitioned
tables in the dataset will have encryption key set to this value, unless table creation request (or query) overrides the
key.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Default<wbr>Partition<wbr>Expiration<wbr>Ms</td>
            <td class="align-top">
                
                <code>*int</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The default partition expiration for all partitioned tables in the dataset, in milliseconds. Once this property is set,
all newly-created partitioned tables in the dataset will have an &#39;expirationMs&#39; property in the &#39;timePartitioning&#39;
settings set to this value, and changing the value will only affect new tables, not existing ones. The storage in a
partition will have an expiration time of its partition time plus this value. Setting this property overrides the use of
&#39;defaultTableExpirationMs&#39; for partitioned tables: only one of &#39;defaultTableExpirationMs&#39; and
&#39;defaultPartitionExpirationMs&#39; will be used for any new partitioned table. If you provide an explicit
&#39;timePartitioning.expirationMs&#39; when creating or updating a partitioned table, that value takes precedence over the
default partition expiration time indicated by this property.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Default<wbr>Table<wbr>Expiration<wbr>Ms</td>
            <td class="align-top">
                
                <code>*int</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The default lifetime of all tables in the dataset, in milliseconds. The minimum value is 3600000 milliseconds (one
hour). Once this property is set, all newly-created tables in the dataset will have an &#39;expirationTime&#39; property set to
the creation time plus the value in this property, and changing the value will only affect new tables, not existing
ones. When the &#39;expirationTime&#39; for a given table is reached, that table will be deleted automatically. If a table&#39;s
&#39;expirationTime&#39; is modified or removed before the table expires, or if you provide an explicit &#39;expirationTime&#39; when
creating a table, that value takes precedence over the default expiration time indicated by this property.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Delete<wbr>Contents<wbr>On<wbr>Destroy</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
If set to `true`, delete all the tables in the
dataset when destroying the resource; otherwise,
destroying the resource will fail if tables are present.
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
A user-friendly description of the dataset
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
A descriptive name for the dataset
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
The labels associated with this dataset. You can use these to organize and group your datasets
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
The geographic location where the dataset should reside. See [official
docs](https://cloud.google.com/bigquery/docs/dataset-locations). There are two types of locations, regional or
multi-regional. A regional location is a specific geographic place, such as Tokyo, and a multi-regional location is a
large geographic area, such as the United States, that contains at least two geographic places. Possible regional values
include: &#39;asia-east1&#39;, &#39;asia-northeast1&#39;, &#39;asia-southeast1&#39;, &#39;australia-southeast1&#39;, &#39;europe-north1&#39;, &#39;europe-west2&#39; and
&#39;us-east4&#39;. Possible multi-regional values: &#39;EU&#39; and &#39;US&#39;. The default value is multi-regional location &#39;US&#39;. Changing
this forces a new resource to be created.
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
            <td class="align-top">accesses</td>
            <td class="align-top">
                
                <code><a href="#datasetaccess">Dataset<wbr>Access[]?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
An array of objects that define dataset access for one or more entities.
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
A unique ID for this dataset, without the project name. The ID must contain only letters (a-z, A-Z), numbers (0-9), or
underscores (_). The maximum length is 1,024 characters.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">default<wbr>Encryption<wbr>Configuration</td>
            <td class="align-top">
                
                <code><a href="#datasetdefaultencryptionconfiguration">Dataset<wbr>Default<wbr>Encryption<wbr>Configuration?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The default encryption key for all tables in the dataset. Once this property is set, all newly-created partitioned
tables in the dataset will have encryption key set to this value, unless table creation request (or query) overrides the
key.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">default<wbr>Partition<wbr>Expiration<wbr>Ms</td>
            <td class="align-top">
                
                <code>number?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The default partition expiration for all partitioned tables in the dataset, in milliseconds. Once this property is set,
all newly-created partitioned tables in the dataset will have an &#39;expirationMs&#39; property in the &#39;timePartitioning&#39;
settings set to this value, and changing the value will only affect new tables, not existing ones. The storage in a
partition will have an expiration time of its partition time plus this value. Setting this property overrides the use of
&#39;defaultTableExpirationMs&#39; for partitioned tables: only one of &#39;defaultTableExpirationMs&#39; and
&#39;defaultPartitionExpirationMs&#39; will be used for any new partitioned table. If you provide an explicit
&#39;timePartitioning.expirationMs&#39; when creating or updating a partitioned table, that value takes precedence over the
default partition expiration time indicated by this property.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">default<wbr>Table<wbr>Expiration<wbr>Ms</td>
            <td class="align-top">
                
                <code>number?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The default lifetime of all tables in the dataset, in milliseconds. The minimum value is 3600000 milliseconds (one
hour). Once this property is set, all newly-created tables in the dataset will have an &#39;expirationTime&#39; property set to
the creation time plus the value in this property, and changing the value will only affect new tables, not existing
ones. When the &#39;expirationTime&#39; for a given table is reached, that table will be deleted automatically. If a table&#39;s
&#39;expirationTime&#39; is modified or removed before the table expires, or if you provide an explicit &#39;expirationTime&#39; when
creating a table, that value takes precedence over the default expiration time indicated by this property.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">delete<wbr>Contents<wbr>On<wbr>Destroy</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
If set to `true`, delete all the tables in the
dataset when destroying the resource; otherwise,
destroying the resource will fail if tables are present.
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
A user-friendly description of the dataset
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
A descriptive name for the dataset
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
The labels associated with this dataset. You can use these to organize and group your datasets
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
The geographic location where the dataset should reside. See [official
docs](https://cloud.google.com/bigquery/docs/dataset-locations). There are two types of locations, regional or
multi-regional. A regional location is a specific geographic place, such as Tokyo, and a multi-regional location is a
large geographic area, such as the United States, that contains at least two geographic places. Possible regional values
include: &#39;asia-east1&#39;, &#39;asia-northeast1&#39;, &#39;asia-southeast1&#39;, &#39;australia-southeast1&#39;, &#39;europe-north1&#39;, &#39;europe-west2&#39; and
&#39;us-east4&#39;. Possible multi-regional values: &#39;EU&#39; and &#39;US&#39;. The default value is multi-regional location &#39;US&#39;. Changing
this forces a new resource to be created.
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
            <td class="align-top">accesses</td>
            <td class="align-top">
                
                <code><a href="#datasetaccess">List[Dataset<wbr>Access]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
An array of objects that define dataset access for one or more entities.
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
A unique ID for this dataset, without the project name. The ID must contain only letters (a-z, A-Z), numbers (0-9), or
underscores (_). The maximum length is 1,024 characters.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">default_<wbr>encryption_<wbr>configuration</td>
            <td class="align-top">
                
                <code><a href="#datasetdefaultencryptionconfiguration">Dict[Dataset<wbr>Default<wbr>Encryption<wbr>Configuration]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The default encryption key for all tables in the dataset. Once this property is set, all newly-created partitioned
tables in the dataset will have encryption key set to this value, unless table creation request (or query) overrides the
key.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">default_<wbr>partition_<wbr>expiration_<wbr>ms</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The default partition expiration for all partitioned tables in the dataset, in milliseconds. Once this property is set,
all newly-created partitioned tables in the dataset will have an &#39;expirationMs&#39; property in the &#39;timePartitioning&#39;
settings set to this value, and changing the value will only affect new tables, not existing ones. The storage in a
partition will have an expiration time of its partition time plus this value. Setting this property overrides the use of
&#39;defaultTableExpirationMs&#39; for partitioned tables: only one of &#39;defaultTableExpirationMs&#39; and
&#39;defaultPartitionExpirationMs&#39; will be used for any new partitioned table. If you provide an explicit
&#39;timePartitioning.expirationMs&#39; when creating or updating a partitioned table, that value takes precedence over the
default partition expiration time indicated by this property.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">default_<wbr>table_<wbr>expiration_<wbr>ms</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The default lifetime of all tables in the dataset, in milliseconds. The minimum value is 3600000 milliseconds (one
hour). Once this property is set, all newly-created tables in the dataset will have an &#39;expirationTime&#39; property set to
the creation time plus the value in this property, and changing the value will only affect new tables, not existing
ones. When the &#39;expirationTime&#39; for a given table is reached, that table will be deleted automatically. If a table&#39;s
&#39;expirationTime&#39; is modified or removed before the table expires, or if you provide an explicit &#39;expirationTime&#39; when
creating a table, that value takes precedence over the default expiration time indicated by this property.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">delete_<wbr>contents_<wbr>on_<wbr>destroy</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
If set to `true`, delete all the tables in the
dataset when destroying the resource; otherwise,
destroying the resource will fail if tables are present.
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
A user-friendly description of the dataset
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
A descriptive name for the dataset
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
The labels associated with this dataset. You can use these to organize and group your datasets
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
The geographic location where the dataset should reside. See [official
docs](https://cloud.google.com/bigquery/docs/dataset-locations). There are two types of locations, regional or
multi-regional. A regional location is a specific geographic place, such as Tokyo, and a multi-regional location is a
large geographic area, such as the United States, that contains at least two geographic places. Possible regional values
include: &#39;asia-east1&#39;, &#39;asia-northeast1&#39;, &#39;asia-southeast1&#39;, &#39;australia-southeast1&#39;, &#39;europe-north1&#39;, &#39;europe-west2&#39; and
&#39;us-east4&#39;. Possible multi-regional values: &#39;EU&#39; and &#39;US&#39;. The default value is multi-regional location &#39;US&#39;. Changing
this forces a new resource to be created.
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
    
    </tbody>
</table>


{{% /lang %}}







## Dataset Output Properties

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
            <td class="align-top">Accesses</td>
            <td class="align-top">
                
                <code><a href="#datasetaccess">List&lt;Dataset<wbr>Access&gt;</a></code>
            </td>
            <td class="align-top">{{% md %}} An array of objects that define dataset access for one or more entities.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Creation<wbr>Time</td>
            <td class="align-top">
                
                <code>int</code>
            </td>
            <td class="align-top">{{% md %}} The time when this dataset was created, in milliseconds since the epoch.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Dataset<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} A unique ID for this dataset, without the project name. The ID must contain only letters (a-z, A-Z), numbers (0-9), or
underscores (_). The maximum length is 1,024 characters.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Default<wbr>Encryption<wbr>Configuration</td>
            <td class="align-top">
                
                <code><a href="#datasetdefaultencryptionconfiguration">Dataset<wbr>Default<wbr>Encryption<wbr>Configuration?</a></code>
            </td>
            <td class="align-top">{{% md %}} The default encryption key for all tables in the dataset. Once this property is set, all newly-created partitioned
tables in the dataset will have encryption key set to this value, unless table creation request (or query) overrides the
key.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Default<wbr>Partition<wbr>Expiration<wbr>Ms</td>
            <td class="align-top">
                
                <code>int?</code>
            </td>
            <td class="align-top">{{% md %}} The default partition expiration for all partitioned tables in the dataset, in milliseconds. Once this property is set,
all newly-created partitioned tables in the dataset will have an &#39;expirationMs&#39; property in the &#39;timePartitioning&#39;
settings set to this value, and changing the value will only affect new tables, not existing ones. The storage in a
partition will have an expiration time of its partition time plus this value. Setting this property overrides the use of
&#39;defaultTableExpirationMs&#39; for partitioned tables: only one of &#39;defaultTableExpirationMs&#39; and
&#39;defaultPartitionExpirationMs&#39; will be used for any new partitioned table. If you provide an explicit
&#39;timePartitioning.expirationMs&#39; when creating or updating a partitioned table, that value takes precedence over the
default partition expiration time indicated by this property.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Default<wbr>Table<wbr>Expiration<wbr>Ms</td>
            <td class="align-top">
                
                <code>int?</code>
            </td>
            <td class="align-top">{{% md %}} The default lifetime of all tables in the dataset, in milliseconds. The minimum value is 3600000 milliseconds (one
hour). Once this property is set, all newly-created tables in the dataset will have an &#39;expirationTime&#39; property set to
the creation time plus the value in this property, and changing the value will only affect new tables, not existing
ones. When the &#39;expirationTime&#39; for a given table is reached, that table will be deleted automatically. If a table&#39;s
&#39;expirationTime&#39; is modified or removed before the table expires, or if you provide an explicit &#39;expirationTime&#39; when
creating a table, that value takes precedence over the default expiration time indicated by this property.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Delete<wbr>Contents<wbr>On<wbr>Destroy</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} If set to `true`, delete all the tables in the
dataset when destroying the resource; otherwise,
destroying the resource will fail if tables are present.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Description</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} A user-friendly description of the dataset
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
            <td class="align-top">Friendly<wbr>Name</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} A descriptive name for the dataset
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Labels</td>
            <td class="align-top">
                
                <code>Dictionary<string, string>?</code>
            </td>
            <td class="align-top">{{% md %}} The labels associated with this dataset. You can use these to organize and group your datasets
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Last<wbr>Modified<wbr>Time</td>
            <td class="align-top">
                
                <code>int</code>
            </td>
            <td class="align-top">{{% md %}} The date when this dataset or any of its tables was last modified, in milliseconds since the epoch.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Location</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} The geographic location where the dataset should reside. See [official
docs](https://cloud.google.com/bigquery/docs/dataset-locations). There are two types of locations, regional or
multi-regional. A regional location is a specific geographic place, such as Tokyo, and a multi-regional location is a
large geographic area, such as the United States, that contains at least two geographic places. Possible regional values
include: &#39;asia-east1&#39;, &#39;asia-northeast1&#39;, &#39;asia-southeast1&#39;, &#39;australia-southeast1&#39;, &#39;europe-north1&#39;, &#39;europe-west2&#39; and
&#39;us-east4&#39;. Possible multi-regional values: &#39;EU&#39; and &#39;US&#39;. The default value is multi-regional location &#39;US&#39;. Changing
this forces a new resource to be created.
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
            <td class="align-top">Self<wbr>Link</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The URI of the created resource.
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
            <td class="align-top">Accesses</td>
            <td class="align-top">
                
                <code><a href="#datasetaccess">[]Dataset<wbr>Access</a></code>
            </td>
            <td class="align-top">{{% md %}} An array of objects that define dataset access for one or more entities.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Creation<wbr>Time</td>
            <td class="align-top">
                
                <code>int</code>
            </td>
            <td class="align-top">{{% md %}} The time when this dataset was created, in milliseconds since the epoch.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Dataset<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} A unique ID for this dataset, without the project name. The ID must contain only letters (a-z, A-Z), numbers (0-9), or
underscores (_). The maximum length is 1,024 characters.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Default<wbr>Encryption<wbr>Configuration</td>
            <td class="align-top">
                
                <code><a href="#datasetdefaultencryptionconfiguration">*Dataset<wbr>Default<wbr>Encryption<wbr>Configuration</a></code>
            </td>
            <td class="align-top">{{% md %}} The default encryption key for all tables in the dataset. Once this property is set, all newly-created partitioned
tables in the dataset will have encryption key set to this value, unless table creation request (or query) overrides the
key.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Default<wbr>Partition<wbr>Expiration<wbr>Ms</td>
            <td class="align-top">
                
                <code>*int</code>
            </td>
            <td class="align-top">{{% md %}} The default partition expiration for all partitioned tables in the dataset, in milliseconds. Once this property is set,
all newly-created partitioned tables in the dataset will have an &#39;expirationMs&#39; property in the &#39;timePartitioning&#39;
settings set to this value, and changing the value will only affect new tables, not existing ones. The storage in a
partition will have an expiration time of its partition time plus this value. Setting this property overrides the use of
&#39;defaultTableExpirationMs&#39; for partitioned tables: only one of &#39;defaultTableExpirationMs&#39; and
&#39;defaultPartitionExpirationMs&#39; will be used for any new partitioned table. If you provide an explicit
&#39;timePartitioning.expirationMs&#39; when creating or updating a partitioned table, that value takes precedence over the
default partition expiration time indicated by this property.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Default<wbr>Table<wbr>Expiration<wbr>Ms</td>
            <td class="align-top">
                
                <code>*int</code>
            </td>
            <td class="align-top">{{% md %}} The default lifetime of all tables in the dataset, in milliseconds. The minimum value is 3600000 milliseconds (one
hour). Once this property is set, all newly-created tables in the dataset will have an &#39;expirationTime&#39; property set to
the creation time plus the value in this property, and changing the value will only affect new tables, not existing
ones. When the &#39;expirationTime&#39; for a given table is reached, that table will be deleted automatically. If a table&#39;s
&#39;expirationTime&#39; is modified or removed before the table expires, or if you provide an explicit &#39;expirationTime&#39; when
creating a table, that value takes precedence over the default expiration time indicated by this property.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Delete<wbr>Contents<wbr>On<wbr>Destroy</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} If set to `true`, delete all the tables in the
dataset when destroying the resource; otherwise,
destroying the resource will fail if tables are present.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Description</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} A user-friendly description of the dataset
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
            <td class="align-top">Friendly<wbr>Name</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} A descriptive name for the dataset
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Labels</td>
            <td class="align-top">
                
                <code>map[string]string</code>
            </td>
            <td class="align-top">{{% md %}} The labels associated with this dataset. You can use these to organize and group your datasets
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Last<wbr>Modified<wbr>Time</td>
            <td class="align-top">
                
                <code>int</code>
            </td>
            <td class="align-top">{{% md %}} The date when this dataset or any of its tables was last modified, in milliseconds since the epoch.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Location</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} The geographic location where the dataset should reside. See [official
docs](https://cloud.google.com/bigquery/docs/dataset-locations). There are two types of locations, regional or
multi-regional. A regional location is a specific geographic place, such as Tokyo, and a multi-regional location is a
large geographic area, such as the United States, that contains at least two geographic places. Possible regional values
include: &#39;asia-east1&#39;, &#39;asia-northeast1&#39;, &#39;asia-southeast1&#39;, &#39;australia-southeast1&#39;, &#39;europe-north1&#39;, &#39;europe-west2&#39; and
&#39;us-east4&#39;. Possible multi-regional values: &#39;EU&#39; and &#39;US&#39;. The default value is multi-regional location &#39;US&#39;. Changing
this forces a new resource to be created.
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
            <td class="align-top">Self<wbr>Link</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The URI of the created resource.
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
            <td class="align-top">accesses</td>
            <td class="align-top">
                
                <code><a href="#datasetaccess">Dataset<wbr>Access[]</a></code>
            </td>
            <td class="align-top">{{% md %}} An array of objects that define dataset access for one or more entities.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">creation<wbr>Time</td>
            <td class="align-top">
                
                <code>number</code>
            </td>
            <td class="align-top">{{% md %}} The time when this dataset was created, in milliseconds since the epoch.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">dataset<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} A unique ID for this dataset, without the project name. The ID must contain only letters (a-z, A-Z), numbers (0-9), or
underscores (_). The maximum length is 1,024 characters.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">default<wbr>Encryption<wbr>Configuration</td>
            <td class="align-top">
                
                <code><a href="#datasetdefaultencryptionconfiguration">Dataset<wbr>Default<wbr>Encryption<wbr>Configuration?</a></code>
            </td>
            <td class="align-top">{{% md %}} The default encryption key for all tables in the dataset. Once this property is set, all newly-created partitioned
tables in the dataset will have encryption key set to this value, unless table creation request (or query) overrides the
key.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">default<wbr>Partition<wbr>Expiration<wbr>Ms</td>
            <td class="align-top">
                
                <code>number?</code>
            </td>
            <td class="align-top">{{% md %}} The default partition expiration for all partitioned tables in the dataset, in milliseconds. Once this property is set,
all newly-created partitioned tables in the dataset will have an &#39;expirationMs&#39; property in the &#39;timePartitioning&#39;
settings set to this value, and changing the value will only affect new tables, not existing ones. The storage in a
partition will have an expiration time of its partition time plus this value. Setting this property overrides the use of
&#39;defaultTableExpirationMs&#39; for partitioned tables: only one of &#39;defaultTableExpirationMs&#39; and
&#39;defaultPartitionExpirationMs&#39; will be used for any new partitioned table. If you provide an explicit
&#39;timePartitioning.expirationMs&#39; when creating or updating a partitioned table, that value takes precedence over the
default partition expiration time indicated by this property.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">default<wbr>Table<wbr>Expiration<wbr>Ms</td>
            <td class="align-top">
                
                <code>number?</code>
            </td>
            <td class="align-top">{{% md %}} The default lifetime of all tables in the dataset, in milliseconds. The minimum value is 3600000 milliseconds (one
hour). Once this property is set, all newly-created tables in the dataset will have an &#39;expirationTime&#39; property set to
the creation time plus the value in this property, and changing the value will only affect new tables, not existing
ones. When the &#39;expirationTime&#39; for a given table is reached, that table will be deleted automatically. If a table&#39;s
&#39;expirationTime&#39; is modified or removed before the table expires, or if you provide an explicit &#39;expirationTime&#39; when
creating a table, that value takes precedence over the default expiration time indicated by this property.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">delete<wbr>Contents<wbr>On<wbr>Destroy</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} If set to `true`, delete all the tables in the
dataset when destroying the resource; otherwise,
destroying the resource will fail if tables are present.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">description</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} A user-friendly description of the dataset
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
            <td class="align-top">friendly<wbr>Name</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} A descriptive name for the dataset
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">labels</td>
            <td class="align-top">
                
                <code>{[key: string]: string}?</code>
            </td>
            <td class="align-top">{{% md %}} The labels associated with this dataset. You can use these to organize and group your datasets
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">last<wbr>Modified<wbr>Time</td>
            <td class="align-top">
                
                <code>number</code>
            </td>
            <td class="align-top">{{% md %}} The date when this dataset or any of its tables was last modified, in milliseconds since the epoch.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">location</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} The geographic location where the dataset should reside. See [official
docs](https://cloud.google.com/bigquery/docs/dataset-locations). There are two types of locations, regional or
multi-regional. A regional location is a specific geographic place, such as Tokyo, and a multi-regional location is a
large geographic area, such as the United States, that contains at least two geographic places. Possible regional values
include: &#39;asia-east1&#39;, &#39;asia-northeast1&#39;, &#39;asia-southeast1&#39;, &#39;australia-southeast1&#39;, &#39;europe-north1&#39;, &#39;europe-west2&#39; and
&#39;us-east4&#39;. Possible multi-regional values: &#39;EU&#39; and &#39;US&#39;. The default value is multi-regional location &#39;US&#39;. Changing
this forces a new resource to be created.
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
            <td class="align-top">self<wbr>Link</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The URI of the created resource.
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
            <td class="align-top">accesses</td>
            <td class="align-top">
                
                <code><a href="#datasetaccess">List[Dataset<wbr>Access]</a></code>
            </td>
            <td class="align-top">{{% md %}} An array of objects that define dataset access for one or more entities.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">creation_<wbr>time</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} The time when this dataset was created, in milliseconds since the epoch.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">dataset_<wbr>id</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} A unique ID for this dataset, without the project name. The ID must contain only letters (a-z, A-Z), numbers (0-9), or
underscores (_). The maximum length is 1,024 characters.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">default_<wbr>encryption_<wbr>configuration</td>
            <td class="align-top">
                
                <code><a href="#datasetdefaultencryptionconfiguration">Dict[Dataset<wbr>Default<wbr>Encryption<wbr>Configuration]</a></code>
            </td>
            <td class="align-top">{{% md %}} The default encryption key for all tables in the dataset. Once this property is set, all newly-created partitioned
tables in the dataset will have encryption key set to this value, unless table creation request (or query) overrides the
key.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">default_<wbr>partition_<wbr>expiration_<wbr>ms</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} The default partition expiration for all partitioned tables in the dataset, in milliseconds. Once this property is set,
all newly-created partitioned tables in the dataset will have an &#39;expirationMs&#39; property in the &#39;timePartitioning&#39;
settings set to this value, and changing the value will only affect new tables, not existing ones. The storage in a
partition will have an expiration time of its partition time plus this value. Setting this property overrides the use of
&#39;defaultTableExpirationMs&#39; for partitioned tables: only one of &#39;defaultTableExpirationMs&#39; and
&#39;defaultPartitionExpirationMs&#39; will be used for any new partitioned table. If you provide an explicit
&#39;timePartitioning.expirationMs&#39; when creating or updating a partitioned table, that value takes precedence over the
default partition expiration time indicated by this property.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">default_<wbr>table_<wbr>expiration_<wbr>ms</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} The default lifetime of all tables in the dataset, in milliseconds. The minimum value is 3600000 milliseconds (one
hour). Once this property is set, all newly-created tables in the dataset will have an &#39;expirationTime&#39; property set to
the creation time plus the value in this property, and changing the value will only affect new tables, not existing
ones. When the &#39;expirationTime&#39; for a given table is reached, that table will be deleted automatically. If a table&#39;s
&#39;expirationTime&#39; is modified or removed before the table expires, or if you provide an explicit &#39;expirationTime&#39; when
creating a table, that value takes precedence over the default expiration time indicated by this property.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">delete_<wbr>contents_<wbr>on_<wbr>destroy</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} If set to `true`, delete all the tables in the
dataset when destroying the resource; otherwise,
destroying the resource will fail if tables are present.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">description</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} A user-friendly description of the dataset
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
            <td class="align-top">friendly_<wbr>name</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} A descriptive name for the dataset
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">labels</td>
            <td class="align-top">
                
                <code>Dict[str, str]</code>
            </td>
            <td class="align-top">{{% md %}} The labels associated with this dataset. You can use these to organize and group your datasets
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">last_<wbr>modified_<wbr>time</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} The date when this dataset or any of its tables was last modified, in milliseconds since the epoch.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">location</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The geographic location where the dataset should reside. See [official
docs](https://cloud.google.com/bigquery/docs/dataset-locations). There are two types of locations, regional or
multi-regional. A regional location is a specific geographic place, such as Tokyo, and a multi-regional location is a
large geographic area, such as the United States, that contains at least two geographic places. Possible regional values
include: &#39;asia-east1&#39;, &#39;asia-northeast1&#39;, &#39;asia-southeast1&#39;, &#39;australia-southeast1&#39;, &#39;europe-north1&#39;, &#39;europe-west2&#39; and
&#39;us-east4&#39;. Possible multi-regional values: &#39;EU&#39; and &#39;US&#39;. The default value is multi-regional location &#39;US&#39;. Changing
this forces a new resource to be created.
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
            <td class="align-top">self_<wbr>link</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The URI of the created resource.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}








## Look up an Existing Dataset Resource

{{< langchoose csharp nojavascript >}}

<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">pulumi.Input&lt;pulumi.ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/bigquery/#DatasetState">DatasetState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/bigquery/#Dataset">Dataset</a></span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>accesses=None<span class="p">, </span>creation_time=None<span class="p">, </span>dataset_id=None<span class="p">, </span>default_encryption_configuration=None<span class="p">, </span>default_partition_expiration_ms=None<span class="p">, </span>default_table_expiration_ms=None<span class="p">, </span>delete_contents_on_destroy=None<span class="p">, </span>description=None<span class="p">, </span>etag=None<span class="p">, </span>friendly_name=None<span class="p">, </span>labels=None<span class="p">, </span>last_modified_time=None<span class="p">, </span>location=None<span class="p">, </span>project=None<span class="p">, </span>self_link=None<span class="p">, __props__=None);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetDataset<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">pulumi.IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/bigquery?tab=doc#DatasetState">DatasetState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/bigquery?tab=doc#Dataset">Dataset</a></span>, error)</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Bigquery.Dataset.html">Dataset</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Pulumi.Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Bigquery.DatasetState.html">DatasetState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>

Get an existing Dataset resource's state with the given name, ID, and optional extra properties used to qualify the lookup.

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
            <td class="align-top">Accesses</td>
            <td class="align-top">
                
                <code><a href="#datasetaccess">List&lt;Dataset<wbr>Access<wbr>Args&gt;?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
An array of objects that define dataset access for one or more entities.
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
The time when this dataset was created, in milliseconds since the epoch.
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
A unique ID for this dataset, without the project name. The ID must contain only letters (a-z, A-Z), numbers (0-9), or
underscores (_). The maximum length is 1,024 characters.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Default<wbr>Encryption<wbr>Configuration</td>
            <td class="align-top">
                
                <code><a href="#datasetdefaultencryptionconfiguration">Dataset<wbr>Default<wbr>Encryption<wbr>Configuration<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The default encryption key for all tables in the dataset. Once this property is set, all newly-created partitioned
tables in the dataset will have encryption key set to this value, unless table creation request (or query) overrides the
key.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Default<wbr>Partition<wbr>Expiration<wbr>Ms</td>
            <td class="align-top">
                
                <code>int?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The default partition expiration for all partitioned tables in the dataset, in milliseconds. Once this property is set,
all newly-created partitioned tables in the dataset will have an &#39;expirationMs&#39; property in the &#39;timePartitioning&#39;
settings set to this value, and changing the value will only affect new tables, not existing ones. The storage in a
partition will have an expiration time of its partition time plus this value. Setting this property overrides the use of
&#39;defaultTableExpirationMs&#39; for partitioned tables: only one of &#39;defaultTableExpirationMs&#39; and
&#39;defaultPartitionExpirationMs&#39; will be used for any new partitioned table. If you provide an explicit
&#39;timePartitioning.expirationMs&#39; when creating or updating a partitioned table, that value takes precedence over the
default partition expiration time indicated by this property.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Default<wbr>Table<wbr>Expiration<wbr>Ms</td>
            <td class="align-top">
                
                <code>int?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The default lifetime of all tables in the dataset, in milliseconds. The minimum value is 3600000 milliseconds (one
hour). Once this property is set, all newly-created tables in the dataset will have an &#39;expirationTime&#39; property set to
the creation time plus the value in this property, and changing the value will only affect new tables, not existing
ones. When the &#39;expirationTime&#39; for a given table is reached, that table will be deleted automatically. If a table&#39;s
&#39;expirationTime&#39; is modified or removed before the table expires, or if you provide an explicit &#39;expirationTime&#39; when
creating a table, that value takes precedence over the default expiration time indicated by this property.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Delete<wbr>Contents<wbr>On<wbr>Destroy</td>
            <td class="align-top">
                
                <code>bool?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
If set to `true`, delete all the tables in the
dataset when destroying the resource; otherwise,
destroying the resource will fail if tables are present.
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
A user-friendly description of the dataset
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
            <td class="align-top">Friendly<wbr>Name</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A descriptive name for the dataset
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
The labels associated with this dataset. You can use these to organize and group your datasets
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
The date when this dataset or any of its tables was last modified, in milliseconds since the epoch.
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
The geographic location where the dataset should reside. See [official
docs](https://cloud.google.com/bigquery/docs/dataset-locations). There are two types of locations, regional or
multi-regional. A regional location is a specific geographic place, such as Tokyo, and a multi-regional location is a
large geographic area, such as the United States, that contains at least two geographic places. Possible regional values
include: &#39;asia-east1&#39;, &#39;asia-northeast1&#39;, &#39;asia-southeast1&#39;, &#39;australia-southeast1&#39;, &#39;europe-north1&#39;, &#39;europe-west2&#39; and
&#39;us-east4&#39;. Possible multi-regional values: &#39;EU&#39; and &#39;US&#39;. The default value is multi-regional location &#39;US&#39;. Changing
this forces a new resource to be created.
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
            <td class="align-top">Accesses</td>
            <td class="align-top">
                
                <code><a href="#datasetaccess">[]Dataset<wbr>Access</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
An array of objects that define dataset access for one or more entities.
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
The time when this dataset was created, in milliseconds since the epoch.
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
A unique ID for this dataset, without the project name. The ID must contain only letters (a-z, A-Z), numbers (0-9), or
underscores (_). The maximum length is 1,024 characters.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Default<wbr>Encryption<wbr>Configuration</td>
            <td class="align-top">
                
                <code><a href="#datasetdefaultencryptionconfiguration">*Dataset<wbr>Default<wbr>Encryption<wbr>Configuration</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The default encryption key for all tables in the dataset. Once this property is set, all newly-created partitioned
tables in the dataset will have encryption key set to this value, unless table creation request (or query) overrides the
key.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Default<wbr>Partition<wbr>Expiration<wbr>Ms</td>
            <td class="align-top">
                
                <code>*int</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The default partition expiration for all partitioned tables in the dataset, in milliseconds. Once this property is set,
all newly-created partitioned tables in the dataset will have an &#39;expirationMs&#39; property in the &#39;timePartitioning&#39;
settings set to this value, and changing the value will only affect new tables, not existing ones. The storage in a
partition will have an expiration time of its partition time plus this value. Setting this property overrides the use of
&#39;defaultTableExpirationMs&#39; for partitioned tables: only one of &#39;defaultTableExpirationMs&#39; and
&#39;defaultPartitionExpirationMs&#39; will be used for any new partitioned table. If you provide an explicit
&#39;timePartitioning.expirationMs&#39; when creating or updating a partitioned table, that value takes precedence over the
default partition expiration time indicated by this property.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Default<wbr>Table<wbr>Expiration<wbr>Ms</td>
            <td class="align-top">
                
                <code>*int</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The default lifetime of all tables in the dataset, in milliseconds. The minimum value is 3600000 milliseconds (one
hour). Once this property is set, all newly-created tables in the dataset will have an &#39;expirationTime&#39; property set to
the creation time plus the value in this property, and changing the value will only affect new tables, not existing
ones. When the &#39;expirationTime&#39; for a given table is reached, that table will be deleted automatically. If a table&#39;s
&#39;expirationTime&#39; is modified or removed before the table expires, or if you provide an explicit &#39;expirationTime&#39; when
creating a table, that value takes precedence over the default expiration time indicated by this property.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Delete<wbr>Contents<wbr>On<wbr>Destroy</td>
            <td class="align-top">
                
                <code>*bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
If set to `true`, delete all the tables in the
dataset when destroying the resource; otherwise,
destroying the resource will fail if tables are present.
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
A user-friendly description of the dataset
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
            <td class="align-top">Friendly<wbr>Name</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A descriptive name for the dataset
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
The labels associated with this dataset. You can use these to organize and group your datasets
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
The date when this dataset or any of its tables was last modified, in milliseconds since the epoch.
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
The geographic location where the dataset should reside. See [official
docs](https://cloud.google.com/bigquery/docs/dataset-locations). There are two types of locations, regional or
multi-regional. A regional location is a specific geographic place, such as Tokyo, and a multi-regional location is a
large geographic area, such as the United States, that contains at least two geographic places. Possible regional values
include: &#39;asia-east1&#39;, &#39;asia-northeast1&#39;, &#39;asia-southeast1&#39;, &#39;australia-southeast1&#39;, &#39;europe-north1&#39;, &#39;europe-west2&#39; and
&#39;us-east4&#39;. Possible multi-regional values: &#39;EU&#39; and &#39;US&#39;. The default value is multi-regional location &#39;US&#39;. Changing
this forces a new resource to be created.
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
            <td class="align-top">accesses</td>
            <td class="align-top">
                
                <code><a href="#datasetaccess">Dataset<wbr>Access[]?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
An array of objects that define dataset access for one or more entities.
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
The time when this dataset was created, in milliseconds since the epoch.
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
A unique ID for this dataset, without the project name. The ID must contain only letters (a-z, A-Z), numbers (0-9), or
underscores (_). The maximum length is 1,024 characters.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">default<wbr>Encryption<wbr>Configuration</td>
            <td class="align-top">
                
                <code><a href="#datasetdefaultencryptionconfiguration">Dataset<wbr>Default<wbr>Encryption<wbr>Configuration?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The default encryption key for all tables in the dataset. Once this property is set, all newly-created partitioned
tables in the dataset will have encryption key set to this value, unless table creation request (or query) overrides the
key.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">default<wbr>Partition<wbr>Expiration<wbr>Ms</td>
            <td class="align-top">
                
                <code>number?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The default partition expiration for all partitioned tables in the dataset, in milliseconds. Once this property is set,
all newly-created partitioned tables in the dataset will have an &#39;expirationMs&#39; property in the &#39;timePartitioning&#39;
settings set to this value, and changing the value will only affect new tables, not existing ones. The storage in a
partition will have an expiration time of its partition time plus this value. Setting this property overrides the use of
&#39;defaultTableExpirationMs&#39; for partitioned tables: only one of &#39;defaultTableExpirationMs&#39; and
&#39;defaultPartitionExpirationMs&#39; will be used for any new partitioned table. If you provide an explicit
&#39;timePartitioning.expirationMs&#39; when creating or updating a partitioned table, that value takes precedence over the
default partition expiration time indicated by this property.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">default<wbr>Table<wbr>Expiration<wbr>Ms</td>
            <td class="align-top">
                
                <code>number?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The default lifetime of all tables in the dataset, in milliseconds. The minimum value is 3600000 milliseconds (one
hour). Once this property is set, all newly-created tables in the dataset will have an &#39;expirationTime&#39; property set to
the creation time plus the value in this property, and changing the value will only affect new tables, not existing
ones. When the &#39;expirationTime&#39; for a given table is reached, that table will be deleted automatically. If a table&#39;s
&#39;expirationTime&#39; is modified or removed before the table expires, or if you provide an explicit &#39;expirationTime&#39; when
creating a table, that value takes precedence over the default expiration time indicated by this property.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">delete<wbr>Contents<wbr>On<wbr>Destroy</td>
            <td class="align-top">
                
                <code>boolean?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
If set to `true`, delete all the tables in the
dataset when destroying the resource; otherwise,
destroying the resource will fail if tables are present.
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
A user-friendly description of the dataset
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
            <td class="align-top">friendly<wbr>Name</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A descriptive name for the dataset
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
The labels associated with this dataset. You can use these to organize and group your datasets
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
The date when this dataset or any of its tables was last modified, in milliseconds since the epoch.
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
The geographic location where the dataset should reside. See [official
docs](https://cloud.google.com/bigquery/docs/dataset-locations). There are two types of locations, regional or
multi-regional. A regional location is a specific geographic place, such as Tokyo, and a multi-regional location is a
large geographic area, such as the United States, that contains at least two geographic places. Possible regional values
include: &#39;asia-east1&#39;, &#39;asia-northeast1&#39;, &#39;asia-southeast1&#39;, &#39;australia-southeast1&#39;, &#39;europe-north1&#39;, &#39;europe-west2&#39; and
&#39;us-east4&#39;. Possible multi-regional values: &#39;EU&#39; and &#39;US&#39;. The default value is multi-regional location &#39;US&#39;. Changing
this forces a new resource to be created.
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
            <td class="align-top">accesses</td>
            <td class="align-top">
                
                <code><a href="#datasetaccess">List[Dataset<wbr>Access]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
An array of objects that define dataset access for one or more entities.
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
The time when this dataset was created, in milliseconds since the epoch.
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
A unique ID for this dataset, without the project name. The ID must contain only letters (a-z, A-Z), numbers (0-9), or
underscores (_). The maximum length is 1,024 characters.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">default_<wbr>encryption_<wbr>configuration</td>
            <td class="align-top">
                
                <code><a href="#datasetdefaultencryptionconfiguration">Dict[Dataset<wbr>Default<wbr>Encryption<wbr>Configuration]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The default encryption key for all tables in the dataset. Once this property is set, all newly-created partitioned
tables in the dataset will have encryption key set to this value, unless table creation request (or query) overrides the
key.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">default_<wbr>partition_<wbr>expiration_<wbr>ms</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The default partition expiration for all partitioned tables in the dataset, in milliseconds. Once this property is set,
all newly-created partitioned tables in the dataset will have an &#39;expirationMs&#39; property in the &#39;timePartitioning&#39;
settings set to this value, and changing the value will only affect new tables, not existing ones. The storage in a
partition will have an expiration time of its partition time plus this value. Setting this property overrides the use of
&#39;defaultTableExpirationMs&#39; for partitioned tables: only one of &#39;defaultTableExpirationMs&#39; and
&#39;defaultPartitionExpirationMs&#39; will be used for any new partitioned table. If you provide an explicit
&#39;timePartitioning.expirationMs&#39; when creating or updating a partitioned table, that value takes precedence over the
default partition expiration time indicated by this property.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">default_<wbr>table_<wbr>expiration_<wbr>ms</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The default lifetime of all tables in the dataset, in milliseconds. The minimum value is 3600000 milliseconds (one
hour). Once this property is set, all newly-created tables in the dataset will have an &#39;expirationTime&#39; property set to
the creation time plus the value in this property, and changing the value will only affect new tables, not existing
ones. When the &#39;expirationTime&#39; for a given table is reached, that table will be deleted automatically. If a table&#39;s
&#39;expirationTime&#39; is modified or removed before the table expires, or if you provide an explicit &#39;expirationTime&#39; when
creating a table, that value takes precedence over the default expiration time indicated by this property.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">delete_<wbr>contents_<wbr>on_<wbr>destroy</td>
            <td class="align-top">
                
                <code>bool</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
If set to `true`, delete all the tables in the
dataset when destroying the resource; otherwise,
destroying the resource will fail if tables are present.
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
A user-friendly description of the dataset
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
            <td class="align-top">friendly_<wbr>name</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A descriptive name for the dataset
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
The labels associated with this dataset. You can use these to organize and group your datasets
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
The date when this dataset or any of its tables was last modified, in milliseconds since the epoch.
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
The geographic location where the dataset should reside. See [official
docs](https://cloud.google.com/bigquery/docs/dataset-locations). There are two types of locations, regional or
multi-regional. A regional location is a specific geographic place, such as Tokyo, and a multi-regional location is a
large geographic area, such as the United States, that contains at least two geographic places. Possible regional values
include: &#39;asia-east1&#39;, &#39;asia-northeast1&#39;, &#39;asia-southeast1&#39;, &#39;australia-southeast1&#39;, &#39;europe-north1&#39;, &#39;europe-west2&#39; and
&#39;us-east4&#39;. Possible multi-regional values: &#39;EU&#39; and &#39;US&#39;. The default value is multi-regional location &#39;US&#39;. Changing
this forces a new resource to be created.
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
    
    </tbody>
</table>


{{% /lang %}}










## Supporting Types

#### DatasetAccess
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#DatasetAccess">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#DatasetAccess">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/bigquery?tab=doc#DatasetAccessArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/bigquery?tab=doc#DatasetAccessOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Bigquery.DatasetAccessArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Bigquery.DatasetAccess.html">output</a> API doc for this type.
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
            <td class="align-top">Domain</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Group<wbr>By<wbr>Email</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Role</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Special<wbr>Group</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">User<wbr>By<wbr>Email</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">View</td>
            <td class="align-top">
                
                <code><a href="#datasetaccessview">Dataset<wbr>Access<wbr>View<wbr>Args?</a></code>
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
            <td class="align-top">Domain</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Group<wbr>By<wbr>Email</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Role</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Special<wbr>Group</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">User<wbr>By<wbr>Email</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">View</td>
            <td class="align-top">
                
                <code><a href="#datasetaccessview">*Dataset<wbr>Access<wbr>View</a></code>
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
            <td class="align-top">domain</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">group<wbr>By<wbr>Email</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">role</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">special<wbr>Group</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">user<wbr>By<wbr>Email</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">view</td>
            <td class="align-top">
                
                <code><a href="#datasetaccessview">Dataset<wbr>Access<wbr>View?</a></code>
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
            <td class="align-top">domain</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">group<wbr>By<wbr>Email</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">role</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">special<wbr>Group</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">user<wbr>By<wbr>Email</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">view</td>
            <td class="align-top">
                
                <code><a href="#datasetaccessview">Dict[Dataset<wbr>Access<wbr>View]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}





#### DatasetAccessView
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#DatasetAccessView">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#DatasetAccessView">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/bigquery?tab=doc#DatasetAccessViewArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/bigquery?tab=doc#DatasetAccessViewOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Bigquery.DatasetAccessViewArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Bigquery.DatasetAccessView.html">output</a> API doc for this type.
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
            <td class="align-top">Dataset<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Project<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
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
            <td class="align-top">Dataset<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Project<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
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
            <td class="align-top">dataset<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">project<wbr>Id</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
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
            <td class="align-top">dataset_<wbr>id</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">project_<wbr>id</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
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
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}





#### DatasetDefaultEncryptionConfiguration
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#DatasetDefaultEncryptionConfiguration">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#DatasetDefaultEncryptionConfiguration">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/bigquery?tab=doc#DatasetDefaultEncryptionConfigurationArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/bigquery?tab=doc#DatasetDefaultEncryptionConfigurationOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Bigquery.DatasetDefaultEncryptionConfigurationArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Bigquery.DatasetDefaultEncryptionConfiguration.html">output</a> API doc for this type.
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








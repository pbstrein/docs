
---
title: "CatalogTable"
block_external_search_index: true
---

Provides a Glue Catalog Table Resource. You can refer to the [Glue Developer Guide](http://docs.aws.amazon.com/glue/latest/dg/populate-data-catalog.html) for a full explanation of the Glue Data Catalog functionality.

## Example Usage

### Basic Table

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const awsGlueCatalogTable = new aws.glue.CatalogTable("aws.glue.CatalogTable", {
    databaseName: "MyCatalogDatabase",
    name: "MyCatalogTable",
});
```

### Parquet Table for Athena

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const awsGlueCatalogTable = new aws.glue.CatalogTable("aws.glue.CatalogTable", {
    databaseName: "MyCatalogDatabase",
    name: "MyCatalogTable",
    parameters: {
        EXTERNAL: "TRUE",
        "parquet.compression": "SNAPPY",
    },
    storageDescriptor: {
        columns: [
            {
                name: "my_string",
                type: "string",
            },
            {
                name: "my_double",
                type: "double",
            },
            {
                comment: "",
                name: "my_date",
                type: "date",
            },
            {
                comment: "",
                name: "my_bigint",
                type: "bigint",
            },
            {
                comment: "",
                name: "my_struct",
                type: "struct<my_nested_string:string>",
            },
        ],
        inputFormat: "org.apache.hadoop.hive.ql.io.parquet.MapredParquetInputFormat",
        location: "s3://my-bucket/event-streams/my-stream",
        outputFormat: "org.apache.hadoop.hive.ql.io.parquet.MapredParquetOutputFormat",
        serDeInfo: {
            name: "my-stream",
            parameters: {
                "serialization.format": 1,
            },
            serializationLibrary: "org.apache.hadoop.hive.ql.io.parquet.serde.ParquetHiveSerDe",
        },
    },
    tableType: "EXTERNAL_TABLE",
});
```

> This content is derived from https://github.com/terraform-providers/terraform-provider-aws/blob/master/website/docs/r/glue_catalog_table.html.markdown.



## Create a CatalogTable Resource

{{< chooser language "javascript,typescript,python,go,csharp" / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/glue/#CatalogTable">CatalogTable</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/glue/#CatalogTableArgs">CatalogTableArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">CatalogTable</span><span class="p">(resource_name, opts=None, </span>catalog_id=None<span class="p">, </span>database_name=None<span class="p">, </span>description=None<span class="p">, </span>name=None<span class="p">, </span>owner=None<span class="p">, </span>parameters=None<span class="p">, </span>partition_keys=None<span class="p">, </span>retention=None<span class="p">, </span>storage_descriptor=None<span class="p">, </span>table_type=None<span class="p">, </span>view_expanded_text=None<span class="p">, </span>view_original_text=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewCatalogTable<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/glue?tab=doc#CatalogTableArgs">CatalogTableArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/glue?tab=doc#CatalogTable">CatalogTable</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Glue.CatalogTable.html">CatalogTable</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Glue.CatalogTableArgs.html">CatalogTableArgs</a></span> <span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
{{% /choosable %}}

Contructor Arguments

{{% choosable language nodejs %}}

<dl class="resources-ctor-args">
    <dt class="property-required" title="Required">
        name
        <span class="property-indicator"></span>
    </dt>
    <dd>The unique name of the resource.</dd>
    <dt class="property-optional" title="Optional">
        args
        <span class="property-indicator"></span>
    </dt>
    <dd>The arguments to use to populate this resource's properties.</dd>
    <dt class="property-optional" title="Optional">
        opts
        <span class="property-indicator"></span>
    </dt>
    <dd>A bag of options that control this resource's behavior.</dd>
</dl>

{{% /choosable %}}

{{% choosable language python %}}
<dl class="resources-ctor-args">
    <dt class="property-required" title="Required">
        name
        <span class="property-indicator"></span>
    </dt>
    <dd>The unique name of the resource.</dd>
    <dt class="property-optional" title="Optional">
        opts
        <span class="property-indicator"></span>
    </dt>
    <dd>A bag of options that control this resource's behavior.</dd>
</dl>
{{% /choosable %}}

{{% choosable language go %}}

<dl class="resources-ctor-args">
    <dt class="property-required" title="Required">
        name
        <span class="property-indicator"></span>
    </dt>
    <dd>The unique name of the resource.</dd>
    <dt class="property-optional" title="Optional">
        args
        <span class="property-indicator"></span>
    </dt>
    <dd>The arguments to use to populate this resource's properties.</dd>
    <dt class="property-optional" title="Optional">
        opts
        <span class="property-indicator"></span>
    </dt>
    <dd>A bag of options that control this resource's behavior.</dd>
</dl>

{{% /choosable %}}

{{% choosable language csharp %}}

<dl class="resources-ctor-args">
    <dt class="property-required" title="Required">
        name
        <span class="property-indicator"></span>
    </dt>
    <dd>The unique name of the resource.</dd>
    <dt class="property-optional" title="Optional">
        args
        <span class="property-indicator"></span>
    </dt>
    <dd>The arguments to use to populate this resource's properties.</dd>
    <dt class="property-optional" title="Optional">
        opts
        <span class="property-indicator"></span>
    </dt>
    <dd>A bag of options that control this resource's behavior.</dd>
</dl>

{{% /choosable %}}

Resource Arguments




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Catalog<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}ID of the Glue Catalog and database to create the table in. If omitted, this defaults to the AWS Account ID plus the database name.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Database<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Name of the metadata database where the table metadata resides. For Hive compatibility, this must be all lowercase.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Description<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Description of the table.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Name of the SerDe.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Owner<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Owner of the table.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Parameters<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, string>?</span>
    </dt>
    <dd>{{% md %}}A map of initialization parameters for the SerDe, in key-value form.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Partition<wbr>Keys<span class="property-indicator"></span>
        <span class="property-type"><a href="#catalogtablepartitionkey">List&lt;Catalog<wbr>Table<wbr>Partition<wbr>Key<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}A list of columns by which the table is partitioned. Only primitive types are supported as partition keys.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Retention<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}Retention time for this table.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Storage<wbr>Descriptor<span class="property-indicator"></span>
        <span class="property-type"><a href="#catalogtablestoragedescriptor">Catalog<wbr>Table<wbr>Storage<wbr>Descriptor<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}A storage descriptor object containing information about the physical storage of this table. You can refer to the [Glue Developer Guide](https://docs.aws.amazon.com/glue/latest/dg/aws-glue-api-catalog-tables.html#aws-glue-api-catalog-tables-StorageDescriptor) for a full explanation of this object.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Table<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The type of this table (EXTERNAL_TABLE, VIRTUAL_VIEW, etc.).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">View<wbr>Expanded<wbr>Text<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}If the table is a view, the expanded text of the view; otherwise null.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">View<wbr>Original<wbr>Text<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}If the table is a view, the original text of the view; otherwise null.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Catalog<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}ID of the Glue Catalog and database to create the table in. If omitted, this defaults to the AWS Account ID plus the database name.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Database<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Name of the metadata database where the table metadata resides. For Hive compatibility, this must be all lowercase.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Description<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Description of the table.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Name of the SerDe.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Owner<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Owner of the table.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Parameters<span class="property-indicator"></span>
        <span class="property-type">map[string]string</span>
    </dt>
    <dd>{{% md %}}A map of initialization parameters for the SerDe, in key-value form.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Partition<wbr>Keys<span class="property-indicator"></span>
        <span class="property-type"><a href="#catalogtablepartitionkey">[]Catalog<wbr>Table<wbr>Partition<wbr>Key</a></span>
    </dt>
    <dd>{{% md %}}A list of columns by which the table is partitioned. Only primitive types are supported as partition keys.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Retention<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}Retention time for this table.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Storage<wbr>Descriptor<span class="property-indicator"></span>
        <span class="property-type"><a href="#catalogtablestoragedescriptor">*Catalog<wbr>Table<wbr>Storage<wbr>Descriptor</a></span>
    </dt>
    <dd>{{% md %}}A storage descriptor object containing information about the physical storage of this table. You can refer to the [Glue Developer Guide](https://docs.aws.amazon.com/glue/latest/dg/aws-glue-api-catalog-tables.html#aws-glue-api-catalog-tables-StorageDescriptor) for a full explanation of this object.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Table<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The type of this table (EXTERNAL_TABLE, VIRTUAL_VIEW, etc.).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">View<wbr>Expanded<wbr>Text<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}If the table is a view, the expanded text of the view; otherwise null.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">View<wbr>Original<wbr>Text<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}If the table is a view, the original text of the view; otherwise null.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">catalog<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}ID of the Glue Catalog and database to create the table in. If omitted, this defaults to the AWS Account ID plus the database name.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">database<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Name of the metadata database where the table metadata resides. For Hive compatibility, this must be all lowercase.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">description<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Description of the table.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Name of the SerDe.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">owner<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Owner of the table.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">parameters<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: string}?</span>
    </dt>
    <dd>{{% md %}}A map of initialization parameters for the SerDe, in key-value form.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">partition<wbr>Keys<span class="property-indicator"></span>
        <span class="property-type"><a href="#catalogtablepartitionkey">Catalog<wbr>Table<wbr>Partition<wbr>Key[]?</a></span>
    </dt>
    <dd>{{% md %}}A list of columns by which the table is partitioned. Only primitive types are supported as partition keys.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">retention<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}Retention time for this table.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">storage<wbr>Descriptor<span class="property-indicator"></span>
        <span class="property-type"><a href="#catalogtablestoragedescriptor">Catalog<wbr>Table<wbr>Storage<wbr>Descriptor?</a></span>
    </dt>
    <dd>{{% md %}}A storage descriptor object containing information about the physical storage of this table. You can refer to the [Glue Developer Guide](https://docs.aws.amazon.com/glue/latest/dg/aws-glue-api-catalog-tables.html#aws-glue-api-catalog-tables-StorageDescriptor) for a full explanation of this object.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">table<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The type of this table (EXTERNAL_TABLE, VIRTUAL_VIEW, etc.).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">view<wbr>Expanded<wbr>Text<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}If the table is a view, the expanded text of the view; otherwise null.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">view<wbr>Original<wbr>Text<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}If the table is a view, the original text of the view; otherwise null.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">catalog_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}ID of the Glue Catalog and database to create the table in. If omitted, this defaults to the AWS Account ID plus the database name.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">database_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Name of the metadata database where the table metadata resides. For Hive compatibility, this must be all lowercase.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">description<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Description of the table.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Name of the SerDe.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">owner<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Owner of the table.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">parameters<span class="property-indicator"></span>
        <span class="property-type">Dict[str, str]</span>
    </dt>
    <dd>{{% md %}}A map of initialization parameters for the SerDe, in key-value form.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">partition_<wbr>keys<span class="property-indicator"></span>
        <span class="property-type"><a href="#catalogtablepartitionkey">List[Catalog<wbr>Table<wbr>Partition<wbr>Key]</a></span>
    </dt>
    <dd>{{% md %}}A list of columns by which the table is partitioned. Only primitive types are supported as partition keys.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">retention<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}Retention time for this table.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">storage_<wbr>descriptor<span class="property-indicator"></span>
        <span class="property-type"><a href="#catalogtablestoragedescriptor">Dict[Catalog<wbr>Table<wbr>Storage<wbr>Descriptor]</a></span>
    </dt>
    <dd>{{% md %}}A storage descriptor object containing information about the physical storage of this table. You can refer to the [Glue Developer Guide](https://docs.aws.amazon.com/glue/latest/dg/aws-glue-api-catalog-tables.html#aws-glue-api-catalog-tables-StorageDescriptor) for a full explanation of this object.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">table_<wbr>type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The type of this table (EXTERNAL_TABLE, VIRTUAL_VIEW, etc.).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">view_<wbr>expanded_<wbr>text<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}If the table is a view, the expanded text of the view; otherwise null.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">view_<wbr>original_<wbr>text<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}If the table is a view, the original text of the view; otherwise null.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}




## CatalogTable Output Properties

The following output properties are available:




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Catalog<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}ID of the Glue Catalog and database to create the table in. If omitted, this defaults to the AWS Account ID plus the database name.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Database<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Name of the metadata database where the table metadata resides. For Hive compatibility, this must be all lowercase.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Description<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Description of the table.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Name of the SerDe.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Owner<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Owner of the table.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Parameters<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, string>?</span>
    </dt>
    <dd>{{% md %}}A map of initialization parameters for the SerDe, in key-value form.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Partition<wbr>Keys<span class="property-indicator"></span>
        <span class="property-type"><a href="#catalogtablepartitionkey">List&lt;Catalog<wbr>Table<wbr>Partition<wbr>Key&gt;?</a></span>
    </dt>
    <dd>{{% md %}}A list of columns by which the table is partitioned. Only primitive types are supported as partition keys.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Retention<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}Retention time for this table.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Storage<wbr>Descriptor<span class="property-indicator"></span>
        <span class="property-type"><a href="#catalogtablestoragedescriptor">Catalog<wbr>Table<wbr>Storage<wbr>Descriptor?</a></span>
    </dt>
    <dd>{{% md %}}A storage descriptor object containing information about the physical storage of this table. You can refer to the [Glue Developer Guide](https://docs.aws.amazon.com/glue/latest/dg/aws-glue-api-catalog-tables.html#aws-glue-api-catalog-tables-StorageDescriptor) for a full explanation of this object.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Table<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The type of this table (EXTERNAL_TABLE, VIRTUAL_VIEW, etc.).
{{% /md %}}</dd>

    <dt class="property-"
            title="">View<wbr>Expanded<wbr>Text<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}If the table is a view, the expanded text of the view; otherwise null.
{{% /md %}}</dd>

    <dt class="property-"
            title="">View<wbr>Original<wbr>Text<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}If the table is a view, the original text of the view; otherwise null.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Catalog<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}ID of the Glue Catalog and database to create the table in. If omitted, this defaults to the AWS Account ID plus the database name.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Database<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Name of the metadata database where the table metadata resides. For Hive compatibility, this must be all lowercase.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Description<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Description of the table.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Name of the SerDe.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Owner<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Owner of the table.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Parameters<span class="property-indicator"></span>
        <span class="property-type">map[string]string</span>
    </dt>
    <dd>{{% md %}}A map of initialization parameters for the SerDe, in key-value form.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Partition<wbr>Keys<span class="property-indicator"></span>
        <span class="property-type"><a href="#catalogtablepartitionkey">[]Catalog<wbr>Table<wbr>Partition<wbr>Key</a></span>
    </dt>
    <dd>{{% md %}}A list of columns by which the table is partitioned. Only primitive types are supported as partition keys.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Retention<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}Retention time for this table.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Storage<wbr>Descriptor<span class="property-indicator"></span>
        <span class="property-type"><a href="#catalogtablestoragedescriptor">*Catalog<wbr>Table<wbr>Storage<wbr>Descriptor</a></span>
    </dt>
    <dd>{{% md %}}A storage descriptor object containing information about the physical storage of this table. You can refer to the [Glue Developer Guide](https://docs.aws.amazon.com/glue/latest/dg/aws-glue-api-catalog-tables.html#aws-glue-api-catalog-tables-StorageDescriptor) for a full explanation of this object.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Table<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The type of this table (EXTERNAL_TABLE, VIRTUAL_VIEW, etc.).
{{% /md %}}</dd>

    <dt class="property-"
            title="">View<wbr>Expanded<wbr>Text<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}If the table is a view, the expanded text of the view; otherwise null.
{{% /md %}}</dd>

    <dt class="property-"
            title="">View<wbr>Original<wbr>Text<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}If the table is a view, the original text of the view; otherwise null.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">catalog<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}ID of the Glue Catalog and database to create the table in. If omitted, this defaults to the AWS Account ID plus the database name.
{{% /md %}}</dd>

    <dt class="property-"
            title="">database<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Name of the metadata database where the table metadata resides. For Hive compatibility, this must be all lowercase.
{{% /md %}}</dd>

    <dt class="property-"
            title="">description<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Description of the table.
{{% /md %}}</dd>

    <dt class="property-"
            title="">name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Name of the SerDe.
{{% /md %}}</dd>

    <dt class="property-"
            title="">owner<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Owner of the table.
{{% /md %}}</dd>

    <dt class="property-"
            title="">parameters<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: string}?</span>
    </dt>
    <dd>{{% md %}}A map of initialization parameters for the SerDe, in key-value form.
{{% /md %}}</dd>

    <dt class="property-"
            title="">partition<wbr>Keys<span class="property-indicator"></span>
        <span class="property-type"><a href="#catalogtablepartitionkey">Catalog<wbr>Table<wbr>Partition<wbr>Key[]?</a></span>
    </dt>
    <dd>{{% md %}}A list of columns by which the table is partitioned. Only primitive types are supported as partition keys.
{{% /md %}}</dd>

    <dt class="property-"
            title="">retention<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}Retention time for this table.
{{% /md %}}</dd>

    <dt class="property-"
            title="">storage<wbr>Descriptor<span class="property-indicator"></span>
        <span class="property-type"><a href="#catalogtablestoragedescriptor">Catalog<wbr>Table<wbr>Storage<wbr>Descriptor?</a></span>
    </dt>
    <dd>{{% md %}}A storage descriptor object containing information about the physical storage of this table. You can refer to the [Glue Developer Guide](https://docs.aws.amazon.com/glue/latest/dg/aws-glue-api-catalog-tables.html#aws-glue-api-catalog-tables-StorageDescriptor) for a full explanation of this object.
{{% /md %}}</dd>

    <dt class="property-"
            title="">table<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The type of this table (EXTERNAL_TABLE, VIRTUAL_VIEW, etc.).
{{% /md %}}</dd>

    <dt class="property-"
            title="">view<wbr>Expanded<wbr>Text<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}If the table is a view, the expanded text of the view; otherwise null.
{{% /md %}}</dd>

    <dt class="property-"
            title="">view<wbr>Original<wbr>Text<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}If the table is a view, the original text of the view; otherwise null.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">catalog_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}ID of the Glue Catalog and database to create the table in. If omitted, this defaults to the AWS Account ID plus the database name.
{{% /md %}}</dd>

    <dt class="property-"
            title="">database_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Name of the metadata database where the table metadata resides. For Hive compatibility, this must be all lowercase.
{{% /md %}}</dd>

    <dt class="property-"
            title="">description<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Description of the table.
{{% /md %}}</dd>

    <dt class="property-"
            title="">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Name of the SerDe.
{{% /md %}}</dd>

    <dt class="property-"
            title="">owner<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Owner of the table.
{{% /md %}}</dd>

    <dt class="property-"
            title="">parameters<span class="property-indicator"></span>
        <span class="property-type">Dict[str, str]</span>
    </dt>
    <dd>{{% md %}}A map of initialization parameters for the SerDe, in key-value form.
{{% /md %}}</dd>

    <dt class="property-"
            title="">partition_<wbr>keys<span class="property-indicator"></span>
        <span class="property-type"><a href="#catalogtablepartitionkey">List[Catalog<wbr>Table<wbr>Partition<wbr>Key]</a></span>
    </dt>
    <dd>{{% md %}}A list of columns by which the table is partitioned. Only primitive types are supported as partition keys.
{{% /md %}}</dd>

    <dt class="property-"
            title="">retention<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}Retention time for this table.
{{% /md %}}</dd>

    <dt class="property-"
            title="">storage_<wbr>descriptor<span class="property-indicator"></span>
        <span class="property-type"><a href="#catalogtablestoragedescriptor">Dict[Catalog<wbr>Table<wbr>Storage<wbr>Descriptor]</a></span>
    </dt>
    <dd>{{% md %}}A storage descriptor object containing information about the physical storage of this table. You can refer to the [Glue Developer Guide](https://docs.aws.amazon.com/glue/latest/dg/aws-glue-api-catalog-tables.html#aws-glue-api-catalog-tables-StorageDescriptor) for a full explanation of this object.
{{% /md %}}</dd>

    <dt class="property-"
            title="">table_<wbr>type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The type of this table (EXTERNAL_TABLE, VIRTUAL_VIEW, etc.).
{{% /md %}}</dd>

    <dt class="property-"
            title="">view_<wbr>expanded_<wbr>text<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}If the table is a view, the expanded text of the view; otherwise null.
{{% /md %}}</dd>

    <dt class="property-"
            title="">view_<wbr>original_<wbr>text<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}If the table is a view, the original text of the view; otherwise null.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





## Look up an Existing CatalogTable Resource

{{< chooser language "javascript,typescript,python,go,csharp  " / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">pulumi.Input&lt;pulumi.ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/glue/#CatalogTableState">CatalogTableState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/glue/#CatalogTable">CatalogTable</a></span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>catalog_id=None<span class="p">, </span>database_name=None<span class="p">, </span>description=None<span class="p">, </span>name=None<span class="p">, </span>owner=None<span class="p">, </span>parameters=None<span class="p">, </span>partition_keys=None<span class="p">, </span>retention=None<span class="p">, </span>storage_descriptor=None<span class="p">, </span>table_type=None<span class="p">, </span>view_expanded_text=None<span class="p">, </span>view_original_text=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetCatalogTable<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">pulumi.IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/glue?tab=doc#CatalogTableState">CatalogTableState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/glue?tab=doc#CatalogTable">CatalogTable</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Glue.CatalogTable.html">CatalogTable</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Pulumi.Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Glue.CatalogTableState.html">CatalogTableState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
{{% /choosable %}}

Get an existing CatalogTable resource's state with the given name, ID, and optional extra properties used to qualify the lookup.

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



{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Catalog<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}ID of the Glue Catalog and database to create the table in. If omitted, this defaults to the AWS Account ID plus the database name.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Database<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Name of the metadata database where the table metadata resides. For Hive compatibility, this must be all lowercase.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Description<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Description of the table.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Name of the SerDe.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Owner<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Owner of the table.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Parameters<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, string>?</span>
    </dt>
    <dd>{{% md %}}A map of initialization parameters for the SerDe, in key-value form.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Partition<wbr>Keys<span class="property-indicator"></span>
        <span class="property-type"><a href="#catalogtablepartitionkey">List&lt;Catalog<wbr>Table<wbr>Partition<wbr>Key<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}A list of columns by which the table is partitioned. Only primitive types are supported as partition keys.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Retention<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}Retention time for this table.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Storage<wbr>Descriptor<span class="property-indicator"></span>
        <span class="property-type"><a href="#catalogtablestoragedescriptor">Catalog<wbr>Table<wbr>Storage<wbr>Descriptor<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}A storage descriptor object containing information about the physical storage of this table. You can refer to the [Glue Developer Guide](https://docs.aws.amazon.com/glue/latest/dg/aws-glue-api-catalog-tables.html#aws-glue-api-catalog-tables-StorageDescriptor) for a full explanation of this object.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Table<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The type of this table (EXTERNAL_TABLE, VIRTUAL_VIEW, etc.).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">View<wbr>Expanded<wbr>Text<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}If the table is a view, the expanded text of the view; otherwise null.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">View<wbr>Original<wbr>Text<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}If the table is a view, the original text of the view; otherwise null.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Catalog<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}ID of the Glue Catalog and database to create the table in. If omitted, this defaults to the AWS Account ID plus the database name.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Database<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Name of the metadata database where the table metadata resides. For Hive compatibility, this must be all lowercase.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Description<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Description of the table.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Name of the SerDe.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Owner<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Owner of the table.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Parameters<span class="property-indicator"></span>
        <span class="property-type">map[string]string</span>
    </dt>
    <dd>{{% md %}}A map of initialization parameters for the SerDe, in key-value form.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Partition<wbr>Keys<span class="property-indicator"></span>
        <span class="property-type"><a href="#catalogtablepartitionkey">[]Catalog<wbr>Table<wbr>Partition<wbr>Key</a></span>
    </dt>
    <dd>{{% md %}}A list of columns by which the table is partitioned. Only primitive types are supported as partition keys.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Retention<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}Retention time for this table.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Storage<wbr>Descriptor<span class="property-indicator"></span>
        <span class="property-type"><a href="#catalogtablestoragedescriptor">*Catalog<wbr>Table<wbr>Storage<wbr>Descriptor</a></span>
    </dt>
    <dd>{{% md %}}A storage descriptor object containing information about the physical storage of this table. You can refer to the [Glue Developer Guide](https://docs.aws.amazon.com/glue/latest/dg/aws-glue-api-catalog-tables.html#aws-glue-api-catalog-tables-StorageDescriptor) for a full explanation of this object.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Table<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The type of this table (EXTERNAL_TABLE, VIRTUAL_VIEW, etc.).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">View<wbr>Expanded<wbr>Text<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}If the table is a view, the expanded text of the view; otherwise null.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">View<wbr>Original<wbr>Text<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}If the table is a view, the original text of the view; otherwise null.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">catalog<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}ID of the Glue Catalog and database to create the table in. If omitted, this defaults to the AWS Account ID plus the database name.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">database<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Name of the metadata database where the table metadata resides. For Hive compatibility, this must be all lowercase.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">description<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Description of the table.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Name of the SerDe.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">owner<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Owner of the table.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">parameters<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: string}?</span>
    </dt>
    <dd>{{% md %}}A map of initialization parameters for the SerDe, in key-value form.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">partition<wbr>Keys<span class="property-indicator"></span>
        <span class="property-type"><a href="#catalogtablepartitionkey">Catalog<wbr>Table<wbr>Partition<wbr>Key[]?</a></span>
    </dt>
    <dd>{{% md %}}A list of columns by which the table is partitioned. Only primitive types are supported as partition keys.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">retention<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}Retention time for this table.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">storage<wbr>Descriptor<span class="property-indicator"></span>
        <span class="property-type"><a href="#catalogtablestoragedescriptor">Catalog<wbr>Table<wbr>Storage<wbr>Descriptor?</a></span>
    </dt>
    <dd>{{% md %}}A storage descriptor object containing information about the physical storage of this table. You can refer to the [Glue Developer Guide](https://docs.aws.amazon.com/glue/latest/dg/aws-glue-api-catalog-tables.html#aws-glue-api-catalog-tables-StorageDescriptor) for a full explanation of this object.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">table<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The type of this table (EXTERNAL_TABLE, VIRTUAL_VIEW, etc.).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">view<wbr>Expanded<wbr>Text<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}If the table is a view, the expanded text of the view; otherwise null.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">view<wbr>Original<wbr>Text<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}If the table is a view, the original text of the view; otherwise null.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">catalog_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}ID of the Glue Catalog and database to create the table in. If omitted, this defaults to the AWS Account ID plus the database name.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">database_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Name of the metadata database where the table metadata resides. For Hive compatibility, this must be all lowercase.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">description<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Description of the table.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Name of the SerDe.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">owner<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Owner of the table.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">parameters<span class="property-indicator"></span>
        <span class="property-type">Dict[str, str]</span>
    </dt>
    <dd>{{% md %}}A map of initialization parameters for the SerDe, in key-value form.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">partition_<wbr>keys<span class="property-indicator"></span>
        <span class="property-type"><a href="#catalogtablepartitionkey">List[Catalog<wbr>Table<wbr>Partition<wbr>Key]</a></span>
    </dt>
    <dd>{{% md %}}A list of columns by which the table is partitioned. Only primitive types are supported as partition keys.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">retention<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}Retention time for this table.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">storage_<wbr>descriptor<span class="property-indicator"></span>
        <span class="property-type"><a href="#catalogtablestoragedescriptor">Dict[Catalog<wbr>Table<wbr>Storage<wbr>Descriptor]</a></span>
    </dt>
    <dd>{{% md %}}A storage descriptor object containing information about the physical storage of this table. You can refer to the [Glue Developer Guide](https://docs.aws.amazon.com/glue/latest/dg/aws-glue-api-catalog-tables.html#aws-glue-api-catalog-tables-StorageDescriptor) for a full explanation of this object.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">table_<wbr>type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The type of this table (EXTERNAL_TABLE, VIRTUAL_VIEW, etc.).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">view_<wbr>expanded_<wbr>text<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}If the table is a view, the expanded text of the view; otherwise null.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">view_<wbr>original_<wbr>text<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}If the table is a view, the original text of the view; otherwise null.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}







## Supporting Types

#### CatalogTablePartitionKey
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#CatalogTablePartitionKey">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#CatalogTablePartitionKey">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/glue?tab=doc#CatalogTablePartitionKeyArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/glue?tab=doc#CatalogTablePartitionKeyOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Glue.CatalogTablePartitionKeyArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Glue.CatalogTablePartitionKey.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Comment<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Free-form text comment.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Name of the SerDe.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The datatype of data in the Column.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Comment<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Free-form text comment.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Name of the SerDe.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Type<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The datatype of data in the Column.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">comment<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Free-form text comment.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Name of the SerDe.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The datatype of data in the Column.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">comment<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Free-form text comment.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Name of the SerDe.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The datatype of data in the Column.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### CatalogTableStorageDescriptor
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#CatalogTableStorageDescriptor">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#CatalogTableStorageDescriptor">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/glue?tab=doc#CatalogTableStorageDescriptorArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/glue?tab=doc#CatalogTableStorageDescriptorOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Glue.CatalogTableStorageDescriptorArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Glue.CatalogTableStorageDescriptor.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Bucket<wbr>Columns<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}A list of reducer grouping columns, clustering columns, and bucketing columns in the table.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Columns<span class="property-indicator"></span>
        <span class="property-type"><a href="#catalogtablestoragedescriptorcolumn">List&lt;Catalog<wbr>Table<wbr>Storage<wbr>Descriptor<wbr>Column<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}A list of the Columns in the table.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Compressed<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}True if the data in the table is compressed, or False if not.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Input<wbr>Format<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The input format: SequenceFileInputFormat (binary), or TextInputFormat, or a custom format.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Location<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The physical location of the table. By default this takes the form of the warehouse location, followed by the database location in the warehouse, followed by the table name.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Number<wbr>Of<wbr>Buckets<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}Must be specified if the table contains any dimension columns.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Output<wbr>Format<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The output format: SequenceFileOutputFormat (binary), or IgnoreKeyTextOutputFormat, or a custom format.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Parameters<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, string>?</span>
    </dt>
    <dd>{{% md %}}A map of initialization parameters for the SerDe, in key-value form.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ser<wbr>De<wbr>Info<span class="property-indicator"></span>
        <span class="property-type"><a href="#catalogtablestoragedescriptorserdeinfo">Catalog<wbr>Table<wbr>Storage<wbr>Descriptor<wbr>Ser<wbr>De<wbr>Info<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}Serialization/deserialization (SerDe) information.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Skewed<wbr>Info<span class="property-indicator"></span>
        <span class="property-type"><a href="#catalogtablestoragedescriptorskewedinfo">Catalog<wbr>Table<wbr>Storage<wbr>Descriptor<wbr>Skewed<wbr>Info<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}Information about values that appear very frequently in a column (skewed values).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Sort<wbr>Columns<span class="property-indicator"></span>
        <span class="property-type"><a href="#catalogtablestoragedescriptorsortcolumn">List&lt;Catalog<wbr>Table<wbr>Storage<wbr>Descriptor<wbr>Sort<wbr>Column<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}A list of Order objects specifying the sort order of each bucket in the table.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Stored<wbr>As<wbr>Sub<wbr>Directories<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}True if the table data is stored in subdirectories, or False if not.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Bucket<wbr>Columns<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}A list of reducer grouping columns, clustering columns, and bucketing columns in the table.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Columns<span class="property-indicator"></span>
        <span class="property-type"><a href="#catalogtablestoragedescriptorcolumn">[]Catalog<wbr>Table<wbr>Storage<wbr>Descriptor<wbr>Column</a></span>
    </dt>
    <dd>{{% md %}}A list of the Columns in the table.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Compressed<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}True if the data in the table is compressed, or False if not.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Input<wbr>Format<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The input format: SequenceFileInputFormat (binary), or TextInputFormat, or a custom format.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Location<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The physical location of the table. By default this takes the form of the warehouse location, followed by the database location in the warehouse, followed by the table name.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Number<wbr>Of<wbr>Buckets<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}Must be specified if the table contains any dimension columns.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Output<wbr>Format<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The output format: SequenceFileOutputFormat (binary), or IgnoreKeyTextOutputFormat, or a custom format.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Parameters<span class="property-indicator"></span>
        <span class="property-type">map[string]string</span>
    </dt>
    <dd>{{% md %}}A map of initialization parameters for the SerDe, in key-value form.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ser<wbr>De<wbr>Info<span class="property-indicator"></span>
        <span class="property-type"><a href="#catalogtablestoragedescriptorserdeinfo">*Catalog<wbr>Table<wbr>Storage<wbr>Descriptor<wbr>Ser<wbr>De<wbr>Info</a></span>
    </dt>
    <dd>{{% md %}}Serialization/deserialization (SerDe) information.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Skewed<wbr>Info<span class="property-indicator"></span>
        <span class="property-type"><a href="#catalogtablestoragedescriptorskewedinfo">*Catalog<wbr>Table<wbr>Storage<wbr>Descriptor<wbr>Skewed<wbr>Info</a></span>
    </dt>
    <dd>{{% md %}}Information about values that appear very frequently in a column (skewed values).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Sort<wbr>Columns<span class="property-indicator"></span>
        <span class="property-type"><a href="#catalogtablestoragedescriptorsortcolumn">[]Catalog<wbr>Table<wbr>Storage<wbr>Descriptor<wbr>Sort<wbr>Column</a></span>
    </dt>
    <dd>{{% md %}}A list of Order objects specifying the sort order of each bucket in the table.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Stored<wbr>As<wbr>Sub<wbr>Directories<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}True if the table data is stored in subdirectories, or False if not.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">bucket<wbr>Columns<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}A list of reducer grouping columns, clustering columns, and bucketing columns in the table.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">columns<span class="property-indicator"></span>
        <span class="property-type"><a href="#catalogtablestoragedescriptorcolumn">Catalog<wbr>Table<wbr>Storage<wbr>Descriptor<wbr>Column[]?</a></span>
    </dt>
    <dd>{{% md %}}A list of the Columns in the table.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">compressed<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}True if the data in the table is compressed, or False if not.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">input<wbr>Format<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The input format: SequenceFileInputFormat (binary), or TextInputFormat, or a custom format.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">location<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The physical location of the table. By default this takes the form of the warehouse location, followed by the database location in the warehouse, followed by the table name.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">number<wbr>Of<wbr>Buckets<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}Must be specified if the table contains any dimension columns.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">output<wbr>Format<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The output format: SequenceFileOutputFormat (binary), or IgnoreKeyTextOutputFormat, or a custom format.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">parameters<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: string}?</span>
    </dt>
    <dd>{{% md %}}A map of initialization parameters for the SerDe, in key-value form.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ser<wbr>De<wbr>Info<span class="property-indicator"></span>
        <span class="property-type"><a href="#catalogtablestoragedescriptorserdeinfo">Catalog<wbr>Table<wbr>Storage<wbr>Descriptor<wbr>Ser<wbr>De<wbr>Info?</a></span>
    </dt>
    <dd>{{% md %}}Serialization/deserialization (SerDe) information.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">skewed<wbr>Info<span class="property-indicator"></span>
        <span class="property-type"><a href="#catalogtablestoragedescriptorskewedinfo">Catalog<wbr>Table<wbr>Storage<wbr>Descriptor<wbr>Skewed<wbr>Info?</a></span>
    </dt>
    <dd>{{% md %}}Information about values that appear very frequently in a column (skewed values).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">sort<wbr>Columns<span class="property-indicator"></span>
        <span class="property-type"><a href="#catalogtablestoragedescriptorsortcolumn">Catalog<wbr>Table<wbr>Storage<wbr>Descriptor<wbr>Sort<wbr>Column[]?</a></span>
    </dt>
    <dd>{{% md %}}A list of Order objects specifying the sort order of each bucket in the table.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">stored<wbr>As<wbr>Sub<wbr>Directories<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}True if the table data is stored in subdirectories, or False if not.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">bucket<wbr>Columns<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}A list of reducer grouping columns, clustering columns, and bucketing columns in the table.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">columns<span class="property-indicator"></span>
        <span class="property-type"><a href="#catalogtablestoragedescriptorcolumn">List[Catalog<wbr>Table<wbr>Storage<wbr>Descriptor<wbr>Column]</a></span>
    </dt>
    <dd>{{% md %}}A list of the Columns in the table.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">compressed<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}True if the data in the table is compressed, or False if not.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">input<wbr>Format<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The input format: SequenceFileInputFormat (binary), or TextInputFormat, or a custom format.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">location<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The physical location of the table. By default this takes the form of the warehouse location, followed by the database location in the warehouse, followed by the table name.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">number<wbr>Of<wbr>Buckets<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}Must be specified if the table contains any dimension columns.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">output<wbr>Format<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The output format: SequenceFileOutputFormat (binary), or IgnoreKeyTextOutputFormat, or a custom format.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">parameters<span class="property-indicator"></span>
        <span class="property-type">Dict[str, str]</span>
    </dt>
    <dd>{{% md %}}A map of initialization parameters for the SerDe, in key-value form.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ser<wbr>De<wbr>Info<span class="property-indicator"></span>
        <span class="property-type"><a href="#catalogtablestoragedescriptorserdeinfo">Dict[Catalog<wbr>Table<wbr>Storage<wbr>Descriptor<wbr>Ser<wbr>De<wbr>Info]</a></span>
    </dt>
    <dd>{{% md %}}Serialization/deserialization (SerDe) information.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">skewed<wbr>Info<span class="property-indicator"></span>
        <span class="property-type"><a href="#catalogtablestoragedescriptorskewedinfo">Dict[Catalog<wbr>Table<wbr>Storage<wbr>Descriptor<wbr>Skewed<wbr>Info]</a></span>
    </dt>
    <dd>{{% md %}}Information about values that appear very frequently in a column (skewed values).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">sort<wbr>Columns<span class="property-indicator"></span>
        <span class="property-type"><a href="#catalogtablestoragedescriptorsortcolumn">List[Catalog<wbr>Table<wbr>Storage<wbr>Descriptor<wbr>Sort<wbr>Column]</a></span>
    </dt>
    <dd>{{% md %}}A list of Order objects specifying the sort order of each bucket in the table.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">stored<wbr>As<wbr>Sub<wbr>Directories<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}True if the table data is stored in subdirectories, or False if not.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### CatalogTableStorageDescriptorColumn
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#CatalogTableStorageDescriptorColumn">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#CatalogTableStorageDescriptorColumn">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/glue?tab=doc#CatalogTableStorageDescriptorColumnArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/glue?tab=doc#CatalogTableStorageDescriptorColumnOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Glue.CatalogTableStorageDescriptorColumnArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Glue.CatalogTableStorageDescriptorColumn.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Comment<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Free-form text comment.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Name of the SerDe.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The datatype of data in the Column.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Comment<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Free-form text comment.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Name of the SerDe.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Type<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The datatype of data in the Column.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">comment<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Free-form text comment.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Name of the SerDe.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The datatype of data in the Column.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">comment<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Free-form text comment.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Name of the SerDe.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The datatype of data in the Column.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### CatalogTableStorageDescriptorSerDeInfo
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#CatalogTableStorageDescriptorSerDeInfo">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#CatalogTableStorageDescriptorSerDeInfo">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/glue?tab=doc#CatalogTableStorageDescriptorSerDeInfoArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/glue?tab=doc#CatalogTableStorageDescriptorSerDeInfoOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Glue.CatalogTableStorageDescriptorSerDeInfoArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Glue.CatalogTableStorageDescriptorSerDeInfo.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Name of the SerDe.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Parameters<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, string>?</span>
    </dt>
    <dd>{{% md %}}A map of initialization parameters for the SerDe, in key-value form.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Serialization<wbr>Library<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Usually the class that implements the SerDe. An example is: org.apache.hadoop.hive.serde2.columnar.ColumnarSerDe.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Name of the SerDe.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Parameters<span class="property-indicator"></span>
        <span class="property-type">map[string]string</span>
    </dt>
    <dd>{{% md %}}A map of initialization parameters for the SerDe, in key-value form.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Serialization<wbr>Library<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Usually the class that implements the SerDe. An example is: org.apache.hadoop.hive.serde2.columnar.ColumnarSerDe.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Name of the SerDe.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">parameters<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: string}?</span>
    </dt>
    <dd>{{% md %}}A map of initialization parameters for the SerDe, in key-value form.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">serialization<wbr>Library<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Usually the class that implements the SerDe. An example is: org.apache.hadoop.hive.serde2.columnar.ColumnarSerDe.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Name of the SerDe.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">parameters<span class="property-indicator"></span>
        <span class="property-type">Dict[str, str]</span>
    </dt>
    <dd>{{% md %}}A map of initialization parameters for the SerDe, in key-value form.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">serialization<wbr>Library<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Usually the class that implements the SerDe. An example is: org.apache.hadoop.hive.serde2.columnar.ColumnarSerDe.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### CatalogTableStorageDescriptorSkewedInfo
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#CatalogTableStorageDescriptorSkewedInfo">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#CatalogTableStorageDescriptorSkewedInfo">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/glue?tab=doc#CatalogTableStorageDescriptorSkewedInfoArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/glue?tab=doc#CatalogTableStorageDescriptorSkewedInfoOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Glue.CatalogTableStorageDescriptorSkewedInfoArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Glue.CatalogTableStorageDescriptorSkewedInfo.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Skewed<wbr>Column<wbr>Names<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}A list of names of columns that contain skewed values.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Skewed<wbr>Column<wbr>Value<wbr>Location<wbr>Maps<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, string>?</span>
    </dt>
    <dd>{{% md %}}A list of values that appear so frequently as to be considered skewed.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Skewed<wbr>Column<wbr>Values<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}A mapping of skewed values to the columns that contain them.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Skewed<wbr>Column<wbr>Names<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}A list of names of columns that contain skewed values.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Skewed<wbr>Column<wbr>Value<wbr>Location<wbr>Maps<span class="property-indicator"></span>
        <span class="property-type">map[string]string</span>
    </dt>
    <dd>{{% md %}}A list of values that appear so frequently as to be considered skewed.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Skewed<wbr>Column<wbr>Values<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}A mapping of skewed values to the columns that contain them.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">skewed<wbr>Column<wbr>Names<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}A list of names of columns that contain skewed values.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">skewed<wbr>Column<wbr>Value<wbr>Location<wbr>Maps<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: string}?</span>
    </dt>
    <dd>{{% md %}}A list of values that appear so frequently as to be considered skewed.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">skewed<wbr>Column<wbr>Values<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}A mapping of skewed values to the columns that contain them.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">skewed<wbr>Column<wbr>Names<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}A list of names of columns that contain skewed values.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">skewed<wbr>Column<wbr>Value<wbr>Location<wbr>Maps<span class="property-indicator"></span>
        <span class="property-type">Dict[str, str]</span>
    </dt>
    <dd>{{% md %}}A list of values that appear so frequently as to be considered skewed.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">skewed<wbr>Column<wbr>Values<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}A mapping of skewed values to the columns that contain them.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### CatalogTableStorageDescriptorSortColumn
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#CatalogTableStorageDescriptorSortColumn">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#CatalogTableStorageDescriptorSortColumn">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/glue?tab=doc#CatalogTableStorageDescriptorSortColumnArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/glue?tab=doc#CatalogTableStorageDescriptorSortColumnOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Glue.CatalogTableStorageDescriptorSortColumnArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Glue.CatalogTableStorageDescriptorSortColumn.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Column<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the column.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Sort<wbr>Order<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}Indicates that the column is sorted in ascending order (== 1), or in descending order (==0).
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Column<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the column.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Sort<wbr>Order<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}Indicates that the column is sorted in ascending order (== 1), or in descending order (==0).
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">column<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the column.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">sort<wbr>Order<span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}Indicates that the column is sorted in ascending order (== 1), or in descending order (==0).
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">column<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the column.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">sort<wbr>Order<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}Indicates that the column is sorted in ascending order (== 1), or in descending order (==0).
{{% /md %}}</dd>

</dl>
{{% /choosable %}}








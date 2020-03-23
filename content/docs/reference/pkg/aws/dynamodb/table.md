
---
title: "Table"
block_external_search_index: true
---

Provides a DynamoDB table resource

> **Note:** It is recommended to use `lifecycle` [`ignore_changes`](https://www.terraform.io/docs/configuration/resources.html#ignore_changes) for `read_capacity` and/or `write_capacity` if there's [autoscaling policy](https://www.terraform.io/docs/providers/aws/r/appautoscaling_policy.html) attached to the table.

## Example Usage

The following dynamodb table description models the table and GSI shown
in the [AWS SDK example documentation](https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/GSI.html)

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const basic_dynamodb_table = new aws.dynamodb.Table("basic-dynamodb-table", {
    attributes: [
        {
            name: "UserId",
            type: "S",
        },
        {
            name: "GameTitle",
            type: "S",
        },
        {
            name: "TopScore",
            type: "N",
        },
    ],
    billingMode: "PROVISIONED",
    globalSecondaryIndexes: [{
        hashKey: "GameTitle",
        name: "GameTitleIndex",
        nonKeyAttributes: ["UserId"],
        projectionType: "INCLUDE",
        rangeKey: "TopScore",
        readCapacity: 10,
        writeCapacity: 10,
    }],
    hashKey: "UserId",
    rangeKey: "GameTitle",
    readCapacity: 20,
    tags: {
        Environment: "production",
        Name: "dynamodb-table-1",
    },
    ttl: {
        attributeName: "TimeToExist",
        enabled: false,
    },
    writeCapacity: 20,
});
```

> This content is derived from https://github.com/terraform-providers/terraform-provider-aws/blob/master/website/docs/r/dynamodb_table.html.markdown.



## Create a Table Resource

{{< chooser language "javascript,typescript,python,go,csharp" / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/dynamodb/#Table">Table</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/dynamodb/#TableArgs">TableArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">Table</span><span class="p">(resource_name, opts=None, </span>attributes=None<span class="p">, </span>billing_mode=None<span class="p">, </span>global_secondary_indexes=None<span class="p">, </span>hash_key=None<span class="p">, </span>local_secondary_indexes=None<span class="p">, </span>name=None<span class="p">, </span>point_in_time_recovery=None<span class="p">, </span>range_key=None<span class="p">, </span>read_capacity=None<span class="p">, </span>server_side_encryption=None<span class="p">, </span>stream_enabled=None<span class="p">, </span>stream_view_type=None<span class="p">, </span>tags=None<span class="p">, </span>ttl=None<span class="p">, </span>write_capacity=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewTable<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/dynamodb?tab=doc#TableArgs">TableArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/dynamodb?tab=doc#Table">Table</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Dynamodb.Table.html">Table</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Dynamodb.TableArgs.html">TableArgs</a></span> <span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
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

    <dt class="property-required"
            title="Required">Attributes<span class="property-indicator"></span>
        <span class="property-type"><a href="#tableattribute">List&lt;Table<wbr>Attribute<wbr>Args&gt;</a></span>
    </dt>
    <dd>{{% md %}}List of nested attribute definitions. Only required for `hash_key` and `range_key` attributes. Each attribute has two properties:
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Billing<wbr>Mode<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Controls how you are charged for read and write throughput and how you manage capacity. The valid values are `PROVISIONED` and `PAY_PER_REQUEST`. Defaults to `PROVISIONED`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Global<wbr>Secondary<wbr>Indexes<span class="property-indicator"></span>
        <span class="property-type"><a href="#tableglobalsecondaryindex">List&lt;Table<wbr>Global<wbr>Secondary<wbr>Index<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}Describe a GSI for the table;
subject to the normal limits on the number of GSIs, projected
attributes, etc.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Hash<wbr>Key<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the hash key in the index; must be
defined as an attribute in the resource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Local<wbr>Secondary<wbr>Indexes<span class="property-indicator"></span>
        <span class="property-type"><a href="#tablelocalsecondaryindex">List&lt;Table<wbr>Local<wbr>Secondary<wbr>Index<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}Describe an LSI on the table;
these can only be allocated *at creation* so you cannot change this
definition after you have created the resource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the index
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Point<wbr>In<wbr>Time<wbr>Recovery<span class="property-indicator"></span>
        <span class="property-type"><a href="#tablepointintimerecovery">Table<wbr>Point<wbr>In<wbr>Time<wbr>Recovery<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}Point-in-time recovery options.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Range<wbr>Key<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the range key; must be defined
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Read<wbr>Capacity<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The number of read units for this index. Must be set if billing_mode is set to PROVISIONED.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Server<wbr>Side<wbr>Encryption<span class="property-indicator"></span>
        <span class="property-type"><a href="#tableserversideencryption">Table<wbr>Server<wbr>Side<wbr>Encryption<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}Encryption at rest options. AWS DynamoDB tables are automatically encrypted at rest with an AWS owned Customer Master Key if this argument isn&#39;t specified.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Stream<wbr>Enabled<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Indicates whether Streams are to be enabled (true) or disabled (false).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Stream<wbr>View<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}When an item in the table is modified, StreamViewType determines what information is written to the table&#39;s stream. Valid values are `KEYS_ONLY`, `NEW_IMAGE`, `OLD_IMAGE`, `NEW_AND_OLD_IMAGES`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}A map of tags to populate on the created table.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ttl<span class="property-indicator"></span>
        <span class="property-type"><a href="#tablettl">Table<wbr>Ttl<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}Defines ttl, has two properties, and can only be specified once:
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Write<wbr>Capacity<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The number of write units for this index. Must be set if billing_mode is set to PROVISIONED.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Attributes<span class="property-indicator"></span>
        <span class="property-type"><a href="#tableattribute">[]Table<wbr>Attribute</a></span>
    </dt>
    <dd>{{% md %}}List of nested attribute definitions. Only required for `hash_key` and `range_key` attributes. Each attribute has two properties:
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Billing<wbr>Mode<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Controls how you are charged for read and write throughput and how you manage capacity. The valid values are `PROVISIONED` and `PAY_PER_REQUEST`. Defaults to `PROVISIONED`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Global<wbr>Secondary<wbr>Indexes<span class="property-indicator"></span>
        <span class="property-type"><a href="#tableglobalsecondaryindex">[]Table<wbr>Global<wbr>Secondary<wbr>Index</a></span>
    </dt>
    <dd>{{% md %}}Describe a GSI for the table;
subject to the normal limits on the number of GSIs, projected
attributes, etc.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Hash<wbr>Key<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the hash key in the index; must be
defined as an attribute in the resource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Local<wbr>Secondary<wbr>Indexes<span class="property-indicator"></span>
        <span class="property-type"><a href="#tablelocalsecondaryindex">[]Table<wbr>Local<wbr>Secondary<wbr>Index</a></span>
    </dt>
    <dd>{{% md %}}Describe an LSI on the table;
these can only be allocated *at creation* so you cannot change this
definition after you have created the resource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name of the index
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Point<wbr>In<wbr>Time<wbr>Recovery<span class="property-indicator"></span>
        <span class="property-type"><a href="#tablepointintimerecovery">*Table<wbr>Point<wbr>In<wbr>Time<wbr>Recovery</a></span>
    </dt>
    <dd>{{% md %}}Point-in-time recovery options.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Range<wbr>Key<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name of the range key; must be defined
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Read<wbr>Capacity<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The number of read units for this index. Must be set if billing_mode is set to PROVISIONED.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Server<wbr>Side<wbr>Encryption<span class="property-indicator"></span>
        <span class="property-type"><a href="#tableserversideencryption">*Table<wbr>Server<wbr>Side<wbr>Encryption</a></span>
    </dt>
    <dd>{{% md %}}Encryption at rest options. AWS DynamoDB tables are automatically encrypted at rest with an AWS owned Customer Master Key if this argument isn&#39;t specified.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Stream<wbr>Enabled<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Indicates whether Streams are to be enabled (true) or disabled (false).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Stream<wbr>View<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}When an item in the table is modified, StreamViewType determines what information is written to the table&#39;s stream. Valid values are `KEYS_ONLY`, `NEW_IMAGE`, `OLD_IMAGE`, `NEW_AND_OLD_IMAGES`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}A map of tags to populate on the created table.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ttl<span class="property-indicator"></span>
        <span class="property-type"><a href="#tablettl">*Table<wbr>Ttl</a></span>
    </dt>
    <dd>{{% md %}}Defines ttl, has two properties, and can only be specified once:
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Write<wbr>Capacity<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The number of write units for this index. Must be set if billing_mode is set to PROVISIONED.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">attributes<span class="property-indicator"></span>
        <span class="property-type"><a href="#tableattribute">Table<wbr>Attribute[]</a></span>
    </dt>
    <dd>{{% md %}}List of nested attribute definitions. Only required for `hash_key` and `range_key` attributes. Each attribute has two properties:
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">billing<wbr>Mode<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Controls how you are charged for read and write throughput and how you manage capacity. The valid values are `PROVISIONED` and `PAY_PER_REQUEST`. Defaults to `PROVISIONED`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">global<wbr>Secondary<wbr>Indexes<span class="property-indicator"></span>
        <span class="property-type"><a href="#tableglobalsecondaryindex">Table<wbr>Global<wbr>Secondary<wbr>Index[]?</a></span>
    </dt>
    <dd>{{% md %}}Describe a GSI for the table;
subject to the normal limits on the number of GSIs, projected
attributes, etc.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">hash<wbr>Key<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the hash key in the index; must be
defined as an attribute in the resource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">local<wbr>Secondary<wbr>Indexes<span class="property-indicator"></span>
        <span class="property-type"><a href="#tablelocalsecondaryindex">Table<wbr>Local<wbr>Secondary<wbr>Index[]?</a></span>
    </dt>
    <dd>{{% md %}}Describe an LSI on the table;
these can only be allocated *at creation* so you cannot change this
definition after you have created the resource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the index
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">point<wbr>In<wbr>Time<wbr>Recovery<span class="property-indicator"></span>
        <span class="property-type"><a href="#tablepointintimerecovery">Table<wbr>Point<wbr>In<wbr>Time<wbr>Recovery?</a></span>
    </dt>
    <dd>{{% md %}}Point-in-time recovery options.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">range<wbr>Key<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the range key; must be defined
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">read<wbr>Capacity<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The number of read units for this index. Must be set if billing_mode is set to PROVISIONED.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">server<wbr>Side<wbr>Encryption<span class="property-indicator"></span>
        <span class="property-type"><a href="#tableserversideencryption">Table<wbr>Server<wbr>Side<wbr>Encryption?</a></span>
    </dt>
    <dd>{{% md %}}Encryption at rest options. AWS DynamoDB tables are automatically encrypted at rest with an AWS owned Customer Master Key if this argument isn&#39;t specified.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">stream<wbr>Enabled<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Indicates whether Streams are to be enabled (true) or disabled (false).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">stream<wbr>View<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}When an item in the table is modified, StreamViewType determines what information is written to the table&#39;s stream. Valid values are `KEYS_ONLY`, `NEW_IMAGE`, `OLD_IMAGE`, `NEW_AND_OLD_IMAGES`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}A map of tags to populate on the created table.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ttl<span class="property-indicator"></span>
        <span class="property-type"><a href="#tablettl">Table<wbr>Ttl?</a></span>
    </dt>
    <dd>{{% md %}}Defines ttl, has two properties, and can only be specified once:
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">write<wbr>Capacity<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The number of write units for this index. Must be set if billing_mode is set to PROVISIONED.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">attributes<span class="property-indicator"></span>
        <span class="property-type"><a href="#tableattribute">List[Table<wbr>Attribute]</a></span>
    </dt>
    <dd>{{% md %}}List of nested attribute definitions. Only required for `hash_key` and `range_key` attributes. Each attribute has two properties:
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">billing_<wbr>mode<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Controls how you are charged for read and write throughput and how you manage capacity. The valid values are `PROVISIONED` and `PAY_PER_REQUEST`. Defaults to `PROVISIONED`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">global_<wbr>secondary_<wbr>indexes<span class="property-indicator"></span>
        <span class="property-type"><a href="#tableglobalsecondaryindex">List[Table<wbr>Global<wbr>Secondary<wbr>Index]</a></span>
    </dt>
    <dd>{{% md %}}Describe a GSI for the table;
subject to the normal limits on the number of GSIs, projected
attributes, etc.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">hash_<wbr>key<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the hash key in the index; must be
defined as an attribute in the resource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">local_<wbr>secondary_<wbr>indexes<span class="property-indicator"></span>
        <span class="property-type"><a href="#tablelocalsecondaryindex">List[Table<wbr>Local<wbr>Secondary<wbr>Index]</a></span>
    </dt>
    <dd>{{% md %}}Describe an LSI on the table;
these can only be allocated *at creation* so you cannot change this
definition after you have created the resource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the index
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">point_<wbr>in_<wbr>time_<wbr>recovery<span class="property-indicator"></span>
        <span class="property-type"><a href="#tablepointintimerecovery">Dict[Table<wbr>Point<wbr>In<wbr>Time<wbr>Recovery]</a></span>
    </dt>
    <dd>{{% md %}}Point-in-time recovery options.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">range_<wbr>key<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the range key; must be defined
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">read_<wbr>capacity<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The number of read units for this index. Must be set if billing_mode is set to PROVISIONED.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">server_<wbr>side_<wbr>encryption<span class="property-indicator"></span>
        <span class="property-type"><a href="#tableserversideencryption">Dict[Table<wbr>Server<wbr>Side<wbr>Encryption]</a></span>
    </dt>
    <dd>{{% md %}}Encryption at rest options. AWS DynamoDB tables are automatically encrypted at rest with an AWS owned Customer Master Key if this argument isn&#39;t specified.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">stream_<wbr>enabled<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Indicates whether Streams are to be enabled (true) or disabled (false).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">stream_<wbr>view_<wbr>type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}When an item in the table is modified, StreamViewType determines what information is written to the table&#39;s stream. Valid values are `KEYS_ONLY`, `NEW_IMAGE`, `OLD_IMAGE`, `NEW_AND_OLD_IMAGES`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}A map of tags to populate on the created table.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ttl<span class="property-indicator"></span>
        <span class="property-type"><a href="#tablettl">Dict[Table<wbr>Ttl]</a></span>
    </dt>
    <dd>{{% md %}}Defines ttl, has two properties, and can only be specified once:
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">write_<wbr>capacity<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The number of write units for this index. Must be set if billing_mode is set to PROVISIONED.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}




## Table Output Properties

The following output properties are available:




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The arn of the table
{{% /md %}}</dd>

    <dt class="property-"
            title="">Attributes<span class="property-indicator"></span>
        <span class="property-type"><a href="#tableattribute">List&lt;Table<wbr>Attribute&gt;</a></span>
    </dt>
    <dd>{{% md %}}List of nested attribute definitions. Only required for `hash_key` and `range_key` attributes. Each attribute has two properties:
{{% /md %}}</dd>

    <dt class="property-"
            title="">Billing<wbr>Mode<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Controls how you are charged for read and write throughput and how you manage capacity. The valid values are `PROVISIONED` and `PAY_PER_REQUEST`. Defaults to `PROVISIONED`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Global<wbr>Secondary<wbr>Indexes<span class="property-indicator"></span>
        <span class="property-type"><a href="#tableglobalsecondaryindex">List&lt;Table<wbr>Global<wbr>Secondary<wbr>Index&gt;?</a></span>
    </dt>
    <dd>{{% md %}}Describe a GSI for the table;
subject to the normal limits on the number of GSIs, projected
attributes, etc.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Hash<wbr>Key<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the hash key in the index; must be
defined as an attribute in the resource.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Local<wbr>Secondary<wbr>Indexes<span class="property-indicator"></span>
        <span class="property-type"><a href="#tablelocalsecondaryindex">List&lt;Table<wbr>Local<wbr>Secondary<wbr>Index&gt;?</a></span>
    </dt>
    <dd>{{% md %}}Describe an LSI on the table;
these can only be allocated *at creation* so you cannot change this
definition after you have created the resource.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the index
{{% /md %}}</dd>

    <dt class="property-"
            title="">Point<wbr>In<wbr>Time<wbr>Recovery<span class="property-indicator"></span>
        <span class="property-type"><a href="#tablepointintimerecovery">Table<wbr>Point<wbr>In<wbr>Time<wbr>Recovery</a></span>
    </dt>
    <dd>{{% md %}}Point-in-time recovery options.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Range<wbr>Key<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the range key; must be defined
{{% /md %}}</dd>

    <dt class="property-"
            title="">Read<wbr>Capacity<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The number of read units for this index. Must be set if billing_mode is set to PROVISIONED.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Server<wbr>Side<wbr>Encryption<span class="property-indicator"></span>
        <span class="property-type"><a href="#tableserversideencryption">Table<wbr>Server<wbr>Side<wbr>Encryption</a></span>
    </dt>
    <dd>{{% md %}}Encryption at rest options. AWS DynamoDB tables are automatically encrypted at rest with an AWS owned Customer Master Key if this argument isn&#39;t specified.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Stream<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of the Table Stream. Only available when `stream_enabled = true`
{{% /md %}}</dd>

    <dt class="property-"
            title="">Stream<wbr>Enabled<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Indicates whether Streams are to be enabled (true) or disabled (false).
{{% /md %}}</dd>

    <dt class="property-"
            title="">Stream<wbr>Label<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}A timestamp, in ISO 8601 format, for this stream. Note that this timestamp is not
a unique identifier for the stream on its own. However, the combination of AWS customer ID,
table name and this field is guaranteed to be unique.
It can be used for creating CloudWatch Alarms. Only available when `stream_enabled = true`
{{% /md %}}</dd>

    <dt class="property-"
            title="">Stream<wbr>View<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}When an item in the table is modified, StreamViewType determines what information is written to the table&#39;s stream. Valid values are `KEYS_ONLY`, `NEW_IMAGE`, `OLD_IMAGE`, `NEW_AND_OLD_IMAGES`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}A map of tags to populate on the created table.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Ttl<span class="property-indicator"></span>
        <span class="property-type"><a href="#tablettl">Table<wbr>Ttl?</a></span>
    </dt>
    <dd>{{% md %}}Defines ttl, has two properties, and can only be specified once:
{{% /md %}}</dd>

    <dt class="property-"
            title="">Write<wbr>Capacity<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The number of write units for this index. Must be set if billing_mode is set to PROVISIONED.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The arn of the table
{{% /md %}}</dd>

    <dt class="property-"
            title="">Attributes<span class="property-indicator"></span>
        <span class="property-type"><a href="#tableattribute">[]Table<wbr>Attribute</a></span>
    </dt>
    <dd>{{% md %}}List of nested attribute definitions. Only required for `hash_key` and `range_key` attributes. Each attribute has two properties:
{{% /md %}}</dd>

    <dt class="property-"
            title="">Billing<wbr>Mode<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Controls how you are charged for read and write throughput and how you manage capacity. The valid values are `PROVISIONED` and `PAY_PER_REQUEST`. Defaults to `PROVISIONED`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Global<wbr>Secondary<wbr>Indexes<span class="property-indicator"></span>
        <span class="property-type"><a href="#tableglobalsecondaryindex">[]Table<wbr>Global<wbr>Secondary<wbr>Index</a></span>
    </dt>
    <dd>{{% md %}}Describe a GSI for the table;
subject to the normal limits on the number of GSIs, projected
attributes, etc.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Hash<wbr>Key<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the hash key in the index; must be
defined as an attribute in the resource.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Local<wbr>Secondary<wbr>Indexes<span class="property-indicator"></span>
        <span class="property-type"><a href="#tablelocalsecondaryindex">[]Table<wbr>Local<wbr>Secondary<wbr>Index</a></span>
    </dt>
    <dd>{{% md %}}Describe an LSI on the table;
these can only be allocated *at creation* so you cannot change this
definition after you have created the resource.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the index
{{% /md %}}</dd>

    <dt class="property-"
            title="">Point<wbr>In<wbr>Time<wbr>Recovery<span class="property-indicator"></span>
        <span class="property-type"><a href="#tablepointintimerecovery">Table<wbr>Point<wbr>In<wbr>Time<wbr>Recovery</a></span>
    </dt>
    <dd>{{% md %}}Point-in-time recovery options.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Range<wbr>Key<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name of the range key; must be defined
{{% /md %}}</dd>

    <dt class="property-"
            title="">Read<wbr>Capacity<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The number of read units for this index. Must be set if billing_mode is set to PROVISIONED.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Server<wbr>Side<wbr>Encryption<span class="property-indicator"></span>
        <span class="property-type"><a href="#tableserversideencryption">Table<wbr>Server<wbr>Side<wbr>Encryption</a></span>
    </dt>
    <dd>{{% md %}}Encryption at rest options. AWS DynamoDB tables are automatically encrypted at rest with an AWS owned Customer Master Key if this argument isn&#39;t specified.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Stream<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of the Table Stream. Only available when `stream_enabled = true`
{{% /md %}}</dd>

    <dt class="property-"
            title="">Stream<wbr>Enabled<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Indicates whether Streams are to be enabled (true) or disabled (false).
{{% /md %}}</dd>

    <dt class="property-"
            title="">Stream<wbr>Label<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}A timestamp, in ISO 8601 format, for this stream. Note that this timestamp is not
a unique identifier for the stream on its own. However, the combination of AWS customer ID,
table name and this field is guaranteed to be unique.
It can be used for creating CloudWatch Alarms. Only available when `stream_enabled = true`
{{% /md %}}</dd>

    <dt class="property-"
            title="">Stream<wbr>View<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}When an item in the table is modified, StreamViewType determines what information is written to the table&#39;s stream. Valid values are `KEYS_ONLY`, `NEW_IMAGE`, `OLD_IMAGE`, `NEW_AND_OLD_IMAGES`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}A map of tags to populate on the created table.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Ttl<span class="property-indicator"></span>
        <span class="property-type"><a href="#tablettl">*Table<wbr>Ttl</a></span>
    </dt>
    <dd>{{% md %}}Defines ttl, has two properties, and can only be specified once:
{{% /md %}}</dd>

    <dt class="property-"
            title="">Write<wbr>Capacity<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The number of write units for this index. Must be set if billing_mode is set to PROVISIONED.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The arn of the table
{{% /md %}}</dd>

    <dt class="property-"
            title="">attributes<span class="property-indicator"></span>
        <span class="property-type"><a href="#tableattribute">Table<wbr>Attribute[]</a></span>
    </dt>
    <dd>{{% md %}}List of nested attribute definitions. Only required for `hash_key` and `range_key` attributes. Each attribute has two properties:
{{% /md %}}</dd>

    <dt class="property-"
            title="">billing<wbr>Mode<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Controls how you are charged for read and write throughput and how you manage capacity. The valid values are `PROVISIONED` and `PAY_PER_REQUEST`. Defaults to `PROVISIONED`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">global<wbr>Secondary<wbr>Indexes<span class="property-indicator"></span>
        <span class="property-type"><a href="#tableglobalsecondaryindex">Table<wbr>Global<wbr>Secondary<wbr>Index[]?</a></span>
    </dt>
    <dd>{{% md %}}Describe a GSI for the table;
subject to the normal limits on the number of GSIs, projected
attributes, etc.
{{% /md %}}</dd>

    <dt class="property-"
            title="">hash<wbr>Key<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the hash key in the index; must be
defined as an attribute in the resource.
{{% /md %}}</dd>

    <dt class="property-"
            title="">local<wbr>Secondary<wbr>Indexes<span class="property-indicator"></span>
        <span class="property-type"><a href="#tablelocalsecondaryindex">Table<wbr>Local<wbr>Secondary<wbr>Index[]?</a></span>
    </dt>
    <dd>{{% md %}}Describe an LSI on the table;
these can only be allocated *at creation* so you cannot change this
definition after you have created the resource.
{{% /md %}}</dd>

    <dt class="property-"
            title="">name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the index
{{% /md %}}</dd>

    <dt class="property-"
            title="">point<wbr>In<wbr>Time<wbr>Recovery<span class="property-indicator"></span>
        <span class="property-type"><a href="#tablepointintimerecovery">Table<wbr>Point<wbr>In<wbr>Time<wbr>Recovery</a></span>
    </dt>
    <dd>{{% md %}}Point-in-time recovery options.
{{% /md %}}</dd>

    <dt class="property-"
            title="">range<wbr>Key<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the range key; must be defined
{{% /md %}}</dd>

    <dt class="property-"
            title="">read<wbr>Capacity<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The number of read units for this index. Must be set if billing_mode is set to PROVISIONED.
{{% /md %}}</dd>

    <dt class="property-"
            title="">server<wbr>Side<wbr>Encryption<span class="property-indicator"></span>
        <span class="property-type"><a href="#tableserversideencryption">Table<wbr>Server<wbr>Side<wbr>Encryption</a></span>
    </dt>
    <dd>{{% md %}}Encryption at rest options. AWS DynamoDB tables are automatically encrypted at rest with an AWS owned Customer Master Key if this argument isn&#39;t specified.
{{% /md %}}</dd>

    <dt class="property-"
            title="">stream<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of the Table Stream. Only available when `stream_enabled = true`
{{% /md %}}</dd>

    <dt class="property-"
            title="">stream<wbr>Enabled<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Indicates whether Streams are to be enabled (true) or disabled (false).
{{% /md %}}</dd>

    <dt class="property-"
            title="">stream<wbr>Label<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}A timestamp, in ISO 8601 format, for this stream. Note that this timestamp is not
a unique identifier for the stream on its own. However, the combination of AWS customer ID,
table name and this field is guaranteed to be unique.
It can be used for creating CloudWatch Alarms. Only available when `stream_enabled = true`
{{% /md %}}</dd>

    <dt class="property-"
            title="">stream<wbr>View<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}When an item in the table is modified, StreamViewType determines what information is written to the table&#39;s stream. Valid values are `KEYS_ONLY`, `NEW_IMAGE`, `OLD_IMAGE`, `NEW_AND_OLD_IMAGES`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}A map of tags to populate on the created table.
{{% /md %}}</dd>

    <dt class="property-"
            title="">ttl<span class="property-indicator"></span>
        <span class="property-type"><a href="#tablettl">Table<wbr>Ttl?</a></span>
    </dt>
    <dd>{{% md %}}Defines ttl, has two properties, and can only be specified once:
{{% /md %}}</dd>

    <dt class="property-"
            title="">write<wbr>Capacity<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The number of write units for this index. Must be set if billing_mode is set to PROVISIONED.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The arn of the table
{{% /md %}}</dd>

    <dt class="property-"
            title="">attributes<span class="property-indicator"></span>
        <span class="property-type"><a href="#tableattribute">List[Table<wbr>Attribute]</a></span>
    </dt>
    <dd>{{% md %}}List of nested attribute definitions. Only required for `hash_key` and `range_key` attributes. Each attribute has two properties:
{{% /md %}}</dd>

    <dt class="property-"
            title="">billing_<wbr>mode<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Controls how you are charged for read and write throughput and how you manage capacity. The valid values are `PROVISIONED` and `PAY_PER_REQUEST`. Defaults to `PROVISIONED`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">global_<wbr>secondary_<wbr>indexes<span class="property-indicator"></span>
        <span class="property-type"><a href="#tableglobalsecondaryindex">List[Table<wbr>Global<wbr>Secondary<wbr>Index]</a></span>
    </dt>
    <dd>{{% md %}}Describe a GSI for the table;
subject to the normal limits on the number of GSIs, projected
attributes, etc.
{{% /md %}}</dd>

    <dt class="property-"
            title="">hash_<wbr>key<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the hash key in the index; must be
defined as an attribute in the resource.
{{% /md %}}</dd>

    <dt class="property-"
            title="">local_<wbr>secondary_<wbr>indexes<span class="property-indicator"></span>
        <span class="property-type"><a href="#tablelocalsecondaryindex">List[Table<wbr>Local<wbr>Secondary<wbr>Index]</a></span>
    </dt>
    <dd>{{% md %}}Describe an LSI on the table;
these can only be allocated *at creation* so you cannot change this
definition after you have created the resource.
{{% /md %}}</dd>

    <dt class="property-"
            title="">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the index
{{% /md %}}</dd>

    <dt class="property-"
            title="">point_<wbr>in_<wbr>time_<wbr>recovery<span class="property-indicator"></span>
        <span class="property-type"><a href="#tablepointintimerecovery">Dict[Table<wbr>Point<wbr>In<wbr>Time<wbr>Recovery]</a></span>
    </dt>
    <dd>{{% md %}}Point-in-time recovery options.
{{% /md %}}</dd>

    <dt class="property-"
            title="">range_<wbr>key<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the range key; must be defined
{{% /md %}}</dd>

    <dt class="property-"
            title="">read_<wbr>capacity<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The number of read units for this index. Must be set if billing_mode is set to PROVISIONED.
{{% /md %}}</dd>

    <dt class="property-"
            title="">server_<wbr>side_<wbr>encryption<span class="property-indicator"></span>
        <span class="property-type"><a href="#tableserversideencryption">Dict[Table<wbr>Server<wbr>Side<wbr>Encryption]</a></span>
    </dt>
    <dd>{{% md %}}Encryption at rest options. AWS DynamoDB tables are automatically encrypted at rest with an AWS owned Customer Master Key if this argument isn&#39;t specified.
{{% /md %}}</dd>

    <dt class="property-"
            title="">stream_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ARN of the Table Stream. Only available when `stream_enabled = true`
{{% /md %}}</dd>

    <dt class="property-"
            title="">stream_<wbr>enabled<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Indicates whether Streams are to be enabled (true) or disabled (false).
{{% /md %}}</dd>

    <dt class="property-"
            title="">stream_<wbr>label<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A timestamp, in ISO 8601 format, for this stream. Note that this timestamp is not
a unique identifier for the stream on its own. However, the combination of AWS customer ID,
table name and this field is guaranteed to be unique.
It can be used for creating CloudWatch Alarms. Only available when `stream_enabled = true`
{{% /md %}}</dd>

    <dt class="property-"
            title="">stream_<wbr>view_<wbr>type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}When an item in the table is modified, StreamViewType determines what information is written to the table&#39;s stream. Valid values are `KEYS_ONLY`, `NEW_IMAGE`, `OLD_IMAGE`, `NEW_AND_OLD_IMAGES`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}A map of tags to populate on the created table.
{{% /md %}}</dd>

    <dt class="property-"
            title="">ttl<span class="property-indicator"></span>
        <span class="property-type"><a href="#tablettl">Dict[Table<wbr>Ttl]</a></span>
    </dt>
    <dd>{{% md %}}Defines ttl, has two properties, and can only be specified once:
{{% /md %}}</dd>

    <dt class="property-"
            title="">write_<wbr>capacity<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The number of write units for this index. Must be set if billing_mode is set to PROVISIONED.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





## Look up an Existing Table Resource

{{< chooser language "javascript,typescript,python,go,csharp  " / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">pulumi.Input&lt;pulumi.ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/dynamodb/#TableState">TableState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/dynamodb/#Table">Table</a></span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>arn=None<span class="p">, </span>attributes=None<span class="p">, </span>billing_mode=None<span class="p">, </span>global_secondary_indexes=None<span class="p">, </span>hash_key=None<span class="p">, </span>local_secondary_indexes=None<span class="p">, </span>name=None<span class="p">, </span>point_in_time_recovery=None<span class="p">, </span>range_key=None<span class="p">, </span>read_capacity=None<span class="p">, </span>server_side_encryption=None<span class="p">, </span>stream_arn=None<span class="p">, </span>stream_enabled=None<span class="p">, </span>stream_label=None<span class="p">, </span>stream_view_type=None<span class="p">, </span>tags=None<span class="p">, </span>ttl=None<span class="p">, </span>write_capacity=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetTable<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">pulumi.IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/dynamodb?tab=doc#TableState">TableState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/dynamodb?tab=doc#Table">Table</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Dynamodb.Table.html">Table</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Pulumi.Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Dynamodb.TableState.html">TableState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
{{% /choosable %}}

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



{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The arn of the table
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Attributes<span class="property-indicator"></span>
        <span class="property-type"><a href="#tableattribute">List&lt;Table<wbr>Attribute<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}List of nested attribute definitions. Only required for `hash_key` and `range_key` attributes. Each attribute has two properties:
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Billing<wbr>Mode<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Controls how you are charged for read and write throughput and how you manage capacity. The valid values are `PROVISIONED` and `PAY_PER_REQUEST`. Defaults to `PROVISIONED`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Global<wbr>Secondary<wbr>Indexes<span class="property-indicator"></span>
        <span class="property-type"><a href="#tableglobalsecondaryindex">List&lt;Table<wbr>Global<wbr>Secondary<wbr>Index<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}Describe a GSI for the table;
subject to the normal limits on the number of GSIs, projected
attributes, etc.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Hash<wbr>Key<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the hash key in the index; must be
defined as an attribute in the resource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Local<wbr>Secondary<wbr>Indexes<span class="property-indicator"></span>
        <span class="property-type"><a href="#tablelocalsecondaryindex">List&lt;Table<wbr>Local<wbr>Secondary<wbr>Index<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}Describe an LSI on the table;
these can only be allocated *at creation* so you cannot change this
definition after you have created the resource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the index
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Point<wbr>In<wbr>Time<wbr>Recovery<span class="property-indicator"></span>
        <span class="property-type"><a href="#tablepointintimerecovery">Table<wbr>Point<wbr>In<wbr>Time<wbr>Recovery<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}Point-in-time recovery options.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Range<wbr>Key<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the range key; must be defined
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Read<wbr>Capacity<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The number of read units for this index. Must be set if billing_mode is set to PROVISIONED.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Server<wbr>Side<wbr>Encryption<span class="property-indicator"></span>
        <span class="property-type"><a href="#tableserversideencryption">Table<wbr>Server<wbr>Side<wbr>Encryption<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}Encryption at rest options. AWS DynamoDB tables are automatically encrypted at rest with an AWS owned Customer Master Key if this argument isn&#39;t specified.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Stream<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ARN of the Table Stream. Only available when `stream_enabled = true`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Stream<wbr>Enabled<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Indicates whether Streams are to be enabled (true) or disabled (false).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Stream<wbr>Label<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A timestamp, in ISO 8601 format, for this stream. Note that this timestamp is not
a unique identifier for the stream on its own. However, the combination of AWS customer ID,
table name and this field is guaranteed to be unique.
It can be used for creating CloudWatch Alarms. Only available when `stream_enabled = true`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Stream<wbr>View<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}When an item in the table is modified, StreamViewType determines what information is written to the table&#39;s stream. Valid values are `KEYS_ONLY`, `NEW_IMAGE`, `OLD_IMAGE`, `NEW_AND_OLD_IMAGES`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}A map of tags to populate on the created table.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ttl<span class="property-indicator"></span>
        <span class="property-type"><a href="#tablettl">Table<wbr>Ttl<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}Defines ttl, has two properties, and can only be specified once:
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Write<wbr>Capacity<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The number of write units for this index. Must be set if billing_mode is set to PROVISIONED.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The arn of the table
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Attributes<span class="property-indicator"></span>
        <span class="property-type"><a href="#tableattribute">[]Table<wbr>Attribute</a></span>
    </dt>
    <dd>{{% md %}}List of nested attribute definitions. Only required for `hash_key` and `range_key` attributes. Each attribute has two properties:
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Billing<wbr>Mode<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Controls how you are charged for read and write throughput and how you manage capacity. The valid values are `PROVISIONED` and `PAY_PER_REQUEST`. Defaults to `PROVISIONED`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Global<wbr>Secondary<wbr>Indexes<span class="property-indicator"></span>
        <span class="property-type"><a href="#tableglobalsecondaryindex">[]Table<wbr>Global<wbr>Secondary<wbr>Index</a></span>
    </dt>
    <dd>{{% md %}}Describe a GSI for the table;
subject to the normal limits on the number of GSIs, projected
attributes, etc.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Hash<wbr>Key<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name of the hash key in the index; must be
defined as an attribute in the resource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Local<wbr>Secondary<wbr>Indexes<span class="property-indicator"></span>
        <span class="property-type"><a href="#tablelocalsecondaryindex">[]Table<wbr>Local<wbr>Secondary<wbr>Index</a></span>
    </dt>
    <dd>{{% md %}}Describe an LSI on the table;
these can only be allocated *at creation* so you cannot change this
definition after you have created the resource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name of the index
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Point<wbr>In<wbr>Time<wbr>Recovery<span class="property-indicator"></span>
        <span class="property-type"><a href="#tablepointintimerecovery">*Table<wbr>Point<wbr>In<wbr>Time<wbr>Recovery</a></span>
    </dt>
    <dd>{{% md %}}Point-in-time recovery options.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Range<wbr>Key<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name of the range key; must be defined
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Read<wbr>Capacity<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The number of read units for this index. Must be set if billing_mode is set to PROVISIONED.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Server<wbr>Side<wbr>Encryption<span class="property-indicator"></span>
        <span class="property-type"><a href="#tableserversideencryption">*Table<wbr>Server<wbr>Side<wbr>Encryption</a></span>
    </dt>
    <dd>{{% md %}}Encryption at rest options. AWS DynamoDB tables are automatically encrypted at rest with an AWS owned Customer Master Key if this argument isn&#39;t specified.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Stream<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The ARN of the Table Stream. Only available when `stream_enabled = true`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Stream<wbr>Enabled<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Indicates whether Streams are to be enabled (true) or disabled (false).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Stream<wbr>Label<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}A timestamp, in ISO 8601 format, for this stream. Note that this timestamp is not
a unique identifier for the stream on its own. However, the combination of AWS customer ID,
table name and this field is guaranteed to be unique.
It can be used for creating CloudWatch Alarms. Only available when `stream_enabled = true`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Stream<wbr>View<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}When an item in the table is modified, StreamViewType determines what information is written to the table&#39;s stream. Valid values are `KEYS_ONLY`, `NEW_IMAGE`, `OLD_IMAGE`, `NEW_AND_OLD_IMAGES`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}A map of tags to populate on the created table.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ttl<span class="property-indicator"></span>
        <span class="property-type"><a href="#tablettl">*Table<wbr>Ttl</a></span>
    </dt>
    <dd>{{% md %}}Defines ttl, has two properties, and can only be specified once:
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Write<wbr>Capacity<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The number of write units for this index. Must be set if billing_mode is set to PROVISIONED.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The arn of the table
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">attributes<span class="property-indicator"></span>
        <span class="property-type"><a href="#tableattribute">Table<wbr>Attribute[]?</a></span>
    </dt>
    <dd>{{% md %}}List of nested attribute definitions. Only required for `hash_key` and `range_key` attributes. Each attribute has two properties:
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">billing<wbr>Mode<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Controls how you are charged for read and write throughput and how you manage capacity. The valid values are `PROVISIONED` and `PAY_PER_REQUEST`. Defaults to `PROVISIONED`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">global<wbr>Secondary<wbr>Indexes<span class="property-indicator"></span>
        <span class="property-type"><a href="#tableglobalsecondaryindex">Table<wbr>Global<wbr>Secondary<wbr>Index[]?</a></span>
    </dt>
    <dd>{{% md %}}Describe a GSI for the table;
subject to the normal limits on the number of GSIs, projected
attributes, etc.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">hash<wbr>Key<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the hash key in the index; must be
defined as an attribute in the resource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">local<wbr>Secondary<wbr>Indexes<span class="property-indicator"></span>
        <span class="property-type"><a href="#tablelocalsecondaryindex">Table<wbr>Local<wbr>Secondary<wbr>Index[]?</a></span>
    </dt>
    <dd>{{% md %}}Describe an LSI on the table;
these can only be allocated *at creation* so you cannot change this
definition after you have created the resource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the index
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">point<wbr>In<wbr>Time<wbr>Recovery<span class="property-indicator"></span>
        <span class="property-type"><a href="#tablepointintimerecovery">Table<wbr>Point<wbr>In<wbr>Time<wbr>Recovery?</a></span>
    </dt>
    <dd>{{% md %}}Point-in-time recovery options.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">range<wbr>Key<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the range key; must be defined
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">read<wbr>Capacity<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The number of read units for this index. Must be set if billing_mode is set to PROVISIONED.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">server<wbr>Side<wbr>Encryption<span class="property-indicator"></span>
        <span class="property-type"><a href="#tableserversideencryption">Table<wbr>Server<wbr>Side<wbr>Encryption?</a></span>
    </dt>
    <dd>{{% md %}}Encryption at rest options. AWS DynamoDB tables are automatically encrypted at rest with an AWS owned Customer Master Key if this argument isn&#39;t specified.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">stream<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ARN of the Table Stream. Only available when `stream_enabled = true`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">stream<wbr>Enabled<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Indicates whether Streams are to be enabled (true) or disabled (false).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">stream<wbr>Label<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A timestamp, in ISO 8601 format, for this stream. Note that this timestamp is not
a unique identifier for the stream on its own. However, the combination of AWS customer ID,
table name and this field is guaranteed to be unique.
It can be used for creating CloudWatch Alarms. Only available when `stream_enabled = true`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">stream<wbr>View<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}When an item in the table is modified, StreamViewType determines what information is written to the table&#39;s stream. Valid values are `KEYS_ONLY`, `NEW_IMAGE`, `OLD_IMAGE`, `NEW_AND_OLD_IMAGES`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}A map of tags to populate on the created table.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ttl<span class="property-indicator"></span>
        <span class="property-type"><a href="#tablettl">Table<wbr>Ttl?</a></span>
    </dt>
    <dd>{{% md %}}Defines ttl, has two properties, and can only be specified once:
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">write<wbr>Capacity<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The number of write units for this index. Must be set if billing_mode is set to PROVISIONED.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The arn of the table
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">attributes<span class="property-indicator"></span>
        <span class="property-type"><a href="#tableattribute">List[Table<wbr>Attribute]</a></span>
    </dt>
    <dd>{{% md %}}List of nested attribute definitions. Only required for `hash_key` and `range_key` attributes. Each attribute has two properties:
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">billing_<wbr>mode<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Controls how you are charged for read and write throughput and how you manage capacity. The valid values are `PROVISIONED` and `PAY_PER_REQUEST`. Defaults to `PROVISIONED`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">global_<wbr>secondary_<wbr>indexes<span class="property-indicator"></span>
        <span class="property-type"><a href="#tableglobalsecondaryindex">List[Table<wbr>Global<wbr>Secondary<wbr>Index]</a></span>
    </dt>
    <dd>{{% md %}}Describe a GSI for the table;
subject to the normal limits on the number of GSIs, projected
attributes, etc.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">hash_<wbr>key<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the hash key in the index; must be
defined as an attribute in the resource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">local_<wbr>secondary_<wbr>indexes<span class="property-indicator"></span>
        <span class="property-type"><a href="#tablelocalsecondaryindex">List[Table<wbr>Local<wbr>Secondary<wbr>Index]</a></span>
    </dt>
    <dd>{{% md %}}Describe an LSI on the table;
these can only be allocated *at creation* so you cannot change this
definition after you have created the resource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the index
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">point_<wbr>in_<wbr>time_<wbr>recovery<span class="property-indicator"></span>
        <span class="property-type"><a href="#tablepointintimerecovery">Dict[Table<wbr>Point<wbr>In<wbr>Time<wbr>Recovery]</a></span>
    </dt>
    <dd>{{% md %}}Point-in-time recovery options.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">range_<wbr>key<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the range key; must be defined
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">read_<wbr>capacity<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The number of read units for this index. Must be set if billing_mode is set to PROVISIONED.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">server_<wbr>side_<wbr>encryption<span class="property-indicator"></span>
        <span class="property-type"><a href="#tableserversideencryption">Dict[Table<wbr>Server<wbr>Side<wbr>Encryption]</a></span>
    </dt>
    <dd>{{% md %}}Encryption at rest options. AWS DynamoDB tables are automatically encrypted at rest with an AWS owned Customer Master Key if this argument isn&#39;t specified.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">stream_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ARN of the Table Stream. Only available when `stream_enabled = true`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">stream_<wbr>enabled<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Indicates whether Streams are to be enabled (true) or disabled (false).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">stream_<wbr>label<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A timestamp, in ISO 8601 format, for this stream. Note that this timestamp is not
a unique identifier for the stream on its own. However, the combination of AWS customer ID,
table name and this field is guaranteed to be unique.
It can be used for creating CloudWatch Alarms. Only available when `stream_enabled = true`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">stream_<wbr>view_<wbr>type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}When an item in the table is modified, StreamViewType determines what information is written to the table&#39;s stream. Valid values are `KEYS_ONLY`, `NEW_IMAGE`, `OLD_IMAGE`, `NEW_AND_OLD_IMAGES`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}A map of tags to populate on the created table.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ttl<span class="property-indicator"></span>
        <span class="property-type"><a href="#tablettl">Dict[Table<wbr>Ttl]</a></span>
    </dt>
    <dd>{{% md %}}Defines ttl, has two properties, and can only be specified once:
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">write_<wbr>capacity<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The number of write units for this index. Must be set if billing_mode is set to PROVISIONED.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}







## Supporting Types

#### TableAttribute
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#TableAttribute">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#TableAttribute">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/dynamodb?tab=doc#TableAttributeArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/dynamodb?tab=doc#TableAttributeOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Dynamodb.TableAttributeArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Dynamodb.TableAttribute.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the index
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Attribute type, which must be a scalar type: `S`, `N`, or `B` for (S)tring, (N)umber or (B)inary data
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the index
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Attribute type, which must be a scalar type: `S`, `N`, or `B` for (S)tring, (N)umber or (B)inary data
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the index
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Attribute type, which must be a scalar type: `S`, `N`, or `B` for (S)tring, (N)umber or (B)inary data
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the index
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Attribute type, which must be a scalar type: `S`, `N`, or `B` for (S)tring, (N)umber or (B)inary data
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### TableGlobalSecondaryIndex
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#TableGlobalSecondaryIndex">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#TableGlobalSecondaryIndex">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/dynamodb?tab=doc#TableGlobalSecondaryIndexArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/dynamodb?tab=doc#TableGlobalSecondaryIndexOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Dynamodb.TableGlobalSecondaryIndexArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Dynamodb.TableGlobalSecondaryIndex.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Hash<wbr>Key<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the hash key in the index; must be
defined as an attribute in the resource.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the index
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Non<wbr>Key<wbr>Attributes<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}Only required with `INCLUDE` as a
projection type; a list of attributes to project into the index. These
do not need to be defined as attributes on the table.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Projection<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}One of `ALL`, `INCLUDE` or `KEYS_ONLY`
where `ALL` projects every attribute into the index, `KEYS_ONLY`
projects just the hash and range key into the index, and `INCLUDE`
projects only the keys specified in the _non_key_attributes_
parameter.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Range<wbr>Key<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the range key; must be defined
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Read<wbr>Capacity<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The number of read units for this index. Must be set if billing_mode is set to PROVISIONED.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Write<wbr>Capacity<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The number of write units for this index. Must be set if billing_mode is set to PROVISIONED.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Hash<wbr>Key<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the hash key in the index; must be
defined as an attribute in the resource.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the index
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Non<wbr>Key<wbr>Attributes<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}Only required with `INCLUDE` as a
projection type; a list of attributes to project into the index. These
do not need to be defined as attributes on the table.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Projection<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}One of `ALL`, `INCLUDE` or `KEYS_ONLY`
where `ALL` projects every attribute into the index, `KEYS_ONLY`
projects just the hash and range key into the index, and `INCLUDE`
projects only the keys specified in the _non_key_attributes_
parameter.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Range<wbr>Key<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name of the range key; must be defined
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Read<wbr>Capacity<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The number of read units for this index. Must be set if billing_mode is set to PROVISIONED.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Write<wbr>Capacity<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The number of write units for this index. Must be set if billing_mode is set to PROVISIONED.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">hash<wbr>Key<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the hash key in the index; must be
defined as an attribute in the resource.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the index
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">non<wbr>Key<wbr>Attributes<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}Only required with `INCLUDE` as a
projection type; a list of attributes to project into the index. These
do not need to be defined as attributes on the table.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">projection<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}One of `ALL`, `INCLUDE` or `KEYS_ONLY`
where `ALL` projects every attribute into the index, `KEYS_ONLY`
projects just the hash and range key into the index, and `INCLUDE`
projects only the keys specified in the _non_key_attributes_
parameter.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">range<wbr>Key<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the range key; must be defined
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">read<wbr>Capacity<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The number of read units for this index. Must be set if billing_mode is set to PROVISIONED.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">write<wbr>Capacity<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The number of write units for this index. Must be set if billing_mode is set to PROVISIONED.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">hash_<wbr>key<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the hash key in the index; must be
defined as an attribute in the resource.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the index
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">non<wbr>Key<wbr>Attributes<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}Only required with `INCLUDE` as a
projection type; a list of attributes to project into the index. These
do not need to be defined as attributes on the table.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">projection<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}One of `ALL`, `INCLUDE` or `KEYS_ONLY`
where `ALL` projects every attribute into the index, `KEYS_ONLY`
projects just the hash and range key into the index, and `INCLUDE`
projects only the keys specified in the _non_key_attributes_
parameter.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">range_<wbr>key<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the range key; must be defined
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">read_<wbr>capacity<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The number of read units for this index. Must be set if billing_mode is set to PROVISIONED.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">write_<wbr>capacity<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The number of write units for this index. Must be set if billing_mode is set to PROVISIONED.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### TableLocalSecondaryIndex
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#TableLocalSecondaryIndex">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#TableLocalSecondaryIndex">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/dynamodb?tab=doc#TableLocalSecondaryIndexArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/dynamodb?tab=doc#TableLocalSecondaryIndexOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Dynamodb.TableLocalSecondaryIndexArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Dynamodb.TableLocalSecondaryIndex.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the index
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Non<wbr>Key<wbr>Attributes<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}Only required with `INCLUDE` as a
projection type; a list of attributes to project into the index. These
do not need to be defined as attributes on the table.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Projection<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}One of `ALL`, `INCLUDE` or `KEYS_ONLY`
where `ALL` projects every attribute into the index, `KEYS_ONLY`
projects just the hash and range key into the index, and `INCLUDE`
projects only the keys specified in the _non_key_attributes_
parameter.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Range<wbr>Key<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the range key; must be defined
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the index
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Non<wbr>Key<wbr>Attributes<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}Only required with `INCLUDE` as a
projection type; a list of attributes to project into the index. These
do not need to be defined as attributes on the table.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Projection<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}One of `ALL`, `INCLUDE` or `KEYS_ONLY`
where `ALL` projects every attribute into the index, `KEYS_ONLY`
projects just the hash and range key into the index, and `INCLUDE`
projects only the keys specified in the _non_key_attributes_
parameter.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Range<wbr>Key<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the range key; must be defined
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the index
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">non<wbr>Key<wbr>Attributes<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}Only required with `INCLUDE` as a
projection type; a list of attributes to project into the index. These
do not need to be defined as attributes on the table.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">projection<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}One of `ALL`, `INCLUDE` or `KEYS_ONLY`
where `ALL` projects every attribute into the index, `KEYS_ONLY`
projects just the hash and range key into the index, and `INCLUDE`
projects only the keys specified in the _non_key_attributes_
parameter.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">range<wbr>Key<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the range key; must be defined
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the index
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">non<wbr>Key<wbr>Attributes<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}Only required with `INCLUDE` as a
projection type; a list of attributes to project into the index. These
do not need to be defined as attributes on the table.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">projection<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}One of `ALL`, `INCLUDE` or `KEYS_ONLY`
where `ALL` projects every attribute into the index, `KEYS_ONLY`
projects just the hash and range key into the index, and `INCLUDE`
projects only the keys specified in the _non_key_attributes_
parameter.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">range_<wbr>key<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the range key; must be defined
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### TablePointInTimeRecovery
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#TablePointInTimeRecovery">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#TablePointInTimeRecovery">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/dynamodb?tab=doc#TablePointInTimeRecoveryArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/dynamodb?tab=doc#TablePointInTimeRecoveryOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Dynamodb.TablePointInTimeRecoveryArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Dynamodb.TablePointInTimeRecovery.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Enabled<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Whether to enable point-in-time recovery - note that it can take up to 10 minutes to enable for new tables. If the `point_in_time_recovery` block is not provided then this defaults to `false`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Enabled<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Whether to enable point-in-time recovery - note that it can take up to 10 minutes to enable for new tables. If the `point_in_time_recovery` block is not provided then this defaults to `false`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">enabled<span class="property-indicator"></span>
        <span class="property-type">boolean</span>
    </dt>
    <dd>{{% md %}}Whether to enable point-in-time recovery - note that it can take up to 10 minutes to enable for new tables. If the `point_in_time_recovery` block is not provided then this defaults to `false`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">enabled<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Whether to enable point-in-time recovery - note that it can take up to 10 minutes to enable for new tables. If the `point_in_time_recovery` block is not provided then this defaults to `false`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### TableServerSideEncryption
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#TableServerSideEncryption">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#TableServerSideEncryption">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/dynamodb?tab=doc#TableServerSideEncryptionArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/dynamodb?tab=doc#TableServerSideEncryptionOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Dynamodb.TableServerSideEncryptionArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Dynamodb.TableServerSideEncryption.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Enabled<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Whether to enable point-in-time recovery - note that it can take up to 10 minutes to enable for new tables. If the `point_in_time_recovery` block is not provided then this defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Kms<wbr>Key<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ARN of the CMK that should be used for the AWS KMS encryption.
This attribute should only be specified if the key is different from the default DynamoDB CMK, `alias/aws/dynamodb`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Enabled<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Whether to enable point-in-time recovery - note that it can take up to 10 minutes to enable for new tables. If the `point_in_time_recovery` block is not provided then this defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Kms<wbr>Key<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The ARN of the CMK that should be used for the AWS KMS encryption.
This attribute should only be specified if the key is different from the default DynamoDB CMK, `alias/aws/dynamodb`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">enabled<span class="property-indicator"></span>
        <span class="property-type">boolean</span>
    </dt>
    <dd>{{% md %}}Whether to enable point-in-time recovery - note that it can take up to 10 minutes to enable for new tables. If the `point_in_time_recovery` block is not provided then this defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">kms<wbr>Key<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ARN of the CMK that should be used for the AWS KMS encryption.
This attribute should only be specified if the key is different from the default DynamoDB CMK, `alias/aws/dynamodb`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">enabled<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Whether to enable point-in-time recovery - note that it can take up to 10 minutes to enable for new tables. If the `point_in_time_recovery` block is not provided then this defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">kms_<wbr>key_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ARN of the CMK that should be used for the AWS KMS encryption.
This attribute should only be specified if the key is different from the default DynamoDB CMK, `alias/aws/dynamodb`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### TableTtl
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#TableTtl">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#TableTtl">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/dynamodb?tab=doc#TableTtlArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/dynamodb?tab=doc#TableTtlOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Dynamodb.TableTtlArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Dynamodb.TableTtl.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Attribute<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the table attribute to store the TTL timestamp in.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Enabled<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Whether to enable point-in-time recovery - note that it can take up to 10 minutes to enable for new tables. If the `point_in_time_recovery` block is not provided then this defaults to `false`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Attribute<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the table attribute to store the TTL timestamp in.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Enabled<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Whether to enable point-in-time recovery - note that it can take up to 10 minutes to enable for new tables. If the `point_in_time_recovery` block is not provided then this defaults to `false`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">attribute<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the table attribute to store the TTL timestamp in.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">enabled<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Whether to enable point-in-time recovery - note that it can take up to 10 minutes to enable for new tables. If the `point_in_time_recovery` block is not provided then this defaults to `false`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">attribute<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the table attribute to store the TTL timestamp in.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">enabled<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Whether to enable point-in-time recovery - note that it can take up to 10 minutes to enable for new tables. If the `point_in_time_recovery` block is not provided then this defaults to `false`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}








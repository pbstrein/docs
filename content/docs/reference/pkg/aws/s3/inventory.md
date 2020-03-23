
---
title: "Inventory"
block_external_search_index: true
---

Provides a S3 bucket [inventory configuration](https://docs.aws.amazon.com/AmazonS3/latest/dev/storage-inventory.html) resource.

## Example Usage

### Add inventory configuration

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const testBucket = new aws.s3.Bucket("test", {});
const inventory = new aws.s3.Bucket("inventory", {});
const testInventory = new aws.s3.Inventory("test", {
    bucket: testBucket.id,
    destination: {
        bucket: {
            bucketArn: inventory.arn,
            format: "ORC",
        },
    },
    includedObjectVersions: "All",
    schedule: {
        frequency: "Daily",
    },
});
```

### Add inventory configuration with S3 bucket object prefix

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const test = new aws.s3.Bucket("test", {});
const inventory = new aws.s3.Bucket("inventory", {});
const test_prefix = new aws.s3.Inventory("test-prefix", {
    bucket: test.id,
    destination: {
        bucket: {
            bucketArn: inventory.arn,
            format: "ORC",
            prefix: "inventory",
        },
    },
    filter: {
        prefix: "documents/",
    },
    includedObjectVersions: "All",
    schedule: {
        frequency: "Daily",
    },
});
```

> This content is derived from https://github.com/terraform-providers/terraform-provider-aws/blob/master/website/docs/r/s3_bucket_inventory.html.markdown.



## Create a Inventory Resource

{{< chooser language "javascript,typescript,python,go,csharp" / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/s3/#Inventory">Inventory</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/s3/#InventoryArgs">InventoryArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">Inventory</span><span class="p">(resource_name, opts=None, </span>bucket=None<span class="p">, </span>destination=None<span class="p">, </span>enabled=None<span class="p">, </span>filter=None<span class="p">, </span>included_object_versions=None<span class="p">, </span>name=None<span class="p">, </span>optional_fields=None<span class="p">, </span>schedule=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewInventory<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/s3?tab=doc#InventoryArgs">InventoryArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/s3?tab=doc#Inventory">Inventory</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.S3.Inventory.html">Inventory</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.S3.InventoryArgs.html">InventoryArgs</a></span> <span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
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
            title="Required">Bucket<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The S3 bucket configuration where inventory results are published (documented below).
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Destination<span class="property-indicator"></span>
        <span class="property-type"><a href="#inventorydestination">Inventory<wbr>Destination<wbr>Args</a></span>
    </dt>
    <dd>{{% md %}}Contains information about where to publish the inventory results (documented below).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Enabled<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Specifies whether the inventory is enabled or disabled.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Filter<span class="property-indicator"></span>
        <span class="property-type"><a href="#inventoryfilter">Inventory<wbr>Filter<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}Specifies an inventory filter. The inventory only includes objects that meet the filter&#39;s criteria (documented below).
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Included<wbr>Object<wbr>Versions<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Object versions to include in the inventory list. Valid values: `All`, `Current`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Unique identifier of the inventory configuration for the bucket.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Optional<wbr>Fields<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}List of optional fields that are included in the inventory results.
Valid values: `Size`, `LastModifiedDate`, `StorageClass`, `ETag`, `IsMultipartUploaded`, `ReplicationStatus`, `EncryptionStatus`, `ObjectLockRetainUntilDate`, `ObjectLockMode`, `ObjectLockLegalHoldStatus`, `IntelligentTieringAccessTier`.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Schedule<span class="property-indicator"></span>
        <span class="property-type"><a href="#inventoryschedule">Inventory<wbr>Schedule<wbr>Args</a></span>
    </dt>
    <dd>{{% md %}}Specifies the schedule for generating inventory results (documented below).
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Bucket<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The S3 bucket configuration where inventory results are published (documented below).
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Destination<span class="property-indicator"></span>
        <span class="property-type"><a href="#inventorydestination">Inventory<wbr>Destination</a></span>
    </dt>
    <dd>{{% md %}}Contains information about where to publish the inventory results (documented below).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Enabled<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Specifies whether the inventory is enabled or disabled.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Filter<span class="property-indicator"></span>
        <span class="property-type"><a href="#inventoryfilter">*Inventory<wbr>Filter</a></span>
    </dt>
    <dd>{{% md %}}Specifies an inventory filter. The inventory only includes objects that meet the filter&#39;s criteria (documented below).
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Included<wbr>Object<wbr>Versions<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Object versions to include in the inventory list. Valid values: `All`, `Current`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Unique identifier of the inventory configuration for the bucket.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Optional<wbr>Fields<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}List of optional fields that are included in the inventory results.
Valid values: `Size`, `LastModifiedDate`, `StorageClass`, `ETag`, `IsMultipartUploaded`, `ReplicationStatus`, `EncryptionStatus`, `ObjectLockRetainUntilDate`, `ObjectLockMode`, `ObjectLockLegalHoldStatus`, `IntelligentTieringAccessTier`.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Schedule<span class="property-indicator"></span>
        <span class="property-type"><a href="#inventoryschedule">Inventory<wbr>Schedule</a></span>
    </dt>
    <dd>{{% md %}}Specifies the schedule for generating inventory results (documented below).
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">bucket<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The S3 bucket configuration where inventory results are published (documented below).
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">destination<span class="property-indicator"></span>
        <span class="property-type"><a href="#inventorydestination">Inventory<wbr>Destination</a></span>
    </dt>
    <dd>{{% md %}}Contains information about where to publish the inventory results (documented below).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">enabled<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Specifies whether the inventory is enabled or disabled.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">filter<span class="property-indicator"></span>
        <span class="property-type"><a href="#inventoryfilter">Inventory<wbr>Filter?</a></span>
    </dt>
    <dd>{{% md %}}Specifies an inventory filter. The inventory only includes objects that meet the filter&#39;s criteria (documented below).
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">included<wbr>Object<wbr>Versions<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Object versions to include in the inventory list. Valid values: `All`, `Current`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Unique identifier of the inventory configuration for the bucket.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">optional<wbr>Fields<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}List of optional fields that are included in the inventory results.
Valid values: `Size`, `LastModifiedDate`, `StorageClass`, `ETag`, `IsMultipartUploaded`, `ReplicationStatus`, `EncryptionStatus`, `ObjectLockRetainUntilDate`, `ObjectLockMode`, `ObjectLockLegalHoldStatus`, `IntelligentTieringAccessTier`.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">schedule<span class="property-indicator"></span>
        <span class="property-type"><a href="#inventoryschedule">Inventory<wbr>Schedule</a></span>
    </dt>
    <dd>{{% md %}}Specifies the schedule for generating inventory results (documented below).
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">bucket<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The S3 bucket configuration where inventory results are published (documented below).
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">destination<span class="property-indicator"></span>
        <span class="property-type"><a href="#inventorydestination">Dict[Inventory<wbr>Destination]</a></span>
    </dt>
    <dd>{{% md %}}Contains information about where to publish the inventory results (documented below).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">enabled<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Specifies whether the inventory is enabled or disabled.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">filter<span class="property-indicator"></span>
        <span class="property-type"><a href="#inventoryfilter">Dict[Inventory<wbr>Filter]</a></span>
    </dt>
    <dd>{{% md %}}Specifies an inventory filter. The inventory only includes objects that meet the filter&#39;s criteria (documented below).
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">included_<wbr>object_<wbr>versions<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Object versions to include in the inventory list. Valid values: `All`, `Current`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Unique identifier of the inventory configuration for the bucket.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">optional_<wbr>fields<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}List of optional fields that are included in the inventory results.
Valid values: `Size`, `LastModifiedDate`, `StorageClass`, `ETag`, `IsMultipartUploaded`, `ReplicationStatus`, `EncryptionStatus`, `ObjectLockRetainUntilDate`, `ObjectLockMode`, `ObjectLockLegalHoldStatus`, `IntelligentTieringAccessTier`.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">schedule<span class="property-indicator"></span>
        <span class="property-type"><a href="#inventoryschedule">Dict[Inventory<wbr>Schedule]</a></span>
    </dt>
    <dd>{{% md %}}Specifies the schedule for generating inventory results (documented below).
{{% /md %}}</dd>

</dl>
{{% /choosable %}}




## Inventory Output Properties

The following output properties are available:




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Bucket<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The S3 bucket configuration where inventory results are published (documented below).
{{% /md %}}</dd>

    <dt class="property-"
            title="">Destination<span class="property-indicator"></span>
        <span class="property-type"><a href="#inventorydestination">Inventory<wbr>Destination</a></span>
    </dt>
    <dd>{{% md %}}Contains information about where to publish the inventory results (documented below).
{{% /md %}}</dd>

    <dt class="property-"
            title="">Enabled<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Specifies whether the inventory is enabled or disabled.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Filter<span class="property-indicator"></span>
        <span class="property-type"><a href="#inventoryfilter">Inventory<wbr>Filter?</a></span>
    </dt>
    <dd>{{% md %}}Specifies an inventory filter. The inventory only includes objects that meet the filter&#39;s criteria (documented below).
{{% /md %}}</dd>

    <dt class="property-"
            title="">Included<wbr>Object<wbr>Versions<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Object versions to include in the inventory list. Valid values: `All`, `Current`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Unique identifier of the inventory configuration for the bucket.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Optional<wbr>Fields<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}List of optional fields that are included in the inventory results.
Valid values: `Size`, `LastModifiedDate`, `StorageClass`, `ETag`, `IsMultipartUploaded`, `ReplicationStatus`, `EncryptionStatus`, `ObjectLockRetainUntilDate`, `ObjectLockMode`, `ObjectLockLegalHoldStatus`, `IntelligentTieringAccessTier`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Schedule<span class="property-indicator"></span>
        <span class="property-type"><a href="#inventoryschedule">Inventory<wbr>Schedule</a></span>
    </dt>
    <dd>{{% md %}}Specifies the schedule for generating inventory results (documented below).
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Bucket<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The S3 bucket configuration where inventory results are published (documented below).
{{% /md %}}</dd>

    <dt class="property-"
            title="">Destination<span class="property-indicator"></span>
        <span class="property-type"><a href="#inventorydestination">Inventory<wbr>Destination</a></span>
    </dt>
    <dd>{{% md %}}Contains information about where to publish the inventory results (documented below).
{{% /md %}}</dd>

    <dt class="property-"
            title="">Enabled<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Specifies whether the inventory is enabled or disabled.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Filter<span class="property-indicator"></span>
        <span class="property-type"><a href="#inventoryfilter">*Inventory<wbr>Filter</a></span>
    </dt>
    <dd>{{% md %}}Specifies an inventory filter. The inventory only includes objects that meet the filter&#39;s criteria (documented below).
{{% /md %}}</dd>

    <dt class="property-"
            title="">Included<wbr>Object<wbr>Versions<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Object versions to include in the inventory list. Valid values: `All`, `Current`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Unique identifier of the inventory configuration for the bucket.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Optional<wbr>Fields<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}List of optional fields that are included in the inventory results.
Valid values: `Size`, `LastModifiedDate`, `StorageClass`, `ETag`, `IsMultipartUploaded`, `ReplicationStatus`, `EncryptionStatus`, `ObjectLockRetainUntilDate`, `ObjectLockMode`, `ObjectLockLegalHoldStatus`, `IntelligentTieringAccessTier`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Schedule<span class="property-indicator"></span>
        <span class="property-type"><a href="#inventoryschedule">Inventory<wbr>Schedule</a></span>
    </dt>
    <dd>{{% md %}}Specifies the schedule for generating inventory results (documented below).
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">bucket<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The S3 bucket configuration where inventory results are published (documented below).
{{% /md %}}</dd>

    <dt class="property-"
            title="">destination<span class="property-indicator"></span>
        <span class="property-type"><a href="#inventorydestination">Inventory<wbr>Destination</a></span>
    </dt>
    <dd>{{% md %}}Contains information about where to publish the inventory results (documented below).
{{% /md %}}</dd>

    <dt class="property-"
            title="">enabled<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Specifies whether the inventory is enabled or disabled.
{{% /md %}}</dd>

    <dt class="property-"
            title="">filter<span class="property-indicator"></span>
        <span class="property-type"><a href="#inventoryfilter">Inventory<wbr>Filter?</a></span>
    </dt>
    <dd>{{% md %}}Specifies an inventory filter. The inventory only includes objects that meet the filter&#39;s criteria (documented below).
{{% /md %}}</dd>

    <dt class="property-"
            title="">included<wbr>Object<wbr>Versions<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Object versions to include in the inventory list. Valid values: `All`, `Current`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Unique identifier of the inventory configuration for the bucket.
{{% /md %}}</dd>

    <dt class="property-"
            title="">optional<wbr>Fields<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}List of optional fields that are included in the inventory results.
Valid values: `Size`, `LastModifiedDate`, `StorageClass`, `ETag`, `IsMultipartUploaded`, `ReplicationStatus`, `EncryptionStatus`, `ObjectLockRetainUntilDate`, `ObjectLockMode`, `ObjectLockLegalHoldStatus`, `IntelligentTieringAccessTier`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">schedule<span class="property-indicator"></span>
        <span class="property-type"><a href="#inventoryschedule">Inventory<wbr>Schedule</a></span>
    </dt>
    <dd>{{% md %}}Specifies the schedule for generating inventory results (documented below).
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">bucket<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The S3 bucket configuration where inventory results are published (documented below).
{{% /md %}}</dd>

    <dt class="property-"
            title="">destination<span class="property-indicator"></span>
        <span class="property-type"><a href="#inventorydestination">Dict[Inventory<wbr>Destination]</a></span>
    </dt>
    <dd>{{% md %}}Contains information about where to publish the inventory results (documented below).
{{% /md %}}</dd>

    <dt class="property-"
            title="">enabled<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Specifies whether the inventory is enabled or disabled.
{{% /md %}}</dd>

    <dt class="property-"
            title="">filter<span class="property-indicator"></span>
        <span class="property-type"><a href="#inventoryfilter">Dict[Inventory<wbr>Filter]</a></span>
    </dt>
    <dd>{{% md %}}Specifies an inventory filter. The inventory only includes objects that meet the filter&#39;s criteria (documented below).
{{% /md %}}</dd>

    <dt class="property-"
            title="">included_<wbr>object_<wbr>versions<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Object versions to include in the inventory list. Valid values: `All`, `Current`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Unique identifier of the inventory configuration for the bucket.
{{% /md %}}</dd>

    <dt class="property-"
            title="">optional_<wbr>fields<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}List of optional fields that are included in the inventory results.
Valid values: `Size`, `LastModifiedDate`, `StorageClass`, `ETag`, `IsMultipartUploaded`, `ReplicationStatus`, `EncryptionStatus`, `ObjectLockRetainUntilDate`, `ObjectLockMode`, `ObjectLockLegalHoldStatus`, `IntelligentTieringAccessTier`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">schedule<span class="property-indicator"></span>
        <span class="property-type"><a href="#inventoryschedule">Dict[Inventory<wbr>Schedule]</a></span>
    </dt>
    <dd>{{% md %}}Specifies the schedule for generating inventory results (documented below).
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





## Look up an Existing Inventory Resource

{{< chooser language "javascript,typescript,python,go,csharp  " / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">pulumi.Input&lt;pulumi.ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/s3/#InventoryState">InventoryState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/s3/#Inventory">Inventory</a></span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>bucket=None<span class="p">, </span>destination=None<span class="p">, </span>enabled=None<span class="p">, </span>filter=None<span class="p">, </span>included_object_versions=None<span class="p">, </span>name=None<span class="p">, </span>optional_fields=None<span class="p">, </span>schedule=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetInventory<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">pulumi.IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/s3?tab=doc#InventoryState">InventoryState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/s3?tab=doc#Inventory">Inventory</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.S3.Inventory.html">Inventory</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Pulumi.Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.S3.InventoryState.html">InventoryState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
{{% /choosable %}}

Get an existing Inventory resource's state with the given name, ID, and optional extra properties used to qualify the lookup.

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
            title="Optional">Bucket<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The S3 bucket configuration where inventory results are published (documented below).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Destination<span class="property-indicator"></span>
        <span class="property-type"><a href="#inventorydestination">Inventory<wbr>Destination<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}Contains information about where to publish the inventory results (documented below).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Enabled<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Specifies whether the inventory is enabled or disabled.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Filter<span class="property-indicator"></span>
        <span class="property-type"><a href="#inventoryfilter">Inventory<wbr>Filter<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}Specifies an inventory filter. The inventory only includes objects that meet the filter&#39;s criteria (documented below).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Included<wbr>Object<wbr>Versions<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Object versions to include in the inventory list. Valid values: `All`, `Current`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Unique identifier of the inventory configuration for the bucket.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Optional<wbr>Fields<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}List of optional fields that are included in the inventory results.
Valid values: `Size`, `LastModifiedDate`, `StorageClass`, `ETag`, `IsMultipartUploaded`, `ReplicationStatus`, `EncryptionStatus`, `ObjectLockRetainUntilDate`, `ObjectLockMode`, `ObjectLockLegalHoldStatus`, `IntelligentTieringAccessTier`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Schedule<span class="property-indicator"></span>
        <span class="property-type"><a href="#inventoryschedule">Inventory<wbr>Schedule<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}Specifies the schedule for generating inventory results (documented below).
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Bucket<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The S3 bucket configuration where inventory results are published (documented below).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Destination<span class="property-indicator"></span>
        <span class="property-type"><a href="#inventorydestination">*Inventory<wbr>Destination</a></span>
    </dt>
    <dd>{{% md %}}Contains information about where to publish the inventory results (documented below).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Enabled<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Specifies whether the inventory is enabled or disabled.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Filter<span class="property-indicator"></span>
        <span class="property-type"><a href="#inventoryfilter">*Inventory<wbr>Filter</a></span>
    </dt>
    <dd>{{% md %}}Specifies an inventory filter. The inventory only includes objects that meet the filter&#39;s criteria (documented below).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Included<wbr>Object<wbr>Versions<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Object versions to include in the inventory list. Valid values: `All`, `Current`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Unique identifier of the inventory configuration for the bucket.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Optional<wbr>Fields<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}List of optional fields that are included in the inventory results.
Valid values: `Size`, `LastModifiedDate`, `StorageClass`, `ETag`, `IsMultipartUploaded`, `ReplicationStatus`, `EncryptionStatus`, `ObjectLockRetainUntilDate`, `ObjectLockMode`, `ObjectLockLegalHoldStatus`, `IntelligentTieringAccessTier`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Schedule<span class="property-indicator"></span>
        <span class="property-type"><a href="#inventoryschedule">*Inventory<wbr>Schedule</a></span>
    </dt>
    <dd>{{% md %}}Specifies the schedule for generating inventory results (documented below).
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">bucket<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The S3 bucket configuration where inventory results are published (documented below).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">destination<span class="property-indicator"></span>
        <span class="property-type"><a href="#inventorydestination">Inventory<wbr>Destination?</a></span>
    </dt>
    <dd>{{% md %}}Contains information about where to publish the inventory results (documented below).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">enabled<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Specifies whether the inventory is enabled or disabled.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">filter<span class="property-indicator"></span>
        <span class="property-type"><a href="#inventoryfilter">Inventory<wbr>Filter?</a></span>
    </dt>
    <dd>{{% md %}}Specifies an inventory filter. The inventory only includes objects that meet the filter&#39;s criteria (documented below).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">included<wbr>Object<wbr>Versions<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Object versions to include in the inventory list. Valid values: `All`, `Current`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Unique identifier of the inventory configuration for the bucket.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">optional<wbr>Fields<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}List of optional fields that are included in the inventory results.
Valid values: `Size`, `LastModifiedDate`, `StorageClass`, `ETag`, `IsMultipartUploaded`, `ReplicationStatus`, `EncryptionStatus`, `ObjectLockRetainUntilDate`, `ObjectLockMode`, `ObjectLockLegalHoldStatus`, `IntelligentTieringAccessTier`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">schedule<span class="property-indicator"></span>
        <span class="property-type"><a href="#inventoryschedule">Inventory<wbr>Schedule?</a></span>
    </dt>
    <dd>{{% md %}}Specifies the schedule for generating inventory results (documented below).
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">bucket<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The S3 bucket configuration where inventory results are published (documented below).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">destination<span class="property-indicator"></span>
        <span class="property-type"><a href="#inventorydestination">Dict[Inventory<wbr>Destination]</a></span>
    </dt>
    <dd>{{% md %}}Contains information about where to publish the inventory results (documented below).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">enabled<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Specifies whether the inventory is enabled or disabled.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">filter<span class="property-indicator"></span>
        <span class="property-type"><a href="#inventoryfilter">Dict[Inventory<wbr>Filter]</a></span>
    </dt>
    <dd>{{% md %}}Specifies an inventory filter. The inventory only includes objects that meet the filter&#39;s criteria (documented below).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">included_<wbr>object_<wbr>versions<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Object versions to include in the inventory list. Valid values: `All`, `Current`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Unique identifier of the inventory configuration for the bucket.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">optional_<wbr>fields<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}List of optional fields that are included in the inventory results.
Valid values: `Size`, `LastModifiedDate`, `StorageClass`, `ETag`, `IsMultipartUploaded`, `ReplicationStatus`, `EncryptionStatus`, `ObjectLockRetainUntilDate`, `ObjectLockMode`, `ObjectLockLegalHoldStatus`, `IntelligentTieringAccessTier`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">schedule<span class="property-indicator"></span>
        <span class="property-type"><a href="#inventoryschedule">Dict[Inventory<wbr>Schedule]</a></span>
    </dt>
    <dd>{{% md %}}Specifies the schedule for generating inventory results (documented below).
{{% /md %}}</dd>

</dl>
{{% /choosable %}}







## Supporting Types

#### InventoryDestination
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#InventoryDestination">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#InventoryDestination">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/s3?tab=doc#InventoryDestinationArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/s3?tab=doc#InventoryDestinationOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.S3.InventoryDestinationArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.S3.InventoryDestination.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Bucket<span class="property-indicator"></span>
        <span class="property-type"><a href="#inventorydestinationbucket">Inventory<wbr>Destination<wbr>Bucket<wbr>Args</a></span>
    </dt>
    <dd>{{% md %}}The S3 bucket configuration where inventory results are published (documented below).
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Bucket<span class="property-indicator"></span>
        <span class="property-type"><a href="#inventorydestinationbucket">Inventory<wbr>Destination<wbr>Bucket</a></span>
    </dt>
    <dd>{{% md %}}The S3 bucket configuration where inventory results are published (documented below).
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">bucket<span class="property-indicator"></span>
        <span class="property-type"><a href="#inventorydestinationbucket">Inventory<wbr>Destination<wbr>Bucket</a></span>
    </dt>
    <dd>{{% md %}}The S3 bucket configuration where inventory results are published (documented below).
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">bucket<span class="property-indicator"></span>
        <span class="property-type"><a href="#inventorydestinationbucket">Dict[Inventory<wbr>Destination<wbr>Bucket]</a></span>
    </dt>
    <dd>{{% md %}}The S3 bucket configuration where inventory results are published (documented below).
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### InventoryDestinationBucket
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#InventoryDestinationBucket">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#InventoryDestinationBucket">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/s3?tab=doc#InventoryDestinationBucketArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/s3?tab=doc#InventoryDestinationBucketOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.S3.InventoryDestinationBucketArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.S3.InventoryDestinationBucket.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Account<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ID of the account that owns the destination bucket. Recommended to be set to prevent problems if the destination bucket ownership changes.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Bucket<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Amazon S3 bucket ARN of the destination.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Encryption<span class="property-indicator"></span>
        <span class="property-type"><a href="#inventorydestinationbucketencryption">Inventory<wbr>Destination<wbr>Bucket<wbr>Encryption<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}Contains the type of server-side encryption to use to encrypt the inventory (documented below).
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Format<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Specifies the output format of the inventory results. Can be `CSV`, [`ORC`](https://orc.apache.org/) or [`Parquet`](https://parquet.apache.org/).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Prefix<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The prefix that is prepended to all inventory results.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Account<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The ID of the account that owns the destination bucket. Recommended to be set to prevent problems if the destination bucket ownership changes.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Bucket<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Amazon S3 bucket ARN of the destination.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Encryption<span class="property-indicator"></span>
        <span class="property-type"><a href="#inventorydestinationbucketencryption">*Inventory<wbr>Destination<wbr>Bucket<wbr>Encryption</a></span>
    </dt>
    <dd>{{% md %}}Contains the type of server-side encryption to use to encrypt the inventory (documented below).
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Format<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Specifies the output format of the inventory results. Can be `CSV`, [`ORC`](https://orc.apache.org/) or [`Parquet`](https://parquet.apache.org/).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Prefix<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The prefix that is prepended to all inventory results.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">account<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ID of the account that owns the destination bucket. Recommended to be set to prevent problems if the destination bucket ownership changes.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">bucket<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Amazon S3 bucket ARN of the destination.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">encryption<span class="property-indicator"></span>
        <span class="property-type"><a href="#inventorydestinationbucketencryption">Inventory<wbr>Destination<wbr>Bucket<wbr>Encryption?</a></span>
    </dt>
    <dd>{{% md %}}Contains the type of server-side encryption to use to encrypt the inventory (documented below).
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">format<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Specifies the output format of the inventory results. Can be `CSV`, [`ORC`](https://orc.apache.org/) or [`Parquet`](https://parquet.apache.org/).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">prefix<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The prefix that is prepended to all inventory results.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">account_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ID of the account that owns the destination bucket. Recommended to be set to prevent problems if the destination bucket ownership changes.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">bucket<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The Amazon S3 bucket ARN of the destination.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">encryption<span class="property-indicator"></span>
        <span class="property-type"><a href="#inventorydestinationbucketencryption">Dict[Inventory<wbr>Destination<wbr>Bucket<wbr>Encryption]</a></span>
    </dt>
    <dd>{{% md %}}Contains the type of server-side encryption to use to encrypt the inventory (documented below).
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">format<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Specifies the output format of the inventory results. Can be `CSV`, [`ORC`](https://orc.apache.org/) or [`Parquet`](https://parquet.apache.org/).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">prefix<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The prefix that is prepended to all inventory results.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### InventoryDestinationBucketEncryption
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#InventoryDestinationBucketEncryption">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#InventoryDestinationBucketEncryption">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/s3?tab=doc#InventoryDestinationBucketEncryptionArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/s3?tab=doc#InventoryDestinationBucketEncryptionOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.S3.InventoryDestinationBucketEncryptionArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.S3.InventoryDestinationBucketEncryption.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Sse<wbr>Kms<span class="property-indicator"></span>
        <span class="property-type"><a href="#inventorydestinationbucketencryptionssekms">Inventory<wbr>Destination<wbr>Bucket<wbr>Encryption<wbr>Sse<wbr>Kms<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}Specifies to use server-side encryption with AWS KMS-managed keys to encrypt the inventory file (documented below).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Sse<wbr>S3<span class="property-indicator"></span>
        <span class="property-type"><a href="#inventorydestinationbucketencryptionsses3">Inventory<wbr>Destination<wbr>Bucket<wbr>Encryption<wbr>Sse<wbr>S3Args?</a></span>
    </dt>
    <dd>{{% md %}}Specifies to use server-side encryption with Amazon S3-managed keys (SSE-S3) to encrypt the inventory file.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Sse<wbr>Kms<span class="property-indicator"></span>
        <span class="property-type"><a href="#inventorydestinationbucketencryptionssekms">*Inventory<wbr>Destination<wbr>Bucket<wbr>Encryption<wbr>Sse<wbr>Kms</a></span>
    </dt>
    <dd>{{% md %}}Specifies to use server-side encryption with AWS KMS-managed keys to encrypt the inventory file (documented below).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Sse<wbr>S3<span class="property-indicator"></span>
        <span class="property-type"><a href="#inventorydestinationbucketencryptionsses3">*Inventory<wbr>Destination<wbr>Bucket<wbr>Encryption<wbr>Sse<wbr>S3</a></span>
    </dt>
    <dd>{{% md %}}Specifies to use server-side encryption with Amazon S3-managed keys (SSE-S3) to encrypt the inventory file.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">sse<wbr>Kms<span class="property-indicator"></span>
        <span class="property-type"><a href="#inventorydestinationbucketencryptionssekms">Inventory<wbr>Destination<wbr>Bucket<wbr>Encryption<wbr>Sse<wbr>Kms?</a></span>
    </dt>
    <dd>{{% md %}}Specifies to use server-side encryption with AWS KMS-managed keys to encrypt the inventory file (documented below).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">sse<wbr>S3<span class="property-indicator"></span>
        <span class="property-type"><a href="#inventorydestinationbucketencryptionsses3">Inventory<wbr>Destination<wbr>Bucket<wbr>Encryption<wbr>Sse<wbr>S3?</a></span>
    </dt>
    <dd>{{% md %}}Specifies to use server-side encryption with Amazon S3-managed keys (SSE-S3) to encrypt the inventory file.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">sse<wbr>Kms<span class="property-indicator"></span>
        <span class="property-type"><a href="#inventorydestinationbucketencryptionssekms">Dict[Inventory<wbr>Destination<wbr>Bucket<wbr>Encryption<wbr>Sse<wbr>Kms]</a></span>
    </dt>
    <dd>{{% md %}}Specifies to use server-side encryption with AWS KMS-managed keys to encrypt the inventory file (documented below).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">sse<wbr>S3<span class="property-indicator"></span>
        <span class="property-type"><a href="#inventorydestinationbucketencryptionsses3">Dict[Inventory<wbr>Destination<wbr>Bucket<wbr>Encryption<wbr>Sse<wbr>S3]</a></span>
    </dt>
    <dd>{{% md %}}Specifies to use server-side encryption with Amazon S3-managed keys (SSE-S3) to encrypt the inventory file.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### InventoryDestinationBucketEncryptionSseKms
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#InventoryDestinationBucketEncryptionSseKms">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#InventoryDestinationBucketEncryptionSseKms">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/s3?tab=doc#InventoryDestinationBucketEncryptionSseKmsArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/s3?tab=doc#InventoryDestinationBucketEncryptionSseKmsOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.S3.InventoryDestinationBucketEncryptionSseKmsArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.S3.InventoryDestinationBucketEncryptionSseKms.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Key<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of the KMS customer master key (CMK) used to encrypt the inventory file.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Key<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of the KMS customer master key (CMK) used to encrypt the inventory file.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">key<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of the KMS customer master key (CMK) used to encrypt the inventory file.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">key_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ARN of the KMS customer master key (CMK) used to encrypt the inventory file.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### InventoryFilter
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#InventoryFilter">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#InventoryFilter">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/s3?tab=doc#InventoryFilterArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/s3?tab=doc#InventoryFilterOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.S3.InventoryFilterArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.S3.InventoryFilter.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Prefix<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The prefix that is prepended to all inventory results.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Prefix<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The prefix that is prepended to all inventory results.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">prefix<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The prefix that is prepended to all inventory results.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">prefix<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The prefix that is prepended to all inventory results.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### InventorySchedule
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#InventorySchedule">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#InventorySchedule">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/s3?tab=doc#InventoryScheduleArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/s3?tab=doc#InventoryScheduleOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.S3.InventoryScheduleArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.S3.InventorySchedule.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Frequency<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Specifies how frequently inventory results are produced. Valid values: `Daily`, `Weekly`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Frequency<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Specifies how frequently inventory results are produced. Valid values: `Daily`, `Weekly`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">frequency<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Specifies how frequently inventory results are produced. Valid values: `Daily`, `Weekly`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">frequency<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Specifies how frequently inventory results are produced. Valid values: `Daily`, `Weekly`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}








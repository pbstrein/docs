
---
title: "FileSystem"
block_external_search_index: true
---

Provides an Elastic File System (EFS) resource.

## Example Usage

### EFS File System w/ tags

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const foo = new aws.efs.FileSystem("foo", {
    tags: {
        Name: "MyProduct",
    },
});
```

### Using lifecycle policy

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const fooWithLifecylePolicy = new aws.efs.FileSystem("foo_with_lifecyle_policy", {
    lifecyclePolicy: {
        transitionToIa: "AFTER_30_DAYS",
    },
});
```

> This content is derived from https://github.com/terraform-providers/terraform-provider-aws/blob/master/website/docs/r/efs_file_system.html.markdown.



## Create a FileSystem Resource

{{< chooser language "javascript,typescript,python,go,csharp" / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/efs/#FileSystem">FileSystem</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/efs/#FileSystemArgs">FileSystemArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">FileSystem</span><span class="p">(resource_name, opts=None, </span>creation_token=None<span class="p">, </span>encrypted=None<span class="p">, </span>kms_key_id=None<span class="p">, </span>lifecycle_policy=None<span class="p">, </span>performance_mode=None<span class="p">, </span>provisioned_throughput_in_mibps=None<span class="p">, </span>tags=None<span class="p">, </span>throughput_mode=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewFileSystem<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/efs?tab=doc#FileSystemArgs">FileSystemArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/efs?tab=doc#FileSystem">FileSystem</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Efs.FileSystem.html">FileSystem</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Efs.FileSystemArgs.html">FileSystemArgs</a></span>? <span class="nx">args = null<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
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
            title="Optional">Creation<wbr>Token<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A unique name (a maximum of 64 characters are allowed)
used as reference when creating the Elastic File System to ensure idempotent file
system creation. By default generated by this provider. See [Elastic File System]
(http://docs.aws.amazon.com/efs/latest/ug/) user guide for more information.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Encrypted<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}If true, the disk will be encrypted.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Kms<wbr>Key<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ARN for the KMS encryption key. When specifying kms_key_id, encrypted needs to be set to true.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Lifecycle<wbr>Policy<span class="property-indicator"></span>
        <span class="property-type"><a href="#filesystemlifecyclepolicy">File<wbr>System<wbr>Lifecycle<wbr>Policy<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}A file system [lifecycle policy](https://docs.aws.amazon.com/efs/latest/ug/API_LifecyclePolicy.html) object (documented below).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Performance<wbr>Mode<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The file system performance mode. Can be either `&#34;generalPurpose&#34;` or `&#34;maxIO&#34;` (Default: `&#34;generalPurpose&#34;`).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Provisioned<wbr>Throughput<wbr>In<wbr>Mibps<span class="property-indicator"></span>
        <span class="property-type">double?</span>
    </dt>
    <dd>{{% md %}}The throughput, measured in MiB/s, that you want to provision for the file system. Only applicable with `throughput_mode` set to `provisioned`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the file system.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Throughput<wbr>Mode<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Throughput mode for the file system. Defaults to `bursting`. Valid values: `bursting`, `provisioned`. When using `provisioned`, also set `provisioned_throughput_in_mibps`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Creation<wbr>Token<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}A unique name (a maximum of 64 characters are allowed)
used as reference when creating the Elastic File System to ensure idempotent file
system creation. By default generated by this provider. See [Elastic File System]
(http://docs.aws.amazon.com/efs/latest/ug/) user guide for more information.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Encrypted<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}If true, the disk will be encrypted.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Kms<wbr>Key<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The ARN for the KMS encryption key. When specifying kms_key_id, encrypted needs to be set to true.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Lifecycle<wbr>Policy<span class="property-indicator"></span>
        <span class="property-type"><a href="#filesystemlifecyclepolicy">*File<wbr>System<wbr>Lifecycle<wbr>Policy</a></span>
    </dt>
    <dd>{{% md %}}A file system [lifecycle policy](https://docs.aws.amazon.com/efs/latest/ug/API_LifecyclePolicy.html) object (documented below).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Performance<wbr>Mode<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The file system performance mode. Can be either `&#34;generalPurpose&#34;` or `&#34;maxIO&#34;` (Default: `&#34;generalPurpose&#34;`).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Provisioned<wbr>Throughput<wbr>In<wbr>Mibps<span class="property-indicator"></span>
        <span class="property-type">*float64</span>
    </dt>
    <dd>{{% md %}}The throughput, measured in MiB/s, that you want to provision for the file system. Only applicable with `throughput_mode` set to `provisioned`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the file system.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Throughput<wbr>Mode<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Throughput mode for the file system. Defaults to `bursting`. Valid values: `bursting`, `provisioned`. When using `provisioned`, also set `provisioned_throughput_in_mibps`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">creation<wbr>Token<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A unique name (a maximum of 64 characters are allowed)
used as reference when creating the Elastic File System to ensure idempotent file
system creation. By default generated by this provider. See [Elastic File System]
(http://docs.aws.amazon.com/efs/latest/ug/) user guide for more information.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">encrypted<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}If true, the disk will be encrypted.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">kms<wbr>Key<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ARN for the KMS encryption key. When specifying kms_key_id, encrypted needs to be set to true.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">lifecycle<wbr>Policy<span class="property-indicator"></span>
        <span class="property-type"><a href="#filesystemlifecyclepolicy">File<wbr>System<wbr>Lifecycle<wbr>Policy?</a></span>
    </dt>
    <dd>{{% md %}}A file system [lifecycle policy](https://docs.aws.amazon.com/efs/latest/ug/API_LifecyclePolicy.html) object (documented below).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">performance<wbr>Mode<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The file system performance mode. Can be either `&#34;generalPurpose&#34;` or `&#34;maxIO&#34;` (Default: `&#34;generalPurpose&#34;`).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">provisioned<wbr>Throughput<wbr>In<wbr>Mibps<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The throughput, measured in MiB/s, that you want to provision for the file system. Only applicable with `throughput_mode` set to `provisioned`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the file system.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">throughput<wbr>Mode<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Throughput mode for the file system. Defaults to `bursting`. Valid values: `bursting`, `provisioned`. When using `provisioned`, also set `provisioned_throughput_in_mibps`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">creation_<wbr>token<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A unique name (a maximum of 64 characters are allowed)
used as reference when creating the Elastic File System to ensure idempotent file
system creation. By default generated by this provider. See [Elastic File System]
(http://docs.aws.amazon.com/efs/latest/ug/) user guide for more information.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">encrypted<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}If true, the disk will be encrypted.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">kms_<wbr>key_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ARN for the KMS encryption key. When specifying kms_key_id, encrypted needs to be set to true.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">lifecycle_<wbr>policy<span class="property-indicator"></span>
        <span class="property-type"><a href="#filesystemlifecyclepolicy">Dict[File<wbr>System<wbr>Lifecycle<wbr>Policy]</a></span>
    </dt>
    <dd>{{% md %}}A file system [lifecycle policy](https://docs.aws.amazon.com/efs/latest/ug/API_LifecyclePolicy.html) object (documented below).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">performance_<wbr>mode<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The file system performance mode. Can be either `&#34;generalPurpose&#34;` or `&#34;maxIO&#34;` (Default: `&#34;generalPurpose&#34;`).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">provisioned_<wbr>throughput_<wbr>in_<wbr>mibps<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The throughput, measured in MiB/s, that you want to provision for the file system. Only applicable with `throughput_mode` set to `provisioned`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the file system.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">throughput_<wbr>mode<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Throughput mode for the file system. Defaults to `bursting`. Valid values: `bursting`, `provisioned`. When using `provisioned`, also set `provisioned_throughput_in_mibps`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}




## FileSystem Output Properties

The following output properties are available:




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name of the file system.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Creation<wbr>Token<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}A unique name (a maximum of 64 characters are allowed)
used as reference when creating the Elastic File System to ensure idempotent file
system creation. By default generated by this provider. See [Elastic File System]
(http://docs.aws.amazon.com/efs/latest/ug/) user guide for more information.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Dns<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The DNS name for the filesystem per [documented convention](http://docs.aws.amazon.com/efs/latest/ug/mounting-fs-mount-cmd-dns-name.html).
{{% /md %}}</dd>

    <dt class="property-"
            title="">Encrypted<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}If true, the disk will be encrypted.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Kms<wbr>Key<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN for the KMS encryption key. When specifying kms_key_id, encrypted needs to be set to true.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Lifecycle<wbr>Policy<span class="property-indicator"></span>
        <span class="property-type"><a href="#filesystemlifecyclepolicy">File<wbr>System<wbr>Lifecycle<wbr>Policy?</a></span>
    </dt>
    <dd>{{% md %}}A file system [lifecycle policy](https://docs.aws.amazon.com/efs/latest/ug/API_LifecyclePolicy.html) object (documented below).
{{% /md %}}</dd>

    <dt class="property-"
            title="">Performance<wbr>Mode<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The file system performance mode. Can be either `&#34;generalPurpose&#34;` or `&#34;maxIO&#34;` (Default: `&#34;generalPurpose&#34;`).
{{% /md %}}</dd>

    <dt class="property-"
            title="">Provisioned<wbr>Throughput<wbr>In<wbr>Mibps<span class="property-indicator"></span>
        <span class="property-type">double?</span>
    </dt>
    <dd>{{% md %}}The throughput, measured in MiB/s, that you want to provision for the file system. Only applicable with `throughput_mode` set to `provisioned`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the file system.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Throughput<wbr>Mode<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Throughput mode for the file system. Defaults to `bursting`. Valid values: `bursting`, `provisioned`. When using `provisioned`, also set `provisioned_throughput_in_mibps`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name of the file system.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Creation<wbr>Token<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}A unique name (a maximum of 64 characters are allowed)
used as reference when creating the Elastic File System to ensure idempotent file
system creation. By default generated by this provider. See [Elastic File System]
(http://docs.aws.amazon.com/efs/latest/ug/) user guide for more information.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Dns<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The DNS name for the filesystem per [documented convention](http://docs.aws.amazon.com/efs/latest/ug/mounting-fs-mount-cmd-dns-name.html).
{{% /md %}}</dd>

    <dt class="property-"
            title="">Encrypted<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}If true, the disk will be encrypted.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Kms<wbr>Key<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN for the KMS encryption key. When specifying kms_key_id, encrypted needs to be set to true.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Lifecycle<wbr>Policy<span class="property-indicator"></span>
        <span class="property-type"><a href="#filesystemlifecyclepolicy">*File<wbr>System<wbr>Lifecycle<wbr>Policy</a></span>
    </dt>
    <dd>{{% md %}}A file system [lifecycle policy](https://docs.aws.amazon.com/efs/latest/ug/API_LifecyclePolicy.html) object (documented below).
{{% /md %}}</dd>

    <dt class="property-"
            title="">Performance<wbr>Mode<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The file system performance mode. Can be either `&#34;generalPurpose&#34;` or `&#34;maxIO&#34;` (Default: `&#34;generalPurpose&#34;`).
{{% /md %}}</dd>

    <dt class="property-"
            title="">Provisioned<wbr>Throughput<wbr>In<wbr>Mibps<span class="property-indicator"></span>
        <span class="property-type">*float64</span>
    </dt>
    <dd>{{% md %}}The throughput, measured in MiB/s, that you want to provision for the file system. Only applicable with `throughput_mode` set to `provisioned`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the file system.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Throughput<wbr>Mode<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Throughput mode for the file system. Defaults to `bursting`. Valid values: `bursting`, `provisioned`. When using `provisioned`, also set `provisioned_throughput_in_mibps`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name of the file system.
{{% /md %}}</dd>

    <dt class="property-"
            title="">creation<wbr>Token<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}A unique name (a maximum of 64 characters are allowed)
used as reference when creating the Elastic File System to ensure idempotent file
system creation. By default generated by this provider. See [Elastic File System]
(http://docs.aws.amazon.com/efs/latest/ug/) user guide for more information.
{{% /md %}}</dd>

    <dt class="property-"
            title="">dns<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The DNS name for the filesystem per [documented convention](http://docs.aws.amazon.com/efs/latest/ug/mounting-fs-mount-cmd-dns-name.html).
{{% /md %}}</dd>

    <dt class="property-"
            title="">encrypted<span class="property-indicator"></span>
        <span class="property-type">boolean</span>
    </dt>
    <dd>{{% md %}}If true, the disk will be encrypted.
{{% /md %}}</dd>

    <dt class="property-"
            title="">kms<wbr>Key<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN for the KMS encryption key. When specifying kms_key_id, encrypted needs to be set to true.
{{% /md %}}</dd>

    <dt class="property-"
            title="">lifecycle<wbr>Policy<span class="property-indicator"></span>
        <span class="property-type"><a href="#filesystemlifecyclepolicy">File<wbr>System<wbr>Lifecycle<wbr>Policy?</a></span>
    </dt>
    <dd>{{% md %}}A file system [lifecycle policy](https://docs.aws.amazon.com/efs/latest/ug/API_LifecyclePolicy.html) object (documented below).
{{% /md %}}</dd>

    <dt class="property-"
            title="">performance<wbr>Mode<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The file system performance mode. Can be either `&#34;generalPurpose&#34;` or `&#34;maxIO&#34;` (Default: `&#34;generalPurpose&#34;`).
{{% /md %}}</dd>

    <dt class="property-"
            title="">provisioned<wbr>Throughput<wbr>In<wbr>Mibps<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The throughput, measured in MiB/s, that you want to provision for the file system. Only applicable with `throughput_mode` set to `provisioned`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the file system.
{{% /md %}}</dd>

    <dt class="property-"
            title="">throughput<wbr>Mode<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Throughput mode for the file system. Defaults to `bursting`. Valid values: `bursting`, `provisioned`. When using `provisioned`, also set `provisioned_throughput_in_mibps`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name of the file system.
{{% /md %}}</dd>

    <dt class="property-"
            title="">creation_<wbr>token<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A unique name (a maximum of 64 characters are allowed)
used as reference when creating the Elastic File System to ensure idempotent file
system creation. By default generated by this provider. See [Elastic File System]
(http://docs.aws.amazon.com/efs/latest/ug/) user guide for more information.
{{% /md %}}</dd>

    <dt class="property-"
            title="">dns_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The DNS name for the filesystem per [documented convention](http://docs.aws.amazon.com/efs/latest/ug/mounting-fs-mount-cmd-dns-name.html).
{{% /md %}}</dd>

    <dt class="property-"
            title="">encrypted<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}If true, the disk will be encrypted.
{{% /md %}}</dd>

    <dt class="property-"
            title="">kms_<wbr>key_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ARN for the KMS encryption key. When specifying kms_key_id, encrypted needs to be set to true.
{{% /md %}}</dd>

    <dt class="property-"
            title="">lifecycle_<wbr>policy<span class="property-indicator"></span>
        <span class="property-type"><a href="#filesystemlifecyclepolicy">Dict[File<wbr>System<wbr>Lifecycle<wbr>Policy]</a></span>
    </dt>
    <dd>{{% md %}}A file system [lifecycle policy](https://docs.aws.amazon.com/efs/latest/ug/API_LifecyclePolicy.html) object (documented below).
{{% /md %}}</dd>

    <dt class="property-"
            title="">performance_<wbr>mode<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The file system performance mode. Can be either `&#34;generalPurpose&#34;` or `&#34;maxIO&#34;` (Default: `&#34;generalPurpose&#34;`).
{{% /md %}}</dd>

    <dt class="property-"
            title="">provisioned_<wbr>throughput_<wbr>in_<wbr>mibps<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The throughput, measured in MiB/s, that you want to provision for the file system. Only applicable with `throughput_mode` set to `provisioned`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the file system.
{{% /md %}}</dd>

    <dt class="property-"
            title="">throughput_<wbr>mode<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Throughput mode for the file system. Defaults to `bursting`. Valid values: `bursting`, `provisioned`. When using `provisioned`, also set `provisioned_throughput_in_mibps`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





## Look up an Existing FileSystem Resource

{{< chooser language "javascript,typescript,python,go,csharp  " / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">pulumi.Input&lt;pulumi.ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/efs/#FileSystemState">FileSystemState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/efs/#FileSystem">FileSystem</a></span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>arn=None<span class="p">, </span>creation_token=None<span class="p">, </span>dns_name=None<span class="p">, </span>encrypted=None<span class="p">, </span>kms_key_id=None<span class="p">, </span>lifecycle_policy=None<span class="p">, </span>performance_mode=None<span class="p">, </span>provisioned_throughput_in_mibps=None<span class="p">, </span>tags=None<span class="p">, </span>throughput_mode=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetFileSystem<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">pulumi.IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/efs?tab=doc#FileSystemState">FileSystemState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/efs?tab=doc#FileSystem">FileSystem</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Efs.FileSystem.html">FileSystem</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Pulumi.Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Efs.FileSystemState.html">FileSystemState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
{{% /choosable %}}

Get an existing FileSystem resource's state with the given name, ID, and optional extra properties used to qualify the lookup.

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
    <dd>{{% md %}}Amazon Resource Name of the file system.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Creation<wbr>Token<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A unique name (a maximum of 64 characters are allowed)
used as reference when creating the Elastic File System to ensure idempotent file
system creation. By default generated by this provider. See [Elastic File System]
(http://docs.aws.amazon.com/efs/latest/ug/) user guide for more information.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Dns<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The DNS name for the filesystem per [documented convention](http://docs.aws.amazon.com/efs/latest/ug/mounting-fs-mount-cmd-dns-name.html).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Encrypted<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}If true, the disk will be encrypted.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Kms<wbr>Key<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ARN for the KMS encryption key. When specifying kms_key_id, encrypted needs to be set to true.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Lifecycle<wbr>Policy<span class="property-indicator"></span>
        <span class="property-type"><a href="#filesystemlifecyclepolicy">File<wbr>System<wbr>Lifecycle<wbr>Policy<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}A file system [lifecycle policy](https://docs.aws.amazon.com/efs/latest/ug/API_LifecyclePolicy.html) object (documented below).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Performance<wbr>Mode<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The file system performance mode. Can be either `&#34;generalPurpose&#34;` or `&#34;maxIO&#34;` (Default: `&#34;generalPurpose&#34;`).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Provisioned<wbr>Throughput<wbr>In<wbr>Mibps<span class="property-indicator"></span>
        <span class="property-type">double?</span>
    </dt>
    <dd>{{% md %}}The throughput, measured in MiB/s, that you want to provision for the file system. Only applicable with `throughput_mode` set to `provisioned`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the file system.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Throughput<wbr>Mode<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Throughput mode for the file system. Defaults to `bursting`. Valid values: `bursting`, `provisioned`. When using `provisioned`, also set `provisioned_throughput_in_mibps`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name of the file system.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Creation<wbr>Token<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}A unique name (a maximum of 64 characters are allowed)
used as reference when creating the Elastic File System to ensure idempotent file
system creation. By default generated by this provider. See [Elastic File System]
(http://docs.aws.amazon.com/efs/latest/ug/) user guide for more information.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Dns<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The DNS name for the filesystem per [documented convention](http://docs.aws.amazon.com/efs/latest/ug/mounting-fs-mount-cmd-dns-name.html).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Encrypted<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}If true, the disk will be encrypted.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Kms<wbr>Key<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The ARN for the KMS encryption key. When specifying kms_key_id, encrypted needs to be set to true.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Lifecycle<wbr>Policy<span class="property-indicator"></span>
        <span class="property-type"><a href="#filesystemlifecyclepolicy">*File<wbr>System<wbr>Lifecycle<wbr>Policy</a></span>
    </dt>
    <dd>{{% md %}}A file system [lifecycle policy](https://docs.aws.amazon.com/efs/latest/ug/API_LifecyclePolicy.html) object (documented below).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Performance<wbr>Mode<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The file system performance mode. Can be either `&#34;generalPurpose&#34;` or `&#34;maxIO&#34;` (Default: `&#34;generalPurpose&#34;`).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Provisioned<wbr>Throughput<wbr>In<wbr>Mibps<span class="property-indicator"></span>
        <span class="property-type">*float64</span>
    </dt>
    <dd>{{% md %}}The throughput, measured in MiB/s, that you want to provision for the file system. Only applicable with `throughput_mode` set to `provisioned`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the file system.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Throughput<wbr>Mode<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Throughput mode for the file system. Defaults to `bursting`. Valid values: `bursting`, `provisioned`. When using `provisioned`, also set `provisioned_throughput_in_mibps`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name of the file system.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">creation<wbr>Token<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A unique name (a maximum of 64 characters are allowed)
used as reference when creating the Elastic File System to ensure idempotent file
system creation. By default generated by this provider. See [Elastic File System]
(http://docs.aws.amazon.com/efs/latest/ug/) user guide for more information.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">dns<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The DNS name for the filesystem per [documented convention](http://docs.aws.amazon.com/efs/latest/ug/mounting-fs-mount-cmd-dns-name.html).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">encrypted<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}If true, the disk will be encrypted.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">kms<wbr>Key<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ARN for the KMS encryption key. When specifying kms_key_id, encrypted needs to be set to true.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">lifecycle<wbr>Policy<span class="property-indicator"></span>
        <span class="property-type"><a href="#filesystemlifecyclepolicy">File<wbr>System<wbr>Lifecycle<wbr>Policy?</a></span>
    </dt>
    <dd>{{% md %}}A file system [lifecycle policy](https://docs.aws.amazon.com/efs/latest/ug/API_LifecyclePolicy.html) object (documented below).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">performance<wbr>Mode<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The file system performance mode. Can be either `&#34;generalPurpose&#34;` or `&#34;maxIO&#34;` (Default: `&#34;generalPurpose&#34;`).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">provisioned<wbr>Throughput<wbr>In<wbr>Mibps<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The throughput, measured in MiB/s, that you want to provision for the file system. Only applicable with `throughput_mode` set to `provisioned`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the file system.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">throughput<wbr>Mode<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Throughput mode for the file system. Defaults to `bursting`. Valid values: `bursting`, `provisioned`. When using `provisioned`, also set `provisioned_throughput_in_mibps`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name of the file system.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">creation_<wbr>token<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A unique name (a maximum of 64 characters are allowed)
used as reference when creating the Elastic File System to ensure idempotent file
system creation. By default generated by this provider. See [Elastic File System]
(http://docs.aws.amazon.com/efs/latest/ug/) user guide for more information.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">dns_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The DNS name for the filesystem per [documented convention](http://docs.aws.amazon.com/efs/latest/ug/mounting-fs-mount-cmd-dns-name.html).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">encrypted<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}If true, the disk will be encrypted.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">kms_<wbr>key_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ARN for the KMS encryption key. When specifying kms_key_id, encrypted needs to be set to true.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">lifecycle_<wbr>policy<span class="property-indicator"></span>
        <span class="property-type"><a href="#filesystemlifecyclepolicy">Dict[File<wbr>System<wbr>Lifecycle<wbr>Policy]</a></span>
    </dt>
    <dd>{{% md %}}A file system [lifecycle policy](https://docs.aws.amazon.com/efs/latest/ug/API_LifecyclePolicy.html) object (documented below).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">performance_<wbr>mode<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The file system performance mode. Can be either `&#34;generalPurpose&#34;` or `&#34;maxIO&#34;` (Default: `&#34;generalPurpose&#34;`).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">provisioned_<wbr>throughput_<wbr>in_<wbr>mibps<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The throughput, measured in MiB/s, that you want to provision for the file system. Only applicable with `throughput_mode` set to `provisioned`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the file system.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">throughput_<wbr>mode<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Throughput mode for the file system. Defaults to `bursting`. Valid values: `bursting`, `provisioned`. When using `provisioned`, also set `provisioned_throughput_in_mibps`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}







## Supporting Types

#### FileSystemLifecyclePolicy
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#FileSystemLifecyclePolicy">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#FileSystemLifecyclePolicy">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/efs?tab=doc#FileSystemLifecyclePolicyArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/efs?tab=doc#FileSystemLifecyclePolicyOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Efs.FileSystemLifecyclePolicyArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Efs.FileSystemLifecyclePolicy.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Transition<wbr>To<wbr>Ia<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Indicates how long it takes to transition files to the IA storage class. Valid values: `AFTER_7_DAYS`, `AFTER_14_DAYS`, `AFTER_30_DAYS`, `AFTER_60_DAYS`, or `AFTER_90_DAYS`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Transition<wbr>To<wbr>Ia<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Indicates how long it takes to transition files to the IA storage class. Valid values: `AFTER_7_DAYS`, `AFTER_14_DAYS`, `AFTER_30_DAYS`, `AFTER_60_DAYS`, or `AFTER_90_DAYS`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">transition<wbr>To<wbr>Ia<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Indicates how long it takes to transition files to the IA storage class. Valid values: `AFTER_7_DAYS`, `AFTER_14_DAYS`, `AFTER_30_DAYS`, `AFTER_60_DAYS`, or `AFTER_90_DAYS`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">transition<wbr>To<wbr>Ia<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Indicates how long it takes to transition files to the IA storage class. Valid values: `AFTER_7_DAYS`, `AFTER_14_DAYS`, `AFTER_30_DAYS`, `AFTER_60_DAYS`, or `AFTER_90_DAYS`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}








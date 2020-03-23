
---
title: "WindowsFileSystem"
block_external_search_index: true
---

Manages a FSx Windows File System. See the [FSx Windows Guide](https://docs.aws.amazon.com/fsx/latest/WindowsGuide/what-is.html) for more information.

> **NOTE:** Either the `active_directory_id` argument or `self_managed_active_directory` configuration block must be specified.

## Example Usage

### Using AWS Directory Service

Additional information for using AWS Directory Service with Windows File Systems can be found in the [FSx Windows Guide](https://docs.aws.amazon.com/fsx/latest/WindowsGuide/fsx-aws-managed-ad.html).

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const example = new aws.fsx.WindowsFileSystem("example", {
    activeDirectoryId: aws_directory_service_directory_example.id,
    kmsKeyId: aws_kms_key_example.arn,
    storageCapacity: 300,
    subnetIds: aws_subnet_example.id,
    throughputCapacity: 1024,
});
```

### Using a Self-Managed Microsoft Active Directory

Additional information for using AWS Directory Service with Windows File Systems can be found in the [FSx Windows Guide](https://docs.aws.amazon.com/fsx/latest/WindowsGuide/self-managed-AD.html).

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const example = new aws.fsx.WindowsFileSystem("example", {
    kmsKeyId: aws_kms_key_example.arn,
    selfManagedActiveDirectory: {
        dnsIps: [
            "10.0.0.111",
            "10.0.0.222",
        ],
        domainName: "corp.example.com",
        password: "avoid-plaintext-passwords",
        username: "Admin",
    },
    storageCapacity: 300,
    subnetIds: aws_subnet_example.id,
    throughputCapacity: 1024,
});
```

> This content is derived from https://github.com/terraform-providers/terraform-provider-aws/blob/master/website/docs/r/fsx_windows_file_system.html.markdown.



## Create a WindowsFileSystem Resource

{{< chooser language "javascript,typescript,python,go,csharp" / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/fsx/#WindowsFileSystem">WindowsFileSystem</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/fsx/#WindowsFileSystemArgs">WindowsFileSystemArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">WindowsFileSystem</span><span class="p">(resource_name, opts=None, </span>active_directory_id=None<span class="p">, </span>automatic_backup_retention_days=None<span class="p">, </span>copy_tags_to_backups=None<span class="p">, </span>daily_automatic_backup_start_time=None<span class="p">, </span>kms_key_id=None<span class="p">, </span>security_group_ids=None<span class="p">, </span>self_managed_active_directory=None<span class="p">, </span>skip_final_backup=None<span class="p">, </span>storage_capacity=None<span class="p">, </span>subnet_ids=None<span class="p">, </span>tags=None<span class="p">, </span>throughput_capacity=None<span class="p">, </span>weekly_maintenance_start_time=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewWindowsFileSystem<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/fsx?tab=doc#WindowsFileSystemArgs">WindowsFileSystemArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/fsx?tab=doc#WindowsFileSystem">WindowsFileSystem</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Fsx.WindowsFileSystem.html">WindowsFileSystem</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Fsx.WindowsFileSystemArgs.html">WindowsFileSystemArgs</a></span> <span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
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
            title="Optional">Active<wbr>Directory<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ID for an existing Microsoft Active Directory instance that the file system should join when it&#39;s created. Cannot be specified with `self_managed_active_directory`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Automatic<wbr>Backup<wbr>Retention<wbr>Days<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The number of days to retain automatic backups. Minimum of `0` and maximum of `35`. Defaults to `7`. Set to `0` to disable.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Copy<wbr>Tags<wbr>To<wbr>Backups<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}A boolean flag indicating whether tags on the file system should be copied to backups. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Daily<wbr>Automatic<wbr>Backup<wbr>Start<wbr>Time<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The preferred time (in `HH:MM` format) to take daily automatic backups, in the UTC time zone.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Kms<wbr>Key<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}ARN for the KMS Key to encrypt the file system at rest. Defaults to an AWS managed KMS Key.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Security<wbr>Group<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}A list of IDs for the security groups that apply to the specified network interfaces created for file system access. These security groups will apply to all network interfaces.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Self<wbr>Managed<wbr>Active<wbr>Directory<span class="property-indicator"></span>
        <span class="property-type"><a href="#windowsfilesystemselfmanagedactivedirectory">Windows<wbr>File<wbr>System<wbr>Self<wbr>Managed<wbr>Active<wbr>Directory<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}Configuration block that Amazon FSx uses to join the Windows File Server instance to your self-managed (including on-premises) Microsoft Active Directory (AD) directory. Cannot be specified with `active_directory_id`. Detailed below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Skip<wbr>Final<wbr>Backup<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}When enabled, will skip the default final backup taken when the file system is deleted. This configuration must be applied separately before attempting to delete the resource to have the desired behavior. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Storage<wbr>Capacity<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}Storage capacity (GiB) of the file system. Minimum of 32 and maximum of 65536.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Subnet<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}A list of IDs for the subnets that the file system will be accessible from. File systems support only one subnet. The file server is also launched in that subnet&#39;s Availability Zone.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the file system.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Throughput<wbr>Capacity<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}Throughput (megabytes per second) of the file system in power of 2 increments. Minimum of `8` and maximum of `2048`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Weekly<wbr>Maintenance<wbr>Start<wbr>Time<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The preferred start time (in `d:HH:MM` format) to perform weekly maintenance, in the UTC time zone.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Active<wbr>Directory<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The ID for an existing Microsoft Active Directory instance that the file system should join when it&#39;s created. Cannot be specified with `self_managed_active_directory`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Automatic<wbr>Backup<wbr>Retention<wbr>Days<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The number of days to retain automatic backups. Minimum of `0` and maximum of `35`. Defaults to `7`. Set to `0` to disable.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Copy<wbr>Tags<wbr>To<wbr>Backups<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}A boolean flag indicating whether tags on the file system should be copied to backups. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Daily<wbr>Automatic<wbr>Backup<wbr>Start<wbr>Time<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The preferred time (in `HH:MM` format) to take daily automatic backups, in the UTC time zone.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Kms<wbr>Key<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}ARN for the KMS Key to encrypt the file system at rest. Defaults to an AWS managed KMS Key.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Security<wbr>Group<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}A list of IDs for the security groups that apply to the specified network interfaces created for file system access. These security groups will apply to all network interfaces.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Self<wbr>Managed<wbr>Active<wbr>Directory<span class="property-indicator"></span>
        <span class="property-type"><a href="#windowsfilesystemselfmanagedactivedirectory">*Windows<wbr>File<wbr>System<wbr>Self<wbr>Managed<wbr>Active<wbr>Directory</a></span>
    </dt>
    <dd>{{% md %}}Configuration block that Amazon FSx uses to join the Windows File Server instance to your self-managed (including on-premises) Microsoft Active Directory (AD) directory. Cannot be specified with `active_directory_id`. Detailed below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Skip<wbr>Final<wbr>Backup<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}When enabled, will skip the default final backup taken when the file system is deleted. This configuration must be applied separately before attempting to delete the resource to have the desired behavior. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Storage<wbr>Capacity<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}Storage capacity (GiB) of the file system. Minimum of 32 and maximum of 65536.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Subnet<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}A list of IDs for the subnets that the file system will be accessible from. File systems support only one subnet. The file server is also launched in that subnet&#39;s Availability Zone.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the file system.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Throughput<wbr>Capacity<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}Throughput (megabytes per second) of the file system in power of 2 increments. Minimum of `8` and maximum of `2048`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Weekly<wbr>Maintenance<wbr>Start<wbr>Time<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The preferred start time (in `d:HH:MM` format) to perform weekly maintenance, in the UTC time zone.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">active<wbr>Directory<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ID for an existing Microsoft Active Directory instance that the file system should join when it&#39;s created. Cannot be specified with `self_managed_active_directory`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">automatic<wbr>Backup<wbr>Retention<wbr>Days<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The number of days to retain automatic backups. Minimum of `0` and maximum of `35`. Defaults to `7`. Set to `0` to disable.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">copy<wbr>Tags<wbr>To<wbr>Backups<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}A boolean flag indicating whether tags on the file system should be copied to backups. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">daily<wbr>Automatic<wbr>Backup<wbr>Start<wbr>Time<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The preferred time (in `HH:MM` format) to take daily automatic backups, in the UTC time zone.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">kms<wbr>Key<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}ARN for the KMS Key to encrypt the file system at rest. Defaults to an AWS managed KMS Key.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">security<wbr>Group<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}A list of IDs for the security groups that apply to the specified network interfaces created for file system access. These security groups will apply to all network interfaces.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">self<wbr>Managed<wbr>Active<wbr>Directory<span class="property-indicator"></span>
        <span class="property-type"><a href="#windowsfilesystemselfmanagedactivedirectory">Windows<wbr>File<wbr>System<wbr>Self<wbr>Managed<wbr>Active<wbr>Directory?</a></span>
    </dt>
    <dd>{{% md %}}Configuration block that Amazon FSx uses to join the Windows File Server instance to your self-managed (including on-premises) Microsoft Active Directory (AD) directory. Cannot be specified with `active_directory_id`. Detailed below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">skip<wbr>Final<wbr>Backup<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}When enabled, will skip the default final backup taken when the file system is deleted. This configuration must be applied separately before attempting to delete the resource to have the desired behavior. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">storage<wbr>Capacity<span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}Storage capacity (GiB) of the file system. Minimum of 32 and maximum of 65536.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">subnet<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}A list of IDs for the subnets that the file system will be accessible from. File systems support only one subnet. The file server is also launched in that subnet&#39;s Availability Zone.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the file system.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">throughput<wbr>Capacity<span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}Throughput (megabytes per second) of the file system in power of 2 increments. Minimum of `8` and maximum of `2048`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">weekly<wbr>Maintenance<wbr>Start<wbr>Time<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The preferred start time (in `d:HH:MM` format) to perform weekly maintenance, in the UTC time zone.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">active_<wbr>directory_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ID for an existing Microsoft Active Directory instance that the file system should join when it&#39;s created. Cannot be specified with `self_managed_active_directory`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">automatic_<wbr>backup_<wbr>retention_<wbr>days<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The number of days to retain automatic backups. Minimum of `0` and maximum of `35`. Defaults to `7`. Set to `0` to disable.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">copy_<wbr>tags_<wbr>to_<wbr>backups<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}A boolean flag indicating whether tags on the file system should be copied to backups. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">daily_<wbr>automatic_<wbr>backup_<wbr>start_<wbr>time<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The preferred time (in `HH:MM` format) to take daily automatic backups, in the UTC time zone.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">kms_<wbr>key_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}ARN for the KMS Key to encrypt the file system at rest. Defaults to an AWS managed KMS Key.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">security_<wbr>group_<wbr>ids<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}A list of IDs for the security groups that apply to the specified network interfaces created for file system access. These security groups will apply to all network interfaces.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">self_<wbr>managed_<wbr>active_<wbr>directory<span class="property-indicator"></span>
        <span class="property-type"><a href="#windowsfilesystemselfmanagedactivedirectory">Dict[Windows<wbr>File<wbr>System<wbr>Self<wbr>Managed<wbr>Active<wbr>Directory]</a></span>
    </dt>
    <dd>{{% md %}}Configuration block that Amazon FSx uses to join the Windows File Server instance to your self-managed (including on-premises) Microsoft Active Directory (AD) directory. Cannot be specified with `active_directory_id`. Detailed below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">skip_<wbr>final_<wbr>backup<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}When enabled, will skip the default final backup taken when the file system is deleted. This configuration must be applied separately before attempting to delete the resource to have the desired behavior. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">storage_<wbr>capacity<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}Storage capacity (GiB) of the file system. Minimum of 32 and maximum of 65536.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">subnet_<wbr>ids<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A list of IDs for the subnets that the file system will be accessible from. File systems support only one subnet. The file server is also launched in that subnet&#39;s Availability Zone.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the file system.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">throughput_<wbr>capacity<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}Throughput (megabytes per second) of the file system in power of 2 increments. Minimum of `8` and maximum of `2048`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">weekly_<wbr>maintenance_<wbr>start_<wbr>time<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The preferred start time (in `d:HH:MM` format) to perform weekly maintenance, in the UTC time zone.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}




## WindowsFileSystem Output Properties

The following output properties are available:




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Active<wbr>Directory<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ID for an existing Microsoft Active Directory instance that the file system should join when it&#39;s created. Cannot be specified with `self_managed_active_directory`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name of the file system.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Automatic<wbr>Backup<wbr>Retention<wbr>Days<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The number of days to retain automatic backups. Minimum of `0` and maximum of `35`. Defaults to `7`. Set to `0` to disable.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Copy<wbr>Tags<wbr>To<wbr>Backups<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}A boolean flag indicating whether tags on the file system should be copied to backups. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Daily<wbr>Automatic<wbr>Backup<wbr>Start<wbr>Time<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The preferred time (in `HH:MM` format) to take daily automatic backups, in the UTC time zone.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Dns<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}DNS name for the file system, e.g. `fs-12345678.corp.example.com` (domain name matching the Active Directory domain name)
{{% /md %}}</dd>

    <dt class="property-"
            title="">Kms<wbr>Key<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}ARN for the KMS Key to encrypt the file system at rest. Defaults to an AWS managed KMS Key.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Network<wbr>Interface<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">List<string></span>
    </dt>
    <dd>{{% md %}}Set of Elastic Network Interface identifiers from which the file system is accessible.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Owner<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}AWS account identifier that created the file system.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Security<wbr>Group<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}A list of IDs for the security groups that apply to the specified network interfaces created for file system access. These security groups will apply to all network interfaces.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Self<wbr>Managed<wbr>Active<wbr>Directory<span class="property-indicator"></span>
        <span class="property-type"><a href="#windowsfilesystemselfmanagedactivedirectory">Windows<wbr>File<wbr>System<wbr>Self<wbr>Managed<wbr>Active<wbr>Directory?</a></span>
    </dt>
    <dd>{{% md %}}Configuration block that Amazon FSx uses to join the Windows File Server instance to your self-managed (including on-premises) Microsoft Active Directory (AD) directory. Cannot be specified with `active_directory_id`. Detailed below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Skip<wbr>Final<wbr>Backup<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}When enabled, will skip the default final backup taken when the file system is deleted. This configuration must be applied separately before attempting to delete the resource to have the desired behavior. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Storage<wbr>Capacity<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}Storage capacity (GiB) of the file system. Minimum of 32 and maximum of 65536.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Subnet<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}A list of IDs for the subnets that the file system will be accessible from. File systems support only one subnet. The file server is also launched in that subnet&#39;s Availability Zone.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the file system.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Throughput<wbr>Capacity<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}Throughput (megabytes per second) of the file system in power of 2 increments. Minimum of `8` and maximum of `2048`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Vpc<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Identifier of the Virtual Private Cloud for the file system.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Weekly<wbr>Maintenance<wbr>Start<wbr>Time<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The preferred start time (in `d:HH:MM` format) to perform weekly maintenance, in the UTC time zone.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Active<wbr>Directory<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The ID for an existing Microsoft Active Directory instance that the file system should join when it&#39;s created. Cannot be specified with `self_managed_active_directory`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name of the file system.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Automatic<wbr>Backup<wbr>Retention<wbr>Days<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The number of days to retain automatic backups. Minimum of `0` and maximum of `35`. Defaults to `7`. Set to `0` to disable.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Copy<wbr>Tags<wbr>To<wbr>Backups<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}A boolean flag indicating whether tags on the file system should be copied to backups. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Daily<wbr>Automatic<wbr>Backup<wbr>Start<wbr>Time<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The preferred time (in `HH:MM` format) to take daily automatic backups, in the UTC time zone.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Dns<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}DNS name for the file system, e.g. `fs-12345678.corp.example.com` (domain name matching the Active Directory domain name)
{{% /md %}}</dd>

    <dt class="property-"
            title="">Kms<wbr>Key<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}ARN for the KMS Key to encrypt the file system at rest. Defaults to an AWS managed KMS Key.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Network<wbr>Interface<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}Set of Elastic Network Interface identifiers from which the file system is accessible.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Owner<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}AWS account identifier that created the file system.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Security<wbr>Group<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}A list of IDs for the security groups that apply to the specified network interfaces created for file system access. These security groups will apply to all network interfaces.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Self<wbr>Managed<wbr>Active<wbr>Directory<span class="property-indicator"></span>
        <span class="property-type"><a href="#windowsfilesystemselfmanagedactivedirectory">*Windows<wbr>File<wbr>System<wbr>Self<wbr>Managed<wbr>Active<wbr>Directory</a></span>
    </dt>
    <dd>{{% md %}}Configuration block that Amazon FSx uses to join the Windows File Server instance to your self-managed (including on-premises) Microsoft Active Directory (AD) directory. Cannot be specified with `active_directory_id`. Detailed below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Skip<wbr>Final<wbr>Backup<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}When enabled, will skip the default final backup taken when the file system is deleted. This configuration must be applied separately before attempting to delete the resource to have the desired behavior. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Storage<wbr>Capacity<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}Storage capacity (GiB) of the file system. Minimum of 32 and maximum of 65536.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Subnet<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}A list of IDs for the subnets that the file system will be accessible from. File systems support only one subnet. The file server is also launched in that subnet&#39;s Availability Zone.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the file system.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Throughput<wbr>Capacity<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}Throughput (megabytes per second) of the file system in power of 2 increments. Minimum of `8` and maximum of `2048`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Vpc<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Identifier of the Virtual Private Cloud for the file system.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Weekly<wbr>Maintenance<wbr>Start<wbr>Time<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The preferred start time (in `d:HH:MM` format) to perform weekly maintenance, in the UTC time zone.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">active<wbr>Directory<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ID for an existing Microsoft Active Directory instance that the file system should join when it&#39;s created. Cannot be specified with `self_managed_active_directory`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name of the file system.
{{% /md %}}</dd>

    <dt class="property-"
            title="">automatic<wbr>Backup<wbr>Retention<wbr>Days<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The number of days to retain automatic backups. Minimum of `0` and maximum of `35`. Defaults to `7`. Set to `0` to disable.
{{% /md %}}</dd>

    <dt class="property-"
            title="">copy<wbr>Tags<wbr>To<wbr>Backups<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}A boolean flag indicating whether tags on the file system should be copied to backups. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">daily<wbr>Automatic<wbr>Backup<wbr>Start<wbr>Time<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The preferred time (in `HH:MM` format) to take daily automatic backups, in the UTC time zone.
{{% /md %}}</dd>

    <dt class="property-"
            title="">dns<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}DNS name for the file system, e.g. `fs-12345678.corp.example.com` (domain name matching the Active Directory domain name)
{{% /md %}}</dd>

    <dt class="property-"
            title="">kms<wbr>Key<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}ARN for the KMS Key to encrypt the file system at rest. Defaults to an AWS managed KMS Key.
{{% /md %}}</dd>

    <dt class="property-"
            title="">network<wbr>Interface<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">string[]</span>
    </dt>
    <dd>{{% md %}}Set of Elastic Network Interface identifiers from which the file system is accessible.
{{% /md %}}</dd>

    <dt class="property-"
            title="">owner<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}AWS account identifier that created the file system.
{{% /md %}}</dd>

    <dt class="property-"
            title="">security<wbr>Group<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}A list of IDs for the security groups that apply to the specified network interfaces created for file system access. These security groups will apply to all network interfaces.
{{% /md %}}</dd>

    <dt class="property-"
            title="">self<wbr>Managed<wbr>Active<wbr>Directory<span class="property-indicator"></span>
        <span class="property-type"><a href="#windowsfilesystemselfmanagedactivedirectory">Windows<wbr>File<wbr>System<wbr>Self<wbr>Managed<wbr>Active<wbr>Directory?</a></span>
    </dt>
    <dd>{{% md %}}Configuration block that Amazon FSx uses to join the Windows File Server instance to your self-managed (including on-premises) Microsoft Active Directory (AD) directory. Cannot be specified with `active_directory_id`. Detailed below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">skip<wbr>Final<wbr>Backup<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}When enabled, will skip the default final backup taken when the file system is deleted. This configuration must be applied separately before attempting to delete the resource to have the desired behavior. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">storage<wbr>Capacity<span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}Storage capacity (GiB) of the file system. Minimum of 32 and maximum of 65536.
{{% /md %}}</dd>

    <dt class="property-"
            title="">subnet<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}A list of IDs for the subnets that the file system will be accessible from. File systems support only one subnet. The file server is also launched in that subnet&#39;s Availability Zone.
{{% /md %}}</dd>

    <dt class="property-"
            title="">tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the file system.
{{% /md %}}</dd>

    <dt class="property-"
            title="">throughput<wbr>Capacity<span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}Throughput (megabytes per second) of the file system in power of 2 increments. Minimum of `8` and maximum of `2048`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">vpc<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Identifier of the Virtual Private Cloud for the file system.
{{% /md %}}</dd>

    <dt class="property-"
            title="">weekly<wbr>Maintenance<wbr>Start<wbr>Time<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The preferred start time (in `d:HH:MM` format) to perform weekly maintenance, in the UTC time zone.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">active_<wbr>directory_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ID for an existing Microsoft Active Directory instance that the file system should join when it&#39;s created. Cannot be specified with `self_managed_active_directory`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name of the file system.
{{% /md %}}</dd>

    <dt class="property-"
            title="">automatic_<wbr>backup_<wbr>retention_<wbr>days<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The number of days to retain automatic backups. Minimum of `0` and maximum of `35`. Defaults to `7`. Set to `0` to disable.
{{% /md %}}</dd>

    <dt class="property-"
            title="">copy_<wbr>tags_<wbr>to_<wbr>backups<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}A boolean flag indicating whether tags on the file system should be copied to backups. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">daily_<wbr>automatic_<wbr>backup_<wbr>start_<wbr>time<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The preferred time (in `HH:MM` format) to take daily automatic backups, in the UTC time zone.
{{% /md %}}</dd>

    <dt class="property-"
            title="">dns_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}DNS name for the file system, e.g. `fs-12345678.corp.example.com` (domain name matching the Active Directory domain name)
{{% /md %}}</dd>

    <dt class="property-"
            title="">kms_<wbr>key_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}ARN for the KMS Key to encrypt the file system at rest. Defaults to an AWS managed KMS Key.
{{% /md %}}</dd>

    <dt class="property-"
            title="">network_<wbr>interface_<wbr>ids<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}Set of Elastic Network Interface identifiers from which the file system is accessible.
{{% /md %}}</dd>

    <dt class="property-"
            title="">owner_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}AWS account identifier that created the file system.
{{% /md %}}</dd>

    <dt class="property-"
            title="">security_<wbr>group_<wbr>ids<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}A list of IDs for the security groups that apply to the specified network interfaces created for file system access. These security groups will apply to all network interfaces.
{{% /md %}}</dd>

    <dt class="property-"
            title="">self_<wbr>managed_<wbr>active_<wbr>directory<span class="property-indicator"></span>
        <span class="property-type"><a href="#windowsfilesystemselfmanagedactivedirectory">Dict[Windows<wbr>File<wbr>System<wbr>Self<wbr>Managed<wbr>Active<wbr>Directory]</a></span>
    </dt>
    <dd>{{% md %}}Configuration block that Amazon FSx uses to join the Windows File Server instance to your self-managed (including on-premises) Microsoft Active Directory (AD) directory. Cannot be specified with `active_directory_id`. Detailed below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">skip_<wbr>final_<wbr>backup<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}When enabled, will skip the default final backup taken when the file system is deleted. This configuration must be applied separately before attempting to delete the resource to have the desired behavior. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">storage_<wbr>capacity<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}Storage capacity (GiB) of the file system. Minimum of 32 and maximum of 65536.
{{% /md %}}</dd>

    <dt class="property-"
            title="">subnet_<wbr>ids<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A list of IDs for the subnets that the file system will be accessible from. File systems support only one subnet. The file server is also launched in that subnet&#39;s Availability Zone.
{{% /md %}}</dd>

    <dt class="property-"
            title="">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the file system.
{{% /md %}}</dd>

    <dt class="property-"
            title="">throughput_<wbr>capacity<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}Throughput (megabytes per second) of the file system in power of 2 increments. Minimum of `8` and maximum of `2048`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">vpc_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Identifier of the Virtual Private Cloud for the file system.
{{% /md %}}</dd>

    <dt class="property-"
            title="">weekly_<wbr>maintenance_<wbr>start_<wbr>time<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The preferred start time (in `d:HH:MM` format) to perform weekly maintenance, in the UTC time zone.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





## Look up an Existing WindowsFileSystem Resource

{{< chooser language "javascript,typescript,python,go,csharp  " / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">pulumi.Input&lt;pulumi.ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/fsx/#WindowsFileSystemState">WindowsFileSystemState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/fsx/#WindowsFileSystem">WindowsFileSystem</a></span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>active_directory_id=None<span class="p">, </span>arn=None<span class="p">, </span>automatic_backup_retention_days=None<span class="p">, </span>copy_tags_to_backups=None<span class="p">, </span>daily_automatic_backup_start_time=None<span class="p">, </span>dns_name=None<span class="p">, </span>kms_key_id=None<span class="p">, </span>network_interface_ids=None<span class="p">, </span>owner_id=None<span class="p">, </span>security_group_ids=None<span class="p">, </span>self_managed_active_directory=None<span class="p">, </span>skip_final_backup=None<span class="p">, </span>storage_capacity=None<span class="p">, </span>subnet_ids=None<span class="p">, </span>tags=None<span class="p">, </span>throughput_capacity=None<span class="p">, </span>vpc_id=None<span class="p">, </span>weekly_maintenance_start_time=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetWindowsFileSystem<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">pulumi.IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/fsx?tab=doc#WindowsFileSystemState">WindowsFileSystemState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/fsx?tab=doc#WindowsFileSystem">WindowsFileSystem</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Fsx.WindowsFileSystem.html">WindowsFileSystem</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Pulumi.Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Fsx.WindowsFileSystemState.html">WindowsFileSystemState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
{{% /choosable %}}

Get an existing WindowsFileSystem resource's state with the given name, ID, and optional extra properties used to qualify the lookup.

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
            title="Optional">Active<wbr>Directory<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ID for an existing Microsoft Active Directory instance that the file system should join when it&#39;s created. Cannot be specified with `self_managed_active_directory`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name of the file system.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Automatic<wbr>Backup<wbr>Retention<wbr>Days<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The number of days to retain automatic backups. Minimum of `0` and maximum of `35`. Defaults to `7`. Set to `0` to disable.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Copy<wbr>Tags<wbr>To<wbr>Backups<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}A boolean flag indicating whether tags on the file system should be copied to backups. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Daily<wbr>Automatic<wbr>Backup<wbr>Start<wbr>Time<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The preferred time (in `HH:MM` format) to take daily automatic backups, in the UTC time zone.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Dns<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}DNS name for the file system, e.g. `fs-12345678.corp.example.com` (domain name matching the Active Directory domain name)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Kms<wbr>Key<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}ARN for the KMS Key to encrypt the file system at rest. Defaults to an AWS managed KMS Key.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Network<wbr>Interface<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}Set of Elastic Network Interface identifiers from which the file system is accessible.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Owner<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}AWS account identifier that created the file system.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Security<wbr>Group<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}A list of IDs for the security groups that apply to the specified network interfaces created for file system access. These security groups will apply to all network interfaces.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Self<wbr>Managed<wbr>Active<wbr>Directory<span class="property-indicator"></span>
        <span class="property-type"><a href="#windowsfilesystemselfmanagedactivedirectory">Windows<wbr>File<wbr>System<wbr>Self<wbr>Managed<wbr>Active<wbr>Directory<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}Configuration block that Amazon FSx uses to join the Windows File Server instance to your self-managed (including on-premises) Microsoft Active Directory (AD) directory. Cannot be specified with `active_directory_id`. Detailed below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Skip<wbr>Final<wbr>Backup<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}When enabled, will skip the default final backup taken when the file system is deleted. This configuration must be applied separately before attempting to delete the resource to have the desired behavior. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Storage<wbr>Capacity<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}Storage capacity (GiB) of the file system. Minimum of 32 and maximum of 65536.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Subnet<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A list of IDs for the subnets that the file system will be accessible from. File systems support only one subnet. The file server is also launched in that subnet&#39;s Availability Zone.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the file system.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Throughput<wbr>Capacity<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}Throughput (megabytes per second) of the file system in power of 2 increments. Minimum of `8` and maximum of `2048`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Vpc<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Identifier of the Virtual Private Cloud for the file system.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Weekly<wbr>Maintenance<wbr>Start<wbr>Time<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The preferred start time (in `d:HH:MM` format) to perform weekly maintenance, in the UTC time zone.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Active<wbr>Directory<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The ID for an existing Microsoft Active Directory instance that the file system should join when it&#39;s created. Cannot be specified with `self_managed_active_directory`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name of the file system.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Automatic<wbr>Backup<wbr>Retention<wbr>Days<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The number of days to retain automatic backups. Minimum of `0` and maximum of `35`. Defaults to `7`. Set to `0` to disable.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Copy<wbr>Tags<wbr>To<wbr>Backups<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}A boolean flag indicating whether tags on the file system should be copied to backups. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Daily<wbr>Automatic<wbr>Backup<wbr>Start<wbr>Time<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The preferred time (in `HH:MM` format) to take daily automatic backups, in the UTC time zone.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Dns<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}DNS name for the file system, e.g. `fs-12345678.corp.example.com` (domain name matching the Active Directory domain name)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Kms<wbr>Key<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}ARN for the KMS Key to encrypt the file system at rest. Defaults to an AWS managed KMS Key.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Network<wbr>Interface<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}Set of Elastic Network Interface identifiers from which the file system is accessible.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Owner<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}AWS account identifier that created the file system.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Security<wbr>Group<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}A list of IDs for the security groups that apply to the specified network interfaces created for file system access. These security groups will apply to all network interfaces.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Self<wbr>Managed<wbr>Active<wbr>Directory<span class="property-indicator"></span>
        <span class="property-type"><a href="#windowsfilesystemselfmanagedactivedirectory">*Windows<wbr>File<wbr>System<wbr>Self<wbr>Managed<wbr>Active<wbr>Directory</a></span>
    </dt>
    <dd>{{% md %}}Configuration block that Amazon FSx uses to join the Windows File Server instance to your self-managed (including on-premises) Microsoft Active Directory (AD) directory. Cannot be specified with `active_directory_id`. Detailed below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Skip<wbr>Final<wbr>Backup<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}When enabled, will skip the default final backup taken when the file system is deleted. This configuration must be applied separately before attempting to delete the resource to have the desired behavior. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Storage<wbr>Capacity<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}Storage capacity (GiB) of the file system. Minimum of 32 and maximum of 65536.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Subnet<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}A list of IDs for the subnets that the file system will be accessible from. File systems support only one subnet. The file server is also launched in that subnet&#39;s Availability Zone.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the file system.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Throughput<wbr>Capacity<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}Throughput (megabytes per second) of the file system in power of 2 increments. Minimum of `8` and maximum of `2048`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Vpc<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Identifier of the Virtual Private Cloud for the file system.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Weekly<wbr>Maintenance<wbr>Start<wbr>Time<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The preferred start time (in `d:HH:MM` format) to perform weekly maintenance, in the UTC time zone.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">active<wbr>Directory<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ID for an existing Microsoft Active Directory instance that the file system should join when it&#39;s created. Cannot be specified with `self_managed_active_directory`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name of the file system.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">automatic<wbr>Backup<wbr>Retention<wbr>Days<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The number of days to retain automatic backups. Minimum of `0` and maximum of `35`. Defaults to `7`. Set to `0` to disable.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">copy<wbr>Tags<wbr>To<wbr>Backups<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}A boolean flag indicating whether tags on the file system should be copied to backups. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">daily<wbr>Automatic<wbr>Backup<wbr>Start<wbr>Time<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The preferred time (in `HH:MM` format) to take daily automatic backups, in the UTC time zone.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">dns<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}DNS name for the file system, e.g. `fs-12345678.corp.example.com` (domain name matching the Active Directory domain name)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">kms<wbr>Key<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}ARN for the KMS Key to encrypt the file system at rest. Defaults to an AWS managed KMS Key.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">network<wbr>Interface<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}Set of Elastic Network Interface identifiers from which the file system is accessible.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">owner<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}AWS account identifier that created the file system.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">security<wbr>Group<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}A list of IDs for the security groups that apply to the specified network interfaces created for file system access. These security groups will apply to all network interfaces.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">self<wbr>Managed<wbr>Active<wbr>Directory<span class="property-indicator"></span>
        <span class="property-type"><a href="#windowsfilesystemselfmanagedactivedirectory">Windows<wbr>File<wbr>System<wbr>Self<wbr>Managed<wbr>Active<wbr>Directory?</a></span>
    </dt>
    <dd>{{% md %}}Configuration block that Amazon FSx uses to join the Windows File Server instance to your self-managed (including on-premises) Microsoft Active Directory (AD) directory. Cannot be specified with `active_directory_id`. Detailed below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">skip<wbr>Final<wbr>Backup<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}When enabled, will skip the default final backup taken when the file system is deleted. This configuration must be applied separately before attempting to delete the resource to have the desired behavior. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">storage<wbr>Capacity<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}Storage capacity (GiB) of the file system. Minimum of 32 and maximum of 65536.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">subnet<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A list of IDs for the subnets that the file system will be accessible from. File systems support only one subnet. The file server is also launched in that subnet&#39;s Availability Zone.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the file system.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">throughput<wbr>Capacity<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}Throughput (megabytes per second) of the file system in power of 2 increments. Minimum of `8` and maximum of `2048`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">vpc<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Identifier of the Virtual Private Cloud for the file system.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">weekly<wbr>Maintenance<wbr>Start<wbr>Time<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The preferred start time (in `d:HH:MM` format) to perform weekly maintenance, in the UTC time zone.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">active_<wbr>directory_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ID for an existing Microsoft Active Directory instance that the file system should join when it&#39;s created. Cannot be specified with `self_managed_active_directory`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name of the file system.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">automatic_<wbr>backup_<wbr>retention_<wbr>days<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The number of days to retain automatic backups. Minimum of `0` and maximum of `35`. Defaults to `7`. Set to `0` to disable.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">copy_<wbr>tags_<wbr>to_<wbr>backups<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}A boolean flag indicating whether tags on the file system should be copied to backups. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">daily_<wbr>automatic_<wbr>backup_<wbr>start_<wbr>time<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The preferred time (in `HH:MM` format) to take daily automatic backups, in the UTC time zone.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">dns_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}DNS name for the file system, e.g. `fs-12345678.corp.example.com` (domain name matching the Active Directory domain name)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">kms_<wbr>key_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}ARN for the KMS Key to encrypt the file system at rest. Defaults to an AWS managed KMS Key.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">network_<wbr>interface_<wbr>ids<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}Set of Elastic Network Interface identifiers from which the file system is accessible.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">owner_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}AWS account identifier that created the file system.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">security_<wbr>group_<wbr>ids<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}A list of IDs for the security groups that apply to the specified network interfaces created for file system access. These security groups will apply to all network interfaces.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">self_<wbr>managed_<wbr>active_<wbr>directory<span class="property-indicator"></span>
        <span class="property-type"><a href="#windowsfilesystemselfmanagedactivedirectory">Dict[Windows<wbr>File<wbr>System<wbr>Self<wbr>Managed<wbr>Active<wbr>Directory]</a></span>
    </dt>
    <dd>{{% md %}}Configuration block that Amazon FSx uses to join the Windows File Server instance to your self-managed (including on-premises) Microsoft Active Directory (AD) directory. Cannot be specified with `active_directory_id`. Detailed below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">skip_<wbr>final_<wbr>backup<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}When enabled, will skip the default final backup taken when the file system is deleted. This configuration must be applied separately before attempting to delete the resource to have the desired behavior. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">storage_<wbr>capacity<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}Storage capacity (GiB) of the file system. Minimum of 32 and maximum of 65536.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">subnet_<wbr>ids<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A list of IDs for the subnets that the file system will be accessible from. File systems support only one subnet. The file server is also launched in that subnet&#39;s Availability Zone.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the file system.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">throughput_<wbr>capacity<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}Throughput (megabytes per second) of the file system in power of 2 increments. Minimum of `8` and maximum of `2048`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">vpc_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Identifier of the Virtual Private Cloud for the file system.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">weekly_<wbr>maintenance_<wbr>start_<wbr>time<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The preferred start time (in `d:HH:MM` format) to perform weekly maintenance, in the UTC time zone.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}







## Supporting Types

#### WindowsFileSystemSelfManagedActiveDirectory
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#WindowsFileSystemSelfManagedActiveDirectory">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#WindowsFileSystemSelfManagedActiveDirectory">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/fsx?tab=doc#WindowsFileSystemSelfManagedActiveDirectoryArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/fsx?tab=doc#WindowsFileSystemSelfManagedActiveDirectoryOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Fsx.WindowsFileSystemSelfManagedActiveDirectoryArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Fsx.WindowsFileSystemSelfManagedActiveDirectory.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Dns<wbr>Ips<span class="property-indicator"></span>
        <span class="property-type">List<string></span>
    </dt>
    <dd>{{% md %}}A list of up to two IP addresses of DNS servers or domain controllers in the self-managed AD directory. The IP addresses need to be either in the same VPC CIDR range as the file system or in the private IP version 4 (IPv4) address ranges as specified in [RFC 1918](https://tools.ietf.org/html/rfc1918).
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Domain<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The fully qualified domain name of the self-managed AD directory. For example, `corp.example.com`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">File<wbr>System<wbr>Administrators<wbr>Group<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the domain group whose members are granted administrative privileges for the file system. Administrative privileges include taking ownership of files and folders, and setting audit controls (audit ACLs) on files and folders. The group that you specify must already exist in your domain. Defaults to `Domain Admins`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Organizational<wbr>Unit<wbr>Distinguished<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The fully qualified distinguished name of the organizational unit within your self-managed AD directory that the Windows File Server instance will join. For example, `OU=FSx,DC=yourdomain,DC=corp,DC=com`. Only accepts OU as the direct parent of the file system. If none is provided, the FSx file system is created in the default location of your self-managed AD directory. To learn more, see [RFC 2253](https://tools.ietf.org/html/rfc2253).
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Password<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The password for the service account on your self-managed AD domain that Amazon FSx will use to join to your AD domain.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Username<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The user name for the service account on your self-managed AD domain that Amazon FSx will use to join to your AD domain.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Dns<wbr>Ips<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}A list of up to two IP addresses of DNS servers or domain controllers in the self-managed AD directory. The IP addresses need to be either in the same VPC CIDR range as the file system or in the private IP version 4 (IPv4) address ranges as specified in [RFC 1918](https://tools.ietf.org/html/rfc1918).
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Domain<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The fully qualified domain name of the self-managed AD directory. For example, `corp.example.com`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">File<wbr>System<wbr>Administrators<wbr>Group<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name of the domain group whose members are granted administrative privileges for the file system. Administrative privileges include taking ownership of files and folders, and setting audit controls (audit ACLs) on files and folders. The group that you specify must already exist in your domain. Defaults to `Domain Admins`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Organizational<wbr>Unit<wbr>Distinguished<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The fully qualified distinguished name of the organizational unit within your self-managed AD directory that the Windows File Server instance will join. For example, `OU=FSx,DC=yourdomain,DC=corp,DC=com`. Only accepts OU as the direct parent of the file system. If none is provided, the FSx file system is created in the default location of your self-managed AD directory. To learn more, see [RFC 2253](https://tools.ietf.org/html/rfc2253).
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Password<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The password for the service account on your self-managed AD domain that Amazon FSx will use to join to your AD domain.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Username<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The user name for the service account on your self-managed AD domain that Amazon FSx will use to join to your AD domain.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">dns<wbr>Ips<span class="property-indicator"></span>
        <span class="property-type">string[]</span>
    </dt>
    <dd>{{% md %}}A list of up to two IP addresses of DNS servers or domain controllers in the self-managed AD directory. The IP addresses need to be either in the same VPC CIDR range as the file system or in the private IP version 4 (IPv4) address ranges as specified in [RFC 1918](https://tools.ietf.org/html/rfc1918).
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">domain<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The fully qualified domain name of the self-managed AD directory. For example, `corp.example.com`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">file<wbr>System<wbr>Administrators<wbr>Group<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the domain group whose members are granted administrative privileges for the file system. Administrative privileges include taking ownership of files and folders, and setting audit controls (audit ACLs) on files and folders. The group that you specify must already exist in your domain. Defaults to `Domain Admins`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">organizational<wbr>Unit<wbr>Distinguished<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The fully qualified distinguished name of the organizational unit within your self-managed AD directory that the Windows File Server instance will join. For example, `OU=FSx,DC=yourdomain,DC=corp,DC=com`. Only accepts OU as the direct parent of the file system. If none is provided, the FSx file system is created in the default location of your self-managed AD directory. To learn more, see [RFC 2253](https://tools.ietf.org/html/rfc2253).
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">password<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The password for the service account on your self-managed AD domain that Amazon FSx will use to join to your AD domain.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">username<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The user name for the service account on your self-managed AD domain that Amazon FSx will use to join to your AD domain.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">dns_<wbr>ips<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}A list of up to two IP addresses of DNS servers or domain controllers in the self-managed AD directory. The IP addresses need to be either in the same VPC CIDR range as the file system or in the private IP version 4 (IPv4) address ranges as specified in [RFC 1918](https://tools.ietf.org/html/rfc1918).
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">domain_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The fully qualified domain name of the self-managed AD directory. For example, `corp.example.com`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">file<wbr>System<wbr>Administrators<wbr>Group<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the domain group whose members are granted administrative privileges for the file system. Administrative privileges include taking ownership of files and folders, and setting audit controls (audit ACLs) on files and folders. The group that you specify must already exist in your domain. Defaults to `Domain Admins`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">organizational<wbr>Unit<wbr>Distinguished<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The fully qualified distinguished name of the organizational unit within your self-managed AD directory that the Windows File Server instance will join. For example, `OU=FSx,DC=yourdomain,DC=corp,DC=com`. Only accepts OU as the direct parent of the file system. If none is provided, the FSx file system is created in the default location of your self-managed AD directory. To learn more, see [RFC 2253](https://tools.ietf.org/html/rfc2253).
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">password<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The password for the service account on your self-managed AD domain that Amazon FSx will use to join to your AD domain.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">username<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The user name for the service account on your self-managed AD domain that Amazon FSx will use to join to your AD domain.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}








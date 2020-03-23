
---
title: "Cluster"
block_external_search_index: true
---

Manages a DocDB Cluster.

Changes to a DocDB Cluster can occur when you manually change a
parameter, such as `port`, and are reflected in the next maintenance
window. Because of this, this provider may report a difference in its planning
phase because a modification has not yet taken place. You can use the
`apply_immediately` flag to instruct the service to apply the change immediately
(see documentation below).

> **Note:** using `apply_immediately` can result in a brief downtime as the server reboots.
> **Note:** All arguments including the username and password will be stored in the raw state as plain-text.
[Read more about sensitive data in state](https://www.terraform.io/docs/state/sensitive-data.html).

## Example Usage

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const docdb = new aws.docdb.Cluster("docdb", {
    backupRetentionPeriod: 5,
    clusterIdentifier: "my-docdb-cluster",
    engine: "docdb",
    masterPassword: "mustbeeightchars",
    masterUsername: "foo",
    preferredBackupWindow: "07:00-09:00",
    skipFinalSnapshot: true,
});
```

> This content is derived from https://github.com/terraform-providers/terraform-provider-aws/blob/master/website/docs/r/docdb_cluster.html.markdown.



## Create a Cluster Resource

{{< chooser language "javascript,typescript,python,go,csharp" / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/docdb/#Cluster">Cluster</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/docdb/#ClusterArgs">ClusterArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">Cluster</span><span class="p">(resource_name, opts=None, </span>apply_immediately=None<span class="p">, </span>availability_zones=None<span class="p">, </span>backup_retention_period=None<span class="p">, </span>cluster_identifier=None<span class="p">, </span>cluster_identifier_prefix=None<span class="p">, </span>cluster_members=None<span class="p">, </span>db_cluster_parameter_group_name=None<span class="p">, </span>db_subnet_group_name=None<span class="p">, </span>enabled_cloudwatch_logs_exports=None<span class="p">, </span>engine=None<span class="p">, </span>engine_version=None<span class="p">, </span>final_snapshot_identifier=None<span class="p">, </span>kms_key_id=None<span class="p">, </span>master_password=None<span class="p">, </span>master_username=None<span class="p">, </span>port=None<span class="p">, </span>preferred_backup_window=None<span class="p">, </span>preferred_maintenance_window=None<span class="p">, </span>skip_final_snapshot=None<span class="p">, </span>snapshot_identifier=None<span class="p">, </span>storage_encrypted=None<span class="p">, </span>tags=None<span class="p">, </span>vpc_security_group_ids=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewCluster<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/docdb?tab=doc#ClusterArgs">ClusterArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/docdb?tab=doc#Cluster">Cluster</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Docdb.Cluster.html">Cluster</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Docdb.ClusterArgs.html">ClusterArgs</a></span>? <span class="nx">args = null<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
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
            title="Optional">Apply<wbr>Immediately<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Specifies whether any cluster modifications
are applied immediately, or during the next maintenance window. Default is
`false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Availability<wbr>Zones<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}A list of EC2 Availability Zones that
instances in the DB cluster can be created in.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Backup<wbr>Retention<wbr>Period<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The days to retain backups for. Default `1`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Cluster<wbr>Identifier<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The cluster identifier. If omitted, this provider will assign a random, unique identifier.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Cluster<wbr>Identifier<wbr>Prefix<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Creates a unique cluster identifier beginning with the specified prefix. Conflicts with `cluster_identifer`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Cluster<wbr>Members<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}List of DocDB Instances that are a part of this cluster
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Db<wbr>Cluster<wbr>Parameter<wbr>Group<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A cluster parameter group to associate with the cluster.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Db<wbr>Subnet<wbr>Group<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A DB subnet group to associate with this DB instance.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Enabled<wbr>Cloudwatch<wbr>Logs<wbr>Exports<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}List of log types to export to cloudwatch. If omitted, no logs will be exported.
The following log types are supported: `audit`, `profiler`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Engine<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the database engine to be used for this DB cluster. Defaults to `docdb`. Valid Values: `docdb`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Engine<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The database engine version. Updating this argument results in an outage.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Final<wbr>Snapshot<wbr>Identifier<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of your final DB snapshot
when this DB cluster is deleted. If omitted, no final snapshot will be
made.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Kms<wbr>Key<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ARN for the KMS encryption key. When specifying `kms_key_id`, `storage_encrypted` needs to be set to true.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Master<wbr>Password<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Password for the master DB user. Note that this may
show up in logs, and it will be stored in the state file. Please refer to the DocDB Naming Constraints.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Master<wbr>Username<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Username for the master DB user. 
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Port<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The port on which the DB accepts connections
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Preferred<wbr>Backup<wbr>Window<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The daily time range during which automated backups are created if automated backups are enabled using the BackupRetentionPeriod parameter.Time in UTC
Default: A 30-minute window selected at random from an 8-hour block of time per region. e.g. 04:00-09:00
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Preferred<wbr>Maintenance<wbr>Window<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Skip<wbr>Final<wbr>Snapshot<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Determines whether a final DB snapshot is created before the DB cluster is deleted. If true is specified, no DB snapshot is created. If false is specified, a DB snapshot is created before the DB cluster is deleted, using the value from `final_snapshot_identifier`. Default is `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Snapshot<wbr>Identifier<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Specifies whether or not to create this cluster from a snapshot. You can use either the name or ARN when specifying a DB cluster snapshot, or the ARN when specifying a DB snapshot.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Storage<wbr>Encrypted<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Specifies whether the DB cluster is encrypted. The default is `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the DB cluster.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Vpc<wbr>Security<wbr>Group<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}List of VPC security groups to associate
with the Cluster
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Apply<wbr>Immediately<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Specifies whether any cluster modifications
are applied immediately, or during the next maintenance window. Default is
`false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Availability<wbr>Zones<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}A list of EC2 Availability Zones that
instances in the DB cluster can be created in.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Backup<wbr>Retention<wbr>Period<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The days to retain backups for. Default `1`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Cluster<wbr>Identifier<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The cluster identifier. If omitted, this provider will assign a random, unique identifier.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Cluster<wbr>Identifier<wbr>Prefix<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Creates a unique cluster identifier beginning with the specified prefix. Conflicts with `cluster_identifer`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Cluster<wbr>Members<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}List of DocDB Instances that are a part of this cluster
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Db<wbr>Cluster<wbr>Parameter<wbr>Group<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}A cluster parameter group to associate with the cluster.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Db<wbr>Subnet<wbr>Group<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}A DB subnet group to associate with this DB instance.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Enabled<wbr>Cloudwatch<wbr>Logs<wbr>Exports<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}List of log types to export to cloudwatch. If omitted, no logs will be exported.
The following log types are supported: `audit`, `profiler`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Engine<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name of the database engine to be used for this DB cluster. Defaults to `docdb`. Valid Values: `docdb`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Engine<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The database engine version. Updating this argument results in an outage.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Final<wbr>Snapshot<wbr>Identifier<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name of your final DB snapshot
when this DB cluster is deleted. If omitted, no final snapshot will be
made.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Kms<wbr>Key<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The ARN for the KMS encryption key. When specifying `kms_key_id`, `storage_encrypted` needs to be set to true.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Master<wbr>Password<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Password for the master DB user. Note that this may
show up in logs, and it will be stored in the state file. Please refer to the DocDB Naming Constraints.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Master<wbr>Username<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Username for the master DB user. 
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Port<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The port on which the DB accepts connections
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Preferred<wbr>Backup<wbr>Window<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The daily time range during which automated backups are created if automated backups are enabled using the BackupRetentionPeriod parameter.Time in UTC
Default: A 30-minute window selected at random from an 8-hour block of time per region. e.g. 04:00-09:00
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Preferred<wbr>Maintenance<wbr>Window<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Skip<wbr>Final<wbr>Snapshot<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Determines whether a final DB snapshot is created before the DB cluster is deleted. If true is specified, no DB snapshot is created. If false is specified, a DB snapshot is created before the DB cluster is deleted, using the value from `final_snapshot_identifier`. Default is `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Snapshot<wbr>Identifier<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Specifies whether or not to create this cluster from a snapshot. You can use either the name or ARN when specifying a DB cluster snapshot, or the ARN when specifying a DB snapshot.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Storage<wbr>Encrypted<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Specifies whether the DB cluster is encrypted. The default is `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the DB cluster.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Vpc<wbr>Security<wbr>Group<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}List of VPC security groups to associate
with the Cluster
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">apply<wbr>Immediately<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Specifies whether any cluster modifications
are applied immediately, or during the next maintenance window. Default is
`false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">availability<wbr>Zones<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}A list of EC2 Availability Zones that
instances in the DB cluster can be created in.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">backup<wbr>Retention<wbr>Period<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The days to retain backups for. Default `1`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">cluster<wbr>Identifier<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The cluster identifier. If omitted, this provider will assign a random, unique identifier.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">cluster<wbr>Identifier<wbr>Prefix<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Creates a unique cluster identifier beginning with the specified prefix. Conflicts with `cluster_identifer`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">cluster<wbr>Members<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}List of DocDB Instances that are a part of this cluster
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">db<wbr>Cluster<wbr>Parameter<wbr>Group<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A cluster parameter group to associate with the cluster.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">db<wbr>Subnet<wbr>Group<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A DB subnet group to associate with this DB instance.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">enabled<wbr>Cloudwatch<wbr>Logs<wbr>Exports<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}List of log types to export to cloudwatch. If omitted, no logs will be exported.
The following log types are supported: `audit`, `profiler`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">engine<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the database engine to be used for this DB cluster. Defaults to `docdb`. Valid Values: `docdb`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">engine<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The database engine version. Updating this argument results in an outage.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">final<wbr>Snapshot<wbr>Identifier<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of your final DB snapshot
when this DB cluster is deleted. If omitted, no final snapshot will be
made.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">kms<wbr>Key<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ARN for the KMS encryption key. When specifying `kms_key_id`, `storage_encrypted` needs to be set to true.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">master<wbr>Password<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Password for the master DB user. Note that this may
show up in logs, and it will be stored in the state file. Please refer to the DocDB Naming Constraints.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">master<wbr>Username<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Username for the master DB user. 
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">port<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The port on which the DB accepts connections
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">preferred<wbr>Backup<wbr>Window<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The daily time range during which automated backups are created if automated backups are enabled using the BackupRetentionPeriod parameter.Time in UTC
Default: A 30-minute window selected at random from an 8-hour block of time per region. e.g. 04:00-09:00
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">preferred<wbr>Maintenance<wbr>Window<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">skip<wbr>Final<wbr>Snapshot<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Determines whether a final DB snapshot is created before the DB cluster is deleted. If true is specified, no DB snapshot is created. If false is specified, a DB snapshot is created before the DB cluster is deleted, using the value from `final_snapshot_identifier`. Default is `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">snapshot<wbr>Identifier<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Specifies whether or not to create this cluster from a snapshot. You can use either the name or ARN when specifying a DB cluster snapshot, or the ARN when specifying a DB snapshot.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">storage<wbr>Encrypted<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Specifies whether the DB cluster is encrypted. The default is `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the DB cluster.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">vpc<wbr>Security<wbr>Group<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}List of VPC security groups to associate
with the Cluster
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">apply_<wbr>immediately<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Specifies whether any cluster modifications
are applied immediately, or during the next maintenance window. Default is
`false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">availability_<wbr>zones<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}A list of EC2 Availability Zones that
instances in the DB cluster can be created in.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">backup_<wbr>retention_<wbr>period<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The days to retain backups for. Default `1`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">cluster_<wbr>identifier<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The cluster identifier. If omitted, this provider will assign a random, unique identifier.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">cluster_<wbr>identifier_<wbr>prefix<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Creates a unique cluster identifier beginning with the specified prefix. Conflicts with `cluster_identifer`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">cluster_<wbr>members<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}List of DocDB Instances that are a part of this cluster
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">db_<wbr>cluster_<wbr>parameter_<wbr>group_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A cluster parameter group to associate with the cluster.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">db_<wbr>subnet_<wbr>group_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A DB subnet group to associate with this DB instance.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">enabled_<wbr>cloudwatch_<wbr>logs_<wbr>exports<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}List of log types to export to cloudwatch. If omitted, no logs will be exported.
The following log types are supported: `audit`, `profiler`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">engine<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the database engine to be used for this DB cluster. Defaults to `docdb`. Valid Values: `docdb`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">engine_<wbr>version<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The database engine version. Updating this argument results in an outage.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">final_<wbr>snapshot_<wbr>identifier<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of your final DB snapshot
when this DB cluster is deleted. If omitted, no final snapshot will be
made.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">kms_<wbr>key_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ARN for the KMS encryption key. When specifying `kms_key_id`, `storage_encrypted` needs to be set to true.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">master_<wbr>password<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Password for the master DB user. Note that this may
show up in logs, and it will be stored in the state file. Please refer to the DocDB Naming Constraints.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">master_<wbr>username<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Username for the master DB user. 
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">port<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The port on which the DB accepts connections
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">preferred_<wbr>backup_<wbr>window<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The daily time range during which automated backups are created if automated backups are enabled using the BackupRetentionPeriod parameter.Time in UTC
Default: A 30-minute window selected at random from an 8-hour block of time per region. e.g. 04:00-09:00
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">preferred_<wbr>maintenance_<wbr>window<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">skip_<wbr>final_<wbr>snapshot<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Determines whether a final DB snapshot is created before the DB cluster is deleted. If true is specified, no DB snapshot is created. If false is specified, a DB snapshot is created before the DB cluster is deleted, using the value from `final_snapshot_identifier`. Default is `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">snapshot_<wbr>identifier<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Specifies whether or not to create this cluster from a snapshot. You can use either the name or ARN when specifying a DB cluster snapshot, or the ARN when specifying a DB snapshot.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">storage_<wbr>encrypted<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Specifies whether the DB cluster is encrypted. The default is `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the DB cluster.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">vpc_<wbr>security_<wbr>group_<wbr>ids<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}List of VPC security groups to associate
with the Cluster
{{% /md %}}</dd>

</dl>
{{% /choosable %}}




## Cluster Output Properties

The following output properties are available:




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Apply<wbr>Immediately<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Specifies whether any cluster modifications
are applied immediately, or during the next maintenance window. Default is
`false`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of cluster
{{% /md %}}</dd>

    <dt class="property-"
            title="">Availability<wbr>Zones<span class="property-indicator"></span>
        <span class="property-type">List<string></span>
    </dt>
    <dd>{{% md %}}A list of EC2 Availability Zones that
instances in the DB cluster can be created in.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Backup<wbr>Retention<wbr>Period<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The days to retain backups for. Default `1`
{{% /md %}}</dd>

    <dt class="property-"
            title="">Cluster<wbr>Identifier<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The cluster identifier. If omitted, this provider will assign a random, unique identifier.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Cluster<wbr>Identifier<wbr>Prefix<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Creates a unique cluster identifier beginning with the specified prefix. Conflicts with `cluster_identifer`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Cluster<wbr>Members<span class="property-indicator"></span>
        <span class="property-type">List<string></span>
    </dt>
    <dd>{{% md %}}List of DocDB Instances that are a part of this cluster
{{% /md %}}</dd>

    <dt class="property-"
            title="">Cluster<wbr>Resource<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The DocDB Cluster Resource ID
{{% /md %}}</dd>

    <dt class="property-"
            title="">Db<wbr>Cluster<wbr>Parameter<wbr>Group<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}A cluster parameter group to associate with the cluster.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Db<wbr>Subnet<wbr>Group<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}A DB subnet group to associate with this DB instance.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Enabled<wbr>Cloudwatch<wbr>Logs<wbr>Exports<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}List of log types to export to cloudwatch. If omitted, no logs will be exported.
The following log types are supported: `audit`, `profiler`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Endpoint<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The DNS address of the DocDB instance
{{% /md %}}</dd>

    <dt class="property-"
            title="">Engine<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the database engine to be used for this DB cluster. Defaults to `docdb`. Valid Values: `docdb`
{{% /md %}}</dd>

    <dt class="property-"
            title="">Engine<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The database engine version. Updating this argument results in an outage.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Final<wbr>Snapshot<wbr>Identifier<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of your final DB snapshot
when this DB cluster is deleted. If omitted, no final snapshot will be
made.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Hosted<wbr>Zone<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Route53 Hosted Zone ID of the endpoint
{{% /md %}}</dd>

    <dt class="property-"
            title="">Kms<wbr>Key<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN for the KMS encryption key. When specifying `kms_key_id`, `storage_encrypted` needs to be set to true.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Master<wbr>Password<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Password for the master DB user. Note that this may
show up in logs, and it will be stored in the state file. Please refer to the DocDB Naming Constraints.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Master<wbr>Username<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Username for the master DB user. 
{{% /md %}}</dd>

    <dt class="property-"
            title="">Port<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The port on which the DB accepts connections
{{% /md %}}</dd>

    <dt class="property-"
            title="">Preferred<wbr>Backup<wbr>Window<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The daily time range during which automated backups are created if automated backups are enabled using the BackupRetentionPeriod parameter.Time in UTC
Default: A 30-minute window selected at random from an 8-hour block of time per region. e.g. 04:00-09:00
{{% /md %}}</dd>

    <dt class="property-"
            title="">Preferred<wbr>Maintenance<wbr>Window<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">Reader<wbr>Endpoint<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}A read-only endpoint for the DocDB cluster, automatically load-balanced across replicas
{{% /md %}}</dd>

    <dt class="property-"
            title="">Skip<wbr>Final<wbr>Snapshot<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Determines whether a final DB snapshot is created before the DB cluster is deleted. If true is specified, no DB snapshot is created. If false is specified, a DB snapshot is created before the DB cluster is deleted, using the value from `final_snapshot_identifier`. Default is `false`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Snapshot<wbr>Identifier<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Specifies whether or not to create this cluster from a snapshot. You can use either the name or ARN when specifying a DB cluster snapshot, or the ARN when specifying a DB snapshot.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Storage<wbr>Encrypted<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Specifies whether the DB cluster is encrypted. The default is `false`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the DB cluster.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Vpc<wbr>Security<wbr>Group<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">List<string></span>
    </dt>
    <dd>{{% md %}}List of VPC security groups to associate
with the Cluster
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Apply<wbr>Immediately<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Specifies whether any cluster modifications
are applied immediately, or during the next maintenance window. Default is
`false`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of cluster
{{% /md %}}</dd>

    <dt class="property-"
            title="">Availability<wbr>Zones<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}A list of EC2 Availability Zones that
instances in the DB cluster can be created in.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Backup<wbr>Retention<wbr>Period<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The days to retain backups for. Default `1`
{{% /md %}}</dd>

    <dt class="property-"
            title="">Cluster<wbr>Identifier<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The cluster identifier. If omitted, this provider will assign a random, unique identifier.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Cluster<wbr>Identifier<wbr>Prefix<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Creates a unique cluster identifier beginning with the specified prefix. Conflicts with `cluster_identifer`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Cluster<wbr>Members<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}List of DocDB Instances that are a part of this cluster
{{% /md %}}</dd>

    <dt class="property-"
            title="">Cluster<wbr>Resource<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The DocDB Cluster Resource ID
{{% /md %}}</dd>

    <dt class="property-"
            title="">Db<wbr>Cluster<wbr>Parameter<wbr>Group<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}A cluster parameter group to associate with the cluster.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Db<wbr>Subnet<wbr>Group<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}A DB subnet group to associate with this DB instance.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Enabled<wbr>Cloudwatch<wbr>Logs<wbr>Exports<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}List of log types to export to cloudwatch. If omitted, no logs will be exported.
The following log types are supported: `audit`, `profiler`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Endpoint<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The DNS address of the DocDB instance
{{% /md %}}</dd>

    <dt class="property-"
            title="">Engine<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name of the database engine to be used for this DB cluster. Defaults to `docdb`. Valid Values: `docdb`
{{% /md %}}</dd>

    <dt class="property-"
            title="">Engine<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The database engine version. Updating this argument results in an outage.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Final<wbr>Snapshot<wbr>Identifier<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name of your final DB snapshot
when this DB cluster is deleted. If omitted, no final snapshot will be
made.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Hosted<wbr>Zone<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Route53 Hosted Zone ID of the endpoint
{{% /md %}}</dd>

    <dt class="property-"
            title="">Kms<wbr>Key<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN for the KMS encryption key. When specifying `kms_key_id`, `storage_encrypted` needs to be set to true.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Master<wbr>Password<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Password for the master DB user. Note that this may
show up in logs, and it will be stored in the state file. Please refer to the DocDB Naming Constraints.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Master<wbr>Username<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Username for the master DB user. 
{{% /md %}}</dd>

    <dt class="property-"
            title="">Port<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The port on which the DB accepts connections
{{% /md %}}</dd>

    <dt class="property-"
            title="">Preferred<wbr>Backup<wbr>Window<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The daily time range during which automated backups are created if automated backups are enabled using the BackupRetentionPeriod parameter.Time in UTC
Default: A 30-minute window selected at random from an 8-hour block of time per region. e.g. 04:00-09:00
{{% /md %}}</dd>

    <dt class="property-"
            title="">Preferred<wbr>Maintenance<wbr>Window<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">Reader<wbr>Endpoint<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}A read-only endpoint for the DocDB cluster, automatically load-balanced across replicas
{{% /md %}}</dd>

    <dt class="property-"
            title="">Skip<wbr>Final<wbr>Snapshot<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Determines whether a final DB snapshot is created before the DB cluster is deleted. If true is specified, no DB snapshot is created. If false is specified, a DB snapshot is created before the DB cluster is deleted, using the value from `final_snapshot_identifier`. Default is `false`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Snapshot<wbr>Identifier<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Specifies whether or not to create this cluster from a snapshot. You can use either the name or ARN when specifying a DB cluster snapshot, or the ARN when specifying a DB snapshot.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Storage<wbr>Encrypted<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Specifies whether the DB cluster is encrypted. The default is `false`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the DB cluster.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Vpc<wbr>Security<wbr>Group<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}List of VPC security groups to associate
with the Cluster
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">apply<wbr>Immediately<span class="property-indicator"></span>
        <span class="property-type">boolean</span>
    </dt>
    <dd>{{% md %}}Specifies whether any cluster modifications
are applied immediately, or during the next maintenance window. Default is
`false`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of cluster
{{% /md %}}</dd>

    <dt class="property-"
            title="">availability<wbr>Zones<span class="property-indicator"></span>
        <span class="property-type">string[]</span>
    </dt>
    <dd>{{% md %}}A list of EC2 Availability Zones that
instances in the DB cluster can be created in.
{{% /md %}}</dd>

    <dt class="property-"
            title="">backup<wbr>Retention<wbr>Period<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The days to retain backups for. Default `1`
{{% /md %}}</dd>

    <dt class="property-"
            title="">cluster<wbr>Identifier<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The cluster identifier. If omitted, this provider will assign a random, unique identifier.
{{% /md %}}</dd>

    <dt class="property-"
            title="">cluster<wbr>Identifier<wbr>Prefix<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Creates a unique cluster identifier beginning with the specified prefix. Conflicts with `cluster_identifer`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">cluster<wbr>Members<span class="property-indicator"></span>
        <span class="property-type">string[]</span>
    </dt>
    <dd>{{% md %}}List of DocDB Instances that are a part of this cluster
{{% /md %}}</dd>

    <dt class="property-"
            title="">cluster<wbr>Resource<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The DocDB Cluster Resource ID
{{% /md %}}</dd>

    <dt class="property-"
            title="">db<wbr>Cluster<wbr>Parameter<wbr>Group<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}A cluster parameter group to associate with the cluster.
{{% /md %}}</dd>

    <dt class="property-"
            title="">db<wbr>Subnet<wbr>Group<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}A DB subnet group to associate with this DB instance.
{{% /md %}}</dd>

    <dt class="property-"
            title="">enabled<wbr>Cloudwatch<wbr>Logs<wbr>Exports<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}List of log types to export to cloudwatch. If omitted, no logs will be exported.
The following log types are supported: `audit`, `profiler`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">endpoint<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The DNS address of the DocDB instance
{{% /md %}}</dd>

    <dt class="property-"
            title="">engine<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the database engine to be used for this DB cluster. Defaults to `docdb`. Valid Values: `docdb`
{{% /md %}}</dd>

    <dt class="property-"
            title="">engine<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The database engine version. Updating this argument results in an outage.
{{% /md %}}</dd>

    <dt class="property-"
            title="">final<wbr>Snapshot<wbr>Identifier<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of your final DB snapshot
when this DB cluster is deleted. If omitted, no final snapshot will be
made.
{{% /md %}}</dd>

    <dt class="property-"
            title="">hosted<wbr>Zone<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Route53 Hosted Zone ID of the endpoint
{{% /md %}}</dd>

    <dt class="property-"
            title="">kms<wbr>Key<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN for the KMS encryption key. When specifying `kms_key_id`, `storage_encrypted` needs to be set to true.
{{% /md %}}</dd>

    <dt class="property-"
            title="">master<wbr>Password<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Password for the master DB user. Note that this may
show up in logs, and it will be stored in the state file. Please refer to the DocDB Naming Constraints.
{{% /md %}}</dd>

    <dt class="property-"
            title="">master<wbr>Username<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Username for the master DB user. 
{{% /md %}}</dd>

    <dt class="property-"
            title="">port<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The port on which the DB accepts connections
{{% /md %}}</dd>

    <dt class="property-"
            title="">preferred<wbr>Backup<wbr>Window<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The daily time range during which automated backups are created if automated backups are enabled using the BackupRetentionPeriod parameter.Time in UTC
Default: A 30-minute window selected at random from an 8-hour block of time per region. e.g. 04:00-09:00
{{% /md %}}</dd>

    <dt class="property-"
            title="">preferred<wbr>Maintenance<wbr>Window<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">reader<wbr>Endpoint<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}A read-only endpoint for the DocDB cluster, automatically load-balanced across replicas
{{% /md %}}</dd>

    <dt class="property-"
            title="">skip<wbr>Final<wbr>Snapshot<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Determines whether a final DB snapshot is created before the DB cluster is deleted. If true is specified, no DB snapshot is created. If false is specified, a DB snapshot is created before the DB cluster is deleted, using the value from `final_snapshot_identifier`. Default is `false`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">snapshot<wbr>Identifier<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Specifies whether or not to create this cluster from a snapshot. You can use either the name or ARN when specifying a DB cluster snapshot, or the ARN when specifying a DB snapshot.
{{% /md %}}</dd>

    <dt class="property-"
            title="">storage<wbr>Encrypted<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Specifies whether the DB cluster is encrypted. The default is `false`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the DB cluster.
{{% /md %}}</dd>

    <dt class="property-"
            title="">vpc<wbr>Security<wbr>Group<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">string[]</span>
    </dt>
    <dd>{{% md %}}List of VPC security groups to associate
with the Cluster
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">apply_<wbr>immediately<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Specifies whether any cluster modifications
are applied immediately, or during the next maintenance window. Default is
`false`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of cluster
{{% /md %}}</dd>

    <dt class="property-"
            title="">availability_<wbr>zones<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}A list of EC2 Availability Zones that
instances in the DB cluster can be created in.
{{% /md %}}</dd>

    <dt class="property-"
            title="">backup_<wbr>retention_<wbr>period<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The days to retain backups for. Default `1`
{{% /md %}}</dd>

    <dt class="property-"
            title="">cluster_<wbr>identifier<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The cluster identifier. If omitted, this provider will assign a random, unique identifier.
{{% /md %}}</dd>

    <dt class="property-"
            title="">cluster_<wbr>identifier_<wbr>prefix<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Creates a unique cluster identifier beginning with the specified prefix. Conflicts with `cluster_identifer`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">cluster_<wbr>members<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}List of DocDB Instances that are a part of this cluster
{{% /md %}}</dd>

    <dt class="property-"
            title="">cluster_<wbr>resource_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The DocDB Cluster Resource ID
{{% /md %}}</dd>

    <dt class="property-"
            title="">db_<wbr>cluster_<wbr>parameter_<wbr>group_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A cluster parameter group to associate with the cluster.
{{% /md %}}</dd>

    <dt class="property-"
            title="">db_<wbr>subnet_<wbr>group_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A DB subnet group to associate with this DB instance.
{{% /md %}}</dd>

    <dt class="property-"
            title="">enabled_<wbr>cloudwatch_<wbr>logs_<wbr>exports<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}List of log types to export to cloudwatch. If omitted, no logs will be exported.
The following log types are supported: `audit`, `profiler`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">endpoint<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The DNS address of the DocDB instance
{{% /md %}}</dd>

    <dt class="property-"
            title="">engine<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the database engine to be used for this DB cluster. Defaults to `docdb`. Valid Values: `docdb`
{{% /md %}}</dd>

    <dt class="property-"
            title="">engine_<wbr>version<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The database engine version. Updating this argument results in an outage.
{{% /md %}}</dd>

    <dt class="property-"
            title="">final_<wbr>snapshot_<wbr>identifier<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of your final DB snapshot
when this DB cluster is deleted. If omitted, no final snapshot will be
made.
{{% /md %}}</dd>

    <dt class="property-"
            title="">hosted_<wbr>zone_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The Route53 Hosted Zone ID of the endpoint
{{% /md %}}</dd>

    <dt class="property-"
            title="">kms_<wbr>key_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ARN for the KMS encryption key. When specifying `kms_key_id`, `storage_encrypted` needs to be set to true.
{{% /md %}}</dd>

    <dt class="property-"
            title="">master_<wbr>password<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Password for the master DB user. Note that this may
show up in logs, and it will be stored in the state file. Please refer to the DocDB Naming Constraints.
{{% /md %}}</dd>

    <dt class="property-"
            title="">master_<wbr>username<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Username for the master DB user. 
{{% /md %}}</dd>

    <dt class="property-"
            title="">port<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The port on which the DB accepts connections
{{% /md %}}</dd>

    <dt class="property-"
            title="">preferred_<wbr>backup_<wbr>window<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The daily time range during which automated backups are created if automated backups are enabled using the BackupRetentionPeriod parameter.Time in UTC
Default: A 30-minute window selected at random from an 8-hour block of time per region. e.g. 04:00-09:00
{{% /md %}}</dd>

    <dt class="property-"
            title="">preferred_<wbr>maintenance_<wbr>window<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">reader_<wbr>endpoint<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A read-only endpoint for the DocDB cluster, automatically load-balanced across replicas
{{% /md %}}</dd>

    <dt class="property-"
            title="">skip_<wbr>final_<wbr>snapshot<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Determines whether a final DB snapshot is created before the DB cluster is deleted. If true is specified, no DB snapshot is created. If false is specified, a DB snapshot is created before the DB cluster is deleted, using the value from `final_snapshot_identifier`. Default is `false`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">snapshot_<wbr>identifier<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Specifies whether or not to create this cluster from a snapshot. You can use either the name or ARN when specifying a DB cluster snapshot, or the ARN when specifying a DB snapshot.
{{% /md %}}</dd>

    <dt class="property-"
            title="">storage_<wbr>encrypted<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Specifies whether the DB cluster is encrypted. The default is `false`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the DB cluster.
{{% /md %}}</dd>

    <dt class="property-"
            title="">vpc_<wbr>security_<wbr>group_<wbr>ids<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}List of VPC security groups to associate
with the Cluster
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





## Look up an Existing Cluster Resource

{{< chooser language "javascript,typescript,python,go,csharp  " / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">pulumi.Input&lt;pulumi.ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/docdb/#ClusterState">ClusterState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/docdb/#Cluster">Cluster</a></span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>apply_immediately=None<span class="p">, </span>arn=None<span class="p">, </span>availability_zones=None<span class="p">, </span>backup_retention_period=None<span class="p">, </span>cluster_identifier=None<span class="p">, </span>cluster_identifier_prefix=None<span class="p">, </span>cluster_members=None<span class="p">, </span>cluster_resource_id=None<span class="p">, </span>db_cluster_parameter_group_name=None<span class="p">, </span>db_subnet_group_name=None<span class="p">, </span>enabled_cloudwatch_logs_exports=None<span class="p">, </span>endpoint=None<span class="p">, </span>engine=None<span class="p">, </span>engine_version=None<span class="p">, </span>final_snapshot_identifier=None<span class="p">, </span>hosted_zone_id=None<span class="p">, </span>kms_key_id=None<span class="p">, </span>master_password=None<span class="p">, </span>master_username=None<span class="p">, </span>port=None<span class="p">, </span>preferred_backup_window=None<span class="p">, </span>preferred_maintenance_window=None<span class="p">, </span>reader_endpoint=None<span class="p">, </span>skip_final_snapshot=None<span class="p">, </span>snapshot_identifier=None<span class="p">, </span>storage_encrypted=None<span class="p">, </span>tags=None<span class="p">, </span>vpc_security_group_ids=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetCluster<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">pulumi.IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/docdb?tab=doc#ClusterState">ClusterState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/docdb?tab=doc#Cluster">Cluster</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Docdb.Cluster.html">Cluster</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Pulumi.Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Docdb.ClusterState.html">ClusterState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
{{% /choosable %}}

Get an existing Cluster resource's state with the given name, ID, and optional extra properties used to qualify the lookup.

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
            title="Optional">Apply<wbr>Immediately<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Specifies whether any cluster modifications
are applied immediately, or during the next maintenance window. Default is
`false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of cluster
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Availability<wbr>Zones<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}A list of EC2 Availability Zones that
instances in the DB cluster can be created in.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Backup<wbr>Retention<wbr>Period<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The days to retain backups for. Default `1`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Cluster<wbr>Identifier<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The cluster identifier. If omitted, this provider will assign a random, unique identifier.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Cluster<wbr>Identifier<wbr>Prefix<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Creates a unique cluster identifier beginning with the specified prefix. Conflicts with `cluster_identifer`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Cluster<wbr>Members<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}List of DocDB Instances that are a part of this cluster
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Cluster<wbr>Resource<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The DocDB Cluster Resource ID
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Db<wbr>Cluster<wbr>Parameter<wbr>Group<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A cluster parameter group to associate with the cluster.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Db<wbr>Subnet<wbr>Group<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A DB subnet group to associate with this DB instance.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Enabled<wbr>Cloudwatch<wbr>Logs<wbr>Exports<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}List of log types to export to cloudwatch. If omitted, no logs will be exported.
The following log types are supported: `audit`, `profiler`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Endpoint<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The DNS address of the DocDB instance
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Engine<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the database engine to be used for this DB cluster. Defaults to `docdb`. Valid Values: `docdb`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Engine<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The database engine version. Updating this argument results in an outage.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Final<wbr>Snapshot<wbr>Identifier<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of your final DB snapshot
when this DB cluster is deleted. If omitted, no final snapshot will be
made.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Hosted<wbr>Zone<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The Route53 Hosted Zone ID of the endpoint
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Kms<wbr>Key<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ARN for the KMS encryption key. When specifying `kms_key_id`, `storage_encrypted` needs to be set to true.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Master<wbr>Password<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Password for the master DB user. Note that this may
show up in logs, and it will be stored in the state file. Please refer to the DocDB Naming Constraints.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Master<wbr>Username<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Username for the master DB user. 
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Port<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The port on which the DB accepts connections
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Preferred<wbr>Backup<wbr>Window<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The daily time range during which automated backups are created if automated backups are enabled using the BackupRetentionPeriod parameter.Time in UTC
Default: A 30-minute window selected at random from an 8-hour block of time per region. e.g. 04:00-09:00
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Preferred<wbr>Maintenance<wbr>Window<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Reader<wbr>Endpoint<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A read-only endpoint for the DocDB cluster, automatically load-balanced across replicas
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Skip<wbr>Final<wbr>Snapshot<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Determines whether a final DB snapshot is created before the DB cluster is deleted. If true is specified, no DB snapshot is created. If false is specified, a DB snapshot is created before the DB cluster is deleted, using the value from `final_snapshot_identifier`. Default is `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Snapshot<wbr>Identifier<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Specifies whether or not to create this cluster from a snapshot. You can use either the name or ARN when specifying a DB cluster snapshot, or the ARN when specifying a DB snapshot.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Storage<wbr>Encrypted<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Specifies whether the DB cluster is encrypted. The default is `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the DB cluster.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Vpc<wbr>Security<wbr>Group<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}List of VPC security groups to associate
with the Cluster
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Apply<wbr>Immediately<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Specifies whether any cluster modifications
are applied immediately, or during the next maintenance window. Default is
`false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of cluster
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Availability<wbr>Zones<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}A list of EC2 Availability Zones that
instances in the DB cluster can be created in.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Backup<wbr>Retention<wbr>Period<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The days to retain backups for. Default `1`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Cluster<wbr>Identifier<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The cluster identifier. If omitted, this provider will assign a random, unique identifier.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Cluster<wbr>Identifier<wbr>Prefix<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Creates a unique cluster identifier beginning with the specified prefix. Conflicts with `cluster_identifer`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Cluster<wbr>Members<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}List of DocDB Instances that are a part of this cluster
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Cluster<wbr>Resource<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The DocDB Cluster Resource ID
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Db<wbr>Cluster<wbr>Parameter<wbr>Group<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}A cluster parameter group to associate with the cluster.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Db<wbr>Subnet<wbr>Group<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}A DB subnet group to associate with this DB instance.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Enabled<wbr>Cloudwatch<wbr>Logs<wbr>Exports<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}List of log types to export to cloudwatch. If omitted, no logs will be exported.
The following log types are supported: `audit`, `profiler`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Endpoint<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The DNS address of the DocDB instance
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Engine<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name of the database engine to be used for this DB cluster. Defaults to `docdb`. Valid Values: `docdb`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Engine<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The database engine version. Updating this argument results in an outage.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Final<wbr>Snapshot<wbr>Identifier<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name of your final DB snapshot
when this DB cluster is deleted. If omitted, no final snapshot will be
made.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Hosted<wbr>Zone<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The Route53 Hosted Zone ID of the endpoint
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Kms<wbr>Key<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The ARN for the KMS encryption key. When specifying `kms_key_id`, `storage_encrypted` needs to be set to true.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Master<wbr>Password<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Password for the master DB user. Note that this may
show up in logs, and it will be stored in the state file. Please refer to the DocDB Naming Constraints.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Master<wbr>Username<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Username for the master DB user. 
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Port<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The port on which the DB accepts connections
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Preferred<wbr>Backup<wbr>Window<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The daily time range during which automated backups are created if automated backups are enabled using the BackupRetentionPeriod parameter.Time in UTC
Default: A 30-minute window selected at random from an 8-hour block of time per region. e.g. 04:00-09:00
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Preferred<wbr>Maintenance<wbr>Window<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Reader<wbr>Endpoint<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}A read-only endpoint for the DocDB cluster, automatically load-balanced across replicas
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Skip<wbr>Final<wbr>Snapshot<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Determines whether a final DB snapshot is created before the DB cluster is deleted. If true is specified, no DB snapshot is created. If false is specified, a DB snapshot is created before the DB cluster is deleted, using the value from `final_snapshot_identifier`. Default is `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Snapshot<wbr>Identifier<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Specifies whether or not to create this cluster from a snapshot. You can use either the name or ARN when specifying a DB cluster snapshot, or the ARN when specifying a DB snapshot.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Storage<wbr>Encrypted<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Specifies whether the DB cluster is encrypted. The default is `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the DB cluster.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Vpc<wbr>Security<wbr>Group<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}List of VPC security groups to associate
with the Cluster
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">apply<wbr>Immediately<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Specifies whether any cluster modifications
are applied immediately, or during the next maintenance window. Default is
`false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of cluster
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">availability<wbr>Zones<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}A list of EC2 Availability Zones that
instances in the DB cluster can be created in.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">backup<wbr>Retention<wbr>Period<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The days to retain backups for. Default `1`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">cluster<wbr>Identifier<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The cluster identifier. If omitted, this provider will assign a random, unique identifier.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">cluster<wbr>Identifier<wbr>Prefix<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Creates a unique cluster identifier beginning with the specified prefix. Conflicts with `cluster_identifer`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">cluster<wbr>Members<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}List of DocDB Instances that are a part of this cluster
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">cluster<wbr>Resource<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The DocDB Cluster Resource ID
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">db<wbr>Cluster<wbr>Parameter<wbr>Group<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A cluster parameter group to associate with the cluster.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">db<wbr>Subnet<wbr>Group<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A DB subnet group to associate with this DB instance.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">enabled<wbr>Cloudwatch<wbr>Logs<wbr>Exports<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}List of log types to export to cloudwatch. If omitted, no logs will be exported.
The following log types are supported: `audit`, `profiler`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">endpoint<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The DNS address of the DocDB instance
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">engine<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the database engine to be used for this DB cluster. Defaults to `docdb`. Valid Values: `docdb`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">engine<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The database engine version. Updating this argument results in an outage.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">final<wbr>Snapshot<wbr>Identifier<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of your final DB snapshot
when this DB cluster is deleted. If omitted, no final snapshot will be
made.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">hosted<wbr>Zone<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The Route53 Hosted Zone ID of the endpoint
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">kms<wbr>Key<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ARN for the KMS encryption key. When specifying `kms_key_id`, `storage_encrypted` needs to be set to true.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">master<wbr>Password<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Password for the master DB user. Note that this may
show up in logs, and it will be stored in the state file. Please refer to the DocDB Naming Constraints.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">master<wbr>Username<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Username for the master DB user. 
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">port<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The port on which the DB accepts connections
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">preferred<wbr>Backup<wbr>Window<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The daily time range during which automated backups are created if automated backups are enabled using the BackupRetentionPeriod parameter.Time in UTC
Default: A 30-minute window selected at random from an 8-hour block of time per region. e.g. 04:00-09:00
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">preferred<wbr>Maintenance<wbr>Window<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">reader<wbr>Endpoint<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A read-only endpoint for the DocDB cluster, automatically load-balanced across replicas
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">skip<wbr>Final<wbr>Snapshot<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Determines whether a final DB snapshot is created before the DB cluster is deleted. If true is specified, no DB snapshot is created. If false is specified, a DB snapshot is created before the DB cluster is deleted, using the value from `final_snapshot_identifier`. Default is `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">snapshot<wbr>Identifier<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Specifies whether or not to create this cluster from a snapshot. You can use either the name or ARN when specifying a DB cluster snapshot, or the ARN when specifying a DB snapshot.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">storage<wbr>Encrypted<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Specifies whether the DB cluster is encrypted. The default is `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the DB cluster.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">vpc<wbr>Security<wbr>Group<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}List of VPC security groups to associate
with the Cluster
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">apply_<wbr>immediately<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Specifies whether any cluster modifications
are applied immediately, or during the next maintenance window. Default is
`false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of cluster
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">availability_<wbr>zones<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}A list of EC2 Availability Zones that
instances in the DB cluster can be created in.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">backup_<wbr>retention_<wbr>period<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The days to retain backups for. Default `1`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">cluster_<wbr>identifier<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The cluster identifier. If omitted, this provider will assign a random, unique identifier.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">cluster_<wbr>identifier_<wbr>prefix<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Creates a unique cluster identifier beginning with the specified prefix. Conflicts with `cluster_identifer`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">cluster_<wbr>members<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}List of DocDB Instances that are a part of this cluster
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">cluster_<wbr>resource_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The DocDB Cluster Resource ID
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">db_<wbr>cluster_<wbr>parameter_<wbr>group_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A cluster parameter group to associate with the cluster.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">db_<wbr>subnet_<wbr>group_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A DB subnet group to associate with this DB instance.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">enabled_<wbr>cloudwatch_<wbr>logs_<wbr>exports<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}List of log types to export to cloudwatch. If omitted, no logs will be exported.
The following log types are supported: `audit`, `profiler`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">endpoint<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The DNS address of the DocDB instance
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">engine<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the database engine to be used for this DB cluster. Defaults to `docdb`. Valid Values: `docdb`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">engine_<wbr>version<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The database engine version. Updating this argument results in an outage.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">final_<wbr>snapshot_<wbr>identifier<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of your final DB snapshot
when this DB cluster is deleted. If omitted, no final snapshot will be
made.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">hosted_<wbr>zone_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The Route53 Hosted Zone ID of the endpoint
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">kms_<wbr>key_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ARN for the KMS encryption key. When specifying `kms_key_id`, `storage_encrypted` needs to be set to true.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">master_<wbr>password<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Password for the master DB user. Note that this may
show up in logs, and it will be stored in the state file. Please refer to the DocDB Naming Constraints.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">master_<wbr>username<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Username for the master DB user. 
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">port<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The port on which the DB accepts connections
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">preferred_<wbr>backup_<wbr>window<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The daily time range during which automated backups are created if automated backups are enabled using the BackupRetentionPeriod parameter.Time in UTC
Default: A 30-minute window selected at random from an 8-hour block of time per region. e.g. 04:00-09:00
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">preferred_<wbr>maintenance_<wbr>window<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">reader_<wbr>endpoint<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A read-only endpoint for the DocDB cluster, automatically load-balanced across replicas
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">skip_<wbr>final_<wbr>snapshot<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Determines whether a final DB snapshot is created before the DB cluster is deleted. If true is specified, no DB snapshot is created. If false is specified, a DB snapshot is created before the DB cluster is deleted, using the value from `final_snapshot_identifier`. Default is `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">snapshot_<wbr>identifier<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Specifies whether or not to create this cluster from a snapshot. You can use either the name or ARN when specifying a DB cluster snapshot, or the ARN when specifying a DB snapshot.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">storage_<wbr>encrypted<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Specifies whether the DB cluster is encrypted. The default is `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the DB cluster.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">vpc_<wbr>security_<wbr>group_<wbr>ids<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}List of VPC security groups to associate
with the Cluster
{{% /md %}}</dd>

</dl>
{{% /choosable %}}







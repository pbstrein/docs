
---
title: "ReplicationGroup"
block_external_search_index: true
---

Provides an ElastiCache Replication Group resource.
For working with Memcached or single primary Redis instances (Cluster Mode Disabled), see the
[`aws.elasticache.Cluster` resource](https://www.terraform.io/docs/providers/aws/r/elasticache_cluster.html).

> **Note:** When you change an attribute, such as `engine_version`, by
default the ElastiCache API applies it in the next maintenance window. Because
of this, this provider may report a difference in its planning phase because the
actual modification has not yet taken place. You can use the
`apply_immediately` flag to instruct the service to apply the change
immediately. Using `apply_immediately` can result in a brief downtime as
servers reboots.

## Example Usage

### Redis Cluster Mode Disabled

To create a single shard primary with single read replica:

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const example = new aws.elasticache.ReplicationGroup("example", {
    automaticFailoverEnabled: true,
    availabilityZones: [
        "us-west-2a",
        "us-west-2b",
    ],
    nodeType: "cache.m4.large",
    numberCacheClusters: 2,
    parameterGroupName: "default.redis3.2",
    port: 6379,
    replicationGroupDescription: "test description",
});
```

You have two options for adjusting the number of replicas:

* Adjusting `number_cache_clusters` directly. This will attempt to automatically add or remove replicas, but provides no granular control (e.g. preferred availability zone, cache cluster ID) for the added or removed replicas. This also currently expects cache cluster IDs in the form of `replication_group_id-00#`.
* Otherwise for fine grained control of the underlying cache clusters, they can be added or removed with the [`aws.elasticache.Cluster` resource](https://www.terraform.io/docs/providers/aws/r/elasticache_cluster.html) and its `replication_group_id` attribute. In this situation, you will need to utilize the [lifecycle configuration block](https://www.terraform.io/docs/configuration/resources.html) with `ignore_changes` to prevent perpetual differences with the `number_cache_cluster` attribute.

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const example = new aws.elasticache.ReplicationGroup("example", {
    automaticFailoverEnabled: true,
    availabilityZones: [
        "us-west-2a",
        "us-west-2b",
    ],
    nodeType: "cache.m4.large",
    numberCacheClusters: 2,
    parameterGroupName: "default.redis3.2",
    port: 6379,
    replicationGroupDescription: "test description",
}, {ignoreChanges: ["numberCacheClusters"]});
const replica = new aws.elasticache.Cluster("replica", {
    replicationGroupId: example.id,
});
```

### Redis Cluster Mode Enabled

To create two shards with a primary and a single read replica each:

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const baz = new aws.elasticache.ReplicationGroup("baz", {
    automaticFailoverEnabled: true,
    clusterMode: {
        numNodeGroups: 2,
        replicasPerNodeGroup: 1,
    },
    nodeType: "cache.t2.small",
    parameterGroupName: "default.redis3.2.cluster.on",
    port: 6379,
    replicationGroupDescription: "test description",
});
```

> **Note:** We currently do not support passing a `primary_cluster_id` in order to create the Replication Group.

> **Note:** Automatic Failover is unavailable for Redis versions earlier than 2.8.6,
and unavailable on T1 node types. For T2 node types, it is only available on Redis version 3.2.4 or later with cluster mode enabled. See the [High Availability Using Replication Groups](https://docs.aws.amazon.com/AmazonElastiCache/latest/red-ug/Replication.html) guide
for full details on using Replication Groups.

> This content is derived from https://github.com/terraform-providers/terraform-provider-aws/blob/master/website/docs/r/elasticache_replication_group.html.markdown.



## Create a ReplicationGroup Resource

{{< chooser language "javascript,typescript,python,go,csharp" / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/elasticache/#ReplicationGroup">ReplicationGroup</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/elasticache/#ReplicationGroupArgs">ReplicationGroupArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">ReplicationGroup</span><span class="p">(resource_name, opts=None, </span>apply_immediately=None<span class="p">, </span>at_rest_encryption_enabled=None<span class="p">, </span>auth_token=None<span class="p">, </span>auto_minor_version_upgrade=None<span class="p">, </span>automatic_failover_enabled=None<span class="p">, </span>availability_zones=None<span class="p">, </span>cluster_mode=None<span class="p">, </span>engine=None<span class="p">, </span>engine_version=None<span class="p">, </span>kms_key_id=None<span class="p">, </span>maintenance_window=None<span class="p">, </span>node_type=None<span class="p">, </span>notification_topic_arn=None<span class="p">, </span>number_cache_clusters=None<span class="p">, </span>parameter_group_name=None<span class="p">, </span>port=None<span class="p">, </span>replication_group_description=None<span class="p">, </span>replication_group_id=None<span class="p">, </span>security_group_ids=None<span class="p">, </span>security_group_names=None<span class="p">, </span>snapshot_arns=None<span class="p">, </span>snapshot_name=None<span class="p">, </span>snapshot_retention_limit=None<span class="p">, </span>snapshot_window=None<span class="p">, </span>subnet_group_name=None<span class="p">, </span>tags=None<span class="p">, </span>transit_encryption_enabled=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewReplicationGroup<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/elasticache?tab=doc#ReplicationGroupArgs">ReplicationGroupArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/elasticache?tab=doc#ReplicationGroup">ReplicationGroup</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Elasticache.ReplicationGroup.html">ReplicationGroup</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Elasticache.ReplicationGroupArgs.html">ReplicationGroupArgs</a></span> <span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
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
    <dd>{{% md %}}Specifies whether any modifications are applied immediately, or during the next maintenance window. Default is `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">At<wbr>Rest<wbr>Encryption<wbr>Enabled<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Whether to enable encryption at rest.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Auth<wbr>Token<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The password used to access a password protected server. Can be specified only if `transit_encryption_enabled = true`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Auto<wbr>Minor<wbr>Version<wbr>Upgrade<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Specifies whether a minor engine upgrades will be applied automatically to the underlying Cache Cluster instances during the maintenance window. Defaults to `true`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Automatic<wbr>Failover<wbr>Enabled<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Specifies whether a read-only replica will be automatically promoted to read/write primary if the existing primary fails. If true, Multi-AZ is enabled for this replication group. If false, Multi-AZ is disabled for this replication group. Must be enabled for Redis (cluster mode enabled) replication groups. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Availability<wbr>Zones<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}A list of EC2 availability zones in which the replication group&#39;s cache clusters will be created. The order of the availability zones in the list is not important.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Cluster<wbr>Mode<span class="property-indicator"></span>
        <span class="property-type"><a href="#replicationgroupclustermode">Replication<wbr>Group<wbr>Cluster<wbr>Mode<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}Create a native redis cluster. `automatic_failover_enabled` must be set to true. Cluster Mode documented below. Only 1 `cluster_mode` block is allowed.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Engine<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the cache engine to be used for the clusters in this replication group. e.g. `redis`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Engine<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The version number of the cache engine to be used for the cache clusters in this replication group.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Kms<wbr>Key<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ARN of the key that you wish to use if encrypting at rest. If not supplied, uses service managed encryption. Can be specified only if `at_rest_encryption_enabled = true`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Maintenance<wbr>Window<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Specifies the weekly time range for when maintenance
on the cache cluster is performed. The format is `ddd:hh24:mi-ddd:hh24:mi` (24H Clock UTC).
The minimum maintenance window is a 60 minute period. Example: `sun:05:00-sun:09:00`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Node<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The compute and memory capacity of the nodes in the node group.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Notification<wbr>Topic<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}An Amazon Resource Name (ARN) of an
SNS topic to send ElastiCache notifications to. Example:
`arn:aws:sns:us-east-1:012345678999:my_sns_topic`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Number<wbr>Cache<wbr>Clusters<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The number of cache clusters (primary and replicas) this replication group will have. If Multi-AZ is enabled, the value of this parameter must be at least 2. Updates will occur before other modifications.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Parameter<wbr>Group<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the parameter group to associate with this replication group. If this argument is omitted, the default cache parameter group for the specified engine is used.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Port<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The port number on which each of the cache nodes will accept connections. For Memcache the default is 11211, and for Redis the default port is 6379.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Replication<wbr>Group<wbr>Description<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}A user-created description for the replication group.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Replication<wbr>Group<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The replication group identifier. This parameter is stored as a lowercase string.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Security<wbr>Group<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}One or more Amazon VPC security groups associated with this replication group. Use this parameter only when you are creating a replication group in an Amazon Virtual Private Cloud
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Security<wbr>Group<wbr>Names<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}A list of cache security group names to associate with this replication group.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Snapshot<wbr>Arns<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}A single-element string list containing an
Amazon Resource Name (ARN) of a Redis RDB snapshot file stored in Amazon S3.
Example: `arn:aws:s3:::my_bucket/snapshot1.rdb`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Snapshot<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of a snapshot from which to restore data into the new node group. Changing the `snapshot_name` forces a new resource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Snapshot<wbr>Retention<wbr>Limit<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The number of days for which ElastiCache will
retain automatic cache cluster snapshots before deleting them. For example, if you set
SnapshotRetentionLimit to 5, then a snapshot that was taken today will be retained for 5 days
before being deleted. If the value of SnapshotRetentionLimit is set to zero (0), backups are turned off.
Please note that setting a `snapshot_retention_limit` is not supported on cache.t1.micro or cache.t2.* cache nodes
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Snapshot<wbr>Window<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The daily time range (in UTC) during which ElastiCache will
begin taking a daily snapshot of your cache cluster. The minimum snapshot window is a 60 minute period. Example: `05:00-09:00`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Subnet<wbr>Group<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the cache subnet group to be used for the replication group.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Transit<wbr>Encryption<wbr>Enabled<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Whether to enable encryption in transit.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Apply<wbr>Immediately<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Specifies whether any modifications are applied immediately, or during the next maintenance window. Default is `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">At<wbr>Rest<wbr>Encryption<wbr>Enabled<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Whether to enable encryption at rest.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Auth<wbr>Token<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The password used to access a password protected server. Can be specified only if `transit_encryption_enabled = true`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Auto<wbr>Minor<wbr>Version<wbr>Upgrade<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Specifies whether a minor engine upgrades will be applied automatically to the underlying Cache Cluster instances during the maintenance window. Defaults to `true`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Automatic<wbr>Failover<wbr>Enabled<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Specifies whether a read-only replica will be automatically promoted to read/write primary if the existing primary fails. If true, Multi-AZ is enabled for this replication group. If false, Multi-AZ is disabled for this replication group. Must be enabled for Redis (cluster mode enabled) replication groups. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Availability<wbr>Zones<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}A list of EC2 availability zones in which the replication group&#39;s cache clusters will be created. The order of the availability zones in the list is not important.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Cluster<wbr>Mode<span class="property-indicator"></span>
        <span class="property-type"><a href="#replicationgroupclustermode">*Replication<wbr>Group<wbr>Cluster<wbr>Mode</a></span>
    </dt>
    <dd>{{% md %}}Create a native redis cluster. `automatic_failover_enabled` must be set to true. Cluster Mode documented below. Only 1 `cluster_mode` block is allowed.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Engine<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name of the cache engine to be used for the clusters in this replication group. e.g. `redis`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Engine<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The version number of the cache engine to be used for the cache clusters in this replication group.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Kms<wbr>Key<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The ARN of the key that you wish to use if encrypting at rest. If not supplied, uses service managed encryption. Can be specified only if `at_rest_encryption_enabled = true`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Maintenance<wbr>Window<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Specifies the weekly time range for when maintenance
on the cache cluster is performed. The format is `ddd:hh24:mi-ddd:hh24:mi` (24H Clock UTC).
The minimum maintenance window is a 60 minute period. Example: `sun:05:00-sun:09:00`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Node<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The compute and memory capacity of the nodes in the node group.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Notification<wbr>Topic<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}An Amazon Resource Name (ARN) of an
SNS topic to send ElastiCache notifications to. Example:
`arn:aws:sns:us-east-1:012345678999:my_sns_topic`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Number<wbr>Cache<wbr>Clusters<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The number of cache clusters (primary and replicas) this replication group will have. If Multi-AZ is enabled, the value of this parameter must be at least 2. Updates will occur before other modifications.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Parameter<wbr>Group<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name of the parameter group to associate with this replication group. If this argument is omitted, the default cache parameter group for the specified engine is used.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Port<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The port number on which each of the cache nodes will accept connections. For Memcache the default is 11211, and for Redis the default port is 6379.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Replication<wbr>Group<wbr>Description<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}A user-created description for the replication group.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Replication<wbr>Group<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The replication group identifier. This parameter is stored as a lowercase string.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Security<wbr>Group<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}One or more Amazon VPC security groups associated with this replication group. Use this parameter only when you are creating a replication group in an Amazon Virtual Private Cloud
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Security<wbr>Group<wbr>Names<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}A list of cache security group names to associate with this replication group.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Snapshot<wbr>Arns<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}A single-element string list containing an
Amazon Resource Name (ARN) of a Redis RDB snapshot file stored in Amazon S3.
Example: `arn:aws:s3:::my_bucket/snapshot1.rdb`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Snapshot<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name of a snapshot from which to restore data into the new node group. Changing the `snapshot_name` forces a new resource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Snapshot<wbr>Retention<wbr>Limit<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The number of days for which ElastiCache will
retain automatic cache cluster snapshots before deleting them. For example, if you set
SnapshotRetentionLimit to 5, then a snapshot that was taken today will be retained for 5 days
before being deleted. If the value of SnapshotRetentionLimit is set to zero (0), backups are turned off.
Please note that setting a `snapshot_retention_limit` is not supported on cache.t1.micro or cache.t2.* cache nodes
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Snapshot<wbr>Window<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The daily time range (in UTC) during which ElastiCache will
begin taking a daily snapshot of your cache cluster. The minimum snapshot window is a 60 minute period. Example: `05:00-09:00`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Subnet<wbr>Group<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name of the cache subnet group to be used for the replication group.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Transit<wbr>Encryption<wbr>Enabled<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Whether to enable encryption in transit.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">apply<wbr>Immediately<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Specifies whether any modifications are applied immediately, or during the next maintenance window. Default is `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">at<wbr>Rest<wbr>Encryption<wbr>Enabled<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Whether to enable encryption at rest.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">auth<wbr>Token<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The password used to access a password protected server. Can be specified only if `transit_encryption_enabled = true`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">auto<wbr>Minor<wbr>Version<wbr>Upgrade<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Specifies whether a minor engine upgrades will be applied automatically to the underlying Cache Cluster instances during the maintenance window. Defaults to `true`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">automatic<wbr>Failover<wbr>Enabled<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Specifies whether a read-only replica will be automatically promoted to read/write primary if the existing primary fails. If true, Multi-AZ is enabled for this replication group. If false, Multi-AZ is disabled for this replication group. Must be enabled for Redis (cluster mode enabled) replication groups. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">availability<wbr>Zones<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}A list of EC2 availability zones in which the replication group&#39;s cache clusters will be created. The order of the availability zones in the list is not important.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">cluster<wbr>Mode<span class="property-indicator"></span>
        <span class="property-type"><a href="#replicationgroupclustermode">Replication<wbr>Group<wbr>Cluster<wbr>Mode?</a></span>
    </dt>
    <dd>{{% md %}}Create a native redis cluster. `automatic_failover_enabled` must be set to true. Cluster Mode documented below. Only 1 `cluster_mode` block is allowed.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">engine<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the cache engine to be used for the clusters in this replication group. e.g. `redis`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">engine<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The version number of the cache engine to be used for the cache clusters in this replication group.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">kms<wbr>Key<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ARN of the key that you wish to use if encrypting at rest. If not supplied, uses service managed encryption. Can be specified only if `at_rest_encryption_enabled = true`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">maintenance<wbr>Window<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Specifies the weekly time range for when maintenance
on the cache cluster is performed. The format is `ddd:hh24:mi-ddd:hh24:mi` (24H Clock UTC).
The minimum maintenance window is a 60 minute period. Example: `sun:05:00-sun:09:00`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">node<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The compute and memory capacity of the nodes in the node group.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">notification<wbr>Topic<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}An Amazon Resource Name (ARN) of an
SNS topic to send ElastiCache notifications to. Example:
`arn:aws:sns:us-east-1:012345678999:my_sns_topic`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">number<wbr>Cache<wbr>Clusters<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The number of cache clusters (primary and replicas) this replication group will have. If Multi-AZ is enabled, the value of this parameter must be at least 2. Updates will occur before other modifications.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">parameter<wbr>Group<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the parameter group to associate with this replication group. If this argument is omitted, the default cache parameter group for the specified engine is used.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">port<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The port number on which each of the cache nodes will accept connections. For Memcache the default is 11211, and for Redis the default port is 6379.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">replication<wbr>Group<wbr>Description<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}A user-created description for the replication group.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">replication<wbr>Group<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The replication group identifier. This parameter is stored as a lowercase string.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">security<wbr>Group<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}One or more Amazon VPC security groups associated with this replication group. Use this parameter only when you are creating a replication group in an Amazon Virtual Private Cloud
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">security<wbr>Group<wbr>Names<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}A list of cache security group names to associate with this replication group.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">snapshot<wbr>Arns<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}A single-element string list containing an
Amazon Resource Name (ARN) of a Redis RDB snapshot file stored in Amazon S3.
Example: `arn:aws:s3:::my_bucket/snapshot1.rdb`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">snapshot<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of a snapshot from which to restore data into the new node group. Changing the `snapshot_name` forces a new resource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">snapshot<wbr>Retention<wbr>Limit<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The number of days for which ElastiCache will
retain automatic cache cluster snapshots before deleting them. For example, if you set
SnapshotRetentionLimit to 5, then a snapshot that was taken today will be retained for 5 days
before being deleted. If the value of SnapshotRetentionLimit is set to zero (0), backups are turned off.
Please note that setting a `snapshot_retention_limit` is not supported on cache.t1.micro or cache.t2.* cache nodes
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">snapshot<wbr>Window<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The daily time range (in UTC) during which ElastiCache will
begin taking a daily snapshot of your cache cluster. The minimum snapshot window is a 60 minute period. Example: `05:00-09:00`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">subnet<wbr>Group<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the cache subnet group to be used for the replication group.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">transit<wbr>Encryption<wbr>Enabled<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Whether to enable encryption in transit.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">apply_<wbr>immediately<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Specifies whether any modifications are applied immediately, or during the next maintenance window. Default is `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">at_<wbr>rest_<wbr>encryption_<wbr>enabled<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Whether to enable encryption at rest.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">auth_<wbr>token<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The password used to access a password protected server. Can be specified only if `transit_encryption_enabled = true`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">auto_<wbr>minor_<wbr>version_<wbr>upgrade<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Specifies whether a minor engine upgrades will be applied automatically to the underlying Cache Cluster instances during the maintenance window. Defaults to `true`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">automatic_<wbr>failover_<wbr>enabled<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Specifies whether a read-only replica will be automatically promoted to read/write primary if the existing primary fails. If true, Multi-AZ is enabled for this replication group. If false, Multi-AZ is disabled for this replication group. Must be enabled for Redis (cluster mode enabled) replication groups. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">availability_<wbr>zones<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}A list of EC2 availability zones in which the replication group&#39;s cache clusters will be created. The order of the availability zones in the list is not important.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">cluster_<wbr>mode<span class="property-indicator"></span>
        <span class="property-type"><a href="#replicationgroupclustermode">Dict[Replication<wbr>Group<wbr>Cluster<wbr>Mode]</a></span>
    </dt>
    <dd>{{% md %}}Create a native redis cluster. `automatic_failover_enabled` must be set to true. Cluster Mode documented below. Only 1 `cluster_mode` block is allowed.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">engine<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the cache engine to be used for the clusters in this replication group. e.g. `redis`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">engine_<wbr>version<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The version number of the cache engine to be used for the cache clusters in this replication group.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">kms_<wbr>key_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ARN of the key that you wish to use if encrypting at rest. If not supplied, uses service managed encryption. Can be specified only if `at_rest_encryption_enabled = true`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">maintenance_<wbr>window<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Specifies the weekly time range for when maintenance
on the cache cluster is performed. The format is `ddd:hh24:mi-ddd:hh24:mi` (24H Clock UTC).
The minimum maintenance window is a 60 minute period. Example: `sun:05:00-sun:09:00`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">node_<wbr>type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The compute and memory capacity of the nodes in the node group.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">notification_<wbr>topic_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}An Amazon Resource Name (ARN) of an
SNS topic to send ElastiCache notifications to. Example:
`arn:aws:sns:us-east-1:012345678999:my_sns_topic`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">number_<wbr>cache_<wbr>clusters<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The number of cache clusters (primary and replicas) this replication group will have. If Multi-AZ is enabled, the value of this parameter must be at least 2. Updates will occur before other modifications.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">parameter_<wbr>group_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the parameter group to associate with this replication group. If this argument is omitted, the default cache parameter group for the specified engine is used.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">port<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The port number on which each of the cache nodes will accept connections. For Memcache the default is 11211, and for Redis the default port is 6379.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">replication_<wbr>group_<wbr>description<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A user-created description for the replication group.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">replication_<wbr>group_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The replication group identifier. This parameter is stored as a lowercase string.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">security_<wbr>group_<wbr>ids<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}One or more Amazon VPC security groups associated with this replication group. Use this parameter only when you are creating a replication group in an Amazon Virtual Private Cloud
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">security_<wbr>group_<wbr>names<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}A list of cache security group names to associate with this replication group.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">snapshot_<wbr>arns<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}A single-element string list containing an
Amazon Resource Name (ARN) of a Redis RDB snapshot file stored in Amazon S3.
Example: `arn:aws:s3:::my_bucket/snapshot1.rdb`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">snapshot_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of a snapshot from which to restore data into the new node group. Changing the `snapshot_name` forces a new resource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">snapshot_<wbr>retention_<wbr>limit<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The number of days for which ElastiCache will
retain automatic cache cluster snapshots before deleting them. For example, if you set
SnapshotRetentionLimit to 5, then a snapshot that was taken today will be retained for 5 days
before being deleted. If the value of SnapshotRetentionLimit is set to zero (0), backups are turned off.
Please note that setting a `snapshot_retention_limit` is not supported on cache.t1.micro or cache.t2.* cache nodes
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">snapshot_<wbr>window<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The daily time range (in UTC) during which ElastiCache will
begin taking a daily snapshot of your cache cluster. The minimum snapshot window is a 60 minute period. Example: `05:00-09:00`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">subnet_<wbr>group_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the cache subnet group to be used for the replication group.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">transit_<wbr>encryption_<wbr>enabled<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Whether to enable encryption in transit.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}




## ReplicationGroup Output Properties

The following output properties are available:




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Apply<wbr>Immediately<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Specifies whether any modifications are applied immediately, or during the next maintenance window. Default is `false`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">At<wbr>Rest<wbr>Encryption<wbr>Enabled<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Whether to enable encryption at rest.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Auth<wbr>Token<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The password used to access a password protected server. Can be specified only if `transit_encryption_enabled = true`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Auto<wbr>Minor<wbr>Version<wbr>Upgrade<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Specifies whether a minor engine upgrades will be applied automatically to the underlying Cache Cluster instances during the maintenance window. Defaults to `true`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Automatic<wbr>Failover<wbr>Enabled<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Specifies whether a read-only replica will be automatically promoted to read/write primary if the existing primary fails. If true, Multi-AZ is enabled for this replication group. If false, Multi-AZ is disabled for this replication group. Must be enabled for Redis (cluster mode enabled) replication groups. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Availability<wbr>Zones<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}A list of EC2 availability zones in which the replication group&#39;s cache clusters will be created. The order of the availability zones in the list is not important.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Cluster<wbr>Mode<span class="property-indicator"></span>
        <span class="property-type"><a href="#replicationgroupclustermode">Replication<wbr>Group<wbr>Cluster<wbr>Mode</a></span>
    </dt>
    <dd>{{% md %}}Create a native redis cluster. `automatic_failover_enabled` must be set to true. Cluster Mode documented below. Only 1 `cluster_mode` block is allowed.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Configuration<wbr>Endpoint<wbr>Address<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The address of the replication group configuration endpoint when cluster mode is enabled.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Engine<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the cache engine to be used for the clusters in this replication group. e.g. `redis`
{{% /md %}}</dd>

    <dt class="property-"
            title="">Engine<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The version number of the cache engine to be used for the cache clusters in this replication group.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Kms<wbr>Key<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ARN of the key that you wish to use if encrypting at rest. If not supplied, uses service managed encryption. Can be specified only if `at_rest_encryption_enabled = true`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Maintenance<wbr>Window<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Specifies the weekly time range for when maintenance
on the cache cluster is performed. The format is `ddd:hh24:mi-ddd:hh24:mi` (24H Clock UTC).
The minimum maintenance window is a 60 minute period. Example: `sun:05:00-sun:09:00`
{{% /md %}}</dd>

    <dt class="property-"
            title="">Member<wbr>Clusters<span class="property-indicator"></span>
        <span class="property-type">List<string></span>
    </dt>
    <dd>{{% md %}}The identifiers of all the nodes that are part of this replication group.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Node<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The compute and memory capacity of the nodes in the node group.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Notification<wbr>Topic<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}An Amazon Resource Name (ARN) of an
SNS topic to send ElastiCache notifications to. Example:
`arn:aws:sns:us-east-1:012345678999:my_sns_topic`
{{% /md %}}</dd>

    <dt class="property-"
            title="">Number<wbr>Cache<wbr>Clusters<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The number of cache clusters (primary and replicas) this replication group will have. If Multi-AZ is enabled, the value of this parameter must be at least 2. Updates will occur before other modifications.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Parameter<wbr>Group<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the parameter group to associate with this replication group. If this argument is omitted, the default cache parameter group for the specified engine is used.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Port<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The port number on which each of the cache nodes will accept connections. For Memcache the default is 11211, and for Redis the default port is 6379.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Primary<wbr>Endpoint<wbr>Address<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}(Redis only) The address of the endpoint for the primary node in the replication group, if the cluster mode is disabled.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Replication<wbr>Group<wbr>Description<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}A user-created description for the replication group.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Replication<wbr>Group<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The replication group identifier. This parameter is stored as a lowercase string.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Security<wbr>Group<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">List<string></span>
    </dt>
    <dd>{{% md %}}One or more Amazon VPC security groups associated with this replication group. Use this parameter only when you are creating a replication group in an Amazon Virtual Private Cloud
{{% /md %}}</dd>

    <dt class="property-"
            title="">Security<wbr>Group<wbr>Names<span class="property-indicator"></span>
        <span class="property-type">List<string></span>
    </dt>
    <dd>{{% md %}}A list of cache security group names to associate with this replication group.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Snapshot<wbr>Arns<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}A single-element string list containing an
Amazon Resource Name (ARN) of a Redis RDB snapshot file stored in Amazon S3.
Example: `arn:aws:s3:::my_bucket/snapshot1.rdb`
{{% /md %}}</dd>

    <dt class="property-"
            title="">Snapshot<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of a snapshot from which to restore data into the new node group. Changing the `snapshot_name` forces a new resource.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Snapshot<wbr>Retention<wbr>Limit<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The number of days for which ElastiCache will
retain automatic cache cluster snapshots before deleting them. For example, if you set
SnapshotRetentionLimit to 5, then a snapshot that was taken today will be retained for 5 days
before being deleted. If the value of SnapshotRetentionLimit is set to zero (0), backups are turned off.
Please note that setting a `snapshot_retention_limit` is not supported on cache.t1.micro or cache.t2.* cache nodes
{{% /md %}}</dd>

    <dt class="property-"
            title="">Snapshot<wbr>Window<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The daily time range (in UTC) during which ElastiCache will
begin taking a daily snapshot of your cache cluster. The minimum snapshot window is a 60 minute period. Example: `05:00-09:00`
{{% /md %}}</dd>

    <dt class="property-"
            title="">Subnet<wbr>Group<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the cache subnet group to be used for the replication group.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource
{{% /md %}}</dd>

    <dt class="property-"
            title="">Transit<wbr>Encryption<wbr>Enabled<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Whether to enable encryption in transit.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Apply<wbr>Immediately<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Specifies whether any modifications are applied immediately, or during the next maintenance window. Default is `false`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">At<wbr>Rest<wbr>Encryption<wbr>Enabled<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Whether to enable encryption at rest.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Auth<wbr>Token<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The password used to access a password protected server. Can be specified only if `transit_encryption_enabled = true`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Auto<wbr>Minor<wbr>Version<wbr>Upgrade<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Specifies whether a minor engine upgrades will be applied automatically to the underlying Cache Cluster instances during the maintenance window. Defaults to `true`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Automatic<wbr>Failover<wbr>Enabled<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Specifies whether a read-only replica will be automatically promoted to read/write primary if the existing primary fails. If true, Multi-AZ is enabled for this replication group. If false, Multi-AZ is disabled for this replication group. Must be enabled for Redis (cluster mode enabled) replication groups. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Availability<wbr>Zones<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}A list of EC2 availability zones in which the replication group&#39;s cache clusters will be created. The order of the availability zones in the list is not important.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Cluster<wbr>Mode<span class="property-indicator"></span>
        <span class="property-type"><a href="#replicationgroupclustermode">Replication<wbr>Group<wbr>Cluster<wbr>Mode</a></span>
    </dt>
    <dd>{{% md %}}Create a native redis cluster. `automatic_failover_enabled` must be set to true. Cluster Mode documented below. Only 1 `cluster_mode` block is allowed.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Configuration<wbr>Endpoint<wbr>Address<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The address of the replication group configuration endpoint when cluster mode is enabled.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Engine<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name of the cache engine to be used for the clusters in this replication group. e.g. `redis`
{{% /md %}}</dd>

    <dt class="property-"
            title="">Engine<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The version number of the cache engine to be used for the cache clusters in this replication group.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Kms<wbr>Key<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The ARN of the key that you wish to use if encrypting at rest. If not supplied, uses service managed encryption. Can be specified only if `at_rest_encryption_enabled = true`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Maintenance<wbr>Window<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Specifies the weekly time range for when maintenance
on the cache cluster is performed. The format is `ddd:hh24:mi-ddd:hh24:mi` (24H Clock UTC).
The minimum maintenance window is a 60 minute period. Example: `sun:05:00-sun:09:00`
{{% /md %}}</dd>

    <dt class="property-"
            title="">Member<wbr>Clusters<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}The identifiers of all the nodes that are part of this replication group.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Node<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The compute and memory capacity of the nodes in the node group.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Notification<wbr>Topic<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}An Amazon Resource Name (ARN) of an
SNS topic to send ElastiCache notifications to. Example:
`arn:aws:sns:us-east-1:012345678999:my_sns_topic`
{{% /md %}}</dd>

    <dt class="property-"
            title="">Number<wbr>Cache<wbr>Clusters<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The number of cache clusters (primary and replicas) this replication group will have. If Multi-AZ is enabled, the value of this parameter must be at least 2. Updates will occur before other modifications.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Parameter<wbr>Group<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the parameter group to associate with this replication group. If this argument is omitted, the default cache parameter group for the specified engine is used.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Port<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The port number on which each of the cache nodes will accept connections. For Memcache the default is 11211, and for Redis the default port is 6379.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Primary<wbr>Endpoint<wbr>Address<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}(Redis only) The address of the endpoint for the primary node in the replication group, if the cluster mode is disabled.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Replication<wbr>Group<wbr>Description<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}A user-created description for the replication group.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Replication<wbr>Group<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The replication group identifier. This parameter is stored as a lowercase string.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Security<wbr>Group<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}One or more Amazon VPC security groups associated with this replication group. Use this parameter only when you are creating a replication group in an Amazon Virtual Private Cloud
{{% /md %}}</dd>

    <dt class="property-"
            title="">Security<wbr>Group<wbr>Names<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}A list of cache security group names to associate with this replication group.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Snapshot<wbr>Arns<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}A single-element string list containing an
Amazon Resource Name (ARN) of a Redis RDB snapshot file stored in Amazon S3.
Example: `arn:aws:s3:::my_bucket/snapshot1.rdb`
{{% /md %}}</dd>

    <dt class="property-"
            title="">Snapshot<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name of a snapshot from which to restore data into the new node group. Changing the `snapshot_name` forces a new resource.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Snapshot<wbr>Retention<wbr>Limit<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The number of days for which ElastiCache will
retain automatic cache cluster snapshots before deleting them. For example, if you set
SnapshotRetentionLimit to 5, then a snapshot that was taken today will be retained for 5 days
before being deleted. If the value of SnapshotRetentionLimit is set to zero (0), backups are turned off.
Please note that setting a `snapshot_retention_limit` is not supported on cache.t1.micro or cache.t2.* cache nodes
{{% /md %}}</dd>

    <dt class="property-"
            title="">Snapshot<wbr>Window<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The daily time range (in UTC) during which ElastiCache will
begin taking a daily snapshot of your cache cluster. The minimum snapshot window is a 60 minute period. Example: `05:00-09:00`
{{% /md %}}</dd>

    <dt class="property-"
            title="">Subnet<wbr>Group<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the cache subnet group to be used for the replication group.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource
{{% /md %}}</dd>

    <dt class="property-"
            title="">Transit<wbr>Encryption<wbr>Enabled<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Whether to enable encryption in transit.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">apply<wbr>Immediately<span class="property-indicator"></span>
        <span class="property-type">boolean</span>
    </dt>
    <dd>{{% md %}}Specifies whether any modifications are applied immediately, or during the next maintenance window. Default is `false`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">at<wbr>Rest<wbr>Encryption<wbr>Enabled<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Whether to enable encryption at rest.
{{% /md %}}</dd>

    <dt class="property-"
            title="">auth<wbr>Token<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The password used to access a password protected server. Can be specified only if `transit_encryption_enabled = true`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">auto<wbr>Minor<wbr>Version<wbr>Upgrade<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Specifies whether a minor engine upgrades will be applied automatically to the underlying Cache Cluster instances during the maintenance window. Defaults to `true`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">automatic<wbr>Failover<wbr>Enabled<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Specifies whether a read-only replica will be automatically promoted to read/write primary if the existing primary fails. If true, Multi-AZ is enabled for this replication group. If false, Multi-AZ is disabled for this replication group. Must be enabled for Redis (cluster mode enabled) replication groups. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">availability<wbr>Zones<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}A list of EC2 availability zones in which the replication group&#39;s cache clusters will be created. The order of the availability zones in the list is not important.
{{% /md %}}</dd>

    <dt class="property-"
            title="">cluster<wbr>Mode<span class="property-indicator"></span>
        <span class="property-type"><a href="#replicationgroupclustermode">Replication<wbr>Group<wbr>Cluster<wbr>Mode</a></span>
    </dt>
    <dd>{{% md %}}Create a native redis cluster. `automatic_failover_enabled` must be set to true. Cluster Mode documented below. Only 1 `cluster_mode` block is allowed.
{{% /md %}}</dd>

    <dt class="property-"
            title="">configuration<wbr>Endpoint<wbr>Address<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The address of the replication group configuration endpoint when cluster mode is enabled.
{{% /md %}}</dd>

    <dt class="property-"
            title="">engine<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the cache engine to be used for the clusters in this replication group. e.g. `redis`
{{% /md %}}</dd>

    <dt class="property-"
            title="">engine<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The version number of the cache engine to be used for the cache clusters in this replication group.
{{% /md %}}</dd>

    <dt class="property-"
            title="">kms<wbr>Key<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ARN of the key that you wish to use if encrypting at rest. If not supplied, uses service managed encryption. Can be specified only if `at_rest_encryption_enabled = true`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">maintenance<wbr>Window<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Specifies the weekly time range for when maintenance
on the cache cluster is performed. The format is `ddd:hh24:mi-ddd:hh24:mi` (24H Clock UTC).
The minimum maintenance window is a 60 minute period. Example: `sun:05:00-sun:09:00`
{{% /md %}}</dd>

    <dt class="property-"
            title="">member<wbr>Clusters<span class="property-indicator"></span>
        <span class="property-type">string[]</span>
    </dt>
    <dd>{{% md %}}The identifiers of all the nodes that are part of this replication group.
{{% /md %}}</dd>

    <dt class="property-"
            title="">node<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The compute and memory capacity of the nodes in the node group.
{{% /md %}}</dd>

    <dt class="property-"
            title="">notification<wbr>Topic<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}An Amazon Resource Name (ARN) of an
SNS topic to send ElastiCache notifications to. Example:
`arn:aws:sns:us-east-1:012345678999:my_sns_topic`
{{% /md %}}</dd>

    <dt class="property-"
            title="">number<wbr>Cache<wbr>Clusters<span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}The number of cache clusters (primary and replicas) this replication group will have. If Multi-AZ is enabled, the value of this parameter must be at least 2. Updates will occur before other modifications.
{{% /md %}}</dd>

    <dt class="property-"
            title="">parameter<wbr>Group<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the parameter group to associate with this replication group. If this argument is omitted, the default cache parameter group for the specified engine is used.
{{% /md %}}</dd>

    <dt class="property-"
            title="">port<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The port number on which each of the cache nodes will accept connections. For Memcache the default is 11211, and for Redis the default port is 6379.
{{% /md %}}</dd>

    <dt class="property-"
            title="">primary<wbr>Endpoint<wbr>Address<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}(Redis only) The address of the endpoint for the primary node in the replication group, if the cluster mode is disabled.
{{% /md %}}</dd>

    <dt class="property-"
            title="">replication<wbr>Group<wbr>Description<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}A user-created description for the replication group.
{{% /md %}}</dd>

    <dt class="property-"
            title="">replication<wbr>Group<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The replication group identifier. This parameter is stored as a lowercase string.
{{% /md %}}</dd>

    <dt class="property-"
            title="">security<wbr>Group<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">string[]</span>
    </dt>
    <dd>{{% md %}}One or more Amazon VPC security groups associated with this replication group. Use this parameter only when you are creating a replication group in an Amazon Virtual Private Cloud
{{% /md %}}</dd>

    <dt class="property-"
            title="">security<wbr>Group<wbr>Names<span class="property-indicator"></span>
        <span class="property-type">string[]</span>
    </dt>
    <dd>{{% md %}}A list of cache security group names to associate with this replication group.
{{% /md %}}</dd>

    <dt class="property-"
            title="">snapshot<wbr>Arns<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}A single-element string list containing an
Amazon Resource Name (ARN) of a Redis RDB snapshot file stored in Amazon S3.
Example: `arn:aws:s3:::my_bucket/snapshot1.rdb`
{{% /md %}}</dd>

    <dt class="property-"
            title="">snapshot<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of a snapshot from which to restore data into the new node group. Changing the `snapshot_name` forces a new resource.
{{% /md %}}</dd>

    <dt class="property-"
            title="">snapshot<wbr>Retention<wbr>Limit<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The number of days for which ElastiCache will
retain automatic cache cluster snapshots before deleting them. For example, if you set
SnapshotRetentionLimit to 5, then a snapshot that was taken today will be retained for 5 days
before being deleted. If the value of SnapshotRetentionLimit is set to zero (0), backups are turned off.
Please note that setting a `snapshot_retention_limit` is not supported on cache.t1.micro or cache.t2.* cache nodes
{{% /md %}}</dd>

    <dt class="property-"
            title="">snapshot<wbr>Window<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The daily time range (in UTC) during which ElastiCache will
begin taking a daily snapshot of your cache cluster. The minimum snapshot window is a 60 minute period. Example: `05:00-09:00`
{{% /md %}}</dd>

    <dt class="property-"
            title="">subnet<wbr>Group<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the cache subnet group to be used for the replication group.
{{% /md %}}</dd>

    <dt class="property-"
            title="">tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource
{{% /md %}}</dd>

    <dt class="property-"
            title="">transit<wbr>Encryption<wbr>Enabled<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Whether to enable encryption in transit.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">apply_<wbr>immediately<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Specifies whether any modifications are applied immediately, or during the next maintenance window. Default is `false`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">at_<wbr>rest_<wbr>encryption_<wbr>enabled<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Whether to enable encryption at rest.
{{% /md %}}</dd>

    <dt class="property-"
            title="">auth_<wbr>token<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The password used to access a password protected server. Can be specified only if `transit_encryption_enabled = true`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">auto_<wbr>minor_<wbr>version_<wbr>upgrade<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Specifies whether a minor engine upgrades will be applied automatically to the underlying Cache Cluster instances during the maintenance window. Defaults to `true`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">automatic_<wbr>failover_<wbr>enabled<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Specifies whether a read-only replica will be automatically promoted to read/write primary if the existing primary fails. If true, Multi-AZ is enabled for this replication group. If false, Multi-AZ is disabled for this replication group. Must be enabled for Redis (cluster mode enabled) replication groups. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">availability_<wbr>zones<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}A list of EC2 availability zones in which the replication group&#39;s cache clusters will be created. The order of the availability zones in the list is not important.
{{% /md %}}</dd>

    <dt class="property-"
            title="">cluster_<wbr>mode<span class="property-indicator"></span>
        <span class="property-type"><a href="#replicationgroupclustermode">Dict[Replication<wbr>Group<wbr>Cluster<wbr>Mode]</a></span>
    </dt>
    <dd>{{% md %}}Create a native redis cluster. `automatic_failover_enabled` must be set to true. Cluster Mode documented below. Only 1 `cluster_mode` block is allowed.
{{% /md %}}</dd>

    <dt class="property-"
            title="">configuration_<wbr>endpoint_<wbr>address<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The address of the replication group configuration endpoint when cluster mode is enabled.
{{% /md %}}</dd>

    <dt class="property-"
            title="">engine<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the cache engine to be used for the clusters in this replication group. e.g. `redis`
{{% /md %}}</dd>

    <dt class="property-"
            title="">engine_<wbr>version<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The version number of the cache engine to be used for the cache clusters in this replication group.
{{% /md %}}</dd>

    <dt class="property-"
            title="">kms_<wbr>key_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ARN of the key that you wish to use if encrypting at rest. If not supplied, uses service managed encryption. Can be specified only if `at_rest_encryption_enabled = true`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">maintenance_<wbr>window<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Specifies the weekly time range for when maintenance
on the cache cluster is performed. The format is `ddd:hh24:mi-ddd:hh24:mi` (24H Clock UTC).
The minimum maintenance window is a 60 minute period. Example: `sun:05:00-sun:09:00`
{{% /md %}}</dd>

    <dt class="property-"
            title="">member_<wbr>clusters<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}The identifiers of all the nodes that are part of this replication group.
{{% /md %}}</dd>

    <dt class="property-"
            title="">node_<wbr>type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The compute and memory capacity of the nodes in the node group.
{{% /md %}}</dd>

    <dt class="property-"
            title="">notification_<wbr>topic_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}An Amazon Resource Name (ARN) of an
SNS topic to send ElastiCache notifications to. Example:
`arn:aws:sns:us-east-1:012345678999:my_sns_topic`
{{% /md %}}</dd>

    <dt class="property-"
            title="">number_<wbr>cache_<wbr>clusters<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The number of cache clusters (primary and replicas) this replication group will have. If Multi-AZ is enabled, the value of this parameter must be at least 2. Updates will occur before other modifications.
{{% /md %}}</dd>

    <dt class="property-"
            title="">parameter_<wbr>group_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the parameter group to associate with this replication group. If this argument is omitted, the default cache parameter group for the specified engine is used.
{{% /md %}}</dd>

    <dt class="property-"
            title="">port<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The port number on which each of the cache nodes will accept connections. For Memcache the default is 11211, and for Redis the default port is 6379.
{{% /md %}}</dd>

    <dt class="property-"
            title="">primary_<wbr>endpoint_<wbr>address<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}(Redis only) The address of the endpoint for the primary node in the replication group, if the cluster mode is disabled.
{{% /md %}}</dd>

    <dt class="property-"
            title="">replication_<wbr>group_<wbr>description<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A user-created description for the replication group.
{{% /md %}}</dd>

    <dt class="property-"
            title="">replication_<wbr>group_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The replication group identifier. This parameter is stored as a lowercase string.
{{% /md %}}</dd>

    <dt class="property-"
            title="">security_<wbr>group_<wbr>ids<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}One or more Amazon VPC security groups associated with this replication group. Use this parameter only when you are creating a replication group in an Amazon Virtual Private Cloud
{{% /md %}}</dd>

    <dt class="property-"
            title="">security_<wbr>group_<wbr>names<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}A list of cache security group names to associate with this replication group.
{{% /md %}}</dd>

    <dt class="property-"
            title="">snapshot_<wbr>arns<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}A single-element string list containing an
Amazon Resource Name (ARN) of a Redis RDB snapshot file stored in Amazon S3.
Example: `arn:aws:s3:::my_bucket/snapshot1.rdb`
{{% /md %}}</dd>

    <dt class="property-"
            title="">snapshot_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of a snapshot from which to restore data into the new node group. Changing the `snapshot_name` forces a new resource.
{{% /md %}}</dd>

    <dt class="property-"
            title="">snapshot_<wbr>retention_<wbr>limit<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The number of days for which ElastiCache will
retain automatic cache cluster snapshots before deleting them. For example, if you set
SnapshotRetentionLimit to 5, then a snapshot that was taken today will be retained for 5 days
before being deleted. If the value of SnapshotRetentionLimit is set to zero (0), backups are turned off.
Please note that setting a `snapshot_retention_limit` is not supported on cache.t1.micro or cache.t2.* cache nodes
{{% /md %}}</dd>

    <dt class="property-"
            title="">snapshot_<wbr>window<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The daily time range (in UTC) during which ElastiCache will
begin taking a daily snapshot of your cache cluster. The minimum snapshot window is a 60 minute period. Example: `05:00-09:00`
{{% /md %}}</dd>

    <dt class="property-"
            title="">subnet_<wbr>group_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the cache subnet group to be used for the replication group.
{{% /md %}}</dd>

    <dt class="property-"
            title="">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource
{{% /md %}}</dd>

    <dt class="property-"
            title="">transit_<wbr>encryption_<wbr>enabled<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Whether to enable encryption in transit.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





## Look up an Existing ReplicationGroup Resource

{{< chooser language "javascript,typescript,python,go,csharp  " / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">pulumi.Input&lt;pulumi.ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/elasticache/#ReplicationGroupState">ReplicationGroupState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/elasticache/#ReplicationGroup">ReplicationGroup</a></span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>apply_immediately=None<span class="p">, </span>at_rest_encryption_enabled=None<span class="p">, </span>auth_token=None<span class="p">, </span>auto_minor_version_upgrade=None<span class="p">, </span>automatic_failover_enabled=None<span class="p">, </span>availability_zones=None<span class="p">, </span>cluster_mode=None<span class="p">, </span>configuration_endpoint_address=None<span class="p">, </span>engine=None<span class="p">, </span>engine_version=None<span class="p">, </span>kms_key_id=None<span class="p">, </span>maintenance_window=None<span class="p">, </span>member_clusters=None<span class="p">, </span>node_type=None<span class="p">, </span>notification_topic_arn=None<span class="p">, </span>number_cache_clusters=None<span class="p">, </span>parameter_group_name=None<span class="p">, </span>port=None<span class="p">, </span>primary_endpoint_address=None<span class="p">, </span>replication_group_description=None<span class="p">, </span>replication_group_id=None<span class="p">, </span>security_group_ids=None<span class="p">, </span>security_group_names=None<span class="p">, </span>snapshot_arns=None<span class="p">, </span>snapshot_name=None<span class="p">, </span>snapshot_retention_limit=None<span class="p">, </span>snapshot_window=None<span class="p">, </span>subnet_group_name=None<span class="p">, </span>tags=None<span class="p">, </span>transit_encryption_enabled=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetReplicationGroup<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">pulumi.IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/elasticache?tab=doc#ReplicationGroupState">ReplicationGroupState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/elasticache?tab=doc#ReplicationGroup">ReplicationGroup</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Elasticache.ReplicationGroup.html">ReplicationGroup</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Pulumi.Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Elasticache.ReplicationGroupState.html">ReplicationGroupState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
{{% /choosable %}}

Get an existing ReplicationGroup resource's state with the given name, ID, and optional extra properties used to qualify the lookup.

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
    <dd>{{% md %}}Specifies whether any modifications are applied immediately, or during the next maintenance window. Default is `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">At<wbr>Rest<wbr>Encryption<wbr>Enabled<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Whether to enable encryption at rest.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Auth<wbr>Token<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The password used to access a password protected server. Can be specified only if `transit_encryption_enabled = true`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Auto<wbr>Minor<wbr>Version<wbr>Upgrade<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Specifies whether a minor engine upgrades will be applied automatically to the underlying Cache Cluster instances during the maintenance window. Defaults to `true`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Automatic<wbr>Failover<wbr>Enabled<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Specifies whether a read-only replica will be automatically promoted to read/write primary if the existing primary fails. If true, Multi-AZ is enabled for this replication group. If false, Multi-AZ is disabled for this replication group. Must be enabled for Redis (cluster mode enabled) replication groups. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Availability<wbr>Zones<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}A list of EC2 availability zones in which the replication group&#39;s cache clusters will be created. The order of the availability zones in the list is not important.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Cluster<wbr>Mode<span class="property-indicator"></span>
        <span class="property-type"><a href="#replicationgroupclustermode">Replication<wbr>Group<wbr>Cluster<wbr>Mode<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}Create a native redis cluster. `automatic_failover_enabled` must be set to true. Cluster Mode documented below. Only 1 `cluster_mode` block is allowed.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Configuration<wbr>Endpoint<wbr>Address<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The address of the replication group configuration endpoint when cluster mode is enabled.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Engine<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the cache engine to be used for the clusters in this replication group. e.g. `redis`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Engine<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The version number of the cache engine to be used for the cache clusters in this replication group.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Kms<wbr>Key<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ARN of the key that you wish to use if encrypting at rest. If not supplied, uses service managed encryption. Can be specified only if `at_rest_encryption_enabled = true`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Maintenance<wbr>Window<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Specifies the weekly time range for when maintenance
on the cache cluster is performed. The format is `ddd:hh24:mi-ddd:hh24:mi` (24H Clock UTC).
The minimum maintenance window is a 60 minute period. Example: `sun:05:00-sun:09:00`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Member<wbr>Clusters<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}The identifiers of all the nodes that are part of this replication group.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Node<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The compute and memory capacity of the nodes in the node group.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Notification<wbr>Topic<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}An Amazon Resource Name (ARN) of an
SNS topic to send ElastiCache notifications to. Example:
`arn:aws:sns:us-east-1:012345678999:my_sns_topic`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Number<wbr>Cache<wbr>Clusters<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The number of cache clusters (primary and replicas) this replication group will have. If Multi-AZ is enabled, the value of this parameter must be at least 2. Updates will occur before other modifications.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Parameter<wbr>Group<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the parameter group to associate with this replication group. If this argument is omitted, the default cache parameter group for the specified engine is used.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Port<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The port number on which each of the cache nodes will accept connections. For Memcache the default is 11211, and for Redis the default port is 6379.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Primary<wbr>Endpoint<wbr>Address<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}(Redis only) The address of the endpoint for the primary node in the replication group, if the cluster mode is disabled.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Replication<wbr>Group<wbr>Description<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A user-created description for the replication group.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Replication<wbr>Group<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The replication group identifier. This parameter is stored as a lowercase string.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Security<wbr>Group<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}One or more Amazon VPC security groups associated with this replication group. Use this parameter only when you are creating a replication group in an Amazon Virtual Private Cloud
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Security<wbr>Group<wbr>Names<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}A list of cache security group names to associate with this replication group.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Snapshot<wbr>Arns<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}A single-element string list containing an
Amazon Resource Name (ARN) of a Redis RDB snapshot file stored in Amazon S3.
Example: `arn:aws:s3:::my_bucket/snapshot1.rdb`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Snapshot<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of a snapshot from which to restore data into the new node group. Changing the `snapshot_name` forces a new resource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Snapshot<wbr>Retention<wbr>Limit<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The number of days for which ElastiCache will
retain automatic cache cluster snapshots before deleting them. For example, if you set
SnapshotRetentionLimit to 5, then a snapshot that was taken today will be retained for 5 days
before being deleted. If the value of SnapshotRetentionLimit is set to zero (0), backups are turned off.
Please note that setting a `snapshot_retention_limit` is not supported on cache.t1.micro or cache.t2.* cache nodes
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Snapshot<wbr>Window<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The daily time range (in UTC) during which ElastiCache will
begin taking a daily snapshot of your cache cluster. The minimum snapshot window is a 60 minute period. Example: `05:00-09:00`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Subnet<wbr>Group<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the cache subnet group to be used for the replication group.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Transit<wbr>Encryption<wbr>Enabled<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Whether to enable encryption in transit.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Apply<wbr>Immediately<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Specifies whether any modifications are applied immediately, or during the next maintenance window. Default is `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">At<wbr>Rest<wbr>Encryption<wbr>Enabled<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Whether to enable encryption at rest.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Auth<wbr>Token<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The password used to access a password protected server. Can be specified only if `transit_encryption_enabled = true`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Auto<wbr>Minor<wbr>Version<wbr>Upgrade<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Specifies whether a minor engine upgrades will be applied automatically to the underlying Cache Cluster instances during the maintenance window. Defaults to `true`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Automatic<wbr>Failover<wbr>Enabled<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Specifies whether a read-only replica will be automatically promoted to read/write primary if the existing primary fails. If true, Multi-AZ is enabled for this replication group. If false, Multi-AZ is disabled for this replication group. Must be enabled for Redis (cluster mode enabled) replication groups. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Availability<wbr>Zones<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}A list of EC2 availability zones in which the replication group&#39;s cache clusters will be created. The order of the availability zones in the list is not important.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Cluster<wbr>Mode<span class="property-indicator"></span>
        <span class="property-type"><a href="#replicationgroupclustermode">*Replication<wbr>Group<wbr>Cluster<wbr>Mode</a></span>
    </dt>
    <dd>{{% md %}}Create a native redis cluster. `automatic_failover_enabled` must be set to true. Cluster Mode documented below. Only 1 `cluster_mode` block is allowed.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Configuration<wbr>Endpoint<wbr>Address<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The address of the replication group configuration endpoint when cluster mode is enabled.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Engine<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name of the cache engine to be used for the clusters in this replication group. e.g. `redis`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Engine<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The version number of the cache engine to be used for the cache clusters in this replication group.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Kms<wbr>Key<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The ARN of the key that you wish to use if encrypting at rest. If not supplied, uses service managed encryption. Can be specified only if `at_rest_encryption_enabled = true`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Maintenance<wbr>Window<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Specifies the weekly time range for when maintenance
on the cache cluster is performed. The format is `ddd:hh24:mi-ddd:hh24:mi` (24H Clock UTC).
The minimum maintenance window is a 60 minute period. Example: `sun:05:00-sun:09:00`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Member<wbr>Clusters<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}The identifiers of all the nodes that are part of this replication group.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Node<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The compute and memory capacity of the nodes in the node group.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Notification<wbr>Topic<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}An Amazon Resource Name (ARN) of an
SNS topic to send ElastiCache notifications to. Example:
`arn:aws:sns:us-east-1:012345678999:my_sns_topic`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Number<wbr>Cache<wbr>Clusters<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The number of cache clusters (primary and replicas) this replication group will have. If Multi-AZ is enabled, the value of this parameter must be at least 2. Updates will occur before other modifications.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Parameter<wbr>Group<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name of the parameter group to associate with this replication group. If this argument is omitted, the default cache parameter group for the specified engine is used.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Port<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The port number on which each of the cache nodes will accept connections. For Memcache the default is 11211, and for Redis the default port is 6379.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Primary<wbr>Endpoint<wbr>Address<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}(Redis only) The address of the endpoint for the primary node in the replication group, if the cluster mode is disabled.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Replication<wbr>Group<wbr>Description<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}A user-created description for the replication group.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Replication<wbr>Group<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The replication group identifier. This parameter is stored as a lowercase string.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Security<wbr>Group<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}One or more Amazon VPC security groups associated with this replication group. Use this parameter only when you are creating a replication group in an Amazon Virtual Private Cloud
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Security<wbr>Group<wbr>Names<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}A list of cache security group names to associate with this replication group.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Snapshot<wbr>Arns<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}A single-element string list containing an
Amazon Resource Name (ARN) of a Redis RDB snapshot file stored in Amazon S3.
Example: `arn:aws:s3:::my_bucket/snapshot1.rdb`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Snapshot<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name of a snapshot from which to restore data into the new node group. Changing the `snapshot_name` forces a new resource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Snapshot<wbr>Retention<wbr>Limit<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The number of days for which ElastiCache will
retain automatic cache cluster snapshots before deleting them. For example, if you set
SnapshotRetentionLimit to 5, then a snapshot that was taken today will be retained for 5 days
before being deleted. If the value of SnapshotRetentionLimit is set to zero (0), backups are turned off.
Please note that setting a `snapshot_retention_limit` is not supported on cache.t1.micro or cache.t2.* cache nodes
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Snapshot<wbr>Window<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The daily time range (in UTC) during which ElastiCache will
begin taking a daily snapshot of your cache cluster. The minimum snapshot window is a 60 minute period. Example: `05:00-09:00`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Subnet<wbr>Group<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name of the cache subnet group to be used for the replication group.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Transit<wbr>Encryption<wbr>Enabled<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Whether to enable encryption in transit.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">apply<wbr>Immediately<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Specifies whether any modifications are applied immediately, or during the next maintenance window. Default is `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">at<wbr>Rest<wbr>Encryption<wbr>Enabled<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Whether to enable encryption at rest.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">auth<wbr>Token<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The password used to access a password protected server. Can be specified only if `transit_encryption_enabled = true`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">auto<wbr>Minor<wbr>Version<wbr>Upgrade<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Specifies whether a minor engine upgrades will be applied automatically to the underlying Cache Cluster instances during the maintenance window. Defaults to `true`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">automatic<wbr>Failover<wbr>Enabled<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Specifies whether a read-only replica will be automatically promoted to read/write primary if the existing primary fails. If true, Multi-AZ is enabled for this replication group. If false, Multi-AZ is disabled for this replication group. Must be enabled for Redis (cluster mode enabled) replication groups. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">availability<wbr>Zones<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}A list of EC2 availability zones in which the replication group&#39;s cache clusters will be created. The order of the availability zones in the list is not important.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">cluster<wbr>Mode<span class="property-indicator"></span>
        <span class="property-type"><a href="#replicationgroupclustermode">Replication<wbr>Group<wbr>Cluster<wbr>Mode?</a></span>
    </dt>
    <dd>{{% md %}}Create a native redis cluster. `automatic_failover_enabled` must be set to true. Cluster Mode documented below. Only 1 `cluster_mode` block is allowed.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">configuration<wbr>Endpoint<wbr>Address<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The address of the replication group configuration endpoint when cluster mode is enabled.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">engine<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the cache engine to be used for the clusters in this replication group. e.g. `redis`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">engine<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The version number of the cache engine to be used for the cache clusters in this replication group.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">kms<wbr>Key<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ARN of the key that you wish to use if encrypting at rest. If not supplied, uses service managed encryption. Can be specified only if `at_rest_encryption_enabled = true`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">maintenance<wbr>Window<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Specifies the weekly time range for when maintenance
on the cache cluster is performed. The format is `ddd:hh24:mi-ddd:hh24:mi` (24H Clock UTC).
The minimum maintenance window is a 60 minute period. Example: `sun:05:00-sun:09:00`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">member<wbr>Clusters<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}The identifiers of all the nodes that are part of this replication group.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">node<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The compute and memory capacity of the nodes in the node group.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">notification<wbr>Topic<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}An Amazon Resource Name (ARN) of an
SNS topic to send ElastiCache notifications to. Example:
`arn:aws:sns:us-east-1:012345678999:my_sns_topic`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">number<wbr>Cache<wbr>Clusters<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The number of cache clusters (primary and replicas) this replication group will have. If Multi-AZ is enabled, the value of this parameter must be at least 2. Updates will occur before other modifications.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">parameter<wbr>Group<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the parameter group to associate with this replication group. If this argument is omitted, the default cache parameter group for the specified engine is used.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">port<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The port number on which each of the cache nodes will accept connections. For Memcache the default is 11211, and for Redis the default port is 6379.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">primary<wbr>Endpoint<wbr>Address<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}(Redis only) The address of the endpoint for the primary node in the replication group, if the cluster mode is disabled.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">replication<wbr>Group<wbr>Description<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A user-created description for the replication group.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">replication<wbr>Group<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The replication group identifier. This parameter is stored as a lowercase string.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">security<wbr>Group<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}One or more Amazon VPC security groups associated with this replication group. Use this parameter only when you are creating a replication group in an Amazon Virtual Private Cloud
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">security<wbr>Group<wbr>Names<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}A list of cache security group names to associate with this replication group.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">snapshot<wbr>Arns<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}A single-element string list containing an
Amazon Resource Name (ARN) of a Redis RDB snapshot file stored in Amazon S3.
Example: `arn:aws:s3:::my_bucket/snapshot1.rdb`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">snapshot<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of a snapshot from which to restore data into the new node group. Changing the `snapshot_name` forces a new resource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">snapshot<wbr>Retention<wbr>Limit<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The number of days for which ElastiCache will
retain automatic cache cluster snapshots before deleting them. For example, if you set
SnapshotRetentionLimit to 5, then a snapshot that was taken today will be retained for 5 days
before being deleted. If the value of SnapshotRetentionLimit is set to zero (0), backups are turned off.
Please note that setting a `snapshot_retention_limit` is not supported on cache.t1.micro or cache.t2.* cache nodes
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">snapshot<wbr>Window<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The daily time range (in UTC) during which ElastiCache will
begin taking a daily snapshot of your cache cluster. The minimum snapshot window is a 60 minute period. Example: `05:00-09:00`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">subnet<wbr>Group<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the cache subnet group to be used for the replication group.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">transit<wbr>Encryption<wbr>Enabled<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Whether to enable encryption in transit.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">apply_<wbr>immediately<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Specifies whether any modifications are applied immediately, or during the next maintenance window. Default is `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">at_<wbr>rest_<wbr>encryption_<wbr>enabled<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Whether to enable encryption at rest.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">auth_<wbr>token<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The password used to access a password protected server. Can be specified only if `transit_encryption_enabled = true`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">auto_<wbr>minor_<wbr>version_<wbr>upgrade<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Specifies whether a minor engine upgrades will be applied automatically to the underlying Cache Cluster instances during the maintenance window. Defaults to `true`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">automatic_<wbr>failover_<wbr>enabled<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Specifies whether a read-only replica will be automatically promoted to read/write primary if the existing primary fails. If true, Multi-AZ is enabled for this replication group. If false, Multi-AZ is disabled for this replication group. Must be enabled for Redis (cluster mode enabled) replication groups. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">availability_<wbr>zones<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}A list of EC2 availability zones in which the replication group&#39;s cache clusters will be created. The order of the availability zones in the list is not important.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">cluster_<wbr>mode<span class="property-indicator"></span>
        <span class="property-type"><a href="#replicationgroupclustermode">Dict[Replication<wbr>Group<wbr>Cluster<wbr>Mode]</a></span>
    </dt>
    <dd>{{% md %}}Create a native redis cluster. `automatic_failover_enabled` must be set to true. Cluster Mode documented below. Only 1 `cluster_mode` block is allowed.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">configuration_<wbr>endpoint_<wbr>address<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The address of the replication group configuration endpoint when cluster mode is enabled.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">engine<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the cache engine to be used for the clusters in this replication group. e.g. `redis`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">engine_<wbr>version<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The version number of the cache engine to be used for the cache clusters in this replication group.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">kms_<wbr>key_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ARN of the key that you wish to use if encrypting at rest. If not supplied, uses service managed encryption. Can be specified only if `at_rest_encryption_enabled = true`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">maintenance_<wbr>window<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Specifies the weekly time range for when maintenance
on the cache cluster is performed. The format is `ddd:hh24:mi-ddd:hh24:mi` (24H Clock UTC).
The minimum maintenance window is a 60 minute period. Example: `sun:05:00-sun:09:00`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">member_<wbr>clusters<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}The identifiers of all the nodes that are part of this replication group.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">node_<wbr>type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The compute and memory capacity of the nodes in the node group.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">notification_<wbr>topic_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}An Amazon Resource Name (ARN) of an
SNS topic to send ElastiCache notifications to. Example:
`arn:aws:sns:us-east-1:012345678999:my_sns_topic`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">number_<wbr>cache_<wbr>clusters<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The number of cache clusters (primary and replicas) this replication group will have. If Multi-AZ is enabled, the value of this parameter must be at least 2. Updates will occur before other modifications.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">parameter_<wbr>group_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the parameter group to associate with this replication group. If this argument is omitted, the default cache parameter group for the specified engine is used.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">port<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The port number on which each of the cache nodes will accept connections. For Memcache the default is 11211, and for Redis the default port is 6379.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">primary_<wbr>endpoint_<wbr>address<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}(Redis only) The address of the endpoint for the primary node in the replication group, if the cluster mode is disabled.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">replication_<wbr>group_<wbr>description<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A user-created description for the replication group.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">replication_<wbr>group_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The replication group identifier. This parameter is stored as a lowercase string.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">security_<wbr>group_<wbr>ids<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}One or more Amazon VPC security groups associated with this replication group. Use this parameter only when you are creating a replication group in an Amazon Virtual Private Cloud
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">security_<wbr>group_<wbr>names<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}A list of cache security group names to associate with this replication group.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">snapshot_<wbr>arns<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}A single-element string list containing an
Amazon Resource Name (ARN) of a Redis RDB snapshot file stored in Amazon S3.
Example: `arn:aws:s3:::my_bucket/snapshot1.rdb`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">snapshot_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of a snapshot from which to restore data into the new node group. Changing the `snapshot_name` forces a new resource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">snapshot_<wbr>retention_<wbr>limit<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The number of days for which ElastiCache will
retain automatic cache cluster snapshots before deleting them. For example, if you set
SnapshotRetentionLimit to 5, then a snapshot that was taken today will be retained for 5 days
before being deleted. If the value of SnapshotRetentionLimit is set to zero (0), backups are turned off.
Please note that setting a `snapshot_retention_limit` is not supported on cache.t1.micro or cache.t2.* cache nodes
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">snapshot_<wbr>window<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The daily time range (in UTC) during which ElastiCache will
begin taking a daily snapshot of your cache cluster. The minimum snapshot window is a 60 minute period. Example: `05:00-09:00`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">subnet_<wbr>group_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the cache subnet group to be used for the replication group.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">transit_<wbr>encryption_<wbr>enabled<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Whether to enable encryption in transit.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}







## Supporting Types

#### ReplicationGroupClusterMode
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#ReplicationGroupClusterMode">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#ReplicationGroupClusterMode">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/elasticache?tab=doc#ReplicationGroupClusterModeArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/elasticache?tab=doc#ReplicationGroupClusterModeOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Elasticache.ReplicationGroupClusterModeArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Elasticache.ReplicationGroupClusterMode.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Num<wbr>Node<wbr>Groups<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}Specify the number of node groups (shards) for this Redis replication group. Changing this number will trigger an online resizing operation before other settings modifications.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Replicas<wbr>Per<wbr>Node<wbr>Group<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}Specify the number of replica nodes in each node group. Valid values are 0 to 5. Changing this number will force a new resource.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Num<wbr>Node<wbr>Groups<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}Specify the number of node groups (shards) for this Redis replication group. Changing this number will trigger an online resizing operation before other settings modifications.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Replicas<wbr>Per<wbr>Node<wbr>Group<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}Specify the number of replica nodes in each node group. Valid values are 0 to 5. Changing this number will force a new resource.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">num<wbr>Node<wbr>Groups<span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}Specify the number of node groups (shards) for this Redis replication group. Changing this number will trigger an online resizing operation before other settings modifications.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">replicas<wbr>Per<wbr>Node<wbr>Group<span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}Specify the number of replica nodes in each node group. Valid values are 0 to 5. Changing this number will force a new resource.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">num<wbr>Node<wbr>Groups<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}Specify the number of node groups (shards) for this Redis replication group. Changing this number will trigger an online resizing operation before other settings modifications.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">replicas<wbr>Per<wbr>Node<wbr>Group<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}Specify the number of replica nodes in each node group. Valid values are 0 to 5. Changing this number will force a new resource.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}








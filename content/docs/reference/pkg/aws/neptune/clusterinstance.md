
---
title: "ClusterInstance"
block_external_search_index: true
---

A Cluster Instance Resource defines attributes that are specific to a single instance in a Neptune Cluster.

You can simply add neptune instances and Neptune manages the replication. You can use the [count][1]
meta-parameter to make multiple instances and join them all to the same Neptune Cluster, or you may specify different Cluster Instance resources with various `instance_class` sizes.


## Example Usage

The following example will create a neptune cluster with two neptune instances(one writer and one reader).

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const defaultCluster = new aws.neptune.Cluster("default", {
    applyImmediately: true,
    backupRetentionPeriod: 5,
    clusterIdentifier: "neptune-cluster-demo",
    engine: "neptune",
    iamDatabaseAuthenticationEnabled: true,
    preferredBackupWindow: "07:00-09:00",
    skipFinalSnapshot: true,
});
const example: aws.neptune.ClusterInstance[] = [];
for (let i = 0; i < 2; i++) {
    example.push(new aws.neptune.ClusterInstance(`example-${i}`, {
        applyImmediately: true,
        clusterIdentifier: defaultCluster.id,
        engine: "neptune",
        instanceClass: "db.r4.large",
    }));
}
```

> This content is derived from https://github.com/terraform-providers/terraform-provider-aws/blob/master/website/docs/r/neptune_cluster_instance.html.markdown.



## Create a ClusterInstance Resource

{{< chooser language "javascript,typescript,python,go,csharp" / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/neptune/#ClusterInstance">ClusterInstance</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/neptune/#ClusterInstanceArgs">ClusterInstanceArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">ClusterInstance</span><span class="p">(resource_name, opts=None, </span>apply_immediately=None<span class="p">, </span>auto_minor_version_upgrade=None<span class="p">, </span>availability_zone=None<span class="p">, </span>cluster_identifier=None<span class="p">, </span>engine=None<span class="p">, </span>engine_version=None<span class="p">, </span>identifier=None<span class="p">, </span>identifier_prefix=None<span class="p">, </span>instance_class=None<span class="p">, </span>neptune_parameter_group_name=None<span class="p">, </span>neptune_subnet_group_name=None<span class="p">, </span>port=None<span class="p">, </span>preferred_backup_window=None<span class="p">, </span>preferred_maintenance_window=None<span class="p">, </span>promotion_tier=None<span class="p">, </span>publicly_accessible=None<span class="p">, </span>tags=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewClusterInstance<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/neptune?tab=doc#ClusterInstanceArgs">ClusterInstanceArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/neptune?tab=doc#ClusterInstance">ClusterInstance</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Neptune.ClusterInstance.html">ClusterInstance</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Neptune.ClusterInstanceArgs.html">ClusterInstanceArgs</a></span> <span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
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
    <dd>{{% md %}}Specifies whether any instance modifications
are applied immediately, or during the next maintenance window. Default is`false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Auto<wbr>Minor<wbr>Version<wbr>Upgrade<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Indicates that minor engine upgrades will be applied automatically to the instance during the maintenance window. Default is `true`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Availability<wbr>Zone<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The EC2 Availability Zone that the neptune instance is created in.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Cluster<wbr>Identifier<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The identifier of the [`aws.neptune.Cluster`](https://www.terraform.io/docs/providers/aws/r/neptune_cluster.html) in which to launch this instance.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Engine<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the database engine to be used for the neptune instance. Defaults to `neptune`. Valid Values: `neptune`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Engine<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The neptune engine version.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Identifier<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The indentifier for the neptune instance, if omitted, this provider will assign a random, unique identifier.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Identifier<wbr>Prefix<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Creates a unique identifier beginning with the specified prefix. Conflicts with `identifier`.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Instance<wbr>Class<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The instance class to use.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Neptune<wbr>Parameter<wbr>Group<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the neptune parameter group to associate with this instance.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Neptune<wbr>Subnet<wbr>Group<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A subnet group to associate with this neptune instance. **NOTE:** This must match the `neptune_subnet_group_name` of the attached [`aws.neptune.Cluster`](https://www.terraform.io/docs/providers/aws/r/neptune_cluster.html).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Port<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The port on which the DB accepts connections. Defaults to `8182`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Preferred<wbr>Backup<wbr>Window<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The daily time range during which automated backups are created if automated backups are enabled. Eg: &#34;04:00-09:00&#34;
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Preferred<wbr>Maintenance<wbr>Window<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The window to perform maintenance in.
Syntax: &#34;ddd:hh24:mi-ddd:hh24:mi&#34;. Eg: &#34;Mon:00:00-Mon:03:00&#34;.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Promotion<wbr>Tier<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}Default 0. Failover Priority setting on instance level. The reader who has lower tier has higher priority to get promoter to writer.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Publicly<wbr>Accessible<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Bool to control if instance is publicly accessible. Default is `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the instance.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Apply<wbr>Immediately<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Specifies whether any instance modifications
are applied immediately, or during the next maintenance window. Default is`false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Auto<wbr>Minor<wbr>Version<wbr>Upgrade<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Indicates that minor engine upgrades will be applied automatically to the instance during the maintenance window. Default is `true`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Availability<wbr>Zone<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The EC2 Availability Zone that the neptune instance is created in.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Cluster<wbr>Identifier<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The identifier of the [`aws.neptune.Cluster`](https://www.terraform.io/docs/providers/aws/r/neptune_cluster.html) in which to launch this instance.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Engine<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name of the database engine to be used for the neptune instance. Defaults to `neptune`. Valid Values: `neptune`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Engine<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The neptune engine version.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Identifier<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The indentifier for the neptune instance, if omitted, this provider will assign a random, unique identifier.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Identifier<wbr>Prefix<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Creates a unique identifier beginning with the specified prefix. Conflicts with `identifier`.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Instance<wbr>Class<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The instance class to use.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Neptune<wbr>Parameter<wbr>Group<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name of the neptune parameter group to associate with this instance.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Neptune<wbr>Subnet<wbr>Group<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}A subnet group to associate with this neptune instance. **NOTE:** This must match the `neptune_subnet_group_name` of the attached [`aws.neptune.Cluster`](https://www.terraform.io/docs/providers/aws/r/neptune_cluster.html).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Port<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The port on which the DB accepts connections. Defaults to `8182`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Preferred<wbr>Backup<wbr>Window<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The daily time range during which automated backups are created if automated backups are enabled. Eg: &#34;04:00-09:00&#34;
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Preferred<wbr>Maintenance<wbr>Window<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The window to perform maintenance in.
Syntax: &#34;ddd:hh24:mi-ddd:hh24:mi&#34;. Eg: &#34;Mon:00:00-Mon:03:00&#34;.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Promotion<wbr>Tier<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}Default 0. Failover Priority setting on instance level. The reader who has lower tier has higher priority to get promoter to writer.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Publicly<wbr>Accessible<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Bool to control if instance is publicly accessible. Default is `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the instance.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">apply<wbr>Immediately<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Specifies whether any instance modifications
are applied immediately, or during the next maintenance window. Default is`false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">auto<wbr>Minor<wbr>Version<wbr>Upgrade<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Indicates that minor engine upgrades will be applied automatically to the instance during the maintenance window. Default is `true`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">availability<wbr>Zone<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The EC2 Availability Zone that the neptune instance is created in.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">cluster<wbr>Identifier<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The identifier of the [`aws.neptune.Cluster`](https://www.terraform.io/docs/providers/aws/r/neptune_cluster.html) in which to launch this instance.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">engine<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the database engine to be used for the neptune instance. Defaults to `neptune`. Valid Values: `neptune`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">engine<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The neptune engine version.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">identifier<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The indentifier for the neptune instance, if omitted, this provider will assign a random, unique identifier.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">identifier<wbr>Prefix<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Creates a unique identifier beginning with the specified prefix. Conflicts with `identifier`.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">instance<wbr>Class<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The instance class to use.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">neptune<wbr>Parameter<wbr>Group<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the neptune parameter group to associate with this instance.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">neptune<wbr>Subnet<wbr>Group<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A subnet group to associate with this neptune instance. **NOTE:** This must match the `neptune_subnet_group_name` of the attached [`aws.neptune.Cluster`](https://www.terraform.io/docs/providers/aws/r/neptune_cluster.html).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">port<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The port on which the DB accepts connections. Defaults to `8182`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">preferred<wbr>Backup<wbr>Window<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The daily time range during which automated backups are created if automated backups are enabled. Eg: &#34;04:00-09:00&#34;
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">preferred<wbr>Maintenance<wbr>Window<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The window to perform maintenance in.
Syntax: &#34;ddd:hh24:mi-ddd:hh24:mi&#34;. Eg: &#34;Mon:00:00-Mon:03:00&#34;.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">promotion<wbr>Tier<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}Default 0. Failover Priority setting on instance level. The reader who has lower tier has higher priority to get promoter to writer.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">publicly<wbr>Accessible<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Bool to control if instance is publicly accessible. Default is `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the instance.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">apply_<wbr>immediately<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Specifies whether any instance modifications
are applied immediately, or during the next maintenance window. Default is`false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">auto_<wbr>minor_<wbr>version_<wbr>upgrade<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Indicates that minor engine upgrades will be applied automatically to the instance during the maintenance window. Default is `true`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">availability_<wbr>zone<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The EC2 Availability Zone that the neptune instance is created in.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">cluster_<wbr>identifier<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The identifier of the [`aws.neptune.Cluster`](https://www.terraform.io/docs/providers/aws/r/neptune_cluster.html) in which to launch this instance.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">engine<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the database engine to be used for the neptune instance. Defaults to `neptune`. Valid Values: `neptune`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">engine_<wbr>version<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The neptune engine version.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">identifier<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The indentifier for the neptune instance, if omitted, this provider will assign a random, unique identifier.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">identifier_<wbr>prefix<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Creates a unique identifier beginning with the specified prefix. Conflicts with `identifier`.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">instance_<wbr>class<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The instance class to use.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">neptune_<wbr>parameter_<wbr>group_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the neptune parameter group to associate with this instance.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">neptune_<wbr>subnet_<wbr>group_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A subnet group to associate with this neptune instance. **NOTE:** This must match the `neptune_subnet_group_name` of the attached [`aws.neptune.Cluster`](https://www.terraform.io/docs/providers/aws/r/neptune_cluster.html).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">port<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The port on which the DB accepts connections. Defaults to `8182`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">preferred_<wbr>backup_<wbr>window<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The daily time range during which automated backups are created if automated backups are enabled. Eg: &#34;04:00-09:00&#34;
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">preferred_<wbr>maintenance_<wbr>window<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The window to perform maintenance in.
Syntax: &#34;ddd:hh24:mi-ddd:hh24:mi&#34;. Eg: &#34;Mon:00:00-Mon:03:00&#34;.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">promotion_<wbr>tier<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}Default 0. Failover Priority setting on instance level. The reader who has lower tier has higher priority to get promoter to writer.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">publicly_<wbr>accessible<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Bool to control if instance is publicly accessible. Default is `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the instance.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}




## ClusterInstance Output Properties

The following output properties are available:




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Address<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The hostname of the instance. See also `endpoint` and `port`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Apply<wbr>Immediately<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Specifies whether any instance modifications
are applied immediately, or during the next maintenance window. Default is`false`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of neptune instance
{{% /md %}}</dd>

    <dt class="property-"
            title="">Auto<wbr>Minor<wbr>Version<wbr>Upgrade<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Indicates that minor engine upgrades will be applied automatically to the instance during the maintenance window. Default is `true`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Availability<wbr>Zone<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The EC2 Availability Zone that the neptune instance is created in.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Cluster<wbr>Identifier<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The identifier of the [`aws.neptune.Cluster`](https://www.terraform.io/docs/providers/aws/r/neptune_cluster.html) in which to launch this instance.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Dbi<wbr>Resource<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The region-unique, immutable identifier for the neptune instance.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Endpoint<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The connection endpoint in `address:port` format.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Engine<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the database engine to be used for the neptune instance. Defaults to `neptune`. Valid Values: `neptune`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Engine<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The neptune engine version.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Identifier<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The indentifier for the neptune instance, if omitted, this provider will assign a random, unique identifier.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Identifier<wbr>Prefix<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Creates a unique identifier beginning with the specified prefix. Conflicts with `identifier`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Instance<wbr>Class<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The instance class to use.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Kms<wbr>Key<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN for the KMS encryption key if one is set to the neptune cluster.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Neptune<wbr>Parameter<wbr>Group<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the neptune parameter group to associate with this instance.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Neptune<wbr>Subnet<wbr>Group<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}A subnet group to associate with this neptune instance. **NOTE:** This must match the `neptune_subnet_group_name` of the attached [`aws.neptune.Cluster`](https://www.terraform.io/docs/providers/aws/r/neptune_cluster.html).
{{% /md %}}</dd>

    <dt class="property-"
            title="">Port<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The port on which the DB accepts connections. Defaults to `8182`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Preferred<wbr>Backup<wbr>Window<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The daily time range during which automated backups are created if automated backups are enabled. Eg: &#34;04:00-09:00&#34;
{{% /md %}}</dd>

    <dt class="property-"
            title="">Preferred<wbr>Maintenance<wbr>Window<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The window to perform maintenance in.
Syntax: &#34;ddd:hh24:mi-ddd:hh24:mi&#34;. Eg: &#34;Mon:00:00-Mon:03:00&#34;.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Promotion<wbr>Tier<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}Default 0. Failover Priority setting on instance level. The reader who has lower tier has higher priority to get promoter to writer.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Publicly<wbr>Accessible<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Bool to control if instance is publicly accessible. Default is `false`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Storage<wbr>Encrypted<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Specifies whether the neptune cluster is encrypted.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the instance.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Writer<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Boolean indicating if this instance is writable. `False` indicates this instance is a read replica.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Address<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The hostname of the instance. See also `endpoint` and `port`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Apply<wbr>Immediately<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Specifies whether any instance modifications
are applied immediately, or during the next maintenance window. Default is`false`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of neptune instance
{{% /md %}}</dd>

    <dt class="property-"
            title="">Auto<wbr>Minor<wbr>Version<wbr>Upgrade<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Indicates that minor engine upgrades will be applied automatically to the instance during the maintenance window. Default is `true`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Availability<wbr>Zone<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The EC2 Availability Zone that the neptune instance is created in.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Cluster<wbr>Identifier<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The identifier of the [`aws.neptune.Cluster`](https://www.terraform.io/docs/providers/aws/r/neptune_cluster.html) in which to launch this instance.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Dbi<wbr>Resource<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The region-unique, immutable identifier for the neptune instance.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Endpoint<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The connection endpoint in `address:port` format.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Engine<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name of the database engine to be used for the neptune instance. Defaults to `neptune`. Valid Values: `neptune`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Engine<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The neptune engine version.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Identifier<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The indentifier for the neptune instance, if omitted, this provider will assign a random, unique identifier.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Identifier<wbr>Prefix<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Creates a unique identifier beginning with the specified prefix. Conflicts with `identifier`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Instance<wbr>Class<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The instance class to use.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Kms<wbr>Key<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN for the KMS encryption key if one is set to the neptune cluster.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Neptune<wbr>Parameter<wbr>Group<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name of the neptune parameter group to associate with this instance.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Neptune<wbr>Subnet<wbr>Group<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}A subnet group to associate with this neptune instance. **NOTE:** This must match the `neptune_subnet_group_name` of the attached [`aws.neptune.Cluster`](https://www.terraform.io/docs/providers/aws/r/neptune_cluster.html).
{{% /md %}}</dd>

    <dt class="property-"
            title="">Port<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The port on which the DB accepts connections. Defaults to `8182`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Preferred<wbr>Backup<wbr>Window<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The daily time range during which automated backups are created if automated backups are enabled. Eg: &#34;04:00-09:00&#34;
{{% /md %}}</dd>

    <dt class="property-"
            title="">Preferred<wbr>Maintenance<wbr>Window<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The window to perform maintenance in.
Syntax: &#34;ddd:hh24:mi-ddd:hh24:mi&#34;. Eg: &#34;Mon:00:00-Mon:03:00&#34;.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Promotion<wbr>Tier<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}Default 0. Failover Priority setting on instance level. The reader who has lower tier has higher priority to get promoter to writer.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Publicly<wbr>Accessible<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Bool to control if instance is publicly accessible. Default is `false`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Storage<wbr>Encrypted<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Specifies whether the neptune cluster is encrypted.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the instance.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Writer<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Boolean indicating if this instance is writable. `False` indicates this instance is a read replica.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">address<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The hostname of the instance. See also `endpoint` and `port`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">apply<wbr>Immediately<span class="property-indicator"></span>
        <span class="property-type">boolean</span>
    </dt>
    <dd>{{% md %}}Specifies whether any instance modifications
are applied immediately, or during the next maintenance window. Default is`false`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of neptune instance
{{% /md %}}</dd>

    <dt class="property-"
            title="">auto<wbr>Minor<wbr>Version<wbr>Upgrade<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Indicates that minor engine upgrades will be applied automatically to the instance during the maintenance window. Default is `true`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">availability<wbr>Zone<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The EC2 Availability Zone that the neptune instance is created in.
{{% /md %}}</dd>

    <dt class="property-"
            title="">cluster<wbr>Identifier<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The identifier of the [`aws.neptune.Cluster`](https://www.terraform.io/docs/providers/aws/r/neptune_cluster.html) in which to launch this instance.
{{% /md %}}</dd>

    <dt class="property-"
            title="">dbi<wbr>Resource<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The region-unique, immutable identifier for the neptune instance.
{{% /md %}}</dd>

    <dt class="property-"
            title="">endpoint<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The connection endpoint in `address:port` format.
{{% /md %}}</dd>

    <dt class="property-"
            title="">engine<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the database engine to be used for the neptune instance. Defaults to `neptune`. Valid Values: `neptune`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">engine<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The neptune engine version.
{{% /md %}}</dd>

    <dt class="property-"
            title="">identifier<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The indentifier for the neptune instance, if omitted, this provider will assign a random, unique identifier.
{{% /md %}}</dd>

    <dt class="property-"
            title="">identifier<wbr>Prefix<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Creates a unique identifier beginning with the specified prefix. Conflicts with `identifier`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">instance<wbr>Class<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The instance class to use.
{{% /md %}}</dd>

    <dt class="property-"
            title="">kms<wbr>Key<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN for the KMS encryption key if one is set to the neptune cluster.
{{% /md %}}</dd>

    <dt class="property-"
            title="">neptune<wbr>Parameter<wbr>Group<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the neptune parameter group to associate with this instance.
{{% /md %}}</dd>

    <dt class="property-"
            title="">neptune<wbr>Subnet<wbr>Group<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}A subnet group to associate with this neptune instance. **NOTE:** This must match the `neptune_subnet_group_name` of the attached [`aws.neptune.Cluster`](https://www.terraform.io/docs/providers/aws/r/neptune_cluster.html).
{{% /md %}}</dd>

    <dt class="property-"
            title="">port<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The port on which the DB accepts connections. Defaults to `8182`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">preferred<wbr>Backup<wbr>Window<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The daily time range during which automated backups are created if automated backups are enabled. Eg: &#34;04:00-09:00&#34;
{{% /md %}}</dd>

    <dt class="property-"
            title="">preferred<wbr>Maintenance<wbr>Window<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The window to perform maintenance in.
Syntax: &#34;ddd:hh24:mi-ddd:hh24:mi&#34;. Eg: &#34;Mon:00:00-Mon:03:00&#34;.
{{% /md %}}</dd>

    <dt class="property-"
            title="">promotion<wbr>Tier<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}Default 0. Failover Priority setting on instance level. The reader who has lower tier has higher priority to get promoter to writer.
{{% /md %}}</dd>

    <dt class="property-"
            title="">publicly<wbr>Accessible<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Bool to control if instance is publicly accessible. Default is `false`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">storage<wbr>Encrypted<span class="property-indicator"></span>
        <span class="property-type">boolean</span>
    </dt>
    <dd>{{% md %}}Specifies whether the neptune cluster is encrypted.
{{% /md %}}</dd>

    <dt class="property-"
            title="">tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the instance.
{{% /md %}}</dd>

    <dt class="property-"
            title="">writer<span class="property-indicator"></span>
        <span class="property-type">boolean</span>
    </dt>
    <dd>{{% md %}}Boolean indicating if this instance is writable. `False` indicates this instance is a read replica.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">address<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The hostname of the instance. See also `endpoint` and `port`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">apply_<wbr>immediately<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Specifies whether any instance modifications
are applied immediately, or during the next maintenance window. Default is`false`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of neptune instance
{{% /md %}}</dd>

    <dt class="property-"
            title="">auto_<wbr>minor_<wbr>version_<wbr>upgrade<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Indicates that minor engine upgrades will be applied automatically to the instance during the maintenance window. Default is `true`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">availability_<wbr>zone<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The EC2 Availability Zone that the neptune instance is created in.
{{% /md %}}</dd>

    <dt class="property-"
            title="">cluster_<wbr>identifier<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The identifier of the [`aws.neptune.Cluster`](https://www.terraform.io/docs/providers/aws/r/neptune_cluster.html) in which to launch this instance.
{{% /md %}}</dd>

    <dt class="property-"
            title="">dbi_<wbr>resource_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The region-unique, immutable identifier for the neptune instance.
{{% /md %}}</dd>

    <dt class="property-"
            title="">endpoint<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The connection endpoint in `address:port` format.
{{% /md %}}</dd>

    <dt class="property-"
            title="">engine<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the database engine to be used for the neptune instance. Defaults to `neptune`. Valid Values: `neptune`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">engine_<wbr>version<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The neptune engine version.
{{% /md %}}</dd>

    <dt class="property-"
            title="">identifier<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The indentifier for the neptune instance, if omitted, this provider will assign a random, unique identifier.
{{% /md %}}</dd>

    <dt class="property-"
            title="">identifier_<wbr>prefix<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Creates a unique identifier beginning with the specified prefix. Conflicts with `identifier`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">instance_<wbr>class<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The instance class to use.
{{% /md %}}</dd>

    <dt class="property-"
            title="">kms_<wbr>key_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ARN for the KMS encryption key if one is set to the neptune cluster.
{{% /md %}}</dd>

    <dt class="property-"
            title="">neptune_<wbr>parameter_<wbr>group_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the neptune parameter group to associate with this instance.
{{% /md %}}</dd>

    <dt class="property-"
            title="">neptune_<wbr>subnet_<wbr>group_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A subnet group to associate with this neptune instance. **NOTE:** This must match the `neptune_subnet_group_name` of the attached [`aws.neptune.Cluster`](https://www.terraform.io/docs/providers/aws/r/neptune_cluster.html).
{{% /md %}}</dd>

    <dt class="property-"
            title="">port<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The port on which the DB accepts connections. Defaults to `8182`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">preferred_<wbr>backup_<wbr>window<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The daily time range during which automated backups are created if automated backups are enabled. Eg: &#34;04:00-09:00&#34;
{{% /md %}}</dd>

    <dt class="property-"
            title="">preferred_<wbr>maintenance_<wbr>window<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The window to perform maintenance in.
Syntax: &#34;ddd:hh24:mi-ddd:hh24:mi&#34;. Eg: &#34;Mon:00:00-Mon:03:00&#34;.
{{% /md %}}</dd>

    <dt class="property-"
            title="">promotion_<wbr>tier<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}Default 0. Failover Priority setting on instance level. The reader who has lower tier has higher priority to get promoter to writer.
{{% /md %}}</dd>

    <dt class="property-"
            title="">publicly_<wbr>accessible<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Bool to control if instance is publicly accessible. Default is `false`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">storage_<wbr>encrypted<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Specifies whether the neptune cluster is encrypted.
{{% /md %}}</dd>

    <dt class="property-"
            title="">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the instance.
{{% /md %}}</dd>

    <dt class="property-"
            title="">writer<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Boolean indicating if this instance is writable. `False` indicates this instance is a read replica.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





## Look up an Existing ClusterInstance Resource

{{< chooser language "javascript,typescript,python,go,csharp  " / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">pulumi.Input&lt;pulumi.ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/neptune/#ClusterInstanceState">ClusterInstanceState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/neptune/#ClusterInstance">ClusterInstance</a></span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>address=None<span class="p">, </span>apply_immediately=None<span class="p">, </span>arn=None<span class="p">, </span>auto_minor_version_upgrade=None<span class="p">, </span>availability_zone=None<span class="p">, </span>cluster_identifier=None<span class="p">, </span>dbi_resource_id=None<span class="p">, </span>endpoint=None<span class="p">, </span>engine=None<span class="p">, </span>engine_version=None<span class="p">, </span>identifier=None<span class="p">, </span>identifier_prefix=None<span class="p">, </span>instance_class=None<span class="p">, </span>kms_key_arn=None<span class="p">, </span>neptune_parameter_group_name=None<span class="p">, </span>neptune_subnet_group_name=None<span class="p">, </span>port=None<span class="p">, </span>preferred_backup_window=None<span class="p">, </span>preferred_maintenance_window=None<span class="p">, </span>promotion_tier=None<span class="p">, </span>publicly_accessible=None<span class="p">, </span>storage_encrypted=None<span class="p">, </span>tags=None<span class="p">, </span>writer=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetClusterInstance<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">pulumi.IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/neptune?tab=doc#ClusterInstanceState">ClusterInstanceState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/neptune?tab=doc#ClusterInstance">ClusterInstance</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Neptune.ClusterInstance.html">ClusterInstance</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Pulumi.Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Neptune.ClusterInstanceState.html">ClusterInstanceState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
{{% /choosable %}}

Get an existing ClusterInstance resource's state with the given name, ID, and optional extra properties used to qualify the lookup.

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
            title="Optional">Address<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The hostname of the instance. See also `endpoint` and `port`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Apply<wbr>Immediately<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Specifies whether any instance modifications
are applied immediately, or during the next maintenance window. Default is`false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of neptune instance
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Auto<wbr>Minor<wbr>Version<wbr>Upgrade<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Indicates that minor engine upgrades will be applied automatically to the instance during the maintenance window. Default is `true`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Availability<wbr>Zone<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The EC2 Availability Zone that the neptune instance is created in.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Cluster<wbr>Identifier<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The identifier of the [`aws.neptune.Cluster`](https://www.terraform.io/docs/providers/aws/r/neptune_cluster.html) in which to launch this instance.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Dbi<wbr>Resource<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The region-unique, immutable identifier for the neptune instance.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Endpoint<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The connection endpoint in `address:port` format.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Engine<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the database engine to be used for the neptune instance. Defaults to `neptune`. Valid Values: `neptune`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Engine<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The neptune engine version.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Identifier<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The indentifier for the neptune instance, if omitted, this provider will assign a random, unique identifier.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Identifier<wbr>Prefix<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Creates a unique identifier beginning with the specified prefix. Conflicts with `identifier`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Instance<wbr>Class<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The instance class to use.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Kms<wbr>Key<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ARN for the KMS encryption key if one is set to the neptune cluster.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Neptune<wbr>Parameter<wbr>Group<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the neptune parameter group to associate with this instance.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Neptune<wbr>Subnet<wbr>Group<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A subnet group to associate with this neptune instance. **NOTE:** This must match the `neptune_subnet_group_name` of the attached [`aws.neptune.Cluster`](https://www.terraform.io/docs/providers/aws/r/neptune_cluster.html).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Port<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The port on which the DB accepts connections. Defaults to `8182`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Preferred<wbr>Backup<wbr>Window<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The daily time range during which automated backups are created if automated backups are enabled. Eg: &#34;04:00-09:00&#34;
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Preferred<wbr>Maintenance<wbr>Window<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The window to perform maintenance in.
Syntax: &#34;ddd:hh24:mi-ddd:hh24:mi&#34;. Eg: &#34;Mon:00:00-Mon:03:00&#34;.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Promotion<wbr>Tier<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}Default 0. Failover Priority setting on instance level. The reader who has lower tier has higher priority to get promoter to writer.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Publicly<wbr>Accessible<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Bool to control if instance is publicly accessible. Default is `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Storage<wbr>Encrypted<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Specifies whether the neptune cluster is encrypted.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the instance.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Writer<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Boolean indicating if this instance is writable. `False` indicates this instance is a read replica.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Address<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The hostname of the instance. See also `endpoint` and `port`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Apply<wbr>Immediately<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Specifies whether any instance modifications
are applied immediately, or during the next maintenance window. Default is`false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of neptune instance
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Auto<wbr>Minor<wbr>Version<wbr>Upgrade<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Indicates that minor engine upgrades will be applied automatically to the instance during the maintenance window. Default is `true`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Availability<wbr>Zone<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The EC2 Availability Zone that the neptune instance is created in.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Cluster<wbr>Identifier<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The identifier of the [`aws.neptune.Cluster`](https://www.terraform.io/docs/providers/aws/r/neptune_cluster.html) in which to launch this instance.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Dbi<wbr>Resource<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The region-unique, immutable identifier for the neptune instance.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Endpoint<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The connection endpoint in `address:port` format.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Engine<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name of the database engine to be used for the neptune instance. Defaults to `neptune`. Valid Values: `neptune`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Engine<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The neptune engine version.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Identifier<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The indentifier for the neptune instance, if omitted, this provider will assign a random, unique identifier.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Identifier<wbr>Prefix<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Creates a unique identifier beginning with the specified prefix. Conflicts with `identifier`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Instance<wbr>Class<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The instance class to use.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Kms<wbr>Key<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The ARN for the KMS encryption key if one is set to the neptune cluster.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Neptune<wbr>Parameter<wbr>Group<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name of the neptune parameter group to associate with this instance.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Neptune<wbr>Subnet<wbr>Group<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}A subnet group to associate with this neptune instance. **NOTE:** This must match the `neptune_subnet_group_name` of the attached [`aws.neptune.Cluster`](https://www.terraform.io/docs/providers/aws/r/neptune_cluster.html).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Port<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The port on which the DB accepts connections. Defaults to `8182`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Preferred<wbr>Backup<wbr>Window<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The daily time range during which automated backups are created if automated backups are enabled. Eg: &#34;04:00-09:00&#34;
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Preferred<wbr>Maintenance<wbr>Window<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The window to perform maintenance in.
Syntax: &#34;ddd:hh24:mi-ddd:hh24:mi&#34;. Eg: &#34;Mon:00:00-Mon:03:00&#34;.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Promotion<wbr>Tier<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}Default 0. Failover Priority setting on instance level. The reader who has lower tier has higher priority to get promoter to writer.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Publicly<wbr>Accessible<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Bool to control if instance is publicly accessible. Default is `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Storage<wbr>Encrypted<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Specifies whether the neptune cluster is encrypted.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the instance.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Writer<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Boolean indicating if this instance is writable. `False` indicates this instance is a read replica.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">address<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The hostname of the instance. See also `endpoint` and `port`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">apply<wbr>Immediately<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Specifies whether any instance modifications
are applied immediately, or during the next maintenance window. Default is`false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of neptune instance
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">auto<wbr>Minor<wbr>Version<wbr>Upgrade<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Indicates that minor engine upgrades will be applied automatically to the instance during the maintenance window. Default is `true`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">availability<wbr>Zone<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The EC2 Availability Zone that the neptune instance is created in.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">cluster<wbr>Identifier<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The identifier of the [`aws.neptune.Cluster`](https://www.terraform.io/docs/providers/aws/r/neptune_cluster.html) in which to launch this instance.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">dbi<wbr>Resource<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The region-unique, immutable identifier for the neptune instance.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">endpoint<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The connection endpoint in `address:port` format.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">engine<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the database engine to be used for the neptune instance. Defaults to `neptune`. Valid Values: `neptune`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">engine<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The neptune engine version.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">identifier<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The indentifier for the neptune instance, if omitted, this provider will assign a random, unique identifier.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">identifier<wbr>Prefix<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Creates a unique identifier beginning with the specified prefix. Conflicts with `identifier`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">instance<wbr>Class<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The instance class to use.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">kms<wbr>Key<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ARN for the KMS encryption key if one is set to the neptune cluster.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">neptune<wbr>Parameter<wbr>Group<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the neptune parameter group to associate with this instance.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">neptune<wbr>Subnet<wbr>Group<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A subnet group to associate with this neptune instance. **NOTE:** This must match the `neptune_subnet_group_name` of the attached [`aws.neptune.Cluster`](https://www.terraform.io/docs/providers/aws/r/neptune_cluster.html).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">port<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The port on which the DB accepts connections. Defaults to `8182`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">preferred<wbr>Backup<wbr>Window<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The daily time range during which automated backups are created if automated backups are enabled. Eg: &#34;04:00-09:00&#34;
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">preferred<wbr>Maintenance<wbr>Window<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The window to perform maintenance in.
Syntax: &#34;ddd:hh24:mi-ddd:hh24:mi&#34;. Eg: &#34;Mon:00:00-Mon:03:00&#34;.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">promotion<wbr>Tier<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}Default 0. Failover Priority setting on instance level. The reader who has lower tier has higher priority to get promoter to writer.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">publicly<wbr>Accessible<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Bool to control if instance is publicly accessible. Default is `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">storage<wbr>Encrypted<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Specifies whether the neptune cluster is encrypted.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the instance.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">writer<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Boolean indicating if this instance is writable. `False` indicates this instance is a read replica.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">address<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The hostname of the instance. See also `endpoint` and `port`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">apply_<wbr>immediately<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Specifies whether any instance modifications
are applied immediately, or during the next maintenance window. Default is`false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of neptune instance
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">auto_<wbr>minor_<wbr>version_<wbr>upgrade<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Indicates that minor engine upgrades will be applied automatically to the instance during the maintenance window. Default is `true`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">availability_<wbr>zone<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The EC2 Availability Zone that the neptune instance is created in.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">cluster_<wbr>identifier<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The identifier of the [`aws.neptune.Cluster`](https://www.terraform.io/docs/providers/aws/r/neptune_cluster.html) in which to launch this instance.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">dbi_<wbr>resource_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The region-unique, immutable identifier for the neptune instance.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">endpoint<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The connection endpoint in `address:port` format.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">engine<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the database engine to be used for the neptune instance. Defaults to `neptune`. Valid Values: `neptune`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">engine_<wbr>version<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The neptune engine version.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">identifier<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The indentifier for the neptune instance, if omitted, this provider will assign a random, unique identifier.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">identifier_<wbr>prefix<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Creates a unique identifier beginning with the specified prefix. Conflicts with `identifier`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">instance_<wbr>class<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The instance class to use.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">kms_<wbr>key_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ARN for the KMS encryption key if one is set to the neptune cluster.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">neptune_<wbr>parameter_<wbr>group_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the neptune parameter group to associate with this instance.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">neptune_<wbr>subnet_<wbr>group_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A subnet group to associate with this neptune instance. **NOTE:** This must match the `neptune_subnet_group_name` of the attached [`aws.neptune.Cluster`](https://www.terraform.io/docs/providers/aws/r/neptune_cluster.html).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">port<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The port on which the DB accepts connections. Defaults to `8182`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">preferred_<wbr>backup_<wbr>window<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The daily time range during which automated backups are created if automated backups are enabled. Eg: &#34;04:00-09:00&#34;
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">preferred_<wbr>maintenance_<wbr>window<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The window to perform maintenance in.
Syntax: &#34;ddd:hh24:mi-ddd:hh24:mi&#34;. Eg: &#34;Mon:00:00-Mon:03:00&#34;.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">promotion_<wbr>tier<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}Default 0. Failover Priority setting on instance level. The reader who has lower tier has higher priority to get promoter to writer.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">publicly_<wbr>accessible<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Bool to control if instance is publicly accessible. Default is `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">storage_<wbr>encrypted<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Specifies whether the neptune cluster is encrypted.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the instance.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">writer<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Boolean indicating if this instance is writable. `False` indicates this instance is a read replica.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}







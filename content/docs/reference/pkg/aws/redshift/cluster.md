
---
title: "Cluster"
block_external_search_index: true
---

Provides a Redshift Cluster Resource.

> **Note:** All arguments including the username and password will be stored in the raw state as plain-text.
[Read more about sensitive data in state](https://www.terraform.io/docs/state/sensitive-data.html).

## Example Usage

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const defaultCluster = new aws.redshift.Cluster("default", {
    clusterIdentifier: "tf-redshift-cluster",
    clusterType: "single-node",
    databaseName: "mydb",
    masterPassword: "Mustbe8characters",
    masterUsername: "foo",
    nodeType: "dc1.large",
});
```

> This content is derived from https://github.com/terraform-providers/terraform-provider-aws/blob/master/website/docs/r/redshift_cluster.html.markdown.



## Create a Cluster Resource

{{< chooser language "javascript,typescript,python,go,csharp" / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/redshift/#Cluster">Cluster</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/redshift/#ClusterArgs">ClusterArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">Cluster</span><span class="p">(resource_name, opts=None, </span>allow_version_upgrade=None<span class="p">, </span>automated_snapshot_retention_period=None<span class="p">, </span>availability_zone=None<span class="p">, </span>cluster_identifier=None<span class="p">, </span>cluster_parameter_group_name=None<span class="p">, </span>cluster_public_key=None<span class="p">, </span>cluster_revision_number=None<span class="p">, </span>cluster_security_groups=None<span class="p">, </span>cluster_subnet_group_name=None<span class="p">, </span>cluster_type=None<span class="p">, </span>cluster_version=None<span class="p">, </span>database_name=None<span class="p">, </span>elastic_ip=None<span class="p">, </span>encrypted=None<span class="p">, </span>endpoint=None<span class="p">, </span>enhanced_vpc_routing=None<span class="p">, </span>final_snapshot_identifier=None<span class="p">, </span>iam_roles=None<span class="p">, </span>kms_key_id=None<span class="p">, </span>logging=None<span class="p">, </span>master_password=None<span class="p">, </span>master_username=None<span class="p">, </span>node_type=None<span class="p">, </span>number_of_nodes=None<span class="p">, </span>owner_account=None<span class="p">, </span>port=None<span class="p">, </span>preferred_maintenance_window=None<span class="p">, </span>publicly_accessible=None<span class="p">, </span>skip_final_snapshot=None<span class="p">, </span>snapshot_cluster_identifier=None<span class="p">, </span>snapshot_copy=None<span class="p">, </span>snapshot_identifier=None<span class="p">, </span>tags=None<span class="p">, </span>vpc_security_group_ids=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewCluster<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/redshift?tab=doc#ClusterArgs">ClusterArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/redshift?tab=doc#Cluster">Cluster</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Redshift.Cluster.html">Cluster</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Redshift.ClusterArgs.html">ClusterArgs</a></span> <span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
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
            title="Optional">Allow<wbr>Version<wbr>Upgrade<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}If true , major version upgrades can be applied during the maintenance window to the Amazon Redshift engine that is running on the cluster. Default is true
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Automated<wbr>Snapshot<wbr>Retention<wbr>Period<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The number of days that automated snapshots are retained. If the value is 0, automated snapshots are disabled. Even if automated snapshots are disabled, you can still create manual snapshots when you want with create-cluster-snapshot. Default is 1.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Availability<wbr>Zone<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The EC2 Availability Zone (AZ) in which you want Amazon Redshift to provision the cluster. For example, if you have several EC2 instances running in a specific Availability Zone, then you might want the cluster to be provisioned in the same zone in order to decrease network latency.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Cluster<wbr>Identifier<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Cluster Identifier. Must be a lower case
string.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Cluster<wbr>Parameter<wbr>Group<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the parameter group to be associated with this cluster.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Cluster<wbr>Public<wbr>Key<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The public key for the cluster
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Cluster<wbr>Revision<wbr>Number<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The specific revision number of the database in the cluster
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Cluster<wbr>Security<wbr>Groups<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}A list of security groups to be associated with this cluster.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Cluster<wbr>Subnet<wbr>Group<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of a cluster subnet group to be associated with this cluster. If this parameter is not provided the resulting cluster will be deployed outside virtual private cloud (VPC).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Cluster<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The cluster type to use. Either `single-node` or `multi-node`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Cluster<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The version of the Amazon Redshift engine software that you want to deploy on the cluster.
The version selected runs on all the nodes in the cluster.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Database<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the first database to be created when the cluster is created.
If you do not provide a name, Amazon Redshift will create a default database called `dev`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Elastic<wbr>Ip<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The Elastic IP (EIP) address for the cluster.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Encrypted<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}If true , the data in the cluster is encrypted at rest.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Endpoint<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The connection endpoint
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Enhanced<wbr>Vpc<wbr>Routing<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}If true , enhanced VPC routing is enabled.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Final<wbr>Snapshot<wbr>Identifier<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The identifier of the final snapshot that is to be created immediately before deleting the cluster. If this parameter is provided, `skip_final_snapshot` must be false.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Iam<wbr>Roles<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}A list of IAM Role ARNs to associate with the cluster. A Maximum of 10 can be associated to the cluster at any time.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Kms<wbr>Key<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ARN for the KMS encryption key. When specifying `kms_key_id`, `encrypted` needs to be set to true.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Logging<span class="property-indicator"></span>
        <span class="property-type"><a href="#clusterlogging">Cluster<wbr>Logging<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}Logging, documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Master<wbr>Password<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Password for the master DB user.
Note that this may show up in logs, and it will be stored in the state file. Password must contain at least 8 chars and
contain at least one uppercase letter, one lowercase letter, and one number.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Master<wbr>Username<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Username for the master DB user.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Node<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The node type to be provisioned for the cluster.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Number<wbr>Of<wbr>Nodes<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The number of compute nodes in the cluster. This parameter is required when the ClusterType parameter is specified as multi-node. Default is 1.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Owner<wbr>Account<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The AWS customer account used to create or copy the snapshot. Required if you are restoring a snapshot you do not own, optional if you own the snapshot.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Port<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The port number on which the cluster accepts incoming connections.
The cluster is accessible only via the JDBC and ODBC connection strings. Part of the connection string requires the port on which the cluster will listen for incoming connections. Default port is 5439.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Preferred<wbr>Maintenance<wbr>Window<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The weekly time range (in UTC) during which automated cluster maintenance can occur.
Format: ddd:hh24:mi-ddd:hh24:mi
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Publicly<wbr>Accessible<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}If true, the cluster can be accessed from a public network. Default is `true`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Skip<wbr>Final<wbr>Snapshot<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Determines whether a final snapshot of the cluster is created before Amazon Redshift deletes the cluster. If true , a final cluster snapshot is not created. If false , a final cluster snapshot is created before the cluster is deleted. Default is false.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Snapshot<wbr>Cluster<wbr>Identifier<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the cluster the source snapshot was created from.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Snapshot<wbr>Copy<span class="property-indicator"></span>
        <span class="property-type"><a href="#clustersnapshotcopy">Cluster<wbr>Snapshot<wbr>Copy<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}Configuration of automatic copy of snapshots from one region to another. Documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Snapshot<wbr>Identifier<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the snapshot from which to create the new cluster.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Vpc<wbr>Security<wbr>Group<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}A list of Virtual Private Cloud (VPC) security groups to be associated with the cluster.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Allow<wbr>Version<wbr>Upgrade<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}If true , major version upgrades can be applied during the maintenance window to the Amazon Redshift engine that is running on the cluster. Default is true
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Automated<wbr>Snapshot<wbr>Retention<wbr>Period<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The number of days that automated snapshots are retained. If the value is 0, automated snapshots are disabled. Even if automated snapshots are disabled, you can still create manual snapshots when you want with create-cluster-snapshot. Default is 1.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Availability<wbr>Zone<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The EC2 Availability Zone (AZ) in which you want Amazon Redshift to provision the cluster. For example, if you have several EC2 instances running in a specific Availability Zone, then you might want the cluster to be provisioned in the same zone in order to decrease network latency.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Cluster<wbr>Identifier<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Cluster Identifier. Must be a lower case
string.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Cluster<wbr>Parameter<wbr>Group<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name of the parameter group to be associated with this cluster.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Cluster<wbr>Public<wbr>Key<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The public key for the cluster
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Cluster<wbr>Revision<wbr>Number<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The specific revision number of the database in the cluster
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Cluster<wbr>Security<wbr>Groups<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}A list of security groups to be associated with this cluster.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Cluster<wbr>Subnet<wbr>Group<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name of a cluster subnet group to be associated with this cluster. If this parameter is not provided the resulting cluster will be deployed outside virtual private cloud (VPC).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Cluster<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The cluster type to use. Either `single-node` or `multi-node`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Cluster<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The version of the Amazon Redshift engine software that you want to deploy on the cluster.
The version selected runs on all the nodes in the cluster.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Database<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name of the first database to be created when the cluster is created.
If you do not provide a name, Amazon Redshift will create a default database called `dev`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Elastic<wbr>Ip<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The Elastic IP (EIP) address for the cluster.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Encrypted<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}If true , the data in the cluster is encrypted at rest.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Endpoint<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The connection endpoint
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Enhanced<wbr>Vpc<wbr>Routing<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}If true , enhanced VPC routing is enabled.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Final<wbr>Snapshot<wbr>Identifier<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The identifier of the final snapshot that is to be created immediately before deleting the cluster. If this parameter is provided, `skip_final_snapshot` must be false.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Iam<wbr>Roles<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}A list of IAM Role ARNs to associate with the cluster. A Maximum of 10 can be associated to the cluster at any time.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Kms<wbr>Key<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The ARN for the KMS encryption key. When specifying `kms_key_id`, `encrypted` needs to be set to true.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Logging<span class="property-indicator"></span>
        <span class="property-type"><a href="#clusterlogging">*Cluster<wbr>Logging</a></span>
    </dt>
    <dd>{{% md %}}Logging, documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Master<wbr>Password<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Password for the master DB user.
Note that this may show up in logs, and it will be stored in the state file. Password must contain at least 8 chars and
contain at least one uppercase letter, one lowercase letter, and one number.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Master<wbr>Username<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Username for the master DB user.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Node<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The node type to be provisioned for the cluster.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Number<wbr>Of<wbr>Nodes<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The number of compute nodes in the cluster. This parameter is required when the ClusterType parameter is specified as multi-node. Default is 1.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Owner<wbr>Account<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The AWS customer account used to create or copy the snapshot. Required if you are restoring a snapshot you do not own, optional if you own the snapshot.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Port<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The port number on which the cluster accepts incoming connections.
The cluster is accessible only via the JDBC and ODBC connection strings. Part of the connection string requires the port on which the cluster will listen for incoming connections. Default port is 5439.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Preferred<wbr>Maintenance<wbr>Window<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The weekly time range (in UTC) during which automated cluster maintenance can occur.
Format: ddd:hh24:mi-ddd:hh24:mi
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Publicly<wbr>Accessible<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}If true, the cluster can be accessed from a public network. Default is `true`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Skip<wbr>Final<wbr>Snapshot<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Determines whether a final snapshot of the cluster is created before Amazon Redshift deletes the cluster. If true , a final cluster snapshot is not created. If false , a final cluster snapshot is created before the cluster is deleted. Default is false.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Snapshot<wbr>Cluster<wbr>Identifier<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name of the cluster the source snapshot was created from.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Snapshot<wbr>Copy<span class="property-indicator"></span>
        <span class="property-type"><a href="#clustersnapshotcopy">*Cluster<wbr>Snapshot<wbr>Copy</a></span>
    </dt>
    <dd>{{% md %}}Configuration of automatic copy of snapshots from one region to another. Documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Snapshot<wbr>Identifier<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name of the snapshot from which to create the new cluster.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Vpc<wbr>Security<wbr>Group<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}A list of Virtual Private Cloud (VPC) security groups to be associated with the cluster.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">allow<wbr>Version<wbr>Upgrade<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}If true , major version upgrades can be applied during the maintenance window to the Amazon Redshift engine that is running on the cluster. Default is true
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">automated<wbr>Snapshot<wbr>Retention<wbr>Period<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The number of days that automated snapshots are retained. If the value is 0, automated snapshots are disabled. Even if automated snapshots are disabled, you can still create manual snapshots when you want with create-cluster-snapshot. Default is 1.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">availability<wbr>Zone<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The EC2 Availability Zone (AZ) in which you want Amazon Redshift to provision the cluster. For example, if you have several EC2 instances running in a specific Availability Zone, then you might want the cluster to be provisioned in the same zone in order to decrease network latency.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">cluster<wbr>Identifier<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Cluster Identifier. Must be a lower case
string.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">cluster<wbr>Parameter<wbr>Group<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the parameter group to be associated with this cluster.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">cluster<wbr>Public<wbr>Key<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The public key for the cluster
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">cluster<wbr>Revision<wbr>Number<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The specific revision number of the database in the cluster
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">cluster<wbr>Security<wbr>Groups<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}A list of security groups to be associated with this cluster.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">cluster<wbr>Subnet<wbr>Group<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of a cluster subnet group to be associated with this cluster. If this parameter is not provided the resulting cluster will be deployed outside virtual private cloud (VPC).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">cluster<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The cluster type to use. Either `single-node` or `multi-node`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">cluster<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The version of the Amazon Redshift engine software that you want to deploy on the cluster.
The version selected runs on all the nodes in the cluster.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">database<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the first database to be created when the cluster is created.
If you do not provide a name, Amazon Redshift will create a default database called `dev`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">elastic<wbr>Ip<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The Elastic IP (EIP) address for the cluster.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">encrypted<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}If true , the data in the cluster is encrypted at rest.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">endpoint<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The connection endpoint
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">enhanced<wbr>Vpc<wbr>Routing<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}If true , enhanced VPC routing is enabled.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">final<wbr>Snapshot<wbr>Identifier<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The identifier of the final snapshot that is to be created immediately before deleting the cluster. If this parameter is provided, `skip_final_snapshot` must be false.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">iam<wbr>Roles<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}A list of IAM Role ARNs to associate with the cluster. A Maximum of 10 can be associated to the cluster at any time.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">kms<wbr>Key<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ARN for the KMS encryption key. When specifying `kms_key_id`, `encrypted` needs to be set to true.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">logging<span class="property-indicator"></span>
        <span class="property-type"><a href="#clusterlogging">Cluster<wbr>Logging?</a></span>
    </dt>
    <dd>{{% md %}}Logging, documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">master<wbr>Password<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Password for the master DB user.
Note that this may show up in logs, and it will be stored in the state file. Password must contain at least 8 chars and
contain at least one uppercase letter, one lowercase letter, and one number.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">master<wbr>Username<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Username for the master DB user.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">node<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The node type to be provisioned for the cluster.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">number<wbr>Of<wbr>Nodes<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The number of compute nodes in the cluster. This parameter is required when the ClusterType parameter is specified as multi-node. Default is 1.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">owner<wbr>Account<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The AWS customer account used to create or copy the snapshot. Required if you are restoring a snapshot you do not own, optional if you own the snapshot.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">port<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The port number on which the cluster accepts incoming connections.
The cluster is accessible only via the JDBC and ODBC connection strings. Part of the connection string requires the port on which the cluster will listen for incoming connections. Default port is 5439.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">preferred<wbr>Maintenance<wbr>Window<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The weekly time range (in UTC) during which automated cluster maintenance can occur.
Format: ddd:hh24:mi-ddd:hh24:mi
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">publicly<wbr>Accessible<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}If true, the cluster can be accessed from a public network. Default is `true`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">skip<wbr>Final<wbr>Snapshot<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Determines whether a final snapshot of the cluster is created before Amazon Redshift deletes the cluster. If true , a final cluster snapshot is not created. If false , a final cluster snapshot is created before the cluster is deleted. Default is false.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">snapshot<wbr>Cluster<wbr>Identifier<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the cluster the source snapshot was created from.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">snapshot<wbr>Copy<span class="property-indicator"></span>
        <span class="property-type"><a href="#clustersnapshotcopy">Cluster<wbr>Snapshot<wbr>Copy?</a></span>
    </dt>
    <dd>{{% md %}}Configuration of automatic copy of snapshots from one region to another. Documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">snapshot<wbr>Identifier<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the snapshot from which to create the new cluster.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">vpc<wbr>Security<wbr>Group<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}A list of Virtual Private Cloud (VPC) security groups to be associated with the cluster.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">allow_<wbr>version_<wbr>upgrade<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}If true , major version upgrades can be applied during the maintenance window to the Amazon Redshift engine that is running on the cluster. Default is true
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">automated_<wbr>snapshot_<wbr>retention_<wbr>period<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The number of days that automated snapshots are retained. If the value is 0, automated snapshots are disabled. Even if automated snapshots are disabled, you can still create manual snapshots when you want with create-cluster-snapshot. Default is 1.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">availability_<wbr>zone<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The EC2 Availability Zone (AZ) in which you want Amazon Redshift to provision the cluster. For example, if you have several EC2 instances running in a specific Availability Zone, then you might want the cluster to be provisioned in the same zone in order to decrease network latency.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">cluster_<wbr>identifier<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The Cluster Identifier. Must be a lower case
string.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">cluster_<wbr>parameter_<wbr>group_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the parameter group to be associated with this cluster.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">cluster_<wbr>public_<wbr>key<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The public key for the cluster
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">cluster_<wbr>revision_<wbr>number<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The specific revision number of the database in the cluster
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">cluster_<wbr>security_<wbr>groups<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}A list of security groups to be associated with this cluster.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">cluster_<wbr>subnet_<wbr>group_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of a cluster subnet group to be associated with this cluster. If this parameter is not provided the resulting cluster will be deployed outside virtual private cloud (VPC).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">cluster_<wbr>type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The cluster type to use. Either `single-node` or `multi-node`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">cluster_<wbr>version<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The version of the Amazon Redshift engine software that you want to deploy on the cluster.
The version selected runs on all the nodes in the cluster.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">database_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the first database to be created when the cluster is created.
If you do not provide a name, Amazon Redshift will create a default database called `dev`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">elastic_<wbr>ip<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The Elastic IP (EIP) address for the cluster.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">encrypted<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}If true , the data in the cluster is encrypted at rest.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">endpoint<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The connection endpoint
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">enhanced_<wbr>vpc_<wbr>routing<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}If true , enhanced VPC routing is enabled.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">final_<wbr>snapshot_<wbr>identifier<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The identifier of the final snapshot that is to be created immediately before deleting the cluster. If this parameter is provided, `skip_final_snapshot` must be false.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">iam_<wbr>roles<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}A list of IAM Role ARNs to associate with the cluster. A Maximum of 10 can be associated to the cluster at any time.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">kms_<wbr>key_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ARN for the KMS encryption key. When specifying `kms_key_id`, `encrypted` needs to be set to true.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">logging<span class="property-indicator"></span>
        <span class="property-type"><a href="#clusterlogging">Dict[Cluster<wbr>Logging]</a></span>
    </dt>
    <dd>{{% md %}}Logging, documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">master_<wbr>password<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Password for the master DB user.
Note that this may show up in logs, and it will be stored in the state file. Password must contain at least 8 chars and
contain at least one uppercase letter, one lowercase letter, and one number.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">master_<wbr>username<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Username for the master DB user.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">node_<wbr>type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The node type to be provisioned for the cluster.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">number_<wbr>of_<wbr>nodes<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The number of compute nodes in the cluster. This parameter is required when the ClusterType parameter is specified as multi-node. Default is 1.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">owner_<wbr>account<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The AWS customer account used to create or copy the snapshot. Required if you are restoring a snapshot you do not own, optional if you own the snapshot.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">port<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The port number on which the cluster accepts incoming connections.
The cluster is accessible only via the JDBC and ODBC connection strings. Part of the connection string requires the port on which the cluster will listen for incoming connections. Default port is 5439.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">preferred_<wbr>maintenance_<wbr>window<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The weekly time range (in UTC) during which automated cluster maintenance can occur.
Format: ddd:hh24:mi-ddd:hh24:mi
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">publicly_<wbr>accessible<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}If true, the cluster can be accessed from a public network. Default is `true`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">skip_<wbr>final_<wbr>snapshot<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Determines whether a final snapshot of the cluster is created before Amazon Redshift deletes the cluster. If true , a final cluster snapshot is not created. If false , a final cluster snapshot is created before the cluster is deleted. Default is false.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">snapshot_<wbr>cluster_<wbr>identifier<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the cluster the source snapshot was created from.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">snapshot_<wbr>copy<span class="property-indicator"></span>
        <span class="property-type"><a href="#clustersnapshotcopy">Dict[Cluster<wbr>Snapshot<wbr>Copy]</a></span>
    </dt>
    <dd>{{% md %}}Configuration of automatic copy of snapshots from one region to another. Documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">snapshot_<wbr>identifier<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the snapshot from which to create the new cluster.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">vpc_<wbr>security_<wbr>group_<wbr>ids<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}A list of Virtual Private Cloud (VPC) security groups to be associated with the cluster.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}




## Cluster Output Properties

The following output properties are available:




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Allow<wbr>Version<wbr>Upgrade<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}If true , major version upgrades can be applied during the maintenance window to the Amazon Redshift engine that is running on the cluster. Default is true
{{% /md %}}</dd>

    <dt class="property-"
            title="">Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of cluster
{{% /md %}}</dd>

    <dt class="property-"
            title="">Automated<wbr>Snapshot<wbr>Retention<wbr>Period<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The number of days that automated snapshots are retained. If the value is 0, automated snapshots are disabled. Even if automated snapshots are disabled, you can still create manual snapshots when you want with create-cluster-snapshot. Default is 1.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Availability<wbr>Zone<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The EC2 Availability Zone (AZ) in which you want Amazon Redshift to provision the cluster. For example, if you have several EC2 instances running in a specific Availability Zone, then you might want the cluster to be provisioned in the same zone in order to decrease network latency.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Cluster<wbr>Identifier<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Cluster Identifier. Must be a lower case
string.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Cluster<wbr>Parameter<wbr>Group<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the parameter group to be associated with this cluster.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Cluster<wbr>Public<wbr>Key<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The public key for the cluster
{{% /md %}}</dd>

    <dt class="property-"
            title="">Cluster<wbr>Revision<wbr>Number<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The specific revision number of the database in the cluster
{{% /md %}}</dd>

    <dt class="property-"
            title="">Cluster<wbr>Security<wbr>Groups<span class="property-indicator"></span>
        <span class="property-type">List<string></span>
    </dt>
    <dd>{{% md %}}A list of security groups to be associated with this cluster.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Cluster<wbr>Subnet<wbr>Group<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of a cluster subnet group to be associated with this cluster. If this parameter is not provided the resulting cluster will be deployed outside virtual private cloud (VPC).
{{% /md %}}</dd>

    <dt class="property-"
            title="">Cluster<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The cluster type to use. Either `single-node` or `multi-node`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Cluster<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The version of the Amazon Redshift engine software that you want to deploy on the cluster.
The version selected runs on all the nodes in the cluster.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Database<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the first database to be created when the cluster is created.
If you do not provide a name, Amazon Redshift will create a default database called `dev`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Dns<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The DNS name of the cluster
{{% /md %}}</dd>

    <dt class="property-"
            title="">Elastic<wbr>Ip<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The Elastic IP (EIP) address for the cluster.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Encrypted<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}If true , the data in the cluster is encrypted at rest.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Endpoint<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The connection endpoint
{{% /md %}}</dd>

    <dt class="property-"
            title="">Enhanced<wbr>Vpc<wbr>Routing<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}If true , enhanced VPC routing is enabled.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Final<wbr>Snapshot<wbr>Identifier<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The identifier of the final snapshot that is to be created immediately before deleting the cluster. If this parameter is provided, `skip_final_snapshot` must be false.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Iam<wbr>Roles<span class="property-indicator"></span>
        <span class="property-type">List<string></span>
    </dt>
    <dd>{{% md %}}A list of IAM Role ARNs to associate with the cluster. A Maximum of 10 can be associated to the cluster at any time.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Kms<wbr>Key<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN for the KMS encryption key. When specifying `kms_key_id`, `encrypted` needs to be set to true.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Logging<span class="property-indicator"></span>
        <span class="property-type"><a href="#clusterlogging">Cluster<wbr>Logging?</a></span>
    </dt>
    <dd>{{% md %}}Logging, documented below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Master<wbr>Password<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Password for the master DB user.
Note that this may show up in logs, and it will be stored in the state file. Password must contain at least 8 chars and
contain at least one uppercase letter, one lowercase letter, and one number.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Master<wbr>Username<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Username for the master DB user.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Node<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The node type to be provisioned for the cluster.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Number<wbr>Of<wbr>Nodes<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The number of compute nodes in the cluster. This parameter is required when the ClusterType parameter is specified as multi-node. Default is 1.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Owner<wbr>Account<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The AWS customer account used to create or copy the snapshot. Required if you are restoring a snapshot you do not own, optional if you own the snapshot.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Port<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The port number on which the cluster accepts incoming connections.
The cluster is accessible only via the JDBC and ODBC connection strings. Part of the connection string requires the port on which the cluster will listen for incoming connections. Default port is 5439.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Preferred<wbr>Maintenance<wbr>Window<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The weekly time range (in UTC) during which automated cluster maintenance can occur.
Format: ddd:hh24:mi-ddd:hh24:mi
{{% /md %}}</dd>

    <dt class="property-"
            title="">Publicly<wbr>Accessible<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}If true, the cluster can be accessed from a public network. Default is `true`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Skip<wbr>Final<wbr>Snapshot<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Determines whether a final snapshot of the cluster is created before Amazon Redshift deletes the cluster. If true , a final cluster snapshot is not created. If false , a final cluster snapshot is created before the cluster is deleted. Default is false.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Snapshot<wbr>Cluster<wbr>Identifier<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the cluster the source snapshot was created from.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Snapshot<wbr>Copy<span class="property-indicator"></span>
        <span class="property-type"><a href="#clustersnapshotcopy">Cluster<wbr>Snapshot<wbr>Copy?</a></span>
    </dt>
    <dd>{{% md %}}Configuration of automatic copy of snapshots from one region to another. Documented below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Snapshot<wbr>Identifier<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the snapshot from which to create the new cluster.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Vpc<wbr>Security<wbr>Group<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">List<string></span>
    </dt>
    <dd>{{% md %}}A list of Virtual Private Cloud (VPC) security groups to be associated with the cluster.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Allow<wbr>Version<wbr>Upgrade<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}If true , major version upgrades can be applied during the maintenance window to the Amazon Redshift engine that is running on the cluster. Default is true
{{% /md %}}</dd>

    <dt class="property-"
            title="">Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of cluster
{{% /md %}}</dd>

    <dt class="property-"
            title="">Automated<wbr>Snapshot<wbr>Retention<wbr>Period<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The number of days that automated snapshots are retained. If the value is 0, automated snapshots are disabled. Even if automated snapshots are disabled, you can still create manual snapshots when you want with create-cluster-snapshot. Default is 1.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Availability<wbr>Zone<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The EC2 Availability Zone (AZ) in which you want Amazon Redshift to provision the cluster. For example, if you have several EC2 instances running in a specific Availability Zone, then you might want the cluster to be provisioned in the same zone in order to decrease network latency.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Cluster<wbr>Identifier<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Cluster Identifier. Must be a lower case
string.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Cluster<wbr>Parameter<wbr>Group<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the parameter group to be associated with this cluster.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Cluster<wbr>Public<wbr>Key<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The public key for the cluster
{{% /md %}}</dd>

    <dt class="property-"
            title="">Cluster<wbr>Revision<wbr>Number<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The specific revision number of the database in the cluster
{{% /md %}}</dd>

    <dt class="property-"
            title="">Cluster<wbr>Security<wbr>Groups<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}A list of security groups to be associated with this cluster.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Cluster<wbr>Subnet<wbr>Group<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of a cluster subnet group to be associated with this cluster. If this parameter is not provided the resulting cluster will be deployed outside virtual private cloud (VPC).
{{% /md %}}</dd>

    <dt class="property-"
            title="">Cluster<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The cluster type to use. Either `single-node` or `multi-node`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Cluster<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The version of the Amazon Redshift engine software that you want to deploy on the cluster.
The version selected runs on all the nodes in the cluster.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Database<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the first database to be created when the cluster is created.
If you do not provide a name, Amazon Redshift will create a default database called `dev`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Dns<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The DNS name of the cluster
{{% /md %}}</dd>

    <dt class="property-"
            title="">Elastic<wbr>Ip<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The Elastic IP (EIP) address for the cluster.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Encrypted<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}If true , the data in the cluster is encrypted at rest.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Endpoint<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The connection endpoint
{{% /md %}}</dd>

    <dt class="property-"
            title="">Enhanced<wbr>Vpc<wbr>Routing<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}If true , enhanced VPC routing is enabled.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Final<wbr>Snapshot<wbr>Identifier<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The identifier of the final snapshot that is to be created immediately before deleting the cluster. If this parameter is provided, `skip_final_snapshot` must be false.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Iam<wbr>Roles<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}A list of IAM Role ARNs to associate with the cluster. A Maximum of 10 can be associated to the cluster at any time.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Kms<wbr>Key<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN for the KMS encryption key. When specifying `kms_key_id`, `encrypted` needs to be set to true.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Logging<span class="property-indicator"></span>
        <span class="property-type"><a href="#clusterlogging">*Cluster<wbr>Logging</a></span>
    </dt>
    <dd>{{% md %}}Logging, documented below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Master<wbr>Password<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Password for the master DB user.
Note that this may show up in logs, and it will be stored in the state file. Password must contain at least 8 chars and
contain at least one uppercase letter, one lowercase letter, and one number.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Master<wbr>Username<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Username for the master DB user.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Node<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The node type to be provisioned for the cluster.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Number<wbr>Of<wbr>Nodes<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The number of compute nodes in the cluster. This parameter is required when the ClusterType parameter is specified as multi-node. Default is 1.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Owner<wbr>Account<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The AWS customer account used to create or copy the snapshot. Required if you are restoring a snapshot you do not own, optional if you own the snapshot.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Port<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The port number on which the cluster accepts incoming connections.
The cluster is accessible only via the JDBC and ODBC connection strings. Part of the connection string requires the port on which the cluster will listen for incoming connections. Default port is 5439.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Preferred<wbr>Maintenance<wbr>Window<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The weekly time range (in UTC) during which automated cluster maintenance can occur.
Format: ddd:hh24:mi-ddd:hh24:mi
{{% /md %}}</dd>

    <dt class="property-"
            title="">Publicly<wbr>Accessible<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}If true, the cluster can be accessed from a public network. Default is `true`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Skip<wbr>Final<wbr>Snapshot<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Determines whether a final snapshot of the cluster is created before Amazon Redshift deletes the cluster. If true , a final cluster snapshot is not created. If false , a final cluster snapshot is created before the cluster is deleted. Default is false.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Snapshot<wbr>Cluster<wbr>Identifier<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name of the cluster the source snapshot was created from.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Snapshot<wbr>Copy<span class="property-indicator"></span>
        <span class="property-type"><a href="#clustersnapshotcopy">*Cluster<wbr>Snapshot<wbr>Copy</a></span>
    </dt>
    <dd>{{% md %}}Configuration of automatic copy of snapshots from one region to another. Documented below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Snapshot<wbr>Identifier<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name of the snapshot from which to create the new cluster.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Vpc<wbr>Security<wbr>Group<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}A list of Virtual Private Cloud (VPC) security groups to be associated with the cluster.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">allow<wbr>Version<wbr>Upgrade<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}If true , major version upgrades can be applied during the maintenance window to the Amazon Redshift engine that is running on the cluster. Default is true
{{% /md %}}</dd>

    <dt class="property-"
            title="">arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of cluster
{{% /md %}}</dd>

    <dt class="property-"
            title="">automated<wbr>Snapshot<wbr>Retention<wbr>Period<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The number of days that automated snapshots are retained. If the value is 0, automated snapshots are disabled. Even if automated snapshots are disabled, you can still create manual snapshots when you want with create-cluster-snapshot. Default is 1.
{{% /md %}}</dd>

    <dt class="property-"
            title="">availability<wbr>Zone<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The EC2 Availability Zone (AZ) in which you want Amazon Redshift to provision the cluster. For example, if you have several EC2 instances running in a specific Availability Zone, then you might want the cluster to be provisioned in the same zone in order to decrease network latency.
{{% /md %}}</dd>

    <dt class="property-"
            title="">cluster<wbr>Identifier<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Cluster Identifier. Must be a lower case
string.
{{% /md %}}</dd>

    <dt class="property-"
            title="">cluster<wbr>Parameter<wbr>Group<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the parameter group to be associated with this cluster.
{{% /md %}}</dd>

    <dt class="property-"
            title="">cluster<wbr>Public<wbr>Key<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The public key for the cluster
{{% /md %}}</dd>

    <dt class="property-"
            title="">cluster<wbr>Revision<wbr>Number<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The specific revision number of the database in the cluster
{{% /md %}}</dd>

    <dt class="property-"
            title="">cluster<wbr>Security<wbr>Groups<span class="property-indicator"></span>
        <span class="property-type">string[]</span>
    </dt>
    <dd>{{% md %}}A list of security groups to be associated with this cluster.
{{% /md %}}</dd>

    <dt class="property-"
            title="">cluster<wbr>Subnet<wbr>Group<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of a cluster subnet group to be associated with this cluster. If this parameter is not provided the resulting cluster will be deployed outside virtual private cloud (VPC).
{{% /md %}}</dd>

    <dt class="property-"
            title="">cluster<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The cluster type to use. Either `single-node` or `multi-node`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">cluster<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The version of the Amazon Redshift engine software that you want to deploy on the cluster.
The version selected runs on all the nodes in the cluster.
{{% /md %}}</dd>

    <dt class="property-"
            title="">database<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the first database to be created when the cluster is created.
If you do not provide a name, Amazon Redshift will create a default database called `dev`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">dns<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The DNS name of the cluster
{{% /md %}}</dd>

    <dt class="property-"
            title="">elastic<wbr>Ip<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The Elastic IP (EIP) address for the cluster.
{{% /md %}}</dd>

    <dt class="property-"
            title="">encrypted<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}If true , the data in the cluster is encrypted at rest.
{{% /md %}}</dd>

    <dt class="property-"
            title="">endpoint<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The connection endpoint
{{% /md %}}</dd>

    <dt class="property-"
            title="">enhanced<wbr>Vpc<wbr>Routing<span class="property-indicator"></span>
        <span class="property-type">boolean</span>
    </dt>
    <dd>{{% md %}}If true , enhanced VPC routing is enabled.
{{% /md %}}</dd>

    <dt class="property-"
            title="">final<wbr>Snapshot<wbr>Identifier<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The identifier of the final snapshot that is to be created immediately before deleting the cluster. If this parameter is provided, `skip_final_snapshot` must be false.
{{% /md %}}</dd>

    <dt class="property-"
            title="">iam<wbr>Roles<span class="property-indicator"></span>
        <span class="property-type">string[]</span>
    </dt>
    <dd>{{% md %}}A list of IAM Role ARNs to associate with the cluster. A Maximum of 10 can be associated to the cluster at any time.
{{% /md %}}</dd>

    <dt class="property-"
            title="">kms<wbr>Key<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN for the KMS encryption key. When specifying `kms_key_id`, `encrypted` needs to be set to true.
{{% /md %}}</dd>

    <dt class="property-"
            title="">logging<span class="property-indicator"></span>
        <span class="property-type"><a href="#clusterlogging">Cluster<wbr>Logging?</a></span>
    </dt>
    <dd>{{% md %}}Logging, documented below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">master<wbr>Password<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Password for the master DB user.
Note that this may show up in logs, and it will be stored in the state file. Password must contain at least 8 chars and
contain at least one uppercase letter, one lowercase letter, and one number.
{{% /md %}}</dd>

    <dt class="property-"
            title="">master<wbr>Username<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Username for the master DB user.
{{% /md %}}</dd>

    <dt class="property-"
            title="">node<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The node type to be provisioned for the cluster.
{{% /md %}}</dd>

    <dt class="property-"
            title="">number<wbr>Of<wbr>Nodes<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The number of compute nodes in the cluster. This parameter is required when the ClusterType parameter is specified as multi-node. Default is 1.
{{% /md %}}</dd>

    <dt class="property-"
            title="">owner<wbr>Account<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The AWS customer account used to create or copy the snapshot. Required if you are restoring a snapshot you do not own, optional if you own the snapshot.
{{% /md %}}</dd>

    <dt class="property-"
            title="">port<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The port number on which the cluster accepts incoming connections.
The cluster is accessible only via the JDBC and ODBC connection strings. Part of the connection string requires the port on which the cluster will listen for incoming connections. Default port is 5439.
{{% /md %}}</dd>

    <dt class="property-"
            title="">preferred<wbr>Maintenance<wbr>Window<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The weekly time range (in UTC) during which automated cluster maintenance can occur.
Format: ddd:hh24:mi-ddd:hh24:mi
{{% /md %}}</dd>

    <dt class="property-"
            title="">publicly<wbr>Accessible<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}If true, the cluster can be accessed from a public network. Default is `true`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">skip<wbr>Final<wbr>Snapshot<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Determines whether a final snapshot of the cluster is created before Amazon Redshift deletes the cluster. If true , a final cluster snapshot is not created. If false , a final cluster snapshot is created before the cluster is deleted. Default is false.
{{% /md %}}</dd>

    <dt class="property-"
            title="">snapshot<wbr>Cluster<wbr>Identifier<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the cluster the source snapshot was created from.
{{% /md %}}</dd>

    <dt class="property-"
            title="">snapshot<wbr>Copy<span class="property-indicator"></span>
        <span class="property-type"><a href="#clustersnapshotcopy">Cluster<wbr>Snapshot<wbr>Copy?</a></span>
    </dt>
    <dd>{{% md %}}Configuration of automatic copy of snapshots from one region to another. Documented below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">snapshot<wbr>Identifier<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the snapshot from which to create the new cluster.
{{% /md %}}</dd>

    <dt class="property-"
            title="">tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-"
            title="">vpc<wbr>Security<wbr>Group<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">string[]</span>
    </dt>
    <dd>{{% md %}}A list of Virtual Private Cloud (VPC) security groups to be associated with the cluster.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">allow_<wbr>version_<wbr>upgrade<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}If true , major version upgrades can be applied during the maintenance window to the Amazon Redshift engine that is running on the cluster. Default is true
{{% /md %}}</dd>

    <dt class="property-"
            title="">arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of cluster
{{% /md %}}</dd>

    <dt class="property-"
            title="">automated_<wbr>snapshot_<wbr>retention_<wbr>period<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The number of days that automated snapshots are retained. If the value is 0, automated snapshots are disabled. Even if automated snapshots are disabled, you can still create manual snapshots when you want with create-cluster-snapshot. Default is 1.
{{% /md %}}</dd>

    <dt class="property-"
            title="">availability_<wbr>zone<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The EC2 Availability Zone (AZ) in which you want Amazon Redshift to provision the cluster. For example, if you have several EC2 instances running in a specific Availability Zone, then you might want the cluster to be provisioned in the same zone in order to decrease network latency.
{{% /md %}}</dd>

    <dt class="property-"
            title="">cluster_<wbr>identifier<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The Cluster Identifier. Must be a lower case
string.
{{% /md %}}</dd>

    <dt class="property-"
            title="">cluster_<wbr>parameter_<wbr>group_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the parameter group to be associated with this cluster.
{{% /md %}}</dd>

    <dt class="property-"
            title="">cluster_<wbr>public_<wbr>key<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The public key for the cluster
{{% /md %}}</dd>

    <dt class="property-"
            title="">cluster_<wbr>revision_<wbr>number<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The specific revision number of the database in the cluster
{{% /md %}}</dd>

    <dt class="property-"
            title="">cluster_<wbr>security_<wbr>groups<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}A list of security groups to be associated with this cluster.
{{% /md %}}</dd>

    <dt class="property-"
            title="">cluster_<wbr>subnet_<wbr>group_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of a cluster subnet group to be associated with this cluster. If this parameter is not provided the resulting cluster will be deployed outside virtual private cloud (VPC).
{{% /md %}}</dd>

    <dt class="property-"
            title="">cluster_<wbr>type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The cluster type to use. Either `single-node` or `multi-node`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">cluster_<wbr>version<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The version of the Amazon Redshift engine software that you want to deploy on the cluster.
The version selected runs on all the nodes in the cluster.
{{% /md %}}</dd>

    <dt class="property-"
            title="">database_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the first database to be created when the cluster is created.
If you do not provide a name, Amazon Redshift will create a default database called `dev`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">dns_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The DNS name of the cluster
{{% /md %}}</dd>

    <dt class="property-"
            title="">elastic_<wbr>ip<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The Elastic IP (EIP) address for the cluster.
{{% /md %}}</dd>

    <dt class="property-"
            title="">encrypted<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}If true , the data in the cluster is encrypted at rest.
{{% /md %}}</dd>

    <dt class="property-"
            title="">endpoint<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The connection endpoint
{{% /md %}}</dd>

    <dt class="property-"
            title="">enhanced_<wbr>vpc_<wbr>routing<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}If true , enhanced VPC routing is enabled.
{{% /md %}}</dd>

    <dt class="property-"
            title="">final_<wbr>snapshot_<wbr>identifier<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The identifier of the final snapshot that is to be created immediately before deleting the cluster. If this parameter is provided, `skip_final_snapshot` must be false.
{{% /md %}}</dd>

    <dt class="property-"
            title="">iam_<wbr>roles<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}A list of IAM Role ARNs to associate with the cluster. A Maximum of 10 can be associated to the cluster at any time.
{{% /md %}}</dd>

    <dt class="property-"
            title="">kms_<wbr>key_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ARN for the KMS encryption key. When specifying `kms_key_id`, `encrypted` needs to be set to true.
{{% /md %}}</dd>

    <dt class="property-"
            title="">logging<span class="property-indicator"></span>
        <span class="property-type"><a href="#clusterlogging">Dict[Cluster<wbr>Logging]</a></span>
    </dt>
    <dd>{{% md %}}Logging, documented below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">master_<wbr>password<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Password for the master DB user.
Note that this may show up in logs, and it will be stored in the state file. Password must contain at least 8 chars and
contain at least one uppercase letter, one lowercase letter, and one number.
{{% /md %}}</dd>

    <dt class="property-"
            title="">master_<wbr>username<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Username for the master DB user.
{{% /md %}}</dd>

    <dt class="property-"
            title="">node_<wbr>type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The node type to be provisioned for the cluster.
{{% /md %}}</dd>

    <dt class="property-"
            title="">number_<wbr>of_<wbr>nodes<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The number of compute nodes in the cluster. This parameter is required when the ClusterType parameter is specified as multi-node. Default is 1.
{{% /md %}}</dd>

    <dt class="property-"
            title="">owner_<wbr>account<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The AWS customer account used to create or copy the snapshot. Required if you are restoring a snapshot you do not own, optional if you own the snapshot.
{{% /md %}}</dd>

    <dt class="property-"
            title="">port<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The port number on which the cluster accepts incoming connections.
The cluster is accessible only via the JDBC and ODBC connection strings. Part of the connection string requires the port on which the cluster will listen for incoming connections. Default port is 5439.
{{% /md %}}</dd>

    <dt class="property-"
            title="">preferred_<wbr>maintenance_<wbr>window<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The weekly time range (in UTC) during which automated cluster maintenance can occur.
Format: ddd:hh24:mi-ddd:hh24:mi
{{% /md %}}</dd>

    <dt class="property-"
            title="">publicly_<wbr>accessible<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}If true, the cluster can be accessed from a public network. Default is `true`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">skip_<wbr>final_<wbr>snapshot<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Determines whether a final snapshot of the cluster is created before Amazon Redshift deletes the cluster. If true , a final cluster snapshot is not created. If false , a final cluster snapshot is created before the cluster is deleted. Default is false.
{{% /md %}}</dd>

    <dt class="property-"
            title="">snapshot_<wbr>cluster_<wbr>identifier<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the cluster the source snapshot was created from.
{{% /md %}}</dd>

    <dt class="property-"
            title="">snapshot_<wbr>copy<span class="property-indicator"></span>
        <span class="property-type"><a href="#clustersnapshotcopy">Dict[Cluster<wbr>Snapshot<wbr>Copy]</a></span>
    </dt>
    <dd>{{% md %}}Configuration of automatic copy of snapshots from one region to another. Documented below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">snapshot_<wbr>identifier<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the snapshot from which to create the new cluster.
{{% /md %}}</dd>

    <dt class="property-"
            title="">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-"
            title="">vpc_<wbr>security_<wbr>group_<wbr>ids<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}A list of Virtual Private Cloud (VPC) security groups to be associated with the cluster.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





## Look up an Existing Cluster Resource

{{< chooser language "javascript,typescript,python,go,csharp  " / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">pulumi.Input&lt;pulumi.ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/redshift/#ClusterState">ClusterState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/redshift/#Cluster">Cluster</a></span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>allow_version_upgrade=None<span class="p">, </span>arn=None<span class="p">, </span>automated_snapshot_retention_period=None<span class="p">, </span>availability_zone=None<span class="p">, </span>cluster_identifier=None<span class="p">, </span>cluster_parameter_group_name=None<span class="p">, </span>cluster_public_key=None<span class="p">, </span>cluster_revision_number=None<span class="p">, </span>cluster_security_groups=None<span class="p">, </span>cluster_subnet_group_name=None<span class="p">, </span>cluster_type=None<span class="p">, </span>cluster_version=None<span class="p">, </span>database_name=None<span class="p">, </span>dns_name=None<span class="p">, </span>elastic_ip=None<span class="p">, </span>encrypted=None<span class="p">, </span>endpoint=None<span class="p">, </span>enhanced_vpc_routing=None<span class="p">, </span>final_snapshot_identifier=None<span class="p">, </span>iam_roles=None<span class="p">, </span>kms_key_id=None<span class="p">, </span>logging=None<span class="p">, </span>master_password=None<span class="p">, </span>master_username=None<span class="p">, </span>node_type=None<span class="p">, </span>number_of_nodes=None<span class="p">, </span>owner_account=None<span class="p">, </span>port=None<span class="p">, </span>preferred_maintenance_window=None<span class="p">, </span>publicly_accessible=None<span class="p">, </span>skip_final_snapshot=None<span class="p">, </span>snapshot_cluster_identifier=None<span class="p">, </span>snapshot_copy=None<span class="p">, </span>snapshot_identifier=None<span class="p">, </span>tags=None<span class="p">, </span>vpc_security_group_ids=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetCluster<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">pulumi.IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/redshift?tab=doc#ClusterState">ClusterState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/redshift?tab=doc#Cluster">Cluster</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Redshift.Cluster.html">Cluster</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Pulumi.Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Redshift.ClusterState.html">ClusterState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
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
            title="Optional">Allow<wbr>Version<wbr>Upgrade<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}If true , major version upgrades can be applied during the maintenance window to the Amazon Redshift engine that is running on the cluster. Default is true
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of cluster
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Automated<wbr>Snapshot<wbr>Retention<wbr>Period<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The number of days that automated snapshots are retained. If the value is 0, automated snapshots are disabled. Even if automated snapshots are disabled, you can still create manual snapshots when you want with create-cluster-snapshot. Default is 1.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Availability<wbr>Zone<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The EC2 Availability Zone (AZ) in which you want Amazon Redshift to provision the cluster. For example, if you have several EC2 instances running in a specific Availability Zone, then you might want the cluster to be provisioned in the same zone in order to decrease network latency.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Cluster<wbr>Identifier<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The Cluster Identifier. Must be a lower case
string.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Cluster<wbr>Parameter<wbr>Group<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the parameter group to be associated with this cluster.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Cluster<wbr>Public<wbr>Key<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The public key for the cluster
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Cluster<wbr>Revision<wbr>Number<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The specific revision number of the database in the cluster
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Cluster<wbr>Security<wbr>Groups<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}A list of security groups to be associated with this cluster.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Cluster<wbr>Subnet<wbr>Group<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of a cluster subnet group to be associated with this cluster. If this parameter is not provided the resulting cluster will be deployed outside virtual private cloud (VPC).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Cluster<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The cluster type to use. Either `single-node` or `multi-node`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Cluster<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The version of the Amazon Redshift engine software that you want to deploy on the cluster.
The version selected runs on all the nodes in the cluster.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Database<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the first database to be created when the cluster is created.
If you do not provide a name, Amazon Redshift will create a default database called `dev`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Dns<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The DNS name of the cluster
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Elastic<wbr>Ip<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The Elastic IP (EIP) address for the cluster.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Encrypted<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}If true , the data in the cluster is encrypted at rest.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Endpoint<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The connection endpoint
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Enhanced<wbr>Vpc<wbr>Routing<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}If true , enhanced VPC routing is enabled.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Final<wbr>Snapshot<wbr>Identifier<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The identifier of the final snapshot that is to be created immediately before deleting the cluster. If this parameter is provided, `skip_final_snapshot` must be false.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Iam<wbr>Roles<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}A list of IAM Role ARNs to associate with the cluster. A Maximum of 10 can be associated to the cluster at any time.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Kms<wbr>Key<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ARN for the KMS encryption key. When specifying `kms_key_id`, `encrypted` needs to be set to true.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Logging<span class="property-indicator"></span>
        <span class="property-type"><a href="#clusterlogging">Cluster<wbr>Logging<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}Logging, documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Master<wbr>Password<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Password for the master DB user.
Note that this may show up in logs, and it will be stored in the state file. Password must contain at least 8 chars and
contain at least one uppercase letter, one lowercase letter, and one number.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Master<wbr>Username<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Username for the master DB user.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Node<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The node type to be provisioned for the cluster.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Number<wbr>Of<wbr>Nodes<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The number of compute nodes in the cluster. This parameter is required when the ClusterType parameter is specified as multi-node. Default is 1.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Owner<wbr>Account<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The AWS customer account used to create or copy the snapshot. Required if you are restoring a snapshot you do not own, optional if you own the snapshot.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Port<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The port number on which the cluster accepts incoming connections.
The cluster is accessible only via the JDBC and ODBC connection strings. Part of the connection string requires the port on which the cluster will listen for incoming connections. Default port is 5439.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Preferred<wbr>Maintenance<wbr>Window<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The weekly time range (in UTC) during which automated cluster maintenance can occur.
Format: ddd:hh24:mi-ddd:hh24:mi
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Publicly<wbr>Accessible<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}If true, the cluster can be accessed from a public network. Default is `true`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Skip<wbr>Final<wbr>Snapshot<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Determines whether a final snapshot of the cluster is created before Amazon Redshift deletes the cluster. If true , a final cluster snapshot is not created. If false , a final cluster snapshot is created before the cluster is deleted. Default is false.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Snapshot<wbr>Cluster<wbr>Identifier<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the cluster the source snapshot was created from.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Snapshot<wbr>Copy<span class="property-indicator"></span>
        <span class="property-type"><a href="#clustersnapshotcopy">Cluster<wbr>Snapshot<wbr>Copy<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}Configuration of automatic copy of snapshots from one region to another. Documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Snapshot<wbr>Identifier<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the snapshot from which to create the new cluster.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Vpc<wbr>Security<wbr>Group<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}A list of Virtual Private Cloud (VPC) security groups to be associated with the cluster.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Allow<wbr>Version<wbr>Upgrade<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}If true , major version upgrades can be applied during the maintenance window to the Amazon Redshift engine that is running on the cluster. Default is true
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of cluster
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Automated<wbr>Snapshot<wbr>Retention<wbr>Period<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The number of days that automated snapshots are retained. If the value is 0, automated snapshots are disabled. Even if automated snapshots are disabled, you can still create manual snapshots when you want with create-cluster-snapshot. Default is 1.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Availability<wbr>Zone<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The EC2 Availability Zone (AZ) in which you want Amazon Redshift to provision the cluster. For example, if you have several EC2 instances running in a specific Availability Zone, then you might want the cluster to be provisioned in the same zone in order to decrease network latency.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Cluster<wbr>Identifier<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The Cluster Identifier. Must be a lower case
string.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Cluster<wbr>Parameter<wbr>Group<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name of the parameter group to be associated with this cluster.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Cluster<wbr>Public<wbr>Key<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The public key for the cluster
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Cluster<wbr>Revision<wbr>Number<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The specific revision number of the database in the cluster
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Cluster<wbr>Security<wbr>Groups<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}A list of security groups to be associated with this cluster.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Cluster<wbr>Subnet<wbr>Group<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name of a cluster subnet group to be associated with this cluster. If this parameter is not provided the resulting cluster will be deployed outside virtual private cloud (VPC).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Cluster<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The cluster type to use. Either `single-node` or `multi-node`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Cluster<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The version of the Amazon Redshift engine software that you want to deploy on the cluster.
The version selected runs on all the nodes in the cluster.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Database<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name of the first database to be created when the cluster is created.
If you do not provide a name, Amazon Redshift will create a default database called `dev`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Dns<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The DNS name of the cluster
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Elastic<wbr>Ip<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The Elastic IP (EIP) address for the cluster.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Encrypted<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}If true , the data in the cluster is encrypted at rest.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Endpoint<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The connection endpoint
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Enhanced<wbr>Vpc<wbr>Routing<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}If true , enhanced VPC routing is enabled.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Final<wbr>Snapshot<wbr>Identifier<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The identifier of the final snapshot that is to be created immediately before deleting the cluster. If this parameter is provided, `skip_final_snapshot` must be false.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Iam<wbr>Roles<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}A list of IAM Role ARNs to associate with the cluster. A Maximum of 10 can be associated to the cluster at any time.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Kms<wbr>Key<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The ARN for the KMS encryption key. When specifying `kms_key_id`, `encrypted` needs to be set to true.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Logging<span class="property-indicator"></span>
        <span class="property-type"><a href="#clusterlogging">*Cluster<wbr>Logging</a></span>
    </dt>
    <dd>{{% md %}}Logging, documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Master<wbr>Password<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Password for the master DB user.
Note that this may show up in logs, and it will be stored in the state file. Password must contain at least 8 chars and
contain at least one uppercase letter, one lowercase letter, and one number.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Master<wbr>Username<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Username for the master DB user.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Node<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The node type to be provisioned for the cluster.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Number<wbr>Of<wbr>Nodes<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The number of compute nodes in the cluster. This parameter is required when the ClusterType parameter is specified as multi-node. Default is 1.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Owner<wbr>Account<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The AWS customer account used to create or copy the snapshot. Required if you are restoring a snapshot you do not own, optional if you own the snapshot.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Port<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The port number on which the cluster accepts incoming connections.
The cluster is accessible only via the JDBC and ODBC connection strings. Part of the connection string requires the port on which the cluster will listen for incoming connections. Default port is 5439.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Preferred<wbr>Maintenance<wbr>Window<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The weekly time range (in UTC) during which automated cluster maintenance can occur.
Format: ddd:hh24:mi-ddd:hh24:mi
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Publicly<wbr>Accessible<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}If true, the cluster can be accessed from a public network. Default is `true`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Skip<wbr>Final<wbr>Snapshot<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Determines whether a final snapshot of the cluster is created before Amazon Redshift deletes the cluster. If true , a final cluster snapshot is not created. If false , a final cluster snapshot is created before the cluster is deleted. Default is false.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Snapshot<wbr>Cluster<wbr>Identifier<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name of the cluster the source snapshot was created from.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Snapshot<wbr>Copy<span class="property-indicator"></span>
        <span class="property-type"><a href="#clustersnapshotcopy">*Cluster<wbr>Snapshot<wbr>Copy</a></span>
    </dt>
    <dd>{{% md %}}Configuration of automatic copy of snapshots from one region to another. Documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Snapshot<wbr>Identifier<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name of the snapshot from which to create the new cluster.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Vpc<wbr>Security<wbr>Group<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}A list of Virtual Private Cloud (VPC) security groups to be associated with the cluster.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">allow<wbr>Version<wbr>Upgrade<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}If true , major version upgrades can be applied during the maintenance window to the Amazon Redshift engine that is running on the cluster. Default is true
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of cluster
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">automated<wbr>Snapshot<wbr>Retention<wbr>Period<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The number of days that automated snapshots are retained. If the value is 0, automated snapshots are disabled. Even if automated snapshots are disabled, you can still create manual snapshots when you want with create-cluster-snapshot. Default is 1.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">availability<wbr>Zone<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The EC2 Availability Zone (AZ) in which you want Amazon Redshift to provision the cluster. For example, if you have several EC2 instances running in a specific Availability Zone, then you might want the cluster to be provisioned in the same zone in order to decrease network latency.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">cluster<wbr>Identifier<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The Cluster Identifier. Must be a lower case
string.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">cluster<wbr>Parameter<wbr>Group<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the parameter group to be associated with this cluster.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">cluster<wbr>Public<wbr>Key<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The public key for the cluster
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">cluster<wbr>Revision<wbr>Number<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The specific revision number of the database in the cluster
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">cluster<wbr>Security<wbr>Groups<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}A list of security groups to be associated with this cluster.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">cluster<wbr>Subnet<wbr>Group<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of a cluster subnet group to be associated with this cluster. If this parameter is not provided the resulting cluster will be deployed outside virtual private cloud (VPC).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">cluster<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The cluster type to use. Either `single-node` or `multi-node`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">cluster<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The version of the Amazon Redshift engine software that you want to deploy on the cluster.
The version selected runs on all the nodes in the cluster.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">database<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the first database to be created when the cluster is created.
If you do not provide a name, Amazon Redshift will create a default database called `dev`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">dns<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The DNS name of the cluster
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">elastic<wbr>Ip<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The Elastic IP (EIP) address for the cluster.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">encrypted<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}If true , the data in the cluster is encrypted at rest.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">endpoint<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The connection endpoint
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">enhanced<wbr>Vpc<wbr>Routing<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}If true , enhanced VPC routing is enabled.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">final<wbr>Snapshot<wbr>Identifier<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The identifier of the final snapshot that is to be created immediately before deleting the cluster. If this parameter is provided, `skip_final_snapshot` must be false.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">iam<wbr>Roles<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}A list of IAM Role ARNs to associate with the cluster. A Maximum of 10 can be associated to the cluster at any time.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">kms<wbr>Key<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ARN for the KMS encryption key. When specifying `kms_key_id`, `encrypted` needs to be set to true.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">logging<span class="property-indicator"></span>
        <span class="property-type"><a href="#clusterlogging">Cluster<wbr>Logging?</a></span>
    </dt>
    <dd>{{% md %}}Logging, documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">master<wbr>Password<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Password for the master DB user.
Note that this may show up in logs, and it will be stored in the state file. Password must contain at least 8 chars and
contain at least one uppercase letter, one lowercase letter, and one number.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">master<wbr>Username<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Username for the master DB user.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">node<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The node type to be provisioned for the cluster.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">number<wbr>Of<wbr>Nodes<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The number of compute nodes in the cluster. This parameter is required when the ClusterType parameter is specified as multi-node. Default is 1.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">owner<wbr>Account<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The AWS customer account used to create or copy the snapshot. Required if you are restoring a snapshot you do not own, optional if you own the snapshot.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">port<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The port number on which the cluster accepts incoming connections.
The cluster is accessible only via the JDBC and ODBC connection strings. Part of the connection string requires the port on which the cluster will listen for incoming connections. Default port is 5439.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">preferred<wbr>Maintenance<wbr>Window<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The weekly time range (in UTC) during which automated cluster maintenance can occur.
Format: ddd:hh24:mi-ddd:hh24:mi
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">publicly<wbr>Accessible<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}If true, the cluster can be accessed from a public network. Default is `true`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">skip<wbr>Final<wbr>Snapshot<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Determines whether a final snapshot of the cluster is created before Amazon Redshift deletes the cluster. If true , a final cluster snapshot is not created. If false , a final cluster snapshot is created before the cluster is deleted. Default is false.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">snapshot<wbr>Cluster<wbr>Identifier<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the cluster the source snapshot was created from.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">snapshot<wbr>Copy<span class="property-indicator"></span>
        <span class="property-type"><a href="#clustersnapshotcopy">Cluster<wbr>Snapshot<wbr>Copy?</a></span>
    </dt>
    <dd>{{% md %}}Configuration of automatic copy of snapshots from one region to another. Documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">snapshot<wbr>Identifier<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the snapshot from which to create the new cluster.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">vpc<wbr>Security<wbr>Group<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}A list of Virtual Private Cloud (VPC) security groups to be associated with the cluster.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">allow_<wbr>version_<wbr>upgrade<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}If true , major version upgrades can be applied during the maintenance window to the Amazon Redshift engine that is running on the cluster. Default is true
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of cluster
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">automated_<wbr>snapshot_<wbr>retention_<wbr>period<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The number of days that automated snapshots are retained. If the value is 0, automated snapshots are disabled. Even if automated snapshots are disabled, you can still create manual snapshots when you want with create-cluster-snapshot. Default is 1.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">availability_<wbr>zone<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The EC2 Availability Zone (AZ) in which you want Amazon Redshift to provision the cluster. For example, if you have several EC2 instances running in a specific Availability Zone, then you might want the cluster to be provisioned in the same zone in order to decrease network latency.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">cluster_<wbr>identifier<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The Cluster Identifier. Must be a lower case
string.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">cluster_<wbr>parameter_<wbr>group_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the parameter group to be associated with this cluster.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">cluster_<wbr>public_<wbr>key<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The public key for the cluster
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">cluster_<wbr>revision_<wbr>number<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The specific revision number of the database in the cluster
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">cluster_<wbr>security_<wbr>groups<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}A list of security groups to be associated with this cluster.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">cluster_<wbr>subnet_<wbr>group_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of a cluster subnet group to be associated with this cluster. If this parameter is not provided the resulting cluster will be deployed outside virtual private cloud (VPC).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">cluster_<wbr>type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The cluster type to use. Either `single-node` or `multi-node`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">cluster_<wbr>version<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The version of the Amazon Redshift engine software that you want to deploy on the cluster.
The version selected runs on all the nodes in the cluster.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">database_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the first database to be created when the cluster is created.
If you do not provide a name, Amazon Redshift will create a default database called `dev`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">dns_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The DNS name of the cluster
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">elastic_<wbr>ip<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The Elastic IP (EIP) address for the cluster.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">encrypted<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}If true , the data in the cluster is encrypted at rest.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">endpoint<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The connection endpoint
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">enhanced_<wbr>vpc_<wbr>routing<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}If true , enhanced VPC routing is enabled.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">final_<wbr>snapshot_<wbr>identifier<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The identifier of the final snapshot that is to be created immediately before deleting the cluster. If this parameter is provided, `skip_final_snapshot` must be false.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">iam_<wbr>roles<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}A list of IAM Role ARNs to associate with the cluster. A Maximum of 10 can be associated to the cluster at any time.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">kms_<wbr>key_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ARN for the KMS encryption key. When specifying `kms_key_id`, `encrypted` needs to be set to true.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">logging<span class="property-indicator"></span>
        <span class="property-type"><a href="#clusterlogging">Dict[Cluster<wbr>Logging]</a></span>
    </dt>
    <dd>{{% md %}}Logging, documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">master_<wbr>password<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Password for the master DB user.
Note that this may show up in logs, and it will be stored in the state file. Password must contain at least 8 chars and
contain at least one uppercase letter, one lowercase letter, and one number.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">master_<wbr>username<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Username for the master DB user.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">node_<wbr>type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The node type to be provisioned for the cluster.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">number_<wbr>of_<wbr>nodes<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The number of compute nodes in the cluster. This parameter is required when the ClusterType parameter is specified as multi-node. Default is 1.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">owner_<wbr>account<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The AWS customer account used to create or copy the snapshot. Required if you are restoring a snapshot you do not own, optional if you own the snapshot.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">port<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The port number on which the cluster accepts incoming connections.
The cluster is accessible only via the JDBC and ODBC connection strings. Part of the connection string requires the port on which the cluster will listen for incoming connections. Default port is 5439.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">preferred_<wbr>maintenance_<wbr>window<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The weekly time range (in UTC) during which automated cluster maintenance can occur.
Format: ddd:hh24:mi-ddd:hh24:mi
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">publicly_<wbr>accessible<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}If true, the cluster can be accessed from a public network. Default is `true`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">skip_<wbr>final_<wbr>snapshot<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Determines whether a final snapshot of the cluster is created before Amazon Redshift deletes the cluster. If true , a final cluster snapshot is not created. If false , a final cluster snapshot is created before the cluster is deleted. Default is false.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">snapshot_<wbr>cluster_<wbr>identifier<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the cluster the source snapshot was created from.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">snapshot_<wbr>copy<span class="property-indicator"></span>
        <span class="property-type"><a href="#clustersnapshotcopy">Dict[Cluster<wbr>Snapshot<wbr>Copy]</a></span>
    </dt>
    <dd>{{% md %}}Configuration of automatic copy of snapshots from one region to another. Documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">snapshot_<wbr>identifier<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the snapshot from which to create the new cluster.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">vpc_<wbr>security_<wbr>group_<wbr>ids<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}A list of Virtual Private Cloud (VPC) security groups to be associated with the cluster.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}







## Supporting Types

#### ClusterLogging
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#ClusterLogging">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#ClusterLogging">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/redshift?tab=doc#ClusterLoggingArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/redshift?tab=doc#ClusterLoggingOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Redshift.ClusterLoggingArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Redshift.ClusterLogging.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Bucket<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of an existing S3 bucket where the log files are to be stored. Must be in the same region as the cluster and the cluster must have read bucket and put object permissions.
For more information on the permissions required for the bucket, please read the AWS [documentation](http://docs.aws.amazon.com/redshift/latest/mgmt/db-auditing.html#db-auditing-enable-logging)
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Enable<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Enables logging information such as queries and connection attempts, for the specified Amazon Redshift cluster.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">S3Key<wbr>Prefix<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The prefix applied to the log file names.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Bucket<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name of an existing S3 bucket where the log files are to be stored. Must be in the same region as the cluster and the cluster must have read bucket and put object permissions.
For more information on the permissions required for the bucket, please read the AWS [documentation](http://docs.aws.amazon.com/redshift/latest/mgmt/db-auditing.html#db-auditing-enable-logging)
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Enable<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Enables logging information such as queries and connection attempts, for the specified Amazon Redshift cluster.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">S3Key<wbr>Prefix<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The prefix applied to the log file names.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">bucket<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of an existing S3 bucket where the log files are to be stored. Must be in the same region as the cluster and the cluster must have read bucket and put object permissions.
For more information on the permissions required for the bucket, please read the AWS [documentation](http://docs.aws.amazon.com/redshift/latest/mgmt/db-auditing.html#db-auditing-enable-logging)
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">enable<span class="property-indicator"></span>
        <span class="property-type">boolean</span>
    </dt>
    <dd>{{% md %}}Enables logging information such as queries and connection attempts, for the specified Amazon Redshift cluster.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">s3Key<wbr>Prefix<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The prefix applied to the log file names.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">bucket_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of an existing S3 bucket where the log files are to be stored. Must be in the same region as the cluster and the cluster must have read bucket and put object permissions.
For more information on the permissions required for the bucket, please read the AWS [documentation](http://docs.aws.amazon.com/redshift/latest/mgmt/db-auditing.html#db-auditing-enable-logging)
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">enable<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Enables logging information such as queries and connection attempts, for the specified Amazon Redshift cluster.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">s3_<wbr>key_<wbr>prefix<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The prefix applied to the log file names.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### ClusterSnapshotCopy
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#ClusterSnapshotCopy">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#ClusterSnapshotCopy">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/redshift?tab=doc#ClusterSnapshotCopyArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/redshift?tab=doc#ClusterSnapshotCopyOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Redshift.ClusterSnapshotCopyArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Redshift.ClusterSnapshotCopy.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Destination<wbr>Region<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The destination region that you want to copy snapshots to.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Grant<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the snapshot copy grant to use when snapshots of an AWS KMS-encrypted cluster are copied to the destination region.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Retention<wbr>Period<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The number of days to retain automated snapshots in the destination region after they are copied from the source region. Defaults to `7`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Destination<wbr>Region<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The destination region that you want to copy snapshots to.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Grant<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name of the snapshot copy grant to use when snapshots of an AWS KMS-encrypted cluster are copied to the destination region.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Retention<wbr>Period<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The number of days to retain automated snapshots in the destination region after they are copied from the source region. Defaults to `7`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">destination<wbr>Region<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The destination region that you want to copy snapshots to.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">grant<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the snapshot copy grant to use when snapshots of an AWS KMS-encrypted cluster are copied to the destination region.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">retention<wbr>Period<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The number of days to retain automated snapshots in the destination region after they are copied from the source region. Defaults to `7`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">destination<wbr>Region<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The destination region that you want to copy snapshots to.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">grant<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the snapshot copy grant to use when snapshots of an AWS KMS-encrypted cluster are copied to the destination region.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">retention_<wbr>period<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The number of days to retain automated snapshots in the destination region after they are copied from the source region. Defaults to `7`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}








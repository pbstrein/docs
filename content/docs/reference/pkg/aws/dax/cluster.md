
---
title: "Cluster"
block_external_search_index: true
---

Provides a DAX Cluster resource.

## Example Usage

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const bar = new aws.dax.Cluster("bar", {
    clusterName: "cluster-example",
    iamRoleArn: aws_iam_role_example.arn,
    nodeType: "dax.r4.large",
    replicationFactor: 1,
});
```

> This content is derived from https://github.com/terraform-providers/terraform-provider-aws/blob/master/website/docs/r/dax_cluster.html.markdown.



## Create a Cluster Resource

{{< chooser language "javascript,typescript,python,go,csharp" / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/dax/#Cluster">Cluster</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/dax/#ClusterArgs">ClusterArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">Cluster</span><span class="p">(resource_name, opts=None, </span>availability_zones=None<span class="p">, </span>cluster_name=None<span class="p">, </span>description=None<span class="p">, </span>iam_role_arn=None<span class="p">, </span>maintenance_window=None<span class="p">, </span>node_type=None<span class="p">, </span>notification_topic_arn=None<span class="p">, </span>parameter_group_name=None<span class="p">, </span>replication_factor=None<span class="p">, </span>security_group_ids=None<span class="p">, </span>server_side_encryption=None<span class="p">, </span>subnet_group_name=None<span class="p">, </span>tags=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewCluster<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/dax?tab=doc#ClusterArgs">ClusterArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/dax?tab=doc#Cluster">Cluster</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Dax.Cluster.html">Cluster</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Dax.ClusterArgs.html">ClusterArgs</a></span> <span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
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
            title="Optional">Availability<wbr>Zones<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}List of Availability Zones in which the
nodes will be created
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Cluster<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Group identifier. DAX converts this name to
lowercase
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Description<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Description for the cluster
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Iam<wbr>Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}A valid Amazon Resource Name (ARN) that identifies
an IAM role. At runtime, DAX will assume this role and use the role&#39;s
permissions to access DynamoDB on your behalf
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Maintenance<wbr>Window<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Specifies the weekly time range for when
maintenance on the cluster is performed. The format is `ddd:hh24:mi-ddd:hh24:mi`
(24H Clock UTC). The minimum maintenance window is a 60 minute period. Example:
`sun:05:00-sun:09:00`
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Node<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The compute and memory capacity of the nodes. See
[Nodes][1] for supported node types
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Notification<wbr>Topic<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}An Amazon Resource Name (ARN) of an
SNS topic to send DAX notifications to. Example:
`arn:aws:sns:us-east-1:012345678999:my_sns_topic`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Parameter<wbr>Group<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Name of the parameter group to associate
with this DAX cluster
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Replication<wbr>Factor<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The number of nodes in the DAX cluster. A
replication factor of 1 will create a single-node cluster, without any read
replicas
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Security<wbr>Group<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}One or more VPC security groups associated
with the cluster
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Server<wbr>Side<wbr>Encryption<span class="property-indicator"></span>
        <span class="property-type"><a href="#clusterserversideencryption">Cluster<wbr>Server<wbr>Side<wbr>Encryption<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}Encrypt at rest options
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Subnet<wbr>Group<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Name of the subnet group to be used for the
cluster
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Availability<wbr>Zones<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}List of Availability Zones in which the
nodes will be created
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Cluster<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Group identifier. DAX converts this name to
lowercase
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Description<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Description for the cluster
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Iam<wbr>Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}A valid Amazon Resource Name (ARN) that identifies
an IAM role. At runtime, DAX will assume this role and use the role&#39;s
permissions to access DynamoDB on your behalf
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Maintenance<wbr>Window<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Specifies the weekly time range for when
maintenance on the cluster is performed. The format is `ddd:hh24:mi-ddd:hh24:mi`
(24H Clock UTC). The minimum maintenance window is a 60 minute period. Example:
`sun:05:00-sun:09:00`
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Node<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The compute and memory capacity of the nodes. See
[Nodes][1] for supported node types
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Notification<wbr>Topic<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}An Amazon Resource Name (ARN) of an
SNS topic to send DAX notifications to. Example:
`arn:aws:sns:us-east-1:012345678999:my_sns_topic`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Parameter<wbr>Group<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Name of the parameter group to associate
with this DAX cluster
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Replication<wbr>Factor<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The number of nodes in the DAX cluster. A
replication factor of 1 will create a single-node cluster, without any read
replicas
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Security<wbr>Group<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}One or more VPC security groups associated
with the cluster
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Server<wbr>Side<wbr>Encryption<span class="property-indicator"></span>
        <span class="property-type"><a href="#clusterserversideencryption">*Cluster<wbr>Server<wbr>Side<wbr>Encryption</a></span>
    </dt>
    <dd>{{% md %}}Encrypt at rest options
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Subnet<wbr>Group<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Name of the subnet group to be used for the
cluster
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">availability<wbr>Zones<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}List of Availability Zones in which the
nodes will be created
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">cluster<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Group identifier. DAX converts this name to
lowercase
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">description<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Description for the cluster
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">iam<wbr>Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}A valid Amazon Resource Name (ARN) that identifies
an IAM role. At runtime, DAX will assume this role and use the role&#39;s
permissions to access DynamoDB on your behalf
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">maintenance<wbr>Window<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Specifies the weekly time range for when
maintenance on the cluster is performed. The format is `ddd:hh24:mi-ddd:hh24:mi`
(24H Clock UTC). The minimum maintenance window is a 60 minute period. Example:
`sun:05:00-sun:09:00`
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">node<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The compute and memory capacity of the nodes. See
[Nodes][1] for supported node types
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">notification<wbr>Topic<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}An Amazon Resource Name (ARN) of an
SNS topic to send DAX notifications to. Example:
`arn:aws:sns:us-east-1:012345678999:my_sns_topic`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">parameter<wbr>Group<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Name of the parameter group to associate
with this DAX cluster
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">replication<wbr>Factor<span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}The number of nodes in the DAX cluster. A
replication factor of 1 will create a single-node cluster, without any read
replicas
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">security<wbr>Group<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}One or more VPC security groups associated
with the cluster
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">server<wbr>Side<wbr>Encryption<span class="property-indicator"></span>
        <span class="property-type"><a href="#clusterserversideencryption">Cluster<wbr>Server<wbr>Side<wbr>Encryption?</a></span>
    </dt>
    <dd>{{% md %}}Encrypt at rest options
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">subnet<wbr>Group<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Name of the subnet group to be used for the
cluster
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">availability_<wbr>zones<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}List of Availability Zones in which the
nodes will be created
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">cluster_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Group identifier. DAX converts this name to
lowercase
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">description<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Description for the cluster
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">iam_<wbr>role_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A valid Amazon Resource Name (ARN) that identifies
an IAM role. At runtime, DAX will assume this role and use the role&#39;s
permissions to access DynamoDB on your behalf
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">maintenance_<wbr>window<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Specifies the weekly time range for when
maintenance on the cluster is performed. The format is `ddd:hh24:mi-ddd:hh24:mi`
(24H Clock UTC). The minimum maintenance window is a 60 minute period. Example:
`sun:05:00-sun:09:00`
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">node_<wbr>type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The compute and memory capacity of the nodes. See
[Nodes][1] for supported node types
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">notification_<wbr>topic_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}An Amazon Resource Name (ARN) of an
SNS topic to send DAX notifications to. Example:
`arn:aws:sns:us-east-1:012345678999:my_sns_topic`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">parameter_<wbr>group_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Name of the parameter group to associate
with this DAX cluster
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">replication_<wbr>factor<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The number of nodes in the DAX cluster. A
replication factor of 1 will create a single-node cluster, without any read
replicas
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">security_<wbr>group_<wbr>ids<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}One or more VPC security groups associated
with the cluster
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">server_<wbr>side_<wbr>encryption<span class="property-indicator"></span>
        <span class="property-type"><a href="#clusterserversideencryption">Dict[Cluster<wbr>Server<wbr>Side<wbr>Encryption]</a></span>
    </dt>
    <dd>{{% md %}}Encrypt at rest options
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">subnet_<wbr>group_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Name of the subnet group to be used for the
cluster
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource
{{% /md %}}</dd>

</dl>
{{% /choosable %}}




## Cluster Output Properties

The following output properties are available:




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of the DAX cluster
{{% /md %}}</dd>

    <dt class="property-"
            title="">Availability<wbr>Zones<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}List of Availability Zones in which the
nodes will be created
{{% /md %}}</dd>

    <dt class="property-"
            title="">Cluster<wbr>Address<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The DNS name of the DAX cluster without the port appended
{{% /md %}}</dd>

    <dt class="property-"
            title="">Cluster<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Group identifier. DAX converts this name to
lowercase
{{% /md %}}</dd>

    <dt class="property-"
            title="">Configuration<wbr>Endpoint<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The configuration endpoint for this DAX cluster,
consisting of a DNS name and a port number
{{% /md %}}</dd>

    <dt class="property-"
            title="">Description<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Description for the cluster
{{% /md %}}</dd>

    <dt class="property-"
            title="">Iam<wbr>Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}A valid Amazon Resource Name (ARN) that identifies
an IAM role. At runtime, DAX will assume this role and use the role&#39;s
permissions to access DynamoDB on your behalf
{{% /md %}}</dd>

    <dt class="property-"
            title="">Maintenance<wbr>Window<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Specifies the weekly time range for when
maintenance on the cluster is performed. The format is `ddd:hh24:mi-ddd:hh24:mi`
(24H Clock UTC). The minimum maintenance window is a 60 minute period. Example:
`sun:05:00-sun:09:00`
{{% /md %}}</dd>

    <dt class="property-"
            title="">Node<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The compute and memory capacity of the nodes. See
[Nodes][1] for supported node types
{{% /md %}}</dd>

    <dt class="property-"
            title="">Nodes<span class="property-indicator"></span>
        <span class="property-type"><a href="#clusternode">List&lt;Cluster<wbr>Node&gt;</a></span>
    </dt>
    <dd>{{% md %}}List of node objects including `id`, `address`, `port` and
`availability_zone`. Referenceable e.g. as
`${aws_dax_cluster.test.nodes.0.address}`
{{% /md %}}</dd>

    <dt class="property-"
            title="">Notification<wbr>Topic<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}An Amazon Resource Name (ARN) of an
SNS topic to send DAX notifications to. Example:
`arn:aws:sns:us-east-1:012345678999:my_sns_topic`
{{% /md %}}</dd>

    <dt class="property-"
            title="">Parameter<wbr>Group<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Name of the parameter group to associate
with this DAX cluster
{{% /md %}}</dd>

    <dt class="property-"
            title="">Port<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The port used by the configuration endpoint
{{% /md %}}</dd>

    <dt class="property-"
            title="">Replication<wbr>Factor<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The number of nodes in the DAX cluster. A
replication factor of 1 will create a single-node cluster, without any read
replicas
{{% /md %}}</dd>

    <dt class="property-"
            title="">Security<wbr>Group<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">List<string></span>
    </dt>
    <dd>{{% md %}}One or more VPC security groups associated
with the cluster
{{% /md %}}</dd>

    <dt class="property-"
            title="">Server<wbr>Side<wbr>Encryption<span class="property-indicator"></span>
        <span class="property-type"><a href="#clusterserversideencryption">Cluster<wbr>Server<wbr>Side<wbr>Encryption?</a></span>
    </dt>
    <dd>{{% md %}}Encrypt at rest options
{{% /md %}}</dd>

    <dt class="property-"
            title="">Subnet<wbr>Group<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Name of the subnet group to be used for the
cluster
{{% /md %}}</dd>

    <dt class="property-"
            title="">Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of the DAX cluster
{{% /md %}}</dd>

    <dt class="property-"
            title="">Availability<wbr>Zones<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}List of Availability Zones in which the
nodes will be created
{{% /md %}}</dd>

    <dt class="property-"
            title="">Cluster<wbr>Address<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The DNS name of the DAX cluster without the port appended
{{% /md %}}</dd>

    <dt class="property-"
            title="">Cluster<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Group identifier. DAX converts this name to
lowercase
{{% /md %}}</dd>

    <dt class="property-"
            title="">Configuration<wbr>Endpoint<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The configuration endpoint for this DAX cluster,
consisting of a DNS name and a port number
{{% /md %}}</dd>

    <dt class="property-"
            title="">Description<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Description for the cluster
{{% /md %}}</dd>

    <dt class="property-"
            title="">Iam<wbr>Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}A valid Amazon Resource Name (ARN) that identifies
an IAM role. At runtime, DAX will assume this role and use the role&#39;s
permissions to access DynamoDB on your behalf
{{% /md %}}</dd>

    <dt class="property-"
            title="">Maintenance<wbr>Window<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Specifies the weekly time range for when
maintenance on the cluster is performed. The format is `ddd:hh24:mi-ddd:hh24:mi`
(24H Clock UTC). The minimum maintenance window is a 60 minute period. Example:
`sun:05:00-sun:09:00`
{{% /md %}}</dd>

    <dt class="property-"
            title="">Node<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The compute and memory capacity of the nodes. See
[Nodes][1] for supported node types
{{% /md %}}</dd>

    <dt class="property-"
            title="">Nodes<span class="property-indicator"></span>
        <span class="property-type"><a href="#clusternode">[]Cluster<wbr>Node</a></span>
    </dt>
    <dd>{{% md %}}List of node objects including `id`, `address`, `port` and
`availability_zone`. Referenceable e.g. as
`${aws_dax_cluster.test.nodes.0.address}`
{{% /md %}}</dd>

    <dt class="property-"
            title="">Notification<wbr>Topic<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}An Amazon Resource Name (ARN) of an
SNS topic to send DAX notifications to. Example:
`arn:aws:sns:us-east-1:012345678999:my_sns_topic`
{{% /md %}}</dd>

    <dt class="property-"
            title="">Parameter<wbr>Group<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Name of the parameter group to associate
with this DAX cluster
{{% /md %}}</dd>

    <dt class="property-"
            title="">Port<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The port used by the configuration endpoint
{{% /md %}}</dd>

    <dt class="property-"
            title="">Replication<wbr>Factor<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The number of nodes in the DAX cluster. A
replication factor of 1 will create a single-node cluster, without any read
replicas
{{% /md %}}</dd>

    <dt class="property-"
            title="">Security<wbr>Group<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}One or more VPC security groups associated
with the cluster
{{% /md %}}</dd>

    <dt class="property-"
            title="">Server<wbr>Side<wbr>Encryption<span class="property-indicator"></span>
        <span class="property-type"><a href="#clusterserversideencryption">*Cluster<wbr>Server<wbr>Side<wbr>Encryption</a></span>
    </dt>
    <dd>{{% md %}}Encrypt at rest options
{{% /md %}}</dd>

    <dt class="property-"
            title="">Subnet<wbr>Group<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Name of the subnet group to be used for the
cluster
{{% /md %}}</dd>

    <dt class="property-"
            title="">Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of the DAX cluster
{{% /md %}}</dd>

    <dt class="property-"
            title="">availability<wbr>Zones<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}List of Availability Zones in which the
nodes will be created
{{% /md %}}</dd>

    <dt class="property-"
            title="">cluster<wbr>Address<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The DNS name of the DAX cluster without the port appended
{{% /md %}}</dd>

    <dt class="property-"
            title="">cluster<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Group identifier. DAX converts this name to
lowercase
{{% /md %}}</dd>

    <dt class="property-"
            title="">configuration<wbr>Endpoint<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The configuration endpoint for this DAX cluster,
consisting of a DNS name and a port number
{{% /md %}}</dd>

    <dt class="property-"
            title="">description<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Description for the cluster
{{% /md %}}</dd>

    <dt class="property-"
            title="">iam<wbr>Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}A valid Amazon Resource Name (ARN) that identifies
an IAM role. At runtime, DAX will assume this role and use the role&#39;s
permissions to access DynamoDB on your behalf
{{% /md %}}</dd>

    <dt class="property-"
            title="">maintenance<wbr>Window<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Specifies the weekly time range for when
maintenance on the cluster is performed. The format is `ddd:hh24:mi-ddd:hh24:mi`
(24H Clock UTC). The minimum maintenance window is a 60 minute period. Example:
`sun:05:00-sun:09:00`
{{% /md %}}</dd>

    <dt class="property-"
            title="">node<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The compute and memory capacity of the nodes. See
[Nodes][1] for supported node types
{{% /md %}}</dd>

    <dt class="property-"
            title="">nodes<span class="property-indicator"></span>
        <span class="property-type"><a href="#clusternode">Cluster<wbr>Node[]</a></span>
    </dt>
    <dd>{{% md %}}List of node objects including `id`, `address`, `port` and
`availability_zone`. Referenceable e.g. as
`${aws_dax_cluster.test.nodes.0.address}`
{{% /md %}}</dd>

    <dt class="property-"
            title="">notification<wbr>Topic<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}An Amazon Resource Name (ARN) of an
SNS topic to send DAX notifications to. Example:
`arn:aws:sns:us-east-1:012345678999:my_sns_topic`
{{% /md %}}</dd>

    <dt class="property-"
            title="">parameter<wbr>Group<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Name of the parameter group to associate
with this DAX cluster
{{% /md %}}</dd>

    <dt class="property-"
            title="">port<span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}The port used by the configuration endpoint
{{% /md %}}</dd>

    <dt class="property-"
            title="">replication<wbr>Factor<span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}The number of nodes in the DAX cluster. A
replication factor of 1 will create a single-node cluster, without any read
replicas
{{% /md %}}</dd>

    <dt class="property-"
            title="">security<wbr>Group<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">string[]</span>
    </dt>
    <dd>{{% md %}}One or more VPC security groups associated
with the cluster
{{% /md %}}</dd>

    <dt class="property-"
            title="">server<wbr>Side<wbr>Encryption<span class="property-indicator"></span>
        <span class="property-type"><a href="#clusterserversideencryption">Cluster<wbr>Server<wbr>Side<wbr>Encryption?</a></span>
    </dt>
    <dd>{{% md %}}Encrypt at rest options
{{% /md %}}</dd>

    <dt class="property-"
            title="">subnet<wbr>Group<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Name of the subnet group to be used for the
cluster
{{% /md %}}</dd>

    <dt class="property-"
            title="">tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ARN of the DAX cluster
{{% /md %}}</dd>

    <dt class="property-"
            title="">availability_<wbr>zones<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}List of Availability Zones in which the
nodes will be created
{{% /md %}}</dd>

    <dt class="property-"
            title="">cluster_<wbr>address<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The DNS name of the DAX cluster without the port appended
{{% /md %}}</dd>

    <dt class="property-"
            title="">cluster_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Group identifier. DAX converts this name to
lowercase
{{% /md %}}</dd>

    <dt class="property-"
            title="">configuration_<wbr>endpoint<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The configuration endpoint for this DAX cluster,
consisting of a DNS name and a port number
{{% /md %}}</dd>

    <dt class="property-"
            title="">description<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Description for the cluster
{{% /md %}}</dd>

    <dt class="property-"
            title="">iam_<wbr>role_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A valid Amazon Resource Name (ARN) that identifies
an IAM role. At runtime, DAX will assume this role and use the role&#39;s
permissions to access DynamoDB on your behalf
{{% /md %}}</dd>

    <dt class="property-"
            title="">maintenance_<wbr>window<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Specifies the weekly time range for when
maintenance on the cluster is performed. The format is `ddd:hh24:mi-ddd:hh24:mi`
(24H Clock UTC). The minimum maintenance window is a 60 minute period. Example:
`sun:05:00-sun:09:00`
{{% /md %}}</dd>

    <dt class="property-"
            title="">node_<wbr>type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The compute and memory capacity of the nodes. See
[Nodes][1] for supported node types
{{% /md %}}</dd>

    <dt class="property-"
            title="">nodes<span class="property-indicator"></span>
        <span class="property-type"><a href="#clusternode">List[Cluster<wbr>Node]</a></span>
    </dt>
    <dd>{{% md %}}List of node objects including `id`, `address`, `port` and
`availability_zone`. Referenceable e.g. as
`${aws_dax_cluster.test.nodes.0.address}`
{{% /md %}}</dd>

    <dt class="property-"
            title="">notification_<wbr>topic_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}An Amazon Resource Name (ARN) of an
SNS topic to send DAX notifications to. Example:
`arn:aws:sns:us-east-1:012345678999:my_sns_topic`
{{% /md %}}</dd>

    <dt class="property-"
            title="">parameter_<wbr>group_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Name of the parameter group to associate
with this DAX cluster
{{% /md %}}</dd>

    <dt class="property-"
            title="">port<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The port used by the configuration endpoint
{{% /md %}}</dd>

    <dt class="property-"
            title="">replication_<wbr>factor<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The number of nodes in the DAX cluster. A
replication factor of 1 will create a single-node cluster, without any read
replicas
{{% /md %}}</dd>

    <dt class="property-"
            title="">security_<wbr>group_<wbr>ids<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}One or more VPC security groups associated
with the cluster
{{% /md %}}</dd>

    <dt class="property-"
            title="">server_<wbr>side_<wbr>encryption<span class="property-indicator"></span>
        <span class="property-type"><a href="#clusterserversideencryption">Dict[Cluster<wbr>Server<wbr>Side<wbr>Encryption]</a></span>
    </dt>
    <dd>{{% md %}}Encrypt at rest options
{{% /md %}}</dd>

    <dt class="property-"
            title="">subnet_<wbr>group_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Name of the subnet group to be used for the
cluster
{{% /md %}}</dd>

    <dt class="property-"
            title="">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





## Look up an Existing Cluster Resource

{{< chooser language "javascript,typescript,python,go,csharp  " / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">pulumi.Input&lt;pulumi.ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/dax/#ClusterState">ClusterState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/dax/#Cluster">Cluster</a></span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>arn=None<span class="p">, </span>availability_zones=None<span class="p">, </span>cluster_address=None<span class="p">, </span>cluster_name=None<span class="p">, </span>configuration_endpoint=None<span class="p">, </span>description=None<span class="p">, </span>iam_role_arn=None<span class="p">, </span>maintenance_window=None<span class="p">, </span>node_type=None<span class="p">, </span>nodes=None<span class="p">, </span>notification_topic_arn=None<span class="p">, </span>parameter_group_name=None<span class="p">, </span>port=None<span class="p">, </span>replication_factor=None<span class="p">, </span>security_group_ids=None<span class="p">, </span>server_side_encryption=None<span class="p">, </span>subnet_group_name=None<span class="p">, </span>tags=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetCluster<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">pulumi.IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/dax?tab=doc#ClusterState">ClusterState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/dax?tab=doc#Cluster">Cluster</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Dax.Cluster.html">Cluster</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Pulumi.Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Dax.ClusterState.html">ClusterState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
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
            title="Optional">Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ARN of the DAX cluster
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Availability<wbr>Zones<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}List of Availability Zones in which the
nodes will be created
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Cluster<wbr>Address<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The DNS name of the DAX cluster without the port appended
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Cluster<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Group identifier. DAX converts this name to
lowercase
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Configuration<wbr>Endpoint<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The configuration endpoint for this DAX cluster,
consisting of a DNS name and a port number
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Description<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Description for the cluster
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Iam<wbr>Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A valid Amazon Resource Name (ARN) that identifies
an IAM role. At runtime, DAX will assume this role and use the role&#39;s
permissions to access DynamoDB on your behalf
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Maintenance<wbr>Window<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Specifies the weekly time range for when
maintenance on the cluster is performed. The format is `ddd:hh24:mi-ddd:hh24:mi`
(24H Clock UTC). The minimum maintenance window is a 60 minute period. Example:
`sun:05:00-sun:09:00`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Node<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The compute and memory capacity of the nodes. See
[Nodes][1] for supported node types
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Nodes<span class="property-indicator"></span>
        <span class="property-type"><a href="#clusternode">List&lt;Cluster<wbr>Node<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}List of node objects including `id`, `address`, `port` and
`availability_zone`. Referenceable e.g. as
`${aws_dax_cluster.test.nodes.0.address}`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Notification<wbr>Topic<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}An Amazon Resource Name (ARN) of an
SNS topic to send DAX notifications to. Example:
`arn:aws:sns:us-east-1:012345678999:my_sns_topic`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Parameter<wbr>Group<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Name of the parameter group to associate
with this DAX cluster
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Port<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The port used by the configuration endpoint
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Replication<wbr>Factor<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The number of nodes in the DAX cluster. A
replication factor of 1 will create a single-node cluster, without any read
replicas
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Security<wbr>Group<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}One or more VPC security groups associated
with the cluster
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Server<wbr>Side<wbr>Encryption<span class="property-indicator"></span>
        <span class="property-type"><a href="#clusterserversideencryption">Cluster<wbr>Server<wbr>Side<wbr>Encryption<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}Encrypt at rest options
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Subnet<wbr>Group<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Name of the subnet group to be used for the
cluster
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The ARN of the DAX cluster
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Availability<wbr>Zones<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}List of Availability Zones in which the
nodes will be created
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Cluster<wbr>Address<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The DNS name of the DAX cluster without the port appended
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Cluster<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Group identifier. DAX converts this name to
lowercase
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Configuration<wbr>Endpoint<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The configuration endpoint for this DAX cluster,
consisting of a DNS name and a port number
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Description<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Description for the cluster
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Iam<wbr>Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}A valid Amazon Resource Name (ARN) that identifies
an IAM role. At runtime, DAX will assume this role and use the role&#39;s
permissions to access DynamoDB on your behalf
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Maintenance<wbr>Window<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Specifies the weekly time range for when
maintenance on the cluster is performed. The format is `ddd:hh24:mi-ddd:hh24:mi`
(24H Clock UTC). The minimum maintenance window is a 60 minute period. Example:
`sun:05:00-sun:09:00`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Node<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The compute and memory capacity of the nodes. See
[Nodes][1] for supported node types
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Nodes<span class="property-indicator"></span>
        <span class="property-type"><a href="#clusternode">[]Cluster<wbr>Node</a></span>
    </dt>
    <dd>{{% md %}}List of node objects including `id`, `address`, `port` and
`availability_zone`. Referenceable e.g. as
`${aws_dax_cluster.test.nodes.0.address}`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Notification<wbr>Topic<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}An Amazon Resource Name (ARN) of an
SNS topic to send DAX notifications to. Example:
`arn:aws:sns:us-east-1:012345678999:my_sns_topic`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Parameter<wbr>Group<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Name of the parameter group to associate
with this DAX cluster
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Port<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The port used by the configuration endpoint
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Replication<wbr>Factor<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The number of nodes in the DAX cluster. A
replication factor of 1 will create a single-node cluster, without any read
replicas
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Security<wbr>Group<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}One or more VPC security groups associated
with the cluster
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Server<wbr>Side<wbr>Encryption<span class="property-indicator"></span>
        <span class="property-type"><a href="#clusterserversideencryption">*Cluster<wbr>Server<wbr>Side<wbr>Encryption</a></span>
    </dt>
    <dd>{{% md %}}Encrypt at rest options
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Subnet<wbr>Group<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Name of the subnet group to be used for the
cluster
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ARN of the DAX cluster
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">availability<wbr>Zones<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}List of Availability Zones in which the
nodes will be created
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">cluster<wbr>Address<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The DNS name of the DAX cluster without the port appended
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">cluster<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Group identifier. DAX converts this name to
lowercase
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">configuration<wbr>Endpoint<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The configuration endpoint for this DAX cluster,
consisting of a DNS name and a port number
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">description<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Description for the cluster
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">iam<wbr>Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A valid Amazon Resource Name (ARN) that identifies
an IAM role. At runtime, DAX will assume this role and use the role&#39;s
permissions to access DynamoDB on your behalf
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">maintenance<wbr>Window<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Specifies the weekly time range for when
maintenance on the cluster is performed. The format is `ddd:hh24:mi-ddd:hh24:mi`
(24H Clock UTC). The minimum maintenance window is a 60 minute period. Example:
`sun:05:00-sun:09:00`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">node<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The compute and memory capacity of the nodes. See
[Nodes][1] for supported node types
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">nodes<span class="property-indicator"></span>
        <span class="property-type"><a href="#clusternode">Cluster<wbr>Node[]?</a></span>
    </dt>
    <dd>{{% md %}}List of node objects including `id`, `address`, `port` and
`availability_zone`. Referenceable e.g. as
`${aws_dax_cluster.test.nodes.0.address}`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">notification<wbr>Topic<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}An Amazon Resource Name (ARN) of an
SNS topic to send DAX notifications to. Example:
`arn:aws:sns:us-east-1:012345678999:my_sns_topic`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">parameter<wbr>Group<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Name of the parameter group to associate
with this DAX cluster
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">port<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The port used by the configuration endpoint
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">replication<wbr>Factor<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The number of nodes in the DAX cluster. A
replication factor of 1 will create a single-node cluster, without any read
replicas
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">security<wbr>Group<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}One or more VPC security groups associated
with the cluster
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">server<wbr>Side<wbr>Encryption<span class="property-indicator"></span>
        <span class="property-type"><a href="#clusterserversideencryption">Cluster<wbr>Server<wbr>Side<wbr>Encryption?</a></span>
    </dt>
    <dd>{{% md %}}Encrypt at rest options
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">subnet<wbr>Group<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Name of the subnet group to be used for the
cluster
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ARN of the DAX cluster
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">availability_<wbr>zones<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}List of Availability Zones in which the
nodes will be created
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">cluster_<wbr>address<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The DNS name of the DAX cluster without the port appended
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">cluster_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Group identifier. DAX converts this name to
lowercase
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">configuration_<wbr>endpoint<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The configuration endpoint for this DAX cluster,
consisting of a DNS name and a port number
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">description<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Description for the cluster
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">iam_<wbr>role_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A valid Amazon Resource Name (ARN) that identifies
an IAM role. At runtime, DAX will assume this role and use the role&#39;s
permissions to access DynamoDB on your behalf
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">maintenance_<wbr>window<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Specifies the weekly time range for when
maintenance on the cluster is performed. The format is `ddd:hh24:mi-ddd:hh24:mi`
(24H Clock UTC). The minimum maintenance window is a 60 minute period. Example:
`sun:05:00-sun:09:00`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">node_<wbr>type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The compute and memory capacity of the nodes. See
[Nodes][1] for supported node types
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">nodes<span class="property-indicator"></span>
        <span class="property-type"><a href="#clusternode">List[Cluster<wbr>Node]</a></span>
    </dt>
    <dd>{{% md %}}List of node objects including `id`, `address`, `port` and
`availability_zone`. Referenceable e.g. as
`${aws_dax_cluster.test.nodes.0.address}`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">notification_<wbr>topic_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}An Amazon Resource Name (ARN) of an
SNS topic to send DAX notifications to. Example:
`arn:aws:sns:us-east-1:012345678999:my_sns_topic`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">parameter_<wbr>group_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Name of the parameter group to associate
with this DAX cluster
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">port<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The port used by the configuration endpoint
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">replication_<wbr>factor<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The number of nodes in the DAX cluster. A
replication factor of 1 will create a single-node cluster, without any read
replicas
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">security_<wbr>group_<wbr>ids<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}One or more VPC security groups associated
with the cluster
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">server_<wbr>side_<wbr>encryption<span class="property-indicator"></span>
        <span class="property-type"><a href="#clusterserversideencryption">Dict[Cluster<wbr>Server<wbr>Side<wbr>Encryption]</a></span>
    </dt>
    <dd>{{% md %}}Encrypt at rest options
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">subnet_<wbr>group_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Name of the subnet group to be used for the
cluster
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource
{{% /md %}}</dd>

</dl>
{{% /choosable %}}







## Supporting Types

#### ClusterNode
{{% lang nodejs %}}
> See the   <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#ClusterNode">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the   <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/dax?tab=doc#ClusterNodeOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the   <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Dax.ClusterNode.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Address<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Availability<wbr>Zone<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Port<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The port used by the configuration endpoint
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Address<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Availability<wbr>Zone<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Port<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The port used by the configuration endpoint
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">address<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">availability<wbr>Zone<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">port<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The port used by the configuration endpoint
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">address<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">availability_<wbr>zone<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">port<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The port used by the configuration endpoint
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### ClusterServerSideEncryption
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#ClusterServerSideEncryption">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#ClusterServerSideEncryption">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/dax?tab=doc#ClusterServerSideEncryptionArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/dax?tab=doc#ClusterServerSideEncryptionOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Dax.ClusterServerSideEncryptionArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Dax.ClusterServerSideEncryption.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Enabled<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Whether to enable encryption at rest. Defaults to `false`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Enabled<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Whether to enable encryption at rest. Defaults to `false`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">enabled<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Whether to enable encryption at rest. Defaults to `false`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">enabled<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Whether to enable encryption at rest. Defaults to `false`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}









---
title: "GetCluster"
block_external_search_index: true
---

Provides details about a specific redshift cluster.

## Example Usage

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const testCluster = aws.redshift.getCluster({
    clusterIdentifier: "test-cluster",
});
const testStream = new aws.kinesis.FirehoseDeliveryStream("test_stream", {
    destination: "redshift",
    redshiftConfiguration: {
        clusterJdbcurl: `jdbc:redshift://${testCluster.endpoint}/${testCluster.databaseName}`,
        copyOptions: "delimiter '|'", // the default delimiter
        dataTableColumns: "test-col",
        dataTableName: "test-table",
        password: "T3stPass",
        roleArn: aws_iam_role_firehose_role.arn,
        username: "testuser",
    },
    s3Configuration: {
        bucketArn: aws_s3_bucket_bucket.arn,
        bufferInterval: 400,
        bufferSize: 10,
        compressionFormat: "GZIP",
        roleArn: aws_iam_role_firehose_role.arn,
    },
});
```

> This content is derived from https://github.com/terraform-providers/terraform-provider-aws/blob/master/website/docs/d/redshift_cluster.html.markdown.





## Using GetCluster

{{< chooser language "typescript,python,go,csharp" >}}

{{% choosable language typescript %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">function </span>getCluster<span class="p">(</span><span class="nx">args</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/redshift/#GetClusterArgs">GetClusterArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#InvokeOptions">pulumi.InvokeOptions</a></span><span class="p">): Promise&lt;<span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/redshift/#GetClusterResult">GetClusterResult</a></span>></span></code></pre></div>
{{% /choosable %}}" }}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">function </span> get_cluster(</span>cluster_identifier=None<span class="p">, </span>tags=None<span class="p">, </span>opts=None<span class="p">)</span></code></pre></div>
{{% /choosable %}}" }}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>LookupCluster<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">args</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/redshift?tab=doc#LookupClusterArgs">LookupClusterArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#InvokeOption">pulumi.InvokeOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/redshift?tab=doc#LookupClusterResult">LookupClusterResult</a></span>, error)</span></code></pre></div>
{{% /choosable %}}" }}

{{% choosable language csharp %}}
<div class="highlight">
<pre class="chroma">
<code class="language-csharp" data-lang="csharp"><span class="k">public static class </span><span class="nx">GetCluster </span><span class="p">{</span>
    <span class="k">public static </span>Task&lt;<span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Redshift.GetClusterResult.html">GetClusterResult</a></span>> <span class="p">InvokeAsync(</span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Redshift.GetClusterArgs.html">GetClusterArgs</a></span> <span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/InvokeOptions.html">InvokeOptions</a></span>? <span class="nx">opts = null<span class="p">)</span>
<span class="p">}</span></code></pre>
</div>
{{% /choosable %}}" }}



The following arguments are supported:



{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Cluster<wbr>Identifier<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The cluster identifier
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Cluster<wbr>Identifier<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The cluster identifier
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">cluster<wbr>Identifier<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The cluster identifier
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">cluster_<wbr>identifier<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The cluster identifier
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}








## GetCluster Result

The following output properties are available:




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Allow<wbr>Version<wbr>Upgrade<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Whether major version upgrades can be applied during maintenance period
{{% /md %}}</dd>

    <dt class="property-"
            title="">Automated<wbr>Snapshot<wbr>Retention<wbr>Period<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The backup retention period
{{% /md %}}</dd>

    <dt class="property-"
            title="">Availability<wbr>Zone<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The availability zone of the cluster
{{% /md %}}</dd>

    <dt class="property-"
            title="">Bucket<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the S3 bucket where the log files are to be stored
{{% /md %}}</dd>

    <dt class="property-"
            title="">Cluster<wbr>Identifier<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The cluster identifier
{{% /md %}}</dd>

    <dt class="property-"
            title="">Cluster<wbr>Parameter<wbr>Group<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the parameter group to be associated with this cluster
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
    <dd>{{% md %}}The cluster revision number
{{% /md %}}</dd>

    <dt class="property-"
            title="">Cluster<wbr>Security<wbr>Groups<span class="property-indicator"></span>
        <span class="property-type">List<string></span>
    </dt>
    <dd>{{% md %}}The security groups associated with the cluster
{{% /md %}}</dd>

    <dt class="property-"
            title="">Cluster<wbr>Subnet<wbr>Group<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of a cluster subnet group to be associated with this cluster
{{% /md %}}</dd>

    <dt class="property-"
            title="">Cluster<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The cluster type
{{% /md %}}</dd>

    <dt class="property-"
            title="">Cluster<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">Database<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the default database in the cluster
{{% /md %}}</dd>

    <dt class="property-"
            title="">Elastic<wbr>Ip<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Elastic IP of the cluster
{{% /md %}}</dd>

    <dt class="property-"
            title="">Enable<wbr>Logging<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Whether cluster logging is enabled
{{% /md %}}</dd>

    <dt class="property-"
            title="">Encrypted<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Whether the cluster data is encrypted
{{% /md %}}</dd>

    <dt class="property-"
            title="">Endpoint<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The cluster endpoint
{{% /md %}}</dd>

    <dt class="property-"
            title="">Enhanced<wbr>Vpc<wbr>Routing<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Whether enhanced VPC routing is enabled
{{% /md %}}</dd>

    <dt class="property-"
            title="">Iam<wbr>Roles<span class="property-indicator"></span>
        <span class="property-type">List<string></span>
    </dt>
    <dd>{{% md %}}The IAM roles associated to the cluster
{{% /md %}}</dd>

    <dt class="property-"
            title="">Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}id is the provider-assigned unique ID for this managed resource.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Kms<wbr>Key<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The KMS encryption key associated to the cluster
{{% /md %}}</dd>

    <dt class="property-"
            title="">Master<wbr>Username<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Username for the master DB user
{{% /md %}}</dd>

    <dt class="property-"
            title="">Node<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The cluster node type
{{% /md %}}</dd>

    <dt class="property-"
            title="">Number<wbr>Of<wbr>Nodes<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The number of nodes in the cluster
{{% /md %}}</dd>

    <dt class="property-"
            title="">Port<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The port the cluster responds on
{{% /md %}}</dd>

    <dt class="property-"
            title="">Preferred<wbr>Maintenance<wbr>Window<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The maintenance window
{{% /md %}}</dd>

    <dt class="property-"
            title="">Publicly<wbr>Accessible<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Whether the cluster is publicly accessible
{{% /md %}}</dd>

    <dt class="property-"
            title="">S3Key<wbr>Prefix<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The folder inside the S3 bucket where the log files are stored
{{% /md %}}</dd>

    <dt class="property-"
            title="">Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}The tags associated to the cluster
{{% /md %}}</dd>

    <dt class="property-"
            title="">Vpc<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The VPC Id associated with the cluster
{{% /md %}}</dd>

    <dt class="property-"
            title="">Vpc<wbr>Security<wbr>Group<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">List<string></span>
    </dt>
    <dd>{{% md %}}The VPC security group Ids associated with the cluster
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Allow<wbr>Version<wbr>Upgrade<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Whether major version upgrades can be applied during maintenance period
{{% /md %}}</dd>

    <dt class="property-"
            title="">Automated<wbr>Snapshot<wbr>Retention<wbr>Period<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The backup retention period
{{% /md %}}</dd>

    <dt class="property-"
            title="">Availability<wbr>Zone<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The availability zone of the cluster
{{% /md %}}</dd>

    <dt class="property-"
            title="">Bucket<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the S3 bucket where the log files are to be stored
{{% /md %}}</dd>

    <dt class="property-"
            title="">Cluster<wbr>Identifier<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The cluster identifier
{{% /md %}}</dd>

    <dt class="property-"
            title="">Cluster<wbr>Parameter<wbr>Group<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the parameter group to be associated with this cluster
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
    <dd>{{% md %}}The cluster revision number
{{% /md %}}</dd>

    <dt class="property-"
            title="">Cluster<wbr>Security<wbr>Groups<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}The security groups associated with the cluster
{{% /md %}}</dd>

    <dt class="property-"
            title="">Cluster<wbr>Subnet<wbr>Group<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of a cluster subnet group to be associated with this cluster
{{% /md %}}</dd>

    <dt class="property-"
            title="">Cluster<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The cluster type
{{% /md %}}</dd>

    <dt class="property-"
            title="">Cluster<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">Database<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the default database in the cluster
{{% /md %}}</dd>

    <dt class="property-"
            title="">Elastic<wbr>Ip<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Elastic IP of the cluster
{{% /md %}}</dd>

    <dt class="property-"
            title="">Enable<wbr>Logging<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Whether cluster logging is enabled
{{% /md %}}</dd>

    <dt class="property-"
            title="">Encrypted<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Whether the cluster data is encrypted
{{% /md %}}</dd>

    <dt class="property-"
            title="">Endpoint<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The cluster endpoint
{{% /md %}}</dd>

    <dt class="property-"
            title="">Enhanced<wbr>Vpc<wbr>Routing<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Whether enhanced VPC routing is enabled
{{% /md %}}</dd>

    <dt class="property-"
            title="">Iam<wbr>Roles<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}The IAM roles associated to the cluster
{{% /md %}}</dd>

    <dt class="property-"
            title="">Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}id is the provider-assigned unique ID for this managed resource.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Kms<wbr>Key<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The KMS encryption key associated to the cluster
{{% /md %}}</dd>

    <dt class="property-"
            title="">Master<wbr>Username<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Username for the master DB user
{{% /md %}}</dd>

    <dt class="property-"
            title="">Node<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The cluster node type
{{% /md %}}</dd>

    <dt class="property-"
            title="">Number<wbr>Of<wbr>Nodes<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The number of nodes in the cluster
{{% /md %}}</dd>

    <dt class="property-"
            title="">Port<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The port the cluster responds on
{{% /md %}}</dd>

    <dt class="property-"
            title="">Preferred<wbr>Maintenance<wbr>Window<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The maintenance window
{{% /md %}}</dd>

    <dt class="property-"
            title="">Publicly<wbr>Accessible<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Whether the cluster is publicly accessible
{{% /md %}}</dd>

    <dt class="property-"
            title="">S3Key<wbr>Prefix<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The folder inside the S3 bucket where the log files are stored
{{% /md %}}</dd>

    <dt class="property-"
            title="">Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}The tags associated to the cluster
{{% /md %}}</dd>

    <dt class="property-"
            title="">Vpc<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The VPC Id associated with the cluster
{{% /md %}}</dd>

    <dt class="property-"
            title="">Vpc<wbr>Security<wbr>Group<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}The VPC security group Ids associated with the cluster
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">allow<wbr>Version<wbr>Upgrade<span class="property-indicator"></span>
        <span class="property-type">boolean</span>
    </dt>
    <dd>{{% md %}}Whether major version upgrades can be applied during maintenance period
{{% /md %}}</dd>

    <dt class="property-"
            title="">automated<wbr>Snapshot<wbr>Retention<wbr>Period<span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}The backup retention period
{{% /md %}}</dd>

    <dt class="property-"
            title="">availability<wbr>Zone<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The availability zone of the cluster
{{% /md %}}</dd>

    <dt class="property-"
            title="">bucket<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the S3 bucket where the log files are to be stored
{{% /md %}}</dd>

    <dt class="property-"
            title="">cluster<wbr>Identifier<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The cluster identifier
{{% /md %}}</dd>

    <dt class="property-"
            title="">cluster<wbr>Parameter<wbr>Group<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the parameter group to be associated with this cluster
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
    <dd>{{% md %}}The cluster revision number
{{% /md %}}</dd>

    <dt class="property-"
            title="">cluster<wbr>Security<wbr>Groups<span class="property-indicator"></span>
        <span class="property-type">string[]</span>
    </dt>
    <dd>{{% md %}}The security groups associated with the cluster
{{% /md %}}</dd>

    <dt class="property-"
            title="">cluster<wbr>Subnet<wbr>Group<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of a cluster subnet group to be associated with this cluster
{{% /md %}}</dd>

    <dt class="property-"
            title="">cluster<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The cluster type
{{% /md %}}</dd>

    <dt class="property-"
            title="">cluster<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">database<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the default database in the cluster
{{% /md %}}</dd>

    <dt class="property-"
            title="">elastic<wbr>Ip<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Elastic IP of the cluster
{{% /md %}}</dd>

    <dt class="property-"
            title="">enable<wbr>Logging<span class="property-indicator"></span>
        <span class="property-type">boolean</span>
    </dt>
    <dd>{{% md %}}Whether cluster logging is enabled
{{% /md %}}</dd>

    <dt class="property-"
            title="">encrypted<span class="property-indicator"></span>
        <span class="property-type">boolean</span>
    </dt>
    <dd>{{% md %}}Whether the cluster data is encrypted
{{% /md %}}</dd>

    <dt class="property-"
            title="">endpoint<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The cluster endpoint
{{% /md %}}</dd>

    <dt class="property-"
            title="">enhanced<wbr>Vpc<wbr>Routing<span class="property-indicator"></span>
        <span class="property-type">boolean</span>
    </dt>
    <dd>{{% md %}}Whether enhanced VPC routing is enabled
{{% /md %}}</dd>

    <dt class="property-"
            title="">iam<wbr>Roles<span class="property-indicator"></span>
        <span class="property-type">string[]</span>
    </dt>
    <dd>{{% md %}}The IAM roles associated to the cluster
{{% /md %}}</dd>

    <dt class="property-"
            title="">id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}id is the provider-assigned unique ID for this managed resource.
{{% /md %}}</dd>

    <dt class="property-"
            title="">kms<wbr>Key<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The KMS encryption key associated to the cluster
{{% /md %}}</dd>

    <dt class="property-"
            title="">master<wbr>Username<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Username for the master DB user
{{% /md %}}</dd>

    <dt class="property-"
            title="">node<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The cluster node type
{{% /md %}}</dd>

    <dt class="property-"
            title="">number<wbr>Of<wbr>Nodes<span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}The number of nodes in the cluster
{{% /md %}}</dd>

    <dt class="property-"
            title="">port<span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}The port the cluster responds on
{{% /md %}}</dd>

    <dt class="property-"
            title="">preferred<wbr>Maintenance<wbr>Window<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The maintenance window
{{% /md %}}</dd>

    <dt class="property-"
            title="">publicly<wbr>Accessible<span class="property-indicator"></span>
        <span class="property-type">boolean</span>
    </dt>
    <dd>{{% md %}}Whether the cluster is publicly accessible
{{% /md %}}</dd>

    <dt class="property-"
            title="">s3Key<wbr>Prefix<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The folder inside the S3 bucket where the log files are stored
{{% /md %}}</dd>

    <dt class="property-"
            title="">tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}The tags associated to the cluster
{{% /md %}}</dd>

    <dt class="property-"
            title="">vpc<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The VPC Id associated with the cluster
{{% /md %}}</dd>

    <dt class="property-"
            title="">vpc<wbr>Security<wbr>Group<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">string[]</span>
    </dt>
    <dd>{{% md %}}The VPC security group Ids associated with the cluster
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">allow_<wbr>version_<wbr>upgrade<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Whether major version upgrades can be applied during maintenance period
{{% /md %}}</dd>

    <dt class="property-"
            title="">automated_<wbr>snapshot_<wbr>retention_<wbr>period<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The backup retention period
{{% /md %}}</dd>

    <dt class="property-"
            title="">availability_<wbr>zone<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The availability zone of the cluster
{{% /md %}}</dd>

    <dt class="property-"
            title="">bucket_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the S3 bucket where the log files are to be stored
{{% /md %}}</dd>

    <dt class="property-"
            title="">cluster_<wbr>identifier<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The cluster identifier
{{% /md %}}</dd>

    <dt class="property-"
            title="">cluster_<wbr>parameter_<wbr>group_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the parameter group to be associated with this cluster
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
    <dd>{{% md %}}The cluster revision number
{{% /md %}}</dd>

    <dt class="property-"
            title="">cluster_<wbr>security_<wbr>groups<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}The security groups associated with the cluster
{{% /md %}}</dd>

    <dt class="property-"
            title="">cluster_<wbr>subnet_<wbr>group_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of a cluster subnet group to be associated with this cluster
{{% /md %}}</dd>

    <dt class="property-"
            title="">cluster_<wbr>type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The cluster type
{{% /md %}}</dd>

    <dt class="property-"
            title="">cluster_<wbr>version<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">database_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the default database in the cluster
{{% /md %}}</dd>

    <dt class="property-"
            title="">elastic_<wbr>ip<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The Elastic IP of the cluster
{{% /md %}}</dd>

    <dt class="property-"
            title="">enable_<wbr>logging<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Whether cluster logging is enabled
{{% /md %}}</dd>

    <dt class="property-"
            title="">encrypted<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Whether the cluster data is encrypted
{{% /md %}}</dd>

    <dt class="property-"
            title="">endpoint<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The cluster endpoint
{{% /md %}}</dd>

    <dt class="property-"
            title="">enhanced_<wbr>vpc_<wbr>routing<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Whether enhanced VPC routing is enabled
{{% /md %}}</dd>

    <dt class="property-"
            title="">iam_<wbr>roles<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}The IAM roles associated to the cluster
{{% /md %}}</dd>

    <dt class="property-"
            title="">id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}id is the provider-assigned unique ID for this managed resource.
{{% /md %}}</dd>

    <dt class="property-"
            title="">kms_<wbr>key_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The KMS encryption key associated to the cluster
{{% /md %}}</dd>

    <dt class="property-"
            title="">master_<wbr>username<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Username for the master DB user
{{% /md %}}</dd>

    <dt class="property-"
            title="">node_<wbr>type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The cluster node type
{{% /md %}}</dd>

    <dt class="property-"
            title="">number_<wbr>of_<wbr>nodes<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The number of nodes in the cluster
{{% /md %}}</dd>

    <dt class="property-"
            title="">port<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The port the cluster responds on
{{% /md %}}</dd>

    <dt class="property-"
            title="">preferred_<wbr>maintenance_<wbr>window<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The maintenance window
{{% /md %}}</dd>

    <dt class="property-"
            title="">publicly_<wbr>accessible<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Whether the cluster is publicly accessible
{{% /md %}}</dd>

    <dt class="property-"
            title="">s3_<wbr>key_<wbr>prefix<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The folder inside the S3 bucket where the log files are stored
{{% /md %}}</dd>

    <dt class="property-"
            title="">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}The tags associated to the cluster
{{% /md %}}</dd>

    <dt class="property-"
            title="">vpc_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The VPC Id associated with the cluster
{{% /md %}}</dd>

    <dt class="property-"
            title="">vpc_<wbr>security_<wbr>group_<wbr>ids<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}The VPC security group Ids associated with the cluster
{{% /md %}}</dd>

</dl>
{{% /choosable %}}








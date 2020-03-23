
---
title: "GetReplicationGroup"
block_external_search_index: true
---

Use this data source to get information about an Elasticache Replication Group.

## Example Usage

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const bar = aws.elasticache.getReplicationGroup({
    replicationGroupId: "example",
});
```

> This content is derived from https://github.com/terraform-providers/terraform-provider-aws/blob/master/website/docs/d/elasticache_replication_group.html.markdown.





## Using GetReplicationGroup

{{< chooser language "typescript,python,go,csharp" >}}

{{% choosable language typescript %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">function </span>getReplicationGroup<span class="p">(</span><span class="nx">args</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/elasticache/#GetReplicationGroupArgs">GetReplicationGroupArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#InvokeOptions">pulumi.InvokeOptions</a></span><span class="p">): Promise&lt;<span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/elasticache/#GetReplicationGroupResult">GetReplicationGroupResult</a></span>></span></code></pre></div>
{{% /choosable %}}" }}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">function </span> get_replication_group(</span>replication_group_id=None<span class="p">, </span>opts=None<span class="p">)</span></code></pre></div>
{{% /choosable %}}" }}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>LookupReplicationGroup<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">args</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/elasticache?tab=doc#LookupReplicationGroupArgs">LookupReplicationGroupArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#InvokeOption">pulumi.InvokeOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/elasticache?tab=doc#LookupReplicationGroupResult">LookupReplicationGroupResult</a></span>, error)</span></code></pre></div>
{{% /choosable %}}" }}

{{% choosable language csharp %}}
<div class="highlight">
<pre class="chroma">
<code class="language-csharp" data-lang="csharp"><span class="k">public static class </span><span class="nx">GetReplicationGroup </span><span class="p">{</span>
    <span class="k">public static </span>Task&lt;<span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Elasticache.GetReplicationGroupResult.html">GetReplicationGroupResult</a></span>> <span class="p">InvokeAsync(</span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Elasticache.GetReplicationGroupArgs.html">GetReplicationGroupArgs</a></span> <span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/InvokeOptions.html">InvokeOptions</a></span>? <span class="nx">opts = null<span class="p">)</span>
<span class="p">}</span></code></pre>
</div>
{{% /choosable %}}" }}



The following arguments are supported:



{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Replication<wbr>Group<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The identifier for the replication group.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Replication<wbr>Group<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The identifier for the replication group.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">replication<wbr>Group<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The identifier for the replication group.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">replication_<wbr>group_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The identifier for the replication group.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}








## GetReplicationGroup Result

The following output properties are available:




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Auth<wbr>Token<wbr>Enabled<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}A flag that enables using an AuthToken (password) when issuing Redis commands.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Automatic<wbr>Failover<wbr>Enabled<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}A flag whether a read-only replica will be automatically promoted to read/write primary if the existing primary fails.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Configuration<wbr>Endpoint<wbr>Address<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The configuration endpoint address to allow host discovery.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}id is the provider-assigned unique ID for this managed resource.
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
    <dd>{{% md %}}The cluster node type.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Number<wbr>Cache<wbr>Clusters<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The number of cache clusters that the replication group has.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Port<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The port number on which the configuration endpoint will accept connections.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Primary<wbr>Endpoint<wbr>Address<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The endpoint of the primary node in this node group (shard).
{{% /md %}}</dd>

    <dt class="property-"
            title="">Replication<wbr>Group<wbr>Description<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The description of the replication group.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Replication<wbr>Group<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The identifier for the replication group.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Snapshot<wbr>Retention<wbr>Limit<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The number of days for which ElastiCache retains automatic cache cluster snapshots before deleting them.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Snapshot<wbr>Window<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The daily time range (in UTC) during which ElastiCache begins taking a daily snapshot of your node group (shard).
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Auth<wbr>Token<wbr>Enabled<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}A flag that enables using an AuthToken (password) when issuing Redis commands.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Automatic<wbr>Failover<wbr>Enabled<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}A flag whether a read-only replica will be automatically promoted to read/write primary if the existing primary fails.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Configuration<wbr>Endpoint<wbr>Address<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The configuration endpoint address to allow host discovery.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}id is the provider-assigned unique ID for this managed resource.
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
    <dd>{{% md %}}The cluster node type.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Number<wbr>Cache<wbr>Clusters<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The number of cache clusters that the replication group has.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Port<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The port number on which the configuration endpoint will accept connections.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Primary<wbr>Endpoint<wbr>Address<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The endpoint of the primary node in this node group (shard).
{{% /md %}}</dd>

    <dt class="property-"
            title="">Replication<wbr>Group<wbr>Description<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The description of the replication group.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Replication<wbr>Group<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The identifier for the replication group.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Snapshot<wbr>Retention<wbr>Limit<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The number of days for which ElastiCache retains automatic cache cluster snapshots before deleting them.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Snapshot<wbr>Window<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The daily time range (in UTC) during which ElastiCache begins taking a daily snapshot of your node group (shard).
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">auth<wbr>Token<wbr>Enabled<span class="property-indicator"></span>
        <span class="property-type">boolean</span>
    </dt>
    <dd>{{% md %}}A flag that enables using an AuthToken (password) when issuing Redis commands.
{{% /md %}}</dd>

    <dt class="property-"
            title="">automatic<wbr>Failover<wbr>Enabled<span class="property-indicator"></span>
        <span class="property-type">boolean</span>
    </dt>
    <dd>{{% md %}}A flag whether a read-only replica will be automatically promoted to read/write primary if the existing primary fails.
{{% /md %}}</dd>

    <dt class="property-"
            title="">configuration<wbr>Endpoint<wbr>Address<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The configuration endpoint address to allow host discovery.
{{% /md %}}</dd>

    <dt class="property-"
            title="">id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}id is the provider-assigned unique ID for this managed resource.
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
    <dd>{{% md %}}The cluster node type.
{{% /md %}}</dd>

    <dt class="property-"
            title="">number<wbr>Cache<wbr>Clusters<span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}The number of cache clusters that the replication group has.
{{% /md %}}</dd>

    <dt class="property-"
            title="">port<span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}The port number on which the configuration endpoint will accept connections.
{{% /md %}}</dd>

    <dt class="property-"
            title="">primary<wbr>Endpoint<wbr>Address<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The endpoint of the primary node in this node group (shard).
{{% /md %}}</dd>

    <dt class="property-"
            title="">replication<wbr>Group<wbr>Description<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The description of the replication group.
{{% /md %}}</dd>

    <dt class="property-"
            title="">replication<wbr>Group<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The identifier for the replication group.
{{% /md %}}</dd>

    <dt class="property-"
            title="">snapshot<wbr>Retention<wbr>Limit<span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}The number of days for which ElastiCache retains automatic cache cluster snapshots before deleting them.
{{% /md %}}</dd>

    <dt class="property-"
            title="">snapshot<wbr>Window<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The daily time range (in UTC) during which ElastiCache begins taking a daily snapshot of your node group (shard).
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">auth_<wbr>token_<wbr>enabled<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}A flag that enables using an AuthToken (password) when issuing Redis commands.
{{% /md %}}</dd>

    <dt class="property-"
            title="">automatic_<wbr>failover_<wbr>enabled<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}A flag whether a read-only replica will be automatically promoted to read/write primary if the existing primary fails.
{{% /md %}}</dd>

    <dt class="property-"
            title="">configuration_<wbr>endpoint_<wbr>address<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The configuration endpoint address to allow host discovery.
{{% /md %}}</dd>

    <dt class="property-"
            title="">id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}id is the provider-assigned unique ID for this managed resource.
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
    <dd>{{% md %}}The cluster node type.
{{% /md %}}</dd>

    <dt class="property-"
            title="">number_<wbr>cache_<wbr>clusters<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The number of cache clusters that the replication group has.
{{% /md %}}</dd>

    <dt class="property-"
            title="">port<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The port number on which the configuration endpoint will accept connections.
{{% /md %}}</dd>

    <dt class="property-"
            title="">primary_<wbr>endpoint_<wbr>address<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The endpoint of the primary node in this node group (shard).
{{% /md %}}</dd>

    <dt class="property-"
            title="">replication_<wbr>group_<wbr>description<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The description of the replication group.
{{% /md %}}</dd>

    <dt class="property-"
            title="">replication_<wbr>group_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The identifier for the replication group.
{{% /md %}}</dd>

    <dt class="property-"
            title="">snapshot_<wbr>retention_<wbr>limit<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The number of days for which ElastiCache retains automatic cache cluster snapshots before deleting them.
{{% /md %}}</dd>

    <dt class="property-"
            title="">snapshot_<wbr>window<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The daily time range (in UTC) during which ElastiCache begins taking a daily snapshot of your node group (shard).
{{% /md %}}</dd>

</dl>
{{% /choosable %}}









---
title: "NodeGroup"
block_external_search_index: true
---

Manages an EKS Node Group, which can provision and optionally update an Auto Scaling Group of Kubernetes worker nodes compatible with EKS. Additional documentation about this functionality can be found in the [EKS User Guide](https://docs.aws.amazon.com/eks/latest/userguide/managed-node-groups.html).

> This content is derived from https://github.com/terraform-providers/terraform-provider-aws/blob/master/website/docs/r/eks_node_group.html.markdown.



## Create a NodeGroup Resource

{{< chooser language "javascript,typescript,python,go,csharp" / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/eks/#NodeGroup">NodeGroup</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/eks/#NodeGroupArgs">NodeGroupArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">NodeGroup</span><span class="p">(resource_name, opts=None, </span>ami_type=None<span class="p">, </span>cluster_name=None<span class="p">, </span>disk_size=None<span class="p">, </span>instance_types=None<span class="p">, </span>labels=None<span class="p">, </span>node_group_name=None<span class="p">, </span>node_role_arn=None<span class="p">, </span>release_version=None<span class="p">, </span>remote_access=None<span class="p">, </span>scaling_config=None<span class="p">, </span>subnet_ids=None<span class="p">, </span>tags=None<span class="p">, </span>version=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewNodeGroup<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/eks?tab=doc#NodeGroupArgs">NodeGroupArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/eks?tab=doc#NodeGroup">NodeGroup</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Eks.NodeGroup.html">NodeGroup</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Eks.NodeGroupArgs.html">NodeGroupArgs</a></span> <span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
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
            title="Optional">Ami<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Cluster<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Name of the EKS Cluster.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Disk<wbr>Size<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Instance<wbr>Types<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Labels<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, string>?</span>
    </dt>
    <dd>{{% md %}}Key-value mapping of Kubernetes labels. Only labels that are applied with the EKS API are managed by this argument. Other Kubernetes labels applied to the EKS Node Group will not be managed.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Node<wbr>Group<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Name of the EKS Node Group.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Node<wbr>Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of the IAM Role that provides permissions for the EKS Node Group.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Release<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}AMI version of the EKS Node Group. Defaults to latest version for Kubernetes version.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Remote<wbr>Access<span class="property-indicator"></span>
        <span class="property-type"><a href="#nodegroupremoteaccess">Node<wbr>Group<wbr>Remote<wbr>Access<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}Configuration block with remote access settings. Detailed below.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Scaling<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#nodegroupscalingconfig">Node<wbr>Group<wbr>Scaling<wbr>Config<wbr>Args</a></span>
    </dt>
    <dd>{{% md %}}Configuration block with scaling settings. Detailed below.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Subnet<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">List<string></span>
    </dt>
    <dd>{{% md %}}Identifiers of EC2 Subnets to associate with the EKS Node Group. These subnets must have the following resource tag: `kubernetes.io/cluster/CLUSTER_NAME` (where `CLUSTER_NAME` is replaced with the name of the EKS Cluster).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}Key-value mapping of resource tags.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Version<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Ami<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Cluster<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Name of the EKS Cluster.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Disk<wbr>Size<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Instance<wbr>Types<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Labels<span class="property-indicator"></span>
        <span class="property-type">map[string]string</span>
    </dt>
    <dd>{{% md %}}Key-value mapping of Kubernetes labels. Only labels that are applied with the EKS API are managed by this argument. Other Kubernetes labels applied to the EKS Node Group will not be managed.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Node<wbr>Group<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Name of the EKS Node Group.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Node<wbr>Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of the IAM Role that provides permissions for the EKS Node Group.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Release<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}AMI version of the EKS Node Group. Defaults to latest version for Kubernetes version.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Remote<wbr>Access<span class="property-indicator"></span>
        <span class="property-type"><a href="#nodegroupremoteaccess">*Node<wbr>Group<wbr>Remote<wbr>Access</a></span>
    </dt>
    <dd>{{% md %}}Configuration block with remote access settings. Detailed below.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Scaling<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#nodegroupscalingconfig">Node<wbr>Group<wbr>Scaling<wbr>Config</a></span>
    </dt>
    <dd>{{% md %}}Configuration block with scaling settings. Detailed below.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Subnet<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}Identifiers of EC2 Subnets to associate with the EKS Node Group. These subnets must have the following resource tag: `kubernetes.io/cluster/CLUSTER_NAME` (where `CLUSTER_NAME` is replaced with the name of the EKS Cluster).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}Key-value mapping of resource tags.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Version<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">ami<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">cluster<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Name of the EKS Cluster.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">disk<wbr>Size<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">instance<wbr>Types<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">labels<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: string}?</span>
    </dt>
    <dd>{{% md %}}Key-value mapping of Kubernetes labels. Only labels that are applied with the EKS API are managed by this argument. Other Kubernetes labels applied to the EKS Node Group will not be managed.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">node<wbr>Group<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Name of the EKS Node Group.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">node<wbr>Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of the IAM Role that provides permissions for the EKS Node Group.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">release<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}AMI version of the EKS Node Group. Defaults to latest version for Kubernetes version.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">remote<wbr>Access<span class="property-indicator"></span>
        <span class="property-type"><a href="#nodegroupremoteaccess">Node<wbr>Group<wbr>Remote<wbr>Access?</a></span>
    </dt>
    <dd>{{% md %}}Configuration block with remote access settings. Detailed below.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">scaling<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#nodegroupscalingconfig">Node<wbr>Group<wbr>Scaling<wbr>Config</a></span>
    </dt>
    <dd>{{% md %}}Configuration block with scaling settings. Detailed below.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">subnet<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">string[]</span>
    </dt>
    <dd>{{% md %}}Identifiers of EC2 Subnets to associate with the EKS Node Group. These subnets must have the following resource tag: `kubernetes.io/cluster/CLUSTER_NAME` (where `CLUSTER_NAME` is replaced with the name of the EKS Cluster).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}Key-value mapping of resource tags.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">version<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">ami_<wbr>type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">cluster_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Name of the EKS Cluster.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">disk_<wbr>size<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">instance_<wbr>types<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">labels<span class="property-indicator"></span>
        <span class="property-type">Dict[str, str]</span>
    </dt>
    <dd>{{% md %}}Key-value mapping of Kubernetes labels. Only labels that are applied with the EKS API are managed by this argument. Other Kubernetes labels applied to the EKS Node Group will not be managed.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">node_<wbr>group_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Name of the EKS Node Group.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">node_<wbr>role_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of the IAM Role that provides permissions for the EKS Node Group.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">release_<wbr>version<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}AMI version of the EKS Node Group. Defaults to latest version for Kubernetes version.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">remote_<wbr>access<span class="property-indicator"></span>
        <span class="property-type"><a href="#nodegroupremoteaccess">Dict[Node<wbr>Group<wbr>Remote<wbr>Access]</a></span>
    </dt>
    <dd>{{% md %}}Configuration block with remote access settings. Detailed below.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">scaling_<wbr>config<span class="property-indicator"></span>
        <span class="property-type"><a href="#nodegroupscalingconfig">Dict[Node<wbr>Group<wbr>Scaling<wbr>Config]</a></span>
    </dt>
    <dd>{{% md %}}Configuration block with scaling settings. Detailed below.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">subnet_<wbr>ids<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}Identifiers of EC2 Subnets to associate with the EKS Node Group. These subnets must have the following resource tag: `kubernetes.io/cluster/CLUSTER_NAME` (where `CLUSTER_NAME` is replaced with the name of the EKS Cluster).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}Key-value mapping of resource tags.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">version<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}




## NodeGroup Output Properties

The following output properties are available:




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Ami<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of the EKS Node Group.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Cluster<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Name of the EKS Cluster.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Disk<wbr>Size<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">Instance<wbr>Types<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">Labels<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, string>?</span>
    </dt>
    <dd>{{% md %}}Key-value mapping of Kubernetes labels. Only labels that are applied with the EKS API are managed by this argument. Other Kubernetes labels applied to the EKS Node Group will not be managed.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Node<wbr>Group<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Name of the EKS Node Group.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Node<wbr>Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of the IAM Role that provides permissions for the EKS Node Group.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Release<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}AMI version of the EKS Node Group. Defaults to latest version for Kubernetes version.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Remote<wbr>Access<span class="property-indicator"></span>
        <span class="property-type"><a href="#nodegroupremoteaccess">Node<wbr>Group<wbr>Remote<wbr>Access?</a></span>
    </dt>
    <dd>{{% md %}}Configuration block with remote access settings. Detailed below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Resources<span class="property-indicator"></span>
        <span class="property-type"><a href="#nodegroupresource">List&lt;Node<wbr>Group<wbr>Resource&gt;</a></span>
    </dt>
    <dd>{{% md %}}List of objects containing information about underlying resources.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Scaling<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#nodegroupscalingconfig">Node<wbr>Group<wbr>Scaling<wbr>Config</a></span>
    </dt>
    <dd>{{% md %}}Configuration block with scaling settings. Detailed below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Status<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Status of the EKS Node Group.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Subnet<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">List<string></span>
    </dt>
    <dd>{{% md %}}Identifiers of EC2 Subnets to associate with the EKS Node Group. These subnets must have the following resource tag: `kubernetes.io/cluster/CLUSTER_NAME` (where `CLUSTER_NAME` is replaced with the name of the EKS Cluster).
{{% /md %}}</dd>

    <dt class="property-"
            title="">Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}Key-value mapping of resource tags.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Version<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Ami<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of the EKS Node Group.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Cluster<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Name of the EKS Cluster.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Disk<wbr>Size<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">Instance<wbr>Types<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">Labels<span class="property-indicator"></span>
        <span class="property-type">map[string]string</span>
    </dt>
    <dd>{{% md %}}Key-value mapping of Kubernetes labels. Only labels that are applied with the EKS API are managed by this argument. Other Kubernetes labels applied to the EKS Node Group will not be managed.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Node<wbr>Group<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Name of the EKS Node Group.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Node<wbr>Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of the IAM Role that provides permissions for the EKS Node Group.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Release<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}AMI version of the EKS Node Group. Defaults to latest version for Kubernetes version.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Remote<wbr>Access<span class="property-indicator"></span>
        <span class="property-type"><a href="#nodegroupremoteaccess">*Node<wbr>Group<wbr>Remote<wbr>Access</a></span>
    </dt>
    <dd>{{% md %}}Configuration block with remote access settings. Detailed below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Resources<span class="property-indicator"></span>
        <span class="property-type"><a href="#nodegroupresource">[]Node<wbr>Group<wbr>Resource</a></span>
    </dt>
    <dd>{{% md %}}List of objects containing information about underlying resources.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Scaling<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#nodegroupscalingconfig">Node<wbr>Group<wbr>Scaling<wbr>Config</a></span>
    </dt>
    <dd>{{% md %}}Configuration block with scaling settings. Detailed below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Status<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Status of the EKS Node Group.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Subnet<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}Identifiers of EC2 Subnets to associate with the EKS Node Group. These subnets must have the following resource tag: `kubernetes.io/cluster/CLUSTER_NAME` (where `CLUSTER_NAME` is replaced with the name of the EKS Cluster).
{{% /md %}}</dd>

    <dt class="property-"
            title="">Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}Key-value mapping of resource tags.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Version<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">ami<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of the EKS Node Group.
{{% /md %}}</dd>

    <dt class="property-"
            title="">cluster<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Name of the EKS Cluster.
{{% /md %}}</dd>

    <dt class="property-"
            title="">disk<wbr>Size<span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">instance<wbr>Types<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">labels<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: string}?</span>
    </dt>
    <dd>{{% md %}}Key-value mapping of Kubernetes labels. Only labels that are applied with the EKS API are managed by this argument. Other Kubernetes labels applied to the EKS Node Group will not be managed.
{{% /md %}}</dd>

    <dt class="property-"
            title="">node<wbr>Group<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Name of the EKS Node Group.
{{% /md %}}</dd>

    <dt class="property-"
            title="">node<wbr>Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of the IAM Role that provides permissions for the EKS Node Group.
{{% /md %}}</dd>

    <dt class="property-"
            title="">release<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}AMI version of the EKS Node Group. Defaults to latest version for Kubernetes version.
{{% /md %}}</dd>

    <dt class="property-"
            title="">remote<wbr>Access<span class="property-indicator"></span>
        <span class="property-type"><a href="#nodegroupremoteaccess">Node<wbr>Group<wbr>Remote<wbr>Access?</a></span>
    </dt>
    <dd>{{% md %}}Configuration block with remote access settings. Detailed below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">resources<span class="property-indicator"></span>
        <span class="property-type"><a href="#nodegroupresource">Node<wbr>Group<wbr>Resource[]</a></span>
    </dt>
    <dd>{{% md %}}List of objects containing information about underlying resources.
{{% /md %}}</dd>

    <dt class="property-"
            title="">scaling<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#nodegroupscalingconfig">Node<wbr>Group<wbr>Scaling<wbr>Config</a></span>
    </dt>
    <dd>{{% md %}}Configuration block with scaling settings. Detailed below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">status<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Status of the EKS Node Group.
{{% /md %}}</dd>

    <dt class="property-"
            title="">subnet<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">string[]</span>
    </dt>
    <dd>{{% md %}}Identifiers of EC2 Subnets to associate with the EKS Node Group. These subnets must have the following resource tag: `kubernetes.io/cluster/CLUSTER_NAME` (where `CLUSTER_NAME` is replaced with the name of the EKS Cluster).
{{% /md %}}</dd>

    <dt class="property-"
            title="">tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}Key-value mapping of resource tags.
{{% /md %}}</dd>

    <dt class="property-"
            title="">version<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">ami_<wbr>type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of the EKS Node Group.
{{% /md %}}</dd>

    <dt class="property-"
            title="">cluster_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Name of the EKS Cluster.
{{% /md %}}</dd>

    <dt class="property-"
            title="">disk_<wbr>size<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">instance_<wbr>types<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">labels<span class="property-indicator"></span>
        <span class="property-type">Dict[str, str]</span>
    </dt>
    <dd>{{% md %}}Key-value mapping of Kubernetes labels. Only labels that are applied with the EKS API are managed by this argument. Other Kubernetes labels applied to the EKS Node Group will not be managed.
{{% /md %}}</dd>

    <dt class="property-"
            title="">node_<wbr>group_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Name of the EKS Node Group.
{{% /md %}}</dd>

    <dt class="property-"
            title="">node_<wbr>role_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of the IAM Role that provides permissions for the EKS Node Group.
{{% /md %}}</dd>

    <dt class="property-"
            title="">release_<wbr>version<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}AMI version of the EKS Node Group. Defaults to latest version for Kubernetes version.
{{% /md %}}</dd>

    <dt class="property-"
            title="">remote_<wbr>access<span class="property-indicator"></span>
        <span class="property-type"><a href="#nodegroupremoteaccess">Dict[Node<wbr>Group<wbr>Remote<wbr>Access]</a></span>
    </dt>
    <dd>{{% md %}}Configuration block with remote access settings. Detailed below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">resources<span class="property-indicator"></span>
        <span class="property-type"><a href="#nodegroupresource">List[Node<wbr>Group<wbr>Resource]</a></span>
    </dt>
    <dd>{{% md %}}List of objects containing information about underlying resources.
{{% /md %}}</dd>

    <dt class="property-"
            title="">scaling_<wbr>config<span class="property-indicator"></span>
        <span class="property-type"><a href="#nodegroupscalingconfig">Dict[Node<wbr>Group<wbr>Scaling<wbr>Config]</a></span>
    </dt>
    <dd>{{% md %}}Configuration block with scaling settings. Detailed below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">status<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Status of the EKS Node Group.
{{% /md %}}</dd>

    <dt class="property-"
            title="">subnet_<wbr>ids<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}Identifiers of EC2 Subnets to associate with the EKS Node Group. These subnets must have the following resource tag: `kubernetes.io/cluster/CLUSTER_NAME` (where `CLUSTER_NAME` is replaced with the name of the EKS Cluster).
{{% /md %}}</dd>

    <dt class="property-"
            title="">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}Key-value mapping of resource tags.
{{% /md %}}</dd>

    <dt class="property-"
            title="">version<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}





## Look up an Existing NodeGroup Resource

{{< chooser language "javascript,typescript,python,go,csharp  " / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">pulumi.Input&lt;pulumi.ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/eks/#NodeGroupState">NodeGroupState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/eks/#NodeGroup">NodeGroup</a></span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>ami_type=None<span class="p">, </span>arn=None<span class="p">, </span>cluster_name=None<span class="p">, </span>disk_size=None<span class="p">, </span>instance_types=None<span class="p">, </span>labels=None<span class="p">, </span>node_group_name=None<span class="p">, </span>node_role_arn=None<span class="p">, </span>release_version=None<span class="p">, </span>remote_access=None<span class="p">, </span>resources=None<span class="p">, </span>scaling_config=None<span class="p">, </span>status=None<span class="p">, </span>subnet_ids=None<span class="p">, </span>tags=None<span class="p">, </span>version=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetNodeGroup<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">pulumi.IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/eks?tab=doc#NodeGroupState">NodeGroupState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/eks?tab=doc#NodeGroup">NodeGroup</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Eks.NodeGroup.html">NodeGroup</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Pulumi.Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Eks.NodeGroupState.html">NodeGroupState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
{{% /choosable %}}

Get an existing NodeGroup resource's state with the given name, ID, and optional extra properties used to qualify the lookup.

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
            title="Optional">Ami<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of the EKS Node Group.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Cluster<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Name of the EKS Cluster.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Disk<wbr>Size<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Instance<wbr>Types<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Labels<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, string>?</span>
    </dt>
    <dd>{{% md %}}Key-value mapping of Kubernetes labels. Only labels that are applied with the EKS API are managed by this argument. Other Kubernetes labels applied to the EKS Node Group will not be managed.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Node<wbr>Group<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Name of the EKS Node Group.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Node<wbr>Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of the IAM Role that provides permissions for the EKS Node Group.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Release<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}AMI version of the EKS Node Group. Defaults to latest version for Kubernetes version.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Remote<wbr>Access<span class="property-indicator"></span>
        <span class="property-type"><a href="#nodegroupremoteaccess">Node<wbr>Group<wbr>Remote<wbr>Access<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}Configuration block with remote access settings. Detailed below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Resources<span class="property-indicator"></span>
        <span class="property-type"><a href="#nodegroupresource">List&lt;Node<wbr>Group<wbr>Resource<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}List of objects containing information about underlying resources.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Scaling<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#nodegroupscalingconfig">Node<wbr>Group<wbr>Scaling<wbr>Config<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}Configuration block with scaling settings. Detailed below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Status<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Status of the EKS Node Group.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Subnet<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}Identifiers of EC2 Subnets to associate with the EKS Node Group. These subnets must have the following resource tag: `kubernetes.io/cluster/CLUSTER_NAME` (where `CLUSTER_NAME` is replaced with the name of the EKS Cluster).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}Key-value mapping of resource tags.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Version<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Ami<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of the EKS Node Group.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Cluster<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Name of the EKS Cluster.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Disk<wbr>Size<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Instance<wbr>Types<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Labels<span class="property-indicator"></span>
        <span class="property-type">map[string]string</span>
    </dt>
    <dd>{{% md %}}Key-value mapping of Kubernetes labels. Only labels that are applied with the EKS API are managed by this argument. Other Kubernetes labels applied to the EKS Node Group will not be managed.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Node<wbr>Group<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Name of the EKS Node Group.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Node<wbr>Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of the IAM Role that provides permissions for the EKS Node Group.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Release<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}AMI version of the EKS Node Group. Defaults to latest version for Kubernetes version.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Remote<wbr>Access<span class="property-indicator"></span>
        <span class="property-type"><a href="#nodegroupremoteaccess">*Node<wbr>Group<wbr>Remote<wbr>Access</a></span>
    </dt>
    <dd>{{% md %}}Configuration block with remote access settings. Detailed below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Resources<span class="property-indicator"></span>
        <span class="property-type"><a href="#nodegroupresource">[]Node<wbr>Group<wbr>Resource</a></span>
    </dt>
    <dd>{{% md %}}List of objects containing information about underlying resources.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Scaling<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#nodegroupscalingconfig">*Node<wbr>Group<wbr>Scaling<wbr>Config</a></span>
    </dt>
    <dd>{{% md %}}Configuration block with scaling settings. Detailed below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Status<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Status of the EKS Node Group.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Subnet<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}Identifiers of EC2 Subnets to associate with the EKS Node Group. These subnets must have the following resource tag: `kubernetes.io/cluster/CLUSTER_NAME` (where `CLUSTER_NAME` is replaced with the name of the EKS Cluster).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}Key-value mapping of resource tags.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Version<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">ami<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of the EKS Node Group.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">cluster<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Name of the EKS Cluster.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">disk<wbr>Size<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">instance<wbr>Types<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">labels<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: string}?</span>
    </dt>
    <dd>{{% md %}}Key-value mapping of Kubernetes labels. Only labels that are applied with the EKS API are managed by this argument. Other Kubernetes labels applied to the EKS Node Group will not be managed.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">node<wbr>Group<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Name of the EKS Node Group.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">node<wbr>Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of the IAM Role that provides permissions for the EKS Node Group.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">release<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}AMI version of the EKS Node Group. Defaults to latest version for Kubernetes version.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">remote<wbr>Access<span class="property-indicator"></span>
        <span class="property-type"><a href="#nodegroupremoteaccess">Node<wbr>Group<wbr>Remote<wbr>Access?</a></span>
    </dt>
    <dd>{{% md %}}Configuration block with remote access settings. Detailed below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">resources<span class="property-indicator"></span>
        <span class="property-type"><a href="#nodegroupresource">Node<wbr>Group<wbr>Resource[]?</a></span>
    </dt>
    <dd>{{% md %}}List of objects containing information about underlying resources.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">scaling<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#nodegroupscalingconfig">Node<wbr>Group<wbr>Scaling<wbr>Config?</a></span>
    </dt>
    <dd>{{% md %}}Configuration block with scaling settings. Detailed below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">status<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Status of the EKS Node Group.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">subnet<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}Identifiers of EC2 Subnets to associate with the EKS Node Group. These subnets must have the following resource tag: `kubernetes.io/cluster/CLUSTER_NAME` (where `CLUSTER_NAME` is replaced with the name of the EKS Cluster).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}Key-value mapping of resource tags.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">version<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">ami_<wbr>type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of the EKS Node Group.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">cluster_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Name of the EKS Cluster.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">disk_<wbr>size<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">instance_<wbr>types<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">labels<span class="property-indicator"></span>
        <span class="property-type">Dict[str, str]</span>
    </dt>
    <dd>{{% md %}}Key-value mapping of Kubernetes labels. Only labels that are applied with the EKS API are managed by this argument. Other Kubernetes labels applied to the EKS Node Group will not be managed.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">node_<wbr>group_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Name of the EKS Node Group.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">node_<wbr>role_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of the IAM Role that provides permissions for the EKS Node Group.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">release_<wbr>version<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}AMI version of the EKS Node Group. Defaults to latest version for Kubernetes version.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">remote_<wbr>access<span class="property-indicator"></span>
        <span class="property-type"><a href="#nodegroupremoteaccess">Dict[Node<wbr>Group<wbr>Remote<wbr>Access]</a></span>
    </dt>
    <dd>{{% md %}}Configuration block with remote access settings. Detailed below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">resources<span class="property-indicator"></span>
        <span class="property-type"><a href="#nodegroupresource">List[Node<wbr>Group<wbr>Resource]</a></span>
    </dt>
    <dd>{{% md %}}List of objects containing information about underlying resources.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">scaling_<wbr>config<span class="property-indicator"></span>
        <span class="property-type"><a href="#nodegroupscalingconfig">Dict[Node<wbr>Group<wbr>Scaling<wbr>Config]</a></span>
    </dt>
    <dd>{{% md %}}Configuration block with scaling settings. Detailed below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">status<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Status of the EKS Node Group.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">subnet_<wbr>ids<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}Identifiers of EC2 Subnets to associate with the EKS Node Group. These subnets must have the following resource tag: `kubernetes.io/cluster/CLUSTER_NAME` (where `CLUSTER_NAME` is replaced with the name of the EKS Cluster).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}Key-value mapping of resource tags.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">version<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}







## Supporting Types

#### NodeGroupRemoteAccess
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#NodeGroupRemoteAccess">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#NodeGroupRemoteAccess">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/eks?tab=doc#NodeGroupRemoteAccessArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/eks?tab=doc#NodeGroupRemoteAccessOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Eks.NodeGroupRemoteAccessArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Eks.NodeGroupRemoteAccess.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Ec2Ssh<wbr>Key<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}EC2 Key Pair name that provides access for SSH communication with the worker nodes in the EKS Node Group. If you specify this configuration, but do not specify `source_security_group_ids` when you create an EKS Node Group, port 22 on the worker nodes is opened to the Internet (0.0.0.0/0).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Source<wbr>Security<wbr>Group<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}Set of EC2 Security Group IDs to allow SSH access (port 22) from on the worker nodes. If you specify `ec2_ssh_key`, but do not specify this configuration when you create an EKS Node Group, port 22 on the worker nodes is opened to the Internet (0.0.0.0/0).
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Ec2Ssh<wbr>Key<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}EC2 Key Pair name that provides access for SSH communication with the worker nodes in the EKS Node Group. If you specify this configuration, but do not specify `source_security_group_ids` when you create an EKS Node Group, port 22 on the worker nodes is opened to the Internet (0.0.0.0/0).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Source<wbr>Security<wbr>Group<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}Set of EC2 Security Group IDs to allow SSH access (port 22) from on the worker nodes. If you specify `ec2_ssh_key`, but do not specify this configuration when you create an EKS Node Group, port 22 on the worker nodes is opened to the Internet (0.0.0.0/0).
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">ec2Ssh<wbr>Key<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}EC2 Key Pair name that provides access for SSH communication with the worker nodes in the EKS Node Group. If you specify this configuration, but do not specify `source_security_group_ids` when you create an EKS Node Group, port 22 on the worker nodes is opened to the Internet (0.0.0.0/0).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">source<wbr>Security<wbr>Group<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}Set of EC2 Security Group IDs to allow SSH access (port 22) from on the worker nodes. If you specify `ec2_ssh_key`, but do not specify this configuration when you create an EKS Node Group, port 22 on the worker nodes is opened to the Internet (0.0.0.0/0).
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">ec2Ssh<wbr>Key<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}EC2 Key Pair name that provides access for SSH communication with the worker nodes in the EKS Node Group. If you specify this configuration, but do not specify `source_security_group_ids` when you create an EKS Node Group, port 22 on the worker nodes is opened to the Internet (0.0.0.0/0).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">source<wbr>Security<wbr>Group<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}Set of EC2 Security Group IDs to allow SSH access (port 22) from on the worker nodes. If you specify `ec2_ssh_key`, but do not specify this configuration when you create an EKS Node Group, port 22 on the worker nodes is opened to the Internet (0.0.0.0/0).
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### NodeGroupResource
{{% lang nodejs %}}
> See the   <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#NodeGroupResource">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the   <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/eks?tab=doc#NodeGroupResourceOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the   <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Eks.NodeGroupResource.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Autoscaling<wbr>Groups<span class="property-indicator"></span>
        <span class="property-type"><a href="#nodegroupresourceautoscalinggroup">List&lt;Node<wbr>Group<wbr>Resource<wbr>Autoscaling<wbr>Group<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}List of objects containing information about AutoScaling Groups.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Remote<wbr>Access<wbr>Security<wbr>Group<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Identifier of the remote access EC2 Security Group.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Autoscaling<wbr>Groups<span class="property-indicator"></span>
        <span class="property-type"><a href="#nodegroupresourceautoscalinggroup">[]Node<wbr>Group<wbr>Resource<wbr>Autoscaling<wbr>Group</a></span>
    </dt>
    <dd>{{% md %}}List of objects containing information about AutoScaling Groups.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Remote<wbr>Access<wbr>Security<wbr>Group<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Identifier of the remote access EC2 Security Group.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">autoscaling<wbr>Groups<span class="property-indicator"></span>
        <span class="property-type"><a href="#nodegroupresourceautoscalinggroup">Node<wbr>Group<wbr>Resource<wbr>Autoscaling<wbr>Group[]?</a></span>
    </dt>
    <dd>{{% md %}}List of objects containing information about AutoScaling Groups.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">remote<wbr>Access<wbr>Security<wbr>Group<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Identifier of the remote access EC2 Security Group.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">autoscaling_<wbr>groups<span class="property-indicator"></span>
        <span class="property-type"><a href="#nodegroupresourceautoscalinggroup">List[Node<wbr>Group<wbr>Resource<wbr>Autoscaling<wbr>Group]</a></span>
    </dt>
    <dd>{{% md %}}List of objects containing information about AutoScaling Groups.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">remote<wbr>Access<wbr>Security<wbr>Group<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Identifier of the remote access EC2 Security Group.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### NodeGroupResourceAutoscalingGroup
{{% lang nodejs %}}
> See the   <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#NodeGroupResourceAutoscalingGroup">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the   <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/eks?tab=doc#NodeGroupResourceAutoscalingGroupOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the   <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Eks.NodeGroupResourceAutoscalingGroup.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Name of the AutoScaling Group.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Name of the AutoScaling Group.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Name of the AutoScaling Group.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Name of the AutoScaling Group.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### NodeGroupScalingConfig
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#NodeGroupScalingConfig">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#NodeGroupScalingConfig">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/eks?tab=doc#NodeGroupScalingConfigArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/eks?tab=doc#NodeGroupScalingConfigOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Eks.NodeGroupScalingConfigArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Eks.NodeGroupScalingConfig.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Desired<wbr>Size<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}Desired number of worker nodes.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Max<wbr>Size<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}Maximum number of worker nodes.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Min<wbr>Size<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}Minimum number of worker nodes.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Desired<wbr>Size<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}Desired number of worker nodes.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Max<wbr>Size<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}Maximum number of worker nodes.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Min<wbr>Size<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}Minimum number of worker nodes.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">desired<wbr>Size<span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}Desired number of worker nodes.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">max<wbr>Size<span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}Maximum number of worker nodes.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">min<wbr>Size<span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}Minimum number of worker nodes.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">desired<wbr>Size<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}Desired number of worker nodes.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">max_<wbr>size<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}Maximum number of worker nodes.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">min_<wbr>size<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}Minimum number of worker nodes.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}








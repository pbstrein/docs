
---
title: "AmiFromInstance"
block_external_search_index: true
---

The "AMI from instance" resource allows the creation of an Amazon Machine
Image (AMI) modelled after an existing EBS-backed EC2 instance.

The created AMI will refer to implicitly-created snapshots of the instance's
EBS volumes and mimick its assigned block device configuration at the time
the resource is created.

This resource is best applied to an instance that is stopped when this instance
is created, so that the contents of the created image are predictable. When
applied to an instance that is running, *the instance will be stopped before taking
the snapshots and then started back up again*, resulting in a period of
downtime.

Note that the source instance is inspected only at the initial creation of this
resource. Ongoing updates to the referenced instance will not be propagated into
the generated AMI. Users may taint or otherwise recreate the resource in order
to produce a fresh snapshot.

## Example Usage

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const example = new aws.ec2.AmiFromInstance("example", {
    sourceInstanceId: "i-xxxxxxxx",
});
```

> This content is derived from https://github.com/terraform-providers/terraform-provider-aws/blob/master/website/docs/r/ami_from_instance.html.markdown.



## Create a AmiFromInstance Resource

{{< chooser language "javascript,typescript,python,go,csharp" / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/ec2/#AmiFromInstance">AmiFromInstance</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/ec2/#AmiFromInstanceArgs">AmiFromInstanceArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">AmiFromInstance</span><span class="p">(resource_name, opts=None, </span>description=None<span class="p">, </span>ebs_block_devices=None<span class="p">, </span>ephemeral_block_devices=None<span class="p">, </span>name=None<span class="p">, </span>snapshot_without_reboot=None<span class="p">, </span>source_instance_id=None<span class="p">, </span>tags=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewAmiFromInstance<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ec2?tab=doc#AmiFromInstanceArgs">AmiFromInstanceArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ec2?tab=doc#AmiFromInstance">AmiFromInstance</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ec2.AmiFromInstance.html">AmiFromInstance</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ec2.AmiFromInstanceArgs.html">AmiFromInstanceArgs</a></span> <span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
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
            title="Optional">Description<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A longer, human-readable description for the AMI.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ebs<wbr>Block<wbr>Devices<span class="property-indicator"></span>
        <span class="property-type"><a href="#amifrominstanceebsblockdevice">List&lt;Ami<wbr>From<wbr>Instance<wbr>Ebs<wbr>Block<wbr>Device<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}Nested block describing an EBS block device that should be
attached to created instances. The structure of this block is described below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ephemeral<wbr>Block<wbr>Devices<span class="property-indicator"></span>
        <span class="property-type"><a href="#amifrominstanceephemeralblockdevice">List&lt;Ami<wbr>From<wbr>Instance<wbr>Ephemeral<wbr>Block<wbr>Device<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}Nested block describing an ephemeral block device that
should be attached to created instances. The structure of this block is described below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A region-unique name for the AMI.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Snapshot<wbr>Without<wbr>Reboot<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Boolean that overrides the behavior of stopping
the instance before snapshotting. This is risky since it may cause a snapshot of an
inconsistent filesystem state, but can be used to avoid downtime if the user otherwise
guarantees that no filesystem writes will be underway at the time of snapshot.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Source<wbr>Instance<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The id of the instance to use as the basis of the AMI.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Description<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}A longer, human-readable description for the AMI.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ebs<wbr>Block<wbr>Devices<span class="property-indicator"></span>
        <span class="property-type"><a href="#amifrominstanceebsblockdevice">[]Ami<wbr>From<wbr>Instance<wbr>Ebs<wbr>Block<wbr>Device</a></span>
    </dt>
    <dd>{{% md %}}Nested block describing an EBS block device that should be
attached to created instances. The structure of this block is described below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ephemeral<wbr>Block<wbr>Devices<span class="property-indicator"></span>
        <span class="property-type"><a href="#amifrominstanceephemeralblockdevice">[]Ami<wbr>From<wbr>Instance<wbr>Ephemeral<wbr>Block<wbr>Device</a></span>
    </dt>
    <dd>{{% md %}}Nested block describing an ephemeral block device that
should be attached to created instances. The structure of this block is described below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}A region-unique name for the AMI.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Snapshot<wbr>Without<wbr>Reboot<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Boolean that overrides the behavior of stopping
the instance before snapshotting. This is risky since it may cause a snapshot of an
inconsistent filesystem state, but can be used to avoid downtime if the user otherwise
guarantees that no filesystem writes will be underway at the time of snapshot.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Source<wbr>Instance<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The id of the instance to use as the basis of the AMI.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">description<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A longer, human-readable description for the AMI.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ebs<wbr>Block<wbr>Devices<span class="property-indicator"></span>
        <span class="property-type"><a href="#amifrominstanceebsblockdevice">Ami<wbr>From<wbr>Instance<wbr>Ebs<wbr>Block<wbr>Device[]?</a></span>
    </dt>
    <dd>{{% md %}}Nested block describing an EBS block device that should be
attached to created instances. The structure of this block is described below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ephemeral<wbr>Block<wbr>Devices<span class="property-indicator"></span>
        <span class="property-type"><a href="#amifrominstanceephemeralblockdevice">Ami<wbr>From<wbr>Instance<wbr>Ephemeral<wbr>Block<wbr>Device[]?</a></span>
    </dt>
    <dd>{{% md %}}Nested block describing an ephemeral block device that
should be attached to created instances. The structure of this block is described below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A region-unique name for the AMI.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">snapshot<wbr>Without<wbr>Reboot<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Boolean that overrides the behavior of stopping
the instance before snapshotting. This is risky since it may cause a snapshot of an
inconsistent filesystem state, but can be used to avoid downtime if the user otherwise
guarantees that no filesystem writes will be underway at the time of snapshot.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">source<wbr>Instance<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The id of the instance to use as the basis of the AMI.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">description<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A longer, human-readable description for the AMI.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ebs_<wbr>block_<wbr>devices<span class="property-indicator"></span>
        <span class="property-type"><a href="#amifrominstanceebsblockdevice">List[Ami<wbr>From<wbr>Instance<wbr>Ebs<wbr>Block<wbr>Device]</a></span>
    </dt>
    <dd>{{% md %}}Nested block describing an EBS block device that should be
attached to created instances. The structure of this block is described below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ephemeral_<wbr>block_<wbr>devices<span class="property-indicator"></span>
        <span class="property-type"><a href="#amifrominstanceephemeralblockdevice">List[Ami<wbr>From<wbr>Instance<wbr>Ephemeral<wbr>Block<wbr>Device]</a></span>
    </dt>
    <dd>{{% md %}}Nested block describing an ephemeral block device that
should be attached to created instances. The structure of this block is described below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A region-unique name for the AMI.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">snapshot_<wbr>without_<wbr>reboot<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Boolean that overrides the behavior of stopping
the instance before snapshotting. This is risky since it may cause a snapshot of an
inconsistent filesystem state, but can be used to avoid downtime if the user otherwise
guarantees that no filesystem writes will be underway at the time of snapshot.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">source_<wbr>instance_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The id of the instance to use as the basis of the AMI.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}




## AmiFromInstance Output Properties

The following output properties are available:




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Architecture<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Machine architecture for created instances. Defaults to &#34;x86_64&#34;.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Description<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A longer, human-readable description for the AMI.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Ebs<wbr>Block<wbr>Devices<span class="property-indicator"></span>
        <span class="property-type"><a href="#amifrominstanceebsblockdevice">List&lt;Ami<wbr>From<wbr>Instance<wbr>Ebs<wbr>Block<wbr>Device&gt;</a></span>
    </dt>
    <dd>{{% md %}}Nested block describing an EBS block device that should be
attached to created instances. The structure of this block is described below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Ena<wbr>Support<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Specifies whether enhanced networking with ENA is enabled. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Ephemeral<wbr>Block<wbr>Devices<span class="property-indicator"></span>
        <span class="property-type"><a href="#amifrominstanceephemeralblockdevice">List&lt;Ami<wbr>From<wbr>Instance<wbr>Ephemeral<wbr>Block<wbr>Device&gt;</a></span>
    </dt>
    <dd>{{% md %}}Nested block describing an ephemeral block device that
should be attached to created instances. The structure of this block is described below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Image<wbr>Location<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Path to an S3 object containing an image manifest, e.g. created
by the `ec2-upload-bundle` command in the EC2 command line tools.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Kernel<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The id of the kernel image (AKI) that will be used as the paravirtual
kernel in created instances.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Manage<wbr>Ebs<wbr>Snapshots<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}A region-unique name for the AMI.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Ramdisk<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The id of an initrd image (ARI) that will be used when booting the
created instances.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Root<wbr>Device<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the root device (for example, `/dev/sda1`, or `/dev/xvda`).
{{% /md %}}</dd>

    <dt class="property-"
            title="">Root<wbr>Snapshot<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">Snapshot<wbr>Without<wbr>Reboot<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Boolean that overrides the behavior of stopping
the instance before snapshotting. This is risky since it may cause a snapshot of an
inconsistent filesystem state, but can be used to avoid downtime if the user otherwise
guarantees that no filesystem writes will be underway at the time of snapshot.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Source<wbr>Instance<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The id of the instance to use as the basis of the AMI.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Sriov<wbr>Net<wbr>Support<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}When set to &#34;simple&#34; (the default), enables enhanced networking
for created instances. No other value is supported at this time.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Virtualization<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Keyword to choose what virtualization mode created instances
will use. Can be either &#34;paravirtual&#34; (the default) or &#34;hvm&#34;. The choice of virtualization type
changes the set of further arguments that are required, as described below.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Architecture<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Machine architecture for created instances. Defaults to &#34;x86_64&#34;.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Description<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}A longer, human-readable description for the AMI.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Ebs<wbr>Block<wbr>Devices<span class="property-indicator"></span>
        <span class="property-type"><a href="#amifrominstanceebsblockdevice">[]Ami<wbr>From<wbr>Instance<wbr>Ebs<wbr>Block<wbr>Device</a></span>
    </dt>
    <dd>{{% md %}}Nested block describing an EBS block device that should be
attached to created instances. The structure of this block is described below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Ena<wbr>Support<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Specifies whether enhanced networking with ENA is enabled. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Ephemeral<wbr>Block<wbr>Devices<span class="property-indicator"></span>
        <span class="property-type"><a href="#amifrominstanceephemeralblockdevice">[]Ami<wbr>From<wbr>Instance<wbr>Ephemeral<wbr>Block<wbr>Device</a></span>
    </dt>
    <dd>{{% md %}}Nested block describing an ephemeral block device that
should be attached to created instances. The structure of this block is described below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Image<wbr>Location<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Path to an S3 object containing an image manifest, e.g. created
by the `ec2-upload-bundle` command in the EC2 command line tools.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Kernel<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The id of the kernel image (AKI) that will be used as the paravirtual
kernel in created instances.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Manage<wbr>Ebs<wbr>Snapshots<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}A region-unique name for the AMI.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Ramdisk<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The id of an initrd image (ARI) that will be used when booting the
created instances.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Root<wbr>Device<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the root device (for example, `/dev/sda1`, or `/dev/xvda`).
{{% /md %}}</dd>

    <dt class="property-"
            title="">Root<wbr>Snapshot<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">Snapshot<wbr>Without<wbr>Reboot<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Boolean that overrides the behavior of stopping
the instance before snapshotting. This is risky since it may cause a snapshot of an
inconsistent filesystem state, but can be used to avoid downtime if the user otherwise
guarantees that no filesystem writes will be underway at the time of snapshot.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Source<wbr>Instance<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The id of the instance to use as the basis of the AMI.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Sriov<wbr>Net<wbr>Support<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}When set to &#34;simple&#34; (the default), enables enhanced networking
for created instances. No other value is supported at this time.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Virtualization<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Keyword to choose what virtualization mode created instances
will use. Can be either &#34;paravirtual&#34; (the default) or &#34;hvm&#34;. The choice of virtualization type
changes the set of further arguments that are required, as described below.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">architecture<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Machine architecture for created instances. Defaults to &#34;x86_64&#34;.
{{% /md %}}</dd>

    <dt class="property-"
            title="">description<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A longer, human-readable description for the AMI.
{{% /md %}}</dd>

    <dt class="property-"
            title="">ebs<wbr>Block<wbr>Devices<span class="property-indicator"></span>
        <span class="property-type"><a href="#amifrominstanceebsblockdevice">Ami<wbr>From<wbr>Instance<wbr>Ebs<wbr>Block<wbr>Device[]</a></span>
    </dt>
    <dd>{{% md %}}Nested block describing an EBS block device that should be
attached to created instances. The structure of this block is described below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">ena<wbr>Support<span class="property-indicator"></span>
        <span class="property-type">boolean</span>
    </dt>
    <dd>{{% md %}}Specifies whether enhanced networking with ENA is enabled. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">ephemeral<wbr>Block<wbr>Devices<span class="property-indicator"></span>
        <span class="property-type"><a href="#amifrominstanceephemeralblockdevice">Ami<wbr>From<wbr>Instance<wbr>Ephemeral<wbr>Block<wbr>Device[]</a></span>
    </dt>
    <dd>{{% md %}}Nested block describing an ephemeral block device that
should be attached to created instances. The structure of this block is described below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">image<wbr>Location<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Path to an S3 object containing an image manifest, e.g. created
by the `ec2-upload-bundle` command in the EC2 command line tools.
{{% /md %}}</dd>

    <dt class="property-"
            title="">kernel<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The id of the kernel image (AKI) that will be used as the paravirtual
kernel in created instances.
{{% /md %}}</dd>

    <dt class="property-"
            title="">manage<wbr>Ebs<wbr>Snapshots<span class="property-indicator"></span>
        <span class="property-type">boolean</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}A region-unique name for the AMI.
{{% /md %}}</dd>

    <dt class="property-"
            title="">ramdisk<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The id of an initrd image (ARI) that will be used when booting the
created instances.
{{% /md %}}</dd>

    <dt class="property-"
            title="">root<wbr>Device<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the root device (for example, `/dev/sda1`, or `/dev/xvda`).
{{% /md %}}</dd>

    <dt class="property-"
            title="">root<wbr>Snapshot<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">snapshot<wbr>Without<wbr>Reboot<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Boolean that overrides the behavior of stopping
the instance before snapshotting. This is risky since it may cause a snapshot of an
inconsistent filesystem state, but can be used to avoid downtime if the user otherwise
guarantees that no filesystem writes will be underway at the time of snapshot.
{{% /md %}}</dd>

    <dt class="property-"
            title="">source<wbr>Instance<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The id of the instance to use as the basis of the AMI.
{{% /md %}}</dd>

    <dt class="property-"
            title="">sriov<wbr>Net<wbr>Support<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}When set to &#34;simple&#34; (the default), enables enhanced networking
for created instances. No other value is supported at this time.
{{% /md %}}</dd>

    <dt class="property-"
            title="">tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-"
            title="">virtualization<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Keyword to choose what virtualization mode created instances
will use. Can be either &#34;paravirtual&#34; (the default) or &#34;hvm&#34;. The choice of virtualization type
changes the set of further arguments that are required, as described below.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">architecture<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Machine architecture for created instances. Defaults to &#34;x86_64&#34;.
{{% /md %}}</dd>

    <dt class="property-"
            title="">description<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A longer, human-readable description for the AMI.
{{% /md %}}</dd>

    <dt class="property-"
            title="">ebs_<wbr>block_<wbr>devices<span class="property-indicator"></span>
        <span class="property-type"><a href="#amifrominstanceebsblockdevice">List[Ami<wbr>From<wbr>Instance<wbr>Ebs<wbr>Block<wbr>Device]</a></span>
    </dt>
    <dd>{{% md %}}Nested block describing an EBS block device that should be
attached to created instances. The structure of this block is described below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">ena_<wbr>support<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Specifies whether enhanced networking with ENA is enabled. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">ephemeral_<wbr>block_<wbr>devices<span class="property-indicator"></span>
        <span class="property-type"><a href="#amifrominstanceephemeralblockdevice">List[Ami<wbr>From<wbr>Instance<wbr>Ephemeral<wbr>Block<wbr>Device]</a></span>
    </dt>
    <dd>{{% md %}}Nested block describing an ephemeral block device that
should be attached to created instances. The structure of this block is described below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">image_<wbr>location<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Path to an S3 object containing an image manifest, e.g. created
by the `ec2-upload-bundle` command in the EC2 command line tools.
{{% /md %}}</dd>

    <dt class="property-"
            title="">kernel_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The id of the kernel image (AKI) that will be used as the paravirtual
kernel in created instances.
{{% /md %}}</dd>

    <dt class="property-"
            title="">manage_<wbr>ebs_<wbr>snapshots<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A region-unique name for the AMI.
{{% /md %}}</dd>

    <dt class="property-"
            title="">ramdisk_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The id of an initrd image (ARI) that will be used when booting the
created instances.
{{% /md %}}</dd>

    <dt class="property-"
            title="">root_<wbr>device_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the root device (for example, `/dev/sda1`, or `/dev/xvda`).
{{% /md %}}</dd>

    <dt class="property-"
            title="">root_<wbr>snapshot_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">snapshot_<wbr>without_<wbr>reboot<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Boolean that overrides the behavior of stopping
the instance before snapshotting. This is risky since it may cause a snapshot of an
inconsistent filesystem state, but can be used to avoid downtime if the user otherwise
guarantees that no filesystem writes will be underway at the time of snapshot.
{{% /md %}}</dd>

    <dt class="property-"
            title="">source_<wbr>instance_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The id of the instance to use as the basis of the AMI.
{{% /md %}}</dd>

    <dt class="property-"
            title="">sriov_<wbr>net_<wbr>support<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}When set to &#34;simple&#34; (the default), enables enhanced networking
for created instances. No other value is supported at this time.
{{% /md %}}</dd>

    <dt class="property-"
            title="">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-"
            title="">virtualization_<wbr>type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Keyword to choose what virtualization mode created instances
will use. Can be either &#34;paravirtual&#34; (the default) or &#34;hvm&#34;. The choice of virtualization type
changes the set of further arguments that are required, as described below.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





## Look up an Existing AmiFromInstance Resource

{{< chooser language "javascript,typescript,python,go,csharp  " / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">pulumi.Input&lt;pulumi.ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/ec2/#AmiFromInstanceState">AmiFromInstanceState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/ec2/#AmiFromInstance">AmiFromInstance</a></span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>architecture=None<span class="p">, </span>description=None<span class="p">, </span>ebs_block_devices=None<span class="p">, </span>ena_support=None<span class="p">, </span>ephemeral_block_devices=None<span class="p">, </span>image_location=None<span class="p">, </span>kernel_id=None<span class="p">, </span>manage_ebs_snapshots=None<span class="p">, </span>name=None<span class="p">, </span>ramdisk_id=None<span class="p">, </span>root_device_name=None<span class="p">, </span>root_snapshot_id=None<span class="p">, </span>snapshot_without_reboot=None<span class="p">, </span>source_instance_id=None<span class="p">, </span>sriov_net_support=None<span class="p">, </span>tags=None<span class="p">, </span>virtualization_type=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetAmiFromInstance<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">pulumi.IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ec2?tab=doc#AmiFromInstanceState">AmiFromInstanceState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ec2?tab=doc#AmiFromInstance">AmiFromInstance</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ec2.AmiFromInstance.html">AmiFromInstance</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Pulumi.Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ec2.AmiFromInstanceState.html">AmiFromInstanceState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
{{% /choosable %}}

Get an existing AmiFromInstance resource's state with the given name, ID, and optional extra properties used to qualify the lookup.

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
            title="Optional">Architecture<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Machine architecture for created instances. Defaults to &#34;x86_64&#34;.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Description<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A longer, human-readable description for the AMI.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ebs<wbr>Block<wbr>Devices<span class="property-indicator"></span>
        <span class="property-type"><a href="#amifrominstanceebsblockdevice">List&lt;Ami<wbr>From<wbr>Instance<wbr>Ebs<wbr>Block<wbr>Device<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}Nested block describing an EBS block device that should be
attached to created instances. The structure of this block is described below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ena<wbr>Support<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Specifies whether enhanced networking with ENA is enabled. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ephemeral<wbr>Block<wbr>Devices<span class="property-indicator"></span>
        <span class="property-type"><a href="#amifrominstanceephemeralblockdevice">List&lt;Ami<wbr>From<wbr>Instance<wbr>Ephemeral<wbr>Block<wbr>Device<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}Nested block describing an ephemeral block device that
should be attached to created instances. The structure of this block is described below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Image<wbr>Location<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Path to an S3 object containing an image manifest, e.g. created
by the `ec2-upload-bundle` command in the EC2 command line tools.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Kernel<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The id of the kernel image (AKI) that will be used as the paravirtual
kernel in created instances.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Manage<wbr>Ebs<wbr>Snapshots<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A region-unique name for the AMI.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ramdisk<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The id of an initrd image (ARI) that will be used when booting the
created instances.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Root<wbr>Device<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the root device (for example, `/dev/sda1`, or `/dev/xvda`).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Root<wbr>Snapshot<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Snapshot<wbr>Without<wbr>Reboot<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Boolean that overrides the behavior of stopping
the instance before snapshotting. This is risky since it may cause a snapshot of an
inconsistent filesystem state, but can be used to avoid downtime if the user otherwise
guarantees that no filesystem writes will be underway at the time of snapshot.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Source<wbr>Instance<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The id of the instance to use as the basis of the AMI.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Sriov<wbr>Net<wbr>Support<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}When set to &#34;simple&#34; (the default), enables enhanced networking
for created instances. No other value is supported at this time.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Virtualization<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Keyword to choose what virtualization mode created instances
will use. Can be either &#34;paravirtual&#34; (the default) or &#34;hvm&#34;. The choice of virtualization type
changes the set of further arguments that are required, as described below.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Architecture<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Machine architecture for created instances. Defaults to &#34;x86_64&#34;.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Description<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}A longer, human-readable description for the AMI.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ebs<wbr>Block<wbr>Devices<span class="property-indicator"></span>
        <span class="property-type"><a href="#amifrominstanceebsblockdevice">[]Ami<wbr>From<wbr>Instance<wbr>Ebs<wbr>Block<wbr>Device</a></span>
    </dt>
    <dd>{{% md %}}Nested block describing an EBS block device that should be
attached to created instances. The structure of this block is described below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ena<wbr>Support<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Specifies whether enhanced networking with ENA is enabled. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ephemeral<wbr>Block<wbr>Devices<span class="property-indicator"></span>
        <span class="property-type"><a href="#amifrominstanceephemeralblockdevice">[]Ami<wbr>From<wbr>Instance<wbr>Ephemeral<wbr>Block<wbr>Device</a></span>
    </dt>
    <dd>{{% md %}}Nested block describing an ephemeral block device that
should be attached to created instances. The structure of this block is described below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Image<wbr>Location<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Path to an S3 object containing an image manifest, e.g. created
by the `ec2-upload-bundle` command in the EC2 command line tools.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Kernel<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The id of the kernel image (AKI) that will be used as the paravirtual
kernel in created instances.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Manage<wbr>Ebs<wbr>Snapshots<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}A region-unique name for the AMI.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ramdisk<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The id of an initrd image (ARI) that will be used when booting the
created instances.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Root<wbr>Device<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name of the root device (for example, `/dev/sda1`, or `/dev/xvda`).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Root<wbr>Snapshot<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Snapshot<wbr>Without<wbr>Reboot<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Boolean that overrides the behavior of stopping
the instance before snapshotting. This is risky since it may cause a snapshot of an
inconsistent filesystem state, but can be used to avoid downtime if the user otherwise
guarantees that no filesystem writes will be underway at the time of snapshot.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Source<wbr>Instance<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The id of the instance to use as the basis of the AMI.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Sriov<wbr>Net<wbr>Support<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}When set to &#34;simple&#34; (the default), enables enhanced networking
for created instances. No other value is supported at this time.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Virtualization<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Keyword to choose what virtualization mode created instances
will use. Can be either &#34;paravirtual&#34; (the default) or &#34;hvm&#34;. The choice of virtualization type
changes the set of further arguments that are required, as described below.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">architecture<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Machine architecture for created instances. Defaults to &#34;x86_64&#34;.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">description<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A longer, human-readable description for the AMI.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ebs<wbr>Block<wbr>Devices<span class="property-indicator"></span>
        <span class="property-type"><a href="#amifrominstanceebsblockdevice">Ami<wbr>From<wbr>Instance<wbr>Ebs<wbr>Block<wbr>Device[]?</a></span>
    </dt>
    <dd>{{% md %}}Nested block describing an EBS block device that should be
attached to created instances. The structure of this block is described below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ena<wbr>Support<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Specifies whether enhanced networking with ENA is enabled. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ephemeral<wbr>Block<wbr>Devices<span class="property-indicator"></span>
        <span class="property-type"><a href="#amifrominstanceephemeralblockdevice">Ami<wbr>From<wbr>Instance<wbr>Ephemeral<wbr>Block<wbr>Device[]?</a></span>
    </dt>
    <dd>{{% md %}}Nested block describing an ephemeral block device that
should be attached to created instances. The structure of this block is described below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">image<wbr>Location<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Path to an S3 object containing an image manifest, e.g. created
by the `ec2-upload-bundle` command in the EC2 command line tools.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">kernel<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The id of the kernel image (AKI) that will be used as the paravirtual
kernel in created instances.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">manage<wbr>Ebs<wbr>Snapshots<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A region-unique name for the AMI.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ramdisk<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The id of an initrd image (ARI) that will be used when booting the
created instances.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">root<wbr>Device<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the root device (for example, `/dev/sda1`, or `/dev/xvda`).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">root<wbr>Snapshot<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">snapshot<wbr>Without<wbr>Reboot<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Boolean that overrides the behavior of stopping
the instance before snapshotting. This is risky since it may cause a snapshot of an
inconsistent filesystem state, but can be used to avoid downtime if the user otherwise
guarantees that no filesystem writes will be underway at the time of snapshot.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">source<wbr>Instance<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The id of the instance to use as the basis of the AMI.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">sriov<wbr>Net<wbr>Support<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}When set to &#34;simple&#34; (the default), enables enhanced networking
for created instances. No other value is supported at this time.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">virtualization<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Keyword to choose what virtualization mode created instances
will use. Can be either &#34;paravirtual&#34; (the default) or &#34;hvm&#34;. The choice of virtualization type
changes the set of further arguments that are required, as described below.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">architecture<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Machine architecture for created instances. Defaults to &#34;x86_64&#34;.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">description<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A longer, human-readable description for the AMI.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ebs_<wbr>block_<wbr>devices<span class="property-indicator"></span>
        <span class="property-type"><a href="#amifrominstanceebsblockdevice">List[Ami<wbr>From<wbr>Instance<wbr>Ebs<wbr>Block<wbr>Device]</a></span>
    </dt>
    <dd>{{% md %}}Nested block describing an EBS block device that should be
attached to created instances. The structure of this block is described below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ena_<wbr>support<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Specifies whether enhanced networking with ENA is enabled. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ephemeral_<wbr>block_<wbr>devices<span class="property-indicator"></span>
        <span class="property-type"><a href="#amifrominstanceephemeralblockdevice">List[Ami<wbr>From<wbr>Instance<wbr>Ephemeral<wbr>Block<wbr>Device]</a></span>
    </dt>
    <dd>{{% md %}}Nested block describing an ephemeral block device that
should be attached to created instances. The structure of this block is described below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">image_<wbr>location<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Path to an S3 object containing an image manifest, e.g. created
by the `ec2-upload-bundle` command in the EC2 command line tools.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">kernel_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The id of the kernel image (AKI) that will be used as the paravirtual
kernel in created instances.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">manage_<wbr>ebs_<wbr>snapshots<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A region-unique name for the AMI.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ramdisk_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The id of an initrd image (ARI) that will be used when booting the
created instances.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">root_<wbr>device_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the root device (for example, `/dev/sda1`, or `/dev/xvda`).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">root_<wbr>snapshot_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">snapshot_<wbr>without_<wbr>reboot<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Boolean that overrides the behavior of stopping
the instance before snapshotting. This is risky since it may cause a snapshot of an
inconsistent filesystem state, but can be used to avoid downtime if the user otherwise
guarantees that no filesystem writes will be underway at the time of snapshot.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">source_<wbr>instance_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The id of the instance to use as the basis of the AMI.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">sriov_<wbr>net_<wbr>support<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}When set to &#34;simple&#34; (the default), enables enhanced networking
for created instances. No other value is supported at this time.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">virtualization_<wbr>type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Keyword to choose what virtualization mode created instances
will use. Can be either &#34;paravirtual&#34; (the default) or &#34;hvm&#34;. The choice of virtualization type
changes the set of further arguments that are required, as described below.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}







## Supporting Types

#### AmiFromInstanceEbsBlockDevice
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#AmiFromInstanceEbsBlockDevice">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#AmiFromInstanceEbsBlockDevice">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ec2?tab=doc#AmiFromInstanceEbsBlockDeviceArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ec2?tab=doc#AmiFromInstanceEbsBlockDeviceOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ec2.AmiFromInstanceEbsBlockDeviceArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ec2.AmiFromInstanceEbsBlockDevice.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Delete<wbr>On<wbr>Termination<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Device<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Encrypted<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Iops<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Snapshot<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Volume<wbr>Size<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Volume<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Delete<wbr>On<wbr>Termination<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Device<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Encrypted<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Iops<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Snapshot<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Volume<wbr>Size<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Volume<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">delete<wbr>On<wbr>Termination<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">device<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">encrypted<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">iops<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">snapshot<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">volume<wbr>Size<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">volume<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">delete<wbr>On<wbr>Termination<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">device_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">encrypted<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">iops<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">snapshot_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">volume_<wbr>size<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">volume<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### AmiFromInstanceEphemeralBlockDevice
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#AmiFromInstanceEphemeralBlockDevice">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#AmiFromInstanceEphemeralBlockDevice">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ec2?tab=doc#AmiFromInstanceEphemeralBlockDeviceArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ec2?tab=doc#AmiFromInstanceEphemeralBlockDeviceOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ec2.AmiFromInstanceEphemeralBlockDeviceArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ec2.AmiFromInstanceEphemeralBlockDevice.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Device<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Virtual<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Device<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Virtual<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">device<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">virtual<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">device_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">virtual<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}









---
title: "Instance"
block_external_search_index: true
---

Provides an OpsWorks instance resource.

## Example Usage

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const my_instance = new aws.opsworks.Instance("my-instance", {
    instanceType: "t2.micro",
    layerIds: [aws_opsworks_custom_layer_my_layer.id],
    os: "Amazon Linux 2015.09",
    stackId: aws_opsworks_stack_main.id,
    state: "stopped",
});
```

## Block devices

Each of the `*_block_device` attributes controls a portion of the AWS
Instance's "Block Device Mapping". It's a good idea to familiarize yourself with [AWS's Block Device
Mapping docs](http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/block-device-mapping-concepts.html)
to understand the implications of using these attributes.

The `root_block_device` mapping supports the following:

* `volume_type` - (Optional) The type of volume. Can be `"standard"`, `"gp2"`,
  or `"io1"`. (Default: `"standard"`).
* `volume_size` - (Optional) The size of the volume in gigabytes.
* `iops` - (Optional) The amount of provisioned
  [IOPS](http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ebs-io-characteristics.html).
  This must be set with a `volume_type` of `"io1"`.
* `delete_on_termination` - (Optional) Whether the volume should be destroyed
  on instance termination (Default: `true`).

Modifying any of the `root_block_device` settings requires resource
replacement.

Each `ebs_block_device` supports the following:

* `device_name` - The name of the device to mount.
* `snapshot_id` - (Optional) The Snapshot ID to mount.
* `volume_type` - (Optional) The type of volume. Can be `"standard"`, `"gp2"`,
  or `"io1"`. (Default: `"standard"`).
* `volume_size` - (Optional) The size of the volume in gigabytes.
* `iops` - (Optional) The amount of provisioned
  [IOPS](http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ebs-io-characteristics.html).
  This must be set with a `volume_type` of `"io1"`.
* `delete_on_termination` - (Optional) Whether the volume should be destroyed
  on instance termination (Default: `true`).

Modifying any `ebs_block_device` currently requires resource replacement.

Each `ephemeral_block_device` supports the following:

* `device_name` - The name of the block device to mount on the instance.
* `virtual_name` - The [Instance Store Device
  Name](http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/InstanceStorage.html#InstanceStoreDeviceNames)
  (e.g. `"ephemeral0"`)

Each AWS Instance type has a different set of Instance Store block devices
available for attachment. AWS [publishes a
list](http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/InstanceStorage.html#StorageOnInstanceTypes)
of which ephemeral devices are available on each type. The devices are always
identified by the `virtual_name` in the format `"ephemeral{0..N}"`.

> **NOTE:** Currently, changes to `*_block_device` configuration of _existing_
resources cannot be automatically detected by this provider. After making updates
to block device configuration, resource recreation can be manually triggered by
using the [`taint` command](https://www.terraform.io/docs/commands/taint.html).

> This content is derived from https://github.com/terraform-providers/terraform-provider-aws/blob/master/website/docs/r/opsworks_instance.html.markdown.



## Create a Instance Resource

{{< chooser language "javascript,typescript,python,go,csharp" / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/opsworks/#Instance">Instance</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/opsworks/#InstanceArgs">InstanceArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">Instance</span><span class="p">(resource_name, opts=None, </span>agent_version=None<span class="p">, </span>ami_id=None<span class="p">, </span>architecture=None<span class="p">, </span>auto_scaling_type=None<span class="p">, </span>availability_zone=None<span class="p">, </span>created_at=None<span class="p">, </span>delete_ebs=None<span class="p">, </span>delete_eip=None<span class="p">, </span>ebs_block_devices=None<span class="p">, </span>ebs_optimized=None<span class="p">, </span>ecs_cluster_arn=None<span class="p">, </span>elastic_ip=None<span class="p">, </span>ephemeral_block_devices=None<span class="p">, </span>hostname=None<span class="p">, </span>infrastructure_class=None<span class="p">, </span>install_updates_on_boot=None<span class="p">, </span>instance_profile_arn=None<span class="p">, </span>instance_type=None<span class="p">, </span>last_service_error_id=None<span class="p">, </span>layer_ids=None<span class="p">, </span>os=None<span class="p">, </span>platform=None<span class="p">, </span>private_dns=None<span class="p">, </span>private_ip=None<span class="p">, </span>public_dns=None<span class="p">, </span>public_ip=None<span class="p">, </span>registered_by=None<span class="p">, </span>reported_agent_version=None<span class="p">, </span>reported_os_family=None<span class="p">, </span>reported_os_name=None<span class="p">, </span>reported_os_version=None<span class="p">, </span>root_block_devices=None<span class="p">, </span>root_device_type=None<span class="p">, </span>root_device_volume_id=None<span class="p">, </span>security_group_ids=None<span class="p">, </span>ssh_host_dsa_key_fingerprint=None<span class="p">, </span>ssh_host_rsa_key_fingerprint=None<span class="p">, </span>ssh_key_name=None<span class="p">, </span>stack_id=None<span class="p">, </span>state=None<span class="p">, </span>status=None<span class="p">, </span>subnet_id=None<span class="p">, </span>tenancy=None<span class="p">, </span>virtualization_type=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewInstance<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/opsworks?tab=doc#InstanceArgs">InstanceArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/opsworks?tab=doc#Instance">Instance</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Opsworks.Instance.html">Instance</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Opsworks.InstanceArgs.html">InstanceArgs</a></span> <span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
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
            title="Optional">Agent<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The AWS OpsWorks agent to install.  Defaults to `&#34;INHERIT&#34;`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ami<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The AMI to use for the instance.  If an AMI is specified, `os` must be `&#34;Custom&#34;`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Architecture<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Machine architecture for created instances.  Can be either `&#34;x86_64&#34;` (the default) or `&#34;i386&#34;`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Auto<wbr>Scaling<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Creates load-based or time-based instances.  If set, can be either: `&#34;load&#34;` or `&#34;timer&#34;`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Availability<wbr>Zone<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Name of the availability zone where instances will be created
by default.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Created<wbr>At<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Delete<wbr>Ebs<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Delete<wbr>Eip<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ebs<wbr>Block<wbr>Devices<span class="property-indicator"></span>
        <span class="property-type"><a href="#instanceebsblockdevice">List&lt;Instance<wbr>Ebs<wbr>Block<wbr>Device<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}Additional EBS block devices to attach to the
instance.  See Block Devices below for details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ebs<wbr>Optimized<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}If true, the launched EC2 instance will be EBS-optimized.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ecs<wbr>Cluster<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Elastic<wbr>Ip<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ephemeral<wbr>Block<wbr>Devices<span class="property-indicator"></span>
        <span class="property-type"><a href="#instanceephemeralblockdevice">List&lt;Instance<wbr>Ephemeral<wbr>Block<wbr>Device<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}Customize Ephemeral (also known as
&#34;Instance Store&#34;) volumes on the instance. See Block Devices below for details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Hostname<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The instance&#39;s host name.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Infrastructure<wbr>Class<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Install<wbr>Updates<wbr>On<wbr>Boot<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Controls where to install OS and package updates when the instance boots.  Defaults to `true`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Instance<wbr>Profile<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Instance<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The type of instance to start
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Last<wbr>Service<wbr>Error<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Layer<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">List<string></span>
    </dt>
    <dd>{{% md %}}The ids of the layers the instance will belong to.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Os<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Name of operating system that will be installed.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Platform<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Private<wbr>Dns<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The private DNS name assigned to the instance. Can only be
used inside the Amazon EC2, and only available if you&#39;ve enabled DNS hostnames
for your VPC
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Private<wbr>Ip<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The private IP address assigned to the instance
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Public<wbr>Dns<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The public DNS name assigned to the instance. For EC2-VPC, this
is only available if you&#39;ve enabled DNS hostnames for your VPC
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Public<wbr>Ip<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The public IP address assigned to the instance, if applicable.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Registered<wbr>By<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Reported<wbr>Agent<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Reported<wbr>Os<wbr>Family<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Reported<wbr>Os<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Reported<wbr>Os<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Root<wbr>Block<wbr>Devices<span class="property-indicator"></span>
        <span class="property-type"><a href="#instancerootblockdevice">List&lt;Instance<wbr>Root<wbr>Block<wbr>Device<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}Customize details about the root block
device of the instance. See Block Devices below for details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Root<wbr>Device<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Name of the type of root device instances will have by default.  Can be either `&#34;ebs&#34;` or `&#34;instance-store&#34;`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Root<wbr>Device<wbr>Volume<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Security<wbr>Group<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}The associated security groups.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ssh<wbr>Host<wbr>Dsa<wbr>Key<wbr>Fingerprint<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ssh<wbr>Host<wbr>Rsa<wbr>Key<wbr>Fingerprint<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ssh<wbr>Key<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Name of the SSH keypair that instances will have by default.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Stack<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The id of the stack the instance will belong to.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">State<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The desired state of the instance.  Can be either `&#34;running&#34;` or `&#34;stopped&#34;`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Status<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Subnet<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Subnet ID to attach to
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tenancy<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Instance tenancy to use. Can be one of `&#34;default&#34;`, `&#34;dedicated&#34;` or `&#34;host&#34;`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Virtualization<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Keyword to choose what virtualization mode created instances
will use. Can be either `&#34;paravirtual&#34;` or `&#34;hvm&#34;`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Agent<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The AWS OpsWorks agent to install.  Defaults to `&#34;INHERIT&#34;`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ami<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The AMI to use for the instance.  If an AMI is specified, `os` must be `&#34;Custom&#34;`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Architecture<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Machine architecture for created instances.  Can be either `&#34;x86_64&#34;` (the default) or `&#34;i386&#34;`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Auto<wbr>Scaling<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Creates load-based or time-based instances.  If set, can be either: `&#34;load&#34;` or `&#34;timer&#34;`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Availability<wbr>Zone<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Name of the availability zone where instances will be created
by default.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Created<wbr>At<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Delete<wbr>Ebs<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Delete<wbr>Eip<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ebs<wbr>Block<wbr>Devices<span class="property-indicator"></span>
        <span class="property-type"><a href="#instanceebsblockdevice">[]Instance<wbr>Ebs<wbr>Block<wbr>Device</a></span>
    </dt>
    <dd>{{% md %}}Additional EBS block devices to attach to the
instance.  See Block Devices below for details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ebs<wbr>Optimized<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}If true, the launched EC2 instance will be EBS-optimized.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ecs<wbr>Cluster<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Elastic<wbr>Ip<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ephemeral<wbr>Block<wbr>Devices<span class="property-indicator"></span>
        <span class="property-type"><a href="#instanceephemeralblockdevice">[]Instance<wbr>Ephemeral<wbr>Block<wbr>Device</a></span>
    </dt>
    <dd>{{% md %}}Customize Ephemeral (also known as
&#34;Instance Store&#34;) volumes on the instance. See Block Devices below for details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Hostname<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The instance&#39;s host name.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Infrastructure<wbr>Class<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Install<wbr>Updates<wbr>On<wbr>Boot<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Controls where to install OS and package updates when the instance boots.  Defaults to `true`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Instance<wbr>Profile<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Instance<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The type of instance to start
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Last<wbr>Service<wbr>Error<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Layer<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}The ids of the layers the instance will belong to.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Os<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Name of operating system that will be installed.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Platform<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Private<wbr>Dns<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The private DNS name assigned to the instance. Can only be
used inside the Amazon EC2, and only available if you&#39;ve enabled DNS hostnames
for your VPC
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Private<wbr>Ip<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The private IP address assigned to the instance
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Public<wbr>Dns<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The public DNS name assigned to the instance. For EC2-VPC, this
is only available if you&#39;ve enabled DNS hostnames for your VPC
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Public<wbr>Ip<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The public IP address assigned to the instance, if applicable.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Registered<wbr>By<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Reported<wbr>Agent<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Reported<wbr>Os<wbr>Family<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Reported<wbr>Os<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Reported<wbr>Os<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Root<wbr>Block<wbr>Devices<span class="property-indicator"></span>
        <span class="property-type"><a href="#instancerootblockdevice">[]Instance<wbr>Root<wbr>Block<wbr>Device</a></span>
    </dt>
    <dd>{{% md %}}Customize details about the root block
device of the instance. See Block Devices below for details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Root<wbr>Device<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Name of the type of root device instances will have by default.  Can be either `&#34;ebs&#34;` or `&#34;instance-store&#34;`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Root<wbr>Device<wbr>Volume<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Security<wbr>Group<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}The associated security groups.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ssh<wbr>Host<wbr>Dsa<wbr>Key<wbr>Fingerprint<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ssh<wbr>Host<wbr>Rsa<wbr>Key<wbr>Fingerprint<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ssh<wbr>Key<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Name of the SSH keypair that instances will have by default.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Stack<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The id of the stack the instance will belong to.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">State<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The desired state of the instance.  Can be either `&#34;running&#34;` or `&#34;stopped&#34;`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Status<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Subnet<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Subnet ID to attach to
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tenancy<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Instance tenancy to use. Can be one of `&#34;default&#34;`, `&#34;dedicated&#34;` or `&#34;host&#34;`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Virtualization<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Keyword to choose what virtualization mode created instances
will use. Can be either `&#34;paravirtual&#34;` or `&#34;hvm&#34;`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">agent<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The AWS OpsWorks agent to install.  Defaults to `&#34;INHERIT&#34;`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ami<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The AMI to use for the instance.  If an AMI is specified, `os` must be `&#34;Custom&#34;`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">architecture<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Machine architecture for created instances.  Can be either `&#34;x86_64&#34;` (the default) or `&#34;i386&#34;`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">auto<wbr>Scaling<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Creates load-based or time-based instances.  If set, can be either: `&#34;load&#34;` or `&#34;timer&#34;`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">availability<wbr>Zone<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Name of the availability zone where instances will be created
by default.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">created<wbr>At<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">delete<wbr>Ebs<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">delete<wbr>Eip<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ebs<wbr>Block<wbr>Devices<span class="property-indicator"></span>
        <span class="property-type"><a href="#instanceebsblockdevice">Instance<wbr>Ebs<wbr>Block<wbr>Device[]?</a></span>
    </dt>
    <dd>{{% md %}}Additional EBS block devices to attach to the
instance.  See Block Devices below for details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ebs<wbr>Optimized<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}If true, the launched EC2 instance will be EBS-optimized.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ecs<wbr>Cluster<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">elastic<wbr>Ip<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ephemeral<wbr>Block<wbr>Devices<span class="property-indicator"></span>
        <span class="property-type"><a href="#instanceephemeralblockdevice">Instance<wbr>Ephemeral<wbr>Block<wbr>Device[]?</a></span>
    </dt>
    <dd>{{% md %}}Customize Ephemeral (also known as
&#34;Instance Store&#34;) volumes on the instance. See Block Devices below for details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">hostname<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The instance&#39;s host name.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">infrastructure<wbr>Class<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">install<wbr>Updates<wbr>On<wbr>Boot<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Controls where to install OS and package updates when the instance boots.  Defaults to `true`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">instance<wbr>Profile<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">instance<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The type of instance to start
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">last<wbr>Service<wbr>Error<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">layer<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">string[]</span>
    </dt>
    <dd>{{% md %}}The ids of the layers the instance will belong to.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">os<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Name of operating system that will be installed.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">platform<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">private<wbr>Dns<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The private DNS name assigned to the instance. Can only be
used inside the Amazon EC2, and only available if you&#39;ve enabled DNS hostnames
for your VPC
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">private<wbr>Ip<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The private IP address assigned to the instance
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">public<wbr>Dns<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The public DNS name assigned to the instance. For EC2-VPC, this
is only available if you&#39;ve enabled DNS hostnames for your VPC
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">public<wbr>Ip<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The public IP address assigned to the instance, if applicable.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">registered<wbr>By<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">reported<wbr>Agent<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">reported<wbr>Os<wbr>Family<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">reported<wbr>Os<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">reported<wbr>Os<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">root<wbr>Block<wbr>Devices<span class="property-indicator"></span>
        <span class="property-type"><a href="#instancerootblockdevice">Instance<wbr>Root<wbr>Block<wbr>Device[]?</a></span>
    </dt>
    <dd>{{% md %}}Customize details about the root block
device of the instance. See Block Devices below for details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">root<wbr>Device<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Name of the type of root device instances will have by default.  Can be either `&#34;ebs&#34;` or `&#34;instance-store&#34;`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">root<wbr>Device<wbr>Volume<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">security<wbr>Group<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}The associated security groups.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ssh<wbr>Host<wbr>Dsa<wbr>Key<wbr>Fingerprint<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ssh<wbr>Host<wbr>Rsa<wbr>Key<wbr>Fingerprint<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ssh<wbr>Key<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Name of the SSH keypair that instances will have by default.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">stack<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The id of the stack the instance will belong to.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">state<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The desired state of the instance.  Can be either `&#34;running&#34;` or `&#34;stopped&#34;`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">status<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">subnet<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Subnet ID to attach to
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tenancy<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Instance tenancy to use. Can be one of `&#34;default&#34;`, `&#34;dedicated&#34;` or `&#34;host&#34;`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">virtualization<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Keyword to choose what virtualization mode created instances
will use. Can be either `&#34;paravirtual&#34;` or `&#34;hvm&#34;`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">agent_<wbr>version<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The AWS OpsWorks agent to install.  Defaults to `&#34;INHERIT&#34;`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ami_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The AMI to use for the instance.  If an AMI is specified, `os` must be `&#34;Custom&#34;`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">architecture<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Machine architecture for created instances.  Can be either `&#34;x86_64&#34;` (the default) or `&#34;i386&#34;`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">auto_<wbr>scaling_<wbr>type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Creates load-based or time-based instances.  If set, can be either: `&#34;load&#34;` or `&#34;timer&#34;`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">availability_<wbr>zone<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Name of the availability zone where instances will be created
by default.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">created_<wbr>at<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">delete_<wbr>ebs<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">delete_<wbr>eip<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ebs_<wbr>block_<wbr>devices<span class="property-indicator"></span>
        <span class="property-type"><a href="#instanceebsblockdevice">List[Instance<wbr>Ebs<wbr>Block<wbr>Device]</a></span>
    </dt>
    <dd>{{% md %}}Additional EBS block devices to attach to the
instance.  See Block Devices below for details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ebs_<wbr>optimized<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}If true, the launched EC2 instance will be EBS-optimized.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ecs_<wbr>cluster_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">elastic_<wbr>ip<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ephemeral_<wbr>block_<wbr>devices<span class="property-indicator"></span>
        <span class="property-type"><a href="#instanceephemeralblockdevice">List[Instance<wbr>Ephemeral<wbr>Block<wbr>Device]</a></span>
    </dt>
    <dd>{{% md %}}Customize Ephemeral (also known as
&#34;Instance Store&#34;) volumes on the instance. See Block Devices below for details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">hostname<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The instance&#39;s host name.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">infrastructure_<wbr>class<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">install_<wbr>updates_<wbr>on_<wbr>boot<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Controls where to install OS and package updates when the instance boots.  Defaults to `true`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">instance_<wbr>profile_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">instance_<wbr>type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The type of instance to start
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">last_<wbr>service_<wbr>error_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">layer_<wbr>ids<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}The ids of the layers the instance will belong to.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">os<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Name of operating system that will be installed.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">platform<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">private_<wbr>dns<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The private DNS name assigned to the instance. Can only be
used inside the Amazon EC2, and only available if you&#39;ve enabled DNS hostnames
for your VPC
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">private_<wbr>ip<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The private IP address assigned to the instance
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">public_<wbr>dns<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The public DNS name assigned to the instance. For EC2-VPC, this
is only available if you&#39;ve enabled DNS hostnames for your VPC
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">public_<wbr>ip<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The public IP address assigned to the instance, if applicable.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">registered_<wbr>by<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">reported_<wbr>agent_<wbr>version<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">reported_<wbr>os_<wbr>family<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">reported_<wbr>os_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">reported_<wbr>os_<wbr>version<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">root_<wbr>block_<wbr>devices<span class="property-indicator"></span>
        <span class="property-type"><a href="#instancerootblockdevice">List[Instance<wbr>Root<wbr>Block<wbr>Device]</a></span>
    </dt>
    <dd>{{% md %}}Customize details about the root block
device of the instance. See Block Devices below for details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">root_<wbr>device_<wbr>type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Name of the type of root device instances will have by default.  Can be either `&#34;ebs&#34;` or `&#34;instance-store&#34;`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">root_<wbr>device_<wbr>volume_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">security_<wbr>group_<wbr>ids<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}The associated security groups.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ssh_<wbr>host_<wbr>dsa_<wbr>key_<wbr>fingerprint<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ssh_<wbr>host_<wbr>rsa_<wbr>key_<wbr>fingerprint<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ssh_<wbr>key_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Name of the SSH keypair that instances will have by default.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">stack_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The id of the stack the instance will belong to.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">state<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The desired state of the instance.  Can be either `&#34;running&#34;` or `&#34;stopped&#34;`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">status<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">subnet_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Subnet ID to attach to
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tenancy<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Instance tenancy to use. Can be one of `&#34;default&#34;`, `&#34;dedicated&#34;` or `&#34;host&#34;`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">virtualization_<wbr>type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Keyword to choose what virtualization mode created instances
will use. Can be either `&#34;paravirtual&#34;` or `&#34;hvm&#34;`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}




## Instance Output Properties

The following output properties are available:




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Agent<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The AWS OpsWorks agent to install.  Defaults to `&#34;INHERIT&#34;`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Ami<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The AMI to use for the instance.  If an AMI is specified, `os` must be `&#34;Custom&#34;`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Architecture<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Machine architecture for created instances.  Can be either `&#34;x86_64&#34;` (the default) or `&#34;i386&#34;`
{{% /md %}}</dd>

    <dt class="property-"
            title="">Auto<wbr>Scaling<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Creates load-based or time-based instances.  If set, can be either: `&#34;load&#34;` or `&#34;timer&#34;`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Availability<wbr>Zone<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Name of the availability zone where instances will be created
by default.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Created<wbr>At<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">Delete<wbr>Ebs<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">Delete<wbr>Eip<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">Ebs<wbr>Block<wbr>Devices<span class="property-indicator"></span>
        <span class="property-type"><a href="#instanceebsblockdevice">List&lt;Instance<wbr>Ebs<wbr>Block<wbr>Device&gt;</a></span>
    </dt>
    <dd>{{% md %}}Additional EBS block devices to attach to the
instance.  See Block Devices below for details.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Ebs<wbr>Optimized<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}If true, the launched EC2 instance will be EBS-optimized.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Ec2Instance<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}EC2 instance ID
{{% /md %}}</dd>

    <dt class="property-"
            title="">Ecs<wbr>Cluster<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">Elastic<wbr>Ip<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">Ephemeral<wbr>Block<wbr>Devices<span class="property-indicator"></span>
        <span class="property-type"><a href="#instanceephemeralblockdevice">List&lt;Instance<wbr>Ephemeral<wbr>Block<wbr>Device&gt;</a></span>
    </dt>
    <dd>{{% md %}}Customize Ephemeral (also known as
&#34;Instance Store&#34;) volumes on the instance. See Block Devices below for details.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Hostname<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The instance&#39;s host name.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Infrastructure<wbr>Class<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">Install<wbr>Updates<wbr>On<wbr>Boot<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Controls where to install OS and package updates when the instance boots.  Defaults to `true`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Instance<wbr>Profile<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">Instance<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The type of instance to start
{{% /md %}}</dd>

    <dt class="property-"
            title="">Last<wbr>Service<wbr>Error<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">Layer<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">List<string></span>
    </dt>
    <dd>{{% md %}}The ids of the layers the instance will belong to.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Os<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Name of operating system that will be installed.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Platform<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">Private<wbr>Dns<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The private DNS name assigned to the instance. Can only be
used inside the Amazon EC2, and only available if you&#39;ve enabled DNS hostnames
for your VPC
{{% /md %}}</dd>

    <dt class="property-"
            title="">Private<wbr>Ip<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The private IP address assigned to the instance
{{% /md %}}</dd>

    <dt class="property-"
            title="">Public<wbr>Dns<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The public DNS name assigned to the instance. For EC2-VPC, this
is only available if you&#39;ve enabled DNS hostnames for your VPC
{{% /md %}}</dd>

    <dt class="property-"
            title="">Public<wbr>Ip<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The public IP address assigned to the instance, if applicable.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Registered<wbr>By<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">Reported<wbr>Agent<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">Reported<wbr>Os<wbr>Family<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">Reported<wbr>Os<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">Reported<wbr>Os<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">Root<wbr>Block<wbr>Devices<span class="property-indicator"></span>
        <span class="property-type"><a href="#instancerootblockdevice">List&lt;Instance<wbr>Root<wbr>Block<wbr>Device&gt;</a></span>
    </dt>
    <dd>{{% md %}}Customize details about the root block
device of the instance. See Block Devices below for details.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Root<wbr>Device<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Name of the type of root device instances will have by default.  Can be either `&#34;ebs&#34;` or `&#34;instance-store&#34;`
{{% /md %}}</dd>

    <dt class="property-"
            title="">Root<wbr>Device<wbr>Volume<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">Security<wbr>Group<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">List<string></span>
    </dt>
    <dd>{{% md %}}The associated security groups.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Ssh<wbr>Host<wbr>Dsa<wbr>Key<wbr>Fingerprint<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">Ssh<wbr>Host<wbr>Rsa<wbr>Key<wbr>Fingerprint<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">Ssh<wbr>Key<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Name of the SSH keypair that instances will have by default.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Stack<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The id of the stack the instance will belong to.
{{% /md %}}</dd>

    <dt class="property-"
            title="">State<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The desired state of the instance.  Can be either `&#34;running&#34;` or `&#34;stopped&#34;`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Status<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">Subnet<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Subnet ID to attach to
{{% /md %}}</dd>

    <dt class="property-"
            title="">Tenancy<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Instance tenancy to use. Can be one of `&#34;default&#34;`, `&#34;dedicated&#34;` or `&#34;host&#34;`
{{% /md %}}</dd>

    <dt class="property-"
            title="">Virtualization<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Keyword to choose what virtualization mode created instances
will use. Can be either `&#34;paravirtual&#34;` or `&#34;hvm&#34;`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Agent<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The AWS OpsWorks agent to install.  Defaults to `&#34;INHERIT&#34;`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Ami<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The AMI to use for the instance.  If an AMI is specified, `os` must be `&#34;Custom&#34;`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Architecture<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Machine architecture for created instances.  Can be either `&#34;x86_64&#34;` (the default) or `&#34;i386&#34;`
{{% /md %}}</dd>

    <dt class="property-"
            title="">Auto<wbr>Scaling<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Creates load-based or time-based instances.  If set, can be either: `&#34;load&#34;` or `&#34;timer&#34;`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Availability<wbr>Zone<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Name of the availability zone where instances will be created
by default.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Created<wbr>At<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">Delete<wbr>Ebs<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">Delete<wbr>Eip<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">Ebs<wbr>Block<wbr>Devices<span class="property-indicator"></span>
        <span class="property-type"><a href="#instanceebsblockdevice">[]Instance<wbr>Ebs<wbr>Block<wbr>Device</a></span>
    </dt>
    <dd>{{% md %}}Additional EBS block devices to attach to the
instance.  See Block Devices below for details.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Ebs<wbr>Optimized<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}If true, the launched EC2 instance will be EBS-optimized.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Ec2Instance<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}EC2 instance ID
{{% /md %}}</dd>

    <dt class="property-"
            title="">Ecs<wbr>Cluster<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">Elastic<wbr>Ip<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">Ephemeral<wbr>Block<wbr>Devices<span class="property-indicator"></span>
        <span class="property-type"><a href="#instanceephemeralblockdevice">[]Instance<wbr>Ephemeral<wbr>Block<wbr>Device</a></span>
    </dt>
    <dd>{{% md %}}Customize Ephemeral (also known as
&#34;Instance Store&#34;) volumes on the instance. See Block Devices below for details.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Hostname<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The instance&#39;s host name.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Infrastructure<wbr>Class<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">Install<wbr>Updates<wbr>On<wbr>Boot<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Controls where to install OS and package updates when the instance boots.  Defaults to `true`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Instance<wbr>Profile<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">Instance<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The type of instance to start
{{% /md %}}</dd>

    <dt class="property-"
            title="">Last<wbr>Service<wbr>Error<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">Layer<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}The ids of the layers the instance will belong to.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Os<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Name of operating system that will be installed.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Platform<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">Private<wbr>Dns<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The private DNS name assigned to the instance. Can only be
used inside the Amazon EC2, and only available if you&#39;ve enabled DNS hostnames
for your VPC
{{% /md %}}</dd>

    <dt class="property-"
            title="">Private<wbr>Ip<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The private IP address assigned to the instance
{{% /md %}}</dd>

    <dt class="property-"
            title="">Public<wbr>Dns<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The public DNS name assigned to the instance. For EC2-VPC, this
is only available if you&#39;ve enabled DNS hostnames for your VPC
{{% /md %}}</dd>

    <dt class="property-"
            title="">Public<wbr>Ip<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The public IP address assigned to the instance, if applicable.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Registered<wbr>By<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">Reported<wbr>Agent<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">Reported<wbr>Os<wbr>Family<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">Reported<wbr>Os<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">Reported<wbr>Os<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">Root<wbr>Block<wbr>Devices<span class="property-indicator"></span>
        <span class="property-type"><a href="#instancerootblockdevice">[]Instance<wbr>Root<wbr>Block<wbr>Device</a></span>
    </dt>
    <dd>{{% md %}}Customize details about the root block
device of the instance. See Block Devices below for details.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Root<wbr>Device<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Name of the type of root device instances will have by default.  Can be either `&#34;ebs&#34;` or `&#34;instance-store&#34;`
{{% /md %}}</dd>

    <dt class="property-"
            title="">Root<wbr>Device<wbr>Volume<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">Security<wbr>Group<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}The associated security groups.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Ssh<wbr>Host<wbr>Dsa<wbr>Key<wbr>Fingerprint<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">Ssh<wbr>Host<wbr>Rsa<wbr>Key<wbr>Fingerprint<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">Ssh<wbr>Key<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Name of the SSH keypair that instances will have by default.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Stack<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The id of the stack the instance will belong to.
{{% /md %}}</dd>

    <dt class="property-"
            title="">State<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The desired state of the instance.  Can be either `&#34;running&#34;` or `&#34;stopped&#34;`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Status<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">Subnet<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Subnet ID to attach to
{{% /md %}}</dd>

    <dt class="property-"
            title="">Tenancy<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Instance tenancy to use. Can be one of `&#34;default&#34;`, `&#34;dedicated&#34;` or `&#34;host&#34;`
{{% /md %}}</dd>

    <dt class="property-"
            title="">Virtualization<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Keyword to choose what virtualization mode created instances
will use. Can be either `&#34;paravirtual&#34;` or `&#34;hvm&#34;`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">agent<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The AWS OpsWorks agent to install.  Defaults to `&#34;INHERIT&#34;`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">ami<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The AMI to use for the instance.  If an AMI is specified, `os` must be `&#34;Custom&#34;`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">architecture<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Machine architecture for created instances.  Can be either `&#34;x86_64&#34;` (the default) or `&#34;i386&#34;`
{{% /md %}}</dd>

    <dt class="property-"
            title="">auto<wbr>Scaling<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Creates load-based or time-based instances.  If set, can be either: `&#34;load&#34;` or `&#34;timer&#34;`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">availability<wbr>Zone<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Name of the availability zone where instances will be created
by default.
{{% /md %}}</dd>

    <dt class="property-"
            title="">created<wbr>At<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">delete<wbr>Ebs<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">delete<wbr>Eip<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">ebs<wbr>Block<wbr>Devices<span class="property-indicator"></span>
        <span class="property-type"><a href="#instanceebsblockdevice">Instance<wbr>Ebs<wbr>Block<wbr>Device[]</a></span>
    </dt>
    <dd>{{% md %}}Additional EBS block devices to attach to the
instance.  See Block Devices below for details.
{{% /md %}}</dd>

    <dt class="property-"
            title="">ebs<wbr>Optimized<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}If true, the launched EC2 instance will be EBS-optimized.
{{% /md %}}</dd>

    <dt class="property-"
            title="">ec2Instance<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}EC2 instance ID
{{% /md %}}</dd>

    <dt class="property-"
            title="">ecs<wbr>Cluster<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">elastic<wbr>Ip<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">ephemeral<wbr>Block<wbr>Devices<span class="property-indicator"></span>
        <span class="property-type"><a href="#instanceephemeralblockdevice">Instance<wbr>Ephemeral<wbr>Block<wbr>Device[]</a></span>
    </dt>
    <dd>{{% md %}}Customize Ephemeral (also known as
&#34;Instance Store&#34;) volumes on the instance. See Block Devices below for details.
{{% /md %}}</dd>

    <dt class="property-"
            title="">hostname<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The instance&#39;s host name.
{{% /md %}}</dd>

    <dt class="property-"
            title="">infrastructure<wbr>Class<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">install<wbr>Updates<wbr>On<wbr>Boot<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Controls where to install OS and package updates when the instance boots.  Defaults to `true`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">instance<wbr>Profile<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">instance<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The type of instance to start
{{% /md %}}</dd>

    <dt class="property-"
            title="">last<wbr>Service<wbr>Error<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">layer<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">string[]</span>
    </dt>
    <dd>{{% md %}}The ids of the layers the instance will belong to.
{{% /md %}}</dd>

    <dt class="property-"
            title="">os<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Name of operating system that will be installed.
{{% /md %}}</dd>

    <dt class="property-"
            title="">platform<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">private<wbr>Dns<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The private DNS name assigned to the instance. Can only be
used inside the Amazon EC2, and only available if you&#39;ve enabled DNS hostnames
for your VPC
{{% /md %}}</dd>

    <dt class="property-"
            title="">private<wbr>Ip<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The private IP address assigned to the instance
{{% /md %}}</dd>

    <dt class="property-"
            title="">public<wbr>Dns<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The public DNS name assigned to the instance. For EC2-VPC, this
is only available if you&#39;ve enabled DNS hostnames for your VPC
{{% /md %}}</dd>

    <dt class="property-"
            title="">public<wbr>Ip<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The public IP address assigned to the instance, if applicable.
{{% /md %}}</dd>

    <dt class="property-"
            title="">registered<wbr>By<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">reported<wbr>Agent<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">reported<wbr>Os<wbr>Family<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">reported<wbr>Os<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">reported<wbr>Os<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">root<wbr>Block<wbr>Devices<span class="property-indicator"></span>
        <span class="property-type"><a href="#instancerootblockdevice">Instance<wbr>Root<wbr>Block<wbr>Device[]</a></span>
    </dt>
    <dd>{{% md %}}Customize details about the root block
device of the instance. See Block Devices below for details.
{{% /md %}}</dd>

    <dt class="property-"
            title="">root<wbr>Device<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Name of the type of root device instances will have by default.  Can be either `&#34;ebs&#34;` or `&#34;instance-store&#34;`
{{% /md %}}</dd>

    <dt class="property-"
            title="">root<wbr>Device<wbr>Volume<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">security<wbr>Group<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">string[]</span>
    </dt>
    <dd>{{% md %}}The associated security groups.
{{% /md %}}</dd>

    <dt class="property-"
            title="">ssh<wbr>Host<wbr>Dsa<wbr>Key<wbr>Fingerprint<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">ssh<wbr>Host<wbr>Rsa<wbr>Key<wbr>Fingerprint<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">ssh<wbr>Key<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Name of the SSH keypair that instances will have by default.
{{% /md %}}</dd>

    <dt class="property-"
            title="">stack<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The id of the stack the instance will belong to.
{{% /md %}}</dd>

    <dt class="property-"
            title="">state<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The desired state of the instance.  Can be either `&#34;running&#34;` or `&#34;stopped&#34;`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">status<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">subnet<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Subnet ID to attach to
{{% /md %}}</dd>

    <dt class="property-"
            title="">tenancy<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Instance tenancy to use. Can be one of `&#34;default&#34;`, `&#34;dedicated&#34;` or `&#34;host&#34;`
{{% /md %}}</dd>

    <dt class="property-"
            title="">virtualization<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Keyword to choose what virtualization mode created instances
will use. Can be either `&#34;paravirtual&#34;` or `&#34;hvm&#34;`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">agent_<wbr>version<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The AWS OpsWorks agent to install.  Defaults to `&#34;INHERIT&#34;`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">ami_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The AMI to use for the instance.  If an AMI is specified, `os` must be `&#34;Custom&#34;`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">architecture<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Machine architecture for created instances.  Can be either `&#34;x86_64&#34;` (the default) or `&#34;i386&#34;`
{{% /md %}}</dd>

    <dt class="property-"
            title="">auto_<wbr>scaling_<wbr>type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Creates load-based or time-based instances.  If set, can be either: `&#34;load&#34;` or `&#34;timer&#34;`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">availability_<wbr>zone<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Name of the availability zone where instances will be created
by default.
{{% /md %}}</dd>

    <dt class="property-"
            title="">created_<wbr>at<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">delete_<wbr>ebs<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">delete_<wbr>eip<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">ebs_<wbr>block_<wbr>devices<span class="property-indicator"></span>
        <span class="property-type"><a href="#instanceebsblockdevice">List[Instance<wbr>Ebs<wbr>Block<wbr>Device]</a></span>
    </dt>
    <dd>{{% md %}}Additional EBS block devices to attach to the
instance.  See Block Devices below for details.
{{% /md %}}</dd>

    <dt class="property-"
            title="">ebs_<wbr>optimized<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}If true, the launched EC2 instance will be EBS-optimized.
{{% /md %}}</dd>

    <dt class="property-"
            title="">ec2_<wbr>instance_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}EC2 instance ID
{{% /md %}}</dd>

    <dt class="property-"
            title="">ecs_<wbr>cluster_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">elastic_<wbr>ip<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">ephemeral_<wbr>block_<wbr>devices<span class="property-indicator"></span>
        <span class="property-type"><a href="#instanceephemeralblockdevice">List[Instance<wbr>Ephemeral<wbr>Block<wbr>Device]</a></span>
    </dt>
    <dd>{{% md %}}Customize Ephemeral (also known as
&#34;Instance Store&#34;) volumes on the instance. See Block Devices below for details.
{{% /md %}}</dd>

    <dt class="property-"
            title="">hostname<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The instance&#39;s host name.
{{% /md %}}</dd>

    <dt class="property-"
            title="">infrastructure_<wbr>class<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">install_<wbr>updates_<wbr>on_<wbr>boot<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Controls where to install OS and package updates when the instance boots.  Defaults to `true`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">instance_<wbr>profile_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">instance_<wbr>type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The type of instance to start
{{% /md %}}</dd>

    <dt class="property-"
            title="">last_<wbr>service_<wbr>error_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">layer_<wbr>ids<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}The ids of the layers the instance will belong to.
{{% /md %}}</dd>

    <dt class="property-"
            title="">os<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Name of operating system that will be installed.
{{% /md %}}</dd>

    <dt class="property-"
            title="">platform<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">private_<wbr>dns<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The private DNS name assigned to the instance. Can only be
used inside the Amazon EC2, and only available if you&#39;ve enabled DNS hostnames
for your VPC
{{% /md %}}</dd>

    <dt class="property-"
            title="">private_<wbr>ip<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The private IP address assigned to the instance
{{% /md %}}</dd>

    <dt class="property-"
            title="">public_<wbr>dns<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The public DNS name assigned to the instance. For EC2-VPC, this
is only available if you&#39;ve enabled DNS hostnames for your VPC
{{% /md %}}</dd>

    <dt class="property-"
            title="">public_<wbr>ip<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The public IP address assigned to the instance, if applicable.
{{% /md %}}</dd>

    <dt class="property-"
            title="">registered_<wbr>by<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">reported_<wbr>agent_<wbr>version<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">reported_<wbr>os_<wbr>family<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">reported_<wbr>os_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">reported_<wbr>os_<wbr>version<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">root_<wbr>block_<wbr>devices<span class="property-indicator"></span>
        <span class="property-type"><a href="#instancerootblockdevice">List[Instance<wbr>Root<wbr>Block<wbr>Device]</a></span>
    </dt>
    <dd>{{% md %}}Customize details about the root block
device of the instance. See Block Devices below for details.
{{% /md %}}</dd>

    <dt class="property-"
            title="">root_<wbr>device_<wbr>type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Name of the type of root device instances will have by default.  Can be either `&#34;ebs&#34;` or `&#34;instance-store&#34;`
{{% /md %}}</dd>

    <dt class="property-"
            title="">root_<wbr>device_<wbr>volume_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">security_<wbr>group_<wbr>ids<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}The associated security groups.
{{% /md %}}</dd>

    <dt class="property-"
            title="">ssh_<wbr>host_<wbr>dsa_<wbr>key_<wbr>fingerprint<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">ssh_<wbr>host_<wbr>rsa_<wbr>key_<wbr>fingerprint<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">ssh_<wbr>key_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Name of the SSH keypair that instances will have by default.
{{% /md %}}</dd>

    <dt class="property-"
            title="">stack_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The id of the stack the instance will belong to.
{{% /md %}}</dd>

    <dt class="property-"
            title="">state<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The desired state of the instance.  Can be either `&#34;running&#34;` or `&#34;stopped&#34;`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">status<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">subnet_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Subnet ID to attach to
{{% /md %}}</dd>

    <dt class="property-"
            title="">tenancy<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Instance tenancy to use. Can be one of `&#34;default&#34;`, `&#34;dedicated&#34;` or `&#34;host&#34;`
{{% /md %}}</dd>

    <dt class="property-"
            title="">virtualization_<wbr>type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Keyword to choose what virtualization mode created instances
will use. Can be either `&#34;paravirtual&#34;` or `&#34;hvm&#34;`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





## Look up an Existing Instance Resource

{{< chooser language "javascript,typescript,python,go,csharp  " / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">pulumi.Input&lt;pulumi.ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/opsworks/#InstanceState">InstanceState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/opsworks/#Instance">Instance</a></span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>agent_version=None<span class="p">, </span>ami_id=None<span class="p">, </span>architecture=None<span class="p">, </span>auto_scaling_type=None<span class="p">, </span>availability_zone=None<span class="p">, </span>created_at=None<span class="p">, </span>delete_ebs=None<span class="p">, </span>delete_eip=None<span class="p">, </span>ebs_block_devices=None<span class="p">, </span>ebs_optimized=None<span class="p">, </span>ec2_instance_id=None<span class="p">, </span>ecs_cluster_arn=None<span class="p">, </span>elastic_ip=None<span class="p">, </span>ephemeral_block_devices=None<span class="p">, </span>hostname=None<span class="p">, </span>infrastructure_class=None<span class="p">, </span>install_updates_on_boot=None<span class="p">, </span>instance_profile_arn=None<span class="p">, </span>instance_type=None<span class="p">, </span>last_service_error_id=None<span class="p">, </span>layer_ids=None<span class="p">, </span>os=None<span class="p">, </span>platform=None<span class="p">, </span>private_dns=None<span class="p">, </span>private_ip=None<span class="p">, </span>public_dns=None<span class="p">, </span>public_ip=None<span class="p">, </span>registered_by=None<span class="p">, </span>reported_agent_version=None<span class="p">, </span>reported_os_family=None<span class="p">, </span>reported_os_name=None<span class="p">, </span>reported_os_version=None<span class="p">, </span>root_block_devices=None<span class="p">, </span>root_device_type=None<span class="p">, </span>root_device_volume_id=None<span class="p">, </span>security_group_ids=None<span class="p">, </span>ssh_host_dsa_key_fingerprint=None<span class="p">, </span>ssh_host_rsa_key_fingerprint=None<span class="p">, </span>ssh_key_name=None<span class="p">, </span>stack_id=None<span class="p">, </span>state=None<span class="p">, </span>status=None<span class="p">, </span>subnet_id=None<span class="p">, </span>tenancy=None<span class="p">, </span>virtualization_type=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetInstance<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">pulumi.IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/opsworks?tab=doc#InstanceState">InstanceState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/opsworks?tab=doc#Instance">Instance</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Opsworks.Instance.html">Instance</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Pulumi.Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Opsworks.InstanceState.html">InstanceState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
{{% /choosable %}}

Get an existing Instance resource's state with the given name, ID, and optional extra properties used to qualify the lookup.

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
            title="Optional">Agent<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The AWS OpsWorks agent to install.  Defaults to `&#34;INHERIT&#34;`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ami<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The AMI to use for the instance.  If an AMI is specified, `os` must be `&#34;Custom&#34;`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Architecture<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Machine architecture for created instances.  Can be either `&#34;x86_64&#34;` (the default) or `&#34;i386&#34;`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Auto<wbr>Scaling<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Creates load-based or time-based instances.  If set, can be either: `&#34;load&#34;` or `&#34;timer&#34;`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Availability<wbr>Zone<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Name of the availability zone where instances will be created
by default.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Created<wbr>At<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Delete<wbr>Ebs<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Delete<wbr>Eip<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ebs<wbr>Block<wbr>Devices<span class="property-indicator"></span>
        <span class="property-type"><a href="#instanceebsblockdevice">List&lt;Instance<wbr>Ebs<wbr>Block<wbr>Device<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}Additional EBS block devices to attach to the
instance.  See Block Devices below for details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ebs<wbr>Optimized<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}If true, the launched EC2 instance will be EBS-optimized.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ec2Instance<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}EC2 instance ID
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ecs<wbr>Cluster<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Elastic<wbr>Ip<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ephemeral<wbr>Block<wbr>Devices<span class="property-indicator"></span>
        <span class="property-type"><a href="#instanceephemeralblockdevice">List&lt;Instance<wbr>Ephemeral<wbr>Block<wbr>Device<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}Customize Ephemeral (also known as
&#34;Instance Store&#34;) volumes on the instance. See Block Devices below for details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Hostname<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The instance&#39;s host name.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Infrastructure<wbr>Class<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Install<wbr>Updates<wbr>On<wbr>Boot<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Controls where to install OS and package updates when the instance boots.  Defaults to `true`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Instance<wbr>Profile<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Instance<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The type of instance to start
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Last<wbr>Service<wbr>Error<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Layer<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}The ids of the layers the instance will belong to.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Os<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Name of operating system that will be installed.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Platform<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Private<wbr>Dns<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The private DNS name assigned to the instance. Can only be
used inside the Amazon EC2, and only available if you&#39;ve enabled DNS hostnames
for your VPC
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Private<wbr>Ip<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The private IP address assigned to the instance
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Public<wbr>Dns<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The public DNS name assigned to the instance. For EC2-VPC, this
is only available if you&#39;ve enabled DNS hostnames for your VPC
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Public<wbr>Ip<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The public IP address assigned to the instance, if applicable.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Registered<wbr>By<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Reported<wbr>Agent<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Reported<wbr>Os<wbr>Family<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Reported<wbr>Os<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Reported<wbr>Os<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Root<wbr>Block<wbr>Devices<span class="property-indicator"></span>
        <span class="property-type"><a href="#instancerootblockdevice">List&lt;Instance<wbr>Root<wbr>Block<wbr>Device<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}Customize details about the root block
device of the instance. See Block Devices below for details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Root<wbr>Device<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Name of the type of root device instances will have by default.  Can be either `&#34;ebs&#34;` or `&#34;instance-store&#34;`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Root<wbr>Device<wbr>Volume<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Security<wbr>Group<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}The associated security groups.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ssh<wbr>Host<wbr>Dsa<wbr>Key<wbr>Fingerprint<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ssh<wbr>Host<wbr>Rsa<wbr>Key<wbr>Fingerprint<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ssh<wbr>Key<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Name of the SSH keypair that instances will have by default.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Stack<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The id of the stack the instance will belong to.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">State<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The desired state of the instance.  Can be either `&#34;running&#34;` or `&#34;stopped&#34;`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Status<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Subnet<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Subnet ID to attach to
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tenancy<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Instance tenancy to use. Can be one of `&#34;default&#34;`, `&#34;dedicated&#34;` or `&#34;host&#34;`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Virtualization<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Keyword to choose what virtualization mode created instances
will use. Can be either `&#34;paravirtual&#34;` or `&#34;hvm&#34;`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Agent<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The AWS OpsWorks agent to install.  Defaults to `&#34;INHERIT&#34;`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ami<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The AMI to use for the instance.  If an AMI is specified, `os` must be `&#34;Custom&#34;`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Architecture<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Machine architecture for created instances.  Can be either `&#34;x86_64&#34;` (the default) or `&#34;i386&#34;`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Auto<wbr>Scaling<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Creates load-based or time-based instances.  If set, can be either: `&#34;load&#34;` or `&#34;timer&#34;`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Availability<wbr>Zone<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Name of the availability zone where instances will be created
by default.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Created<wbr>At<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Delete<wbr>Ebs<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Delete<wbr>Eip<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ebs<wbr>Block<wbr>Devices<span class="property-indicator"></span>
        <span class="property-type"><a href="#instanceebsblockdevice">[]Instance<wbr>Ebs<wbr>Block<wbr>Device</a></span>
    </dt>
    <dd>{{% md %}}Additional EBS block devices to attach to the
instance.  See Block Devices below for details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ebs<wbr>Optimized<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}If true, the launched EC2 instance will be EBS-optimized.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ec2Instance<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}EC2 instance ID
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ecs<wbr>Cluster<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Elastic<wbr>Ip<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ephemeral<wbr>Block<wbr>Devices<span class="property-indicator"></span>
        <span class="property-type"><a href="#instanceephemeralblockdevice">[]Instance<wbr>Ephemeral<wbr>Block<wbr>Device</a></span>
    </dt>
    <dd>{{% md %}}Customize Ephemeral (also known as
&#34;Instance Store&#34;) volumes on the instance. See Block Devices below for details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Hostname<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The instance&#39;s host name.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Infrastructure<wbr>Class<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Install<wbr>Updates<wbr>On<wbr>Boot<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Controls where to install OS and package updates when the instance boots.  Defaults to `true`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Instance<wbr>Profile<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Instance<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The type of instance to start
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Last<wbr>Service<wbr>Error<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Layer<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}The ids of the layers the instance will belong to.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Os<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Name of operating system that will be installed.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Platform<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Private<wbr>Dns<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The private DNS name assigned to the instance. Can only be
used inside the Amazon EC2, and only available if you&#39;ve enabled DNS hostnames
for your VPC
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Private<wbr>Ip<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The private IP address assigned to the instance
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Public<wbr>Dns<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The public DNS name assigned to the instance. For EC2-VPC, this
is only available if you&#39;ve enabled DNS hostnames for your VPC
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Public<wbr>Ip<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The public IP address assigned to the instance, if applicable.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Registered<wbr>By<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Reported<wbr>Agent<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Reported<wbr>Os<wbr>Family<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Reported<wbr>Os<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Reported<wbr>Os<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Root<wbr>Block<wbr>Devices<span class="property-indicator"></span>
        <span class="property-type"><a href="#instancerootblockdevice">[]Instance<wbr>Root<wbr>Block<wbr>Device</a></span>
    </dt>
    <dd>{{% md %}}Customize details about the root block
device of the instance. See Block Devices below for details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Root<wbr>Device<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Name of the type of root device instances will have by default.  Can be either `&#34;ebs&#34;` or `&#34;instance-store&#34;`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Root<wbr>Device<wbr>Volume<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Security<wbr>Group<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}The associated security groups.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ssh<wbr>Host<wbr>Dsa<wbr>Key<wbr>Fingerprint<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ssh<wbr>Host<wbr>Rsa<wbr>Key<wbr>Fingerprint<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ssh<wbr>Key<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Name of the SSH keypair that instances will have by default.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Stack<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The id of the stack the instance will belong to.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">State<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The desired state of the instance.  Can be either `&#34;running&#34;` or `&#34;stopped&#34;`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Status<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Subnet<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Subnet ID to attach to
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tenancy<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Instance tenancy to use. Can be one of `&#34;default&#34;`, `&#34;dedicated&#34;` or `&#34;host&#34;`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Virtualization<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Keyword to choose what virtualization mode created instances
will use. Can be either `&#34;paravirtual&#34;` or `&#34;hvm&#34;`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">agent<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The AWS OpsWorks agent to install.  Defaults to `&#34;INHERIT&#34;`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ami<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The AMI to use for the instance.  If an AMI is specified, `os` must be `&#34;Custom&#34;`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">architecture<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Machine architecture for created instances.  Can be either `&#34;x86_64&#34;` (the default) or `&#34;i386&#34;`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">auto<wbr>Scaling<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Creates load-based or time-based instances.  If set, can be either: `&#34;load&#34;` or `&#34;timer&#34;`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">availability<wbr>Zone<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Name of the availability zone where instances will be created
by default.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">created<wbr>At<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">delete<wbr>Ebs<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">delete<wbr>Eip<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ebs<wbr>Block<wbr>Devices<span class="property-indicator"></span>
        <span class="property-type"><a href="#instanceebsblockdevice">Instance<wbr>Ebs<wbr>Block<wbr>Device[]?</a></span>
    </dt>
    <dd>{{% md %}}Additional EBS block devices to attach to the
instance.  See Block Devices below for details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ebs<wbr>Optimized<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}If true, the launched EC2 instance will be EBS-optimized.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ec2Instance<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}EC2 instance ID
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ecs<wbr>Cluster<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">elastic<wbr>Ip<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ephemeral<wbr>Block<wbr>Devices<span class="property-indicator"></span>
        <span class="property-type"><a href="#instanceephemeralblockdevice">Instance<wbr>Ephemeral<wbr>Block<wbr>Device[]?</a></span>
    </dt>
    <dd>{{% md %}}Customize Ephemeral (also known as
&#34;Instance Store&#34;) volumes on the instance. See Block Devices below for details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">hostname<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The instance&#39;s host name.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">infrastructure<wbr>Class<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">install<wbr>Updates<wbr>On<wbr>Boot<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Controls where to install OS and package updates when the instance boots.  Defaults to `true`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">instance<wbr>Profile<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">instance<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The type of instance to start
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">last<wbr>Service<wbr>Error<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">layer<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}The ids of the layers the instance will belong to.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">os<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Name of operating system that will be installed.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">platform<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">private<wbr>Dns<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The private DNS name assigned to the instance. Can only be
used inside the Amazon EC2, and only available if you&#39;ve enabled DNS hostnames
for your VPC
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">private<wbr>Ip<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The private IP address assigned to the instance
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">public<wbr>Dns<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The public DNS name assigned to the instance. For EC2-VPC, this
is only available if you&#39;ve enabled DNS hostnames for your VPC
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">public<wbr>Ip<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The public IP address assigned to the instance, if applicable.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">registered<wbr>By<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">reported<wbr>Agent<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">reported<wbr>Os<wbr>Family<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">reported<wbr>Os<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">reported<wbr>Os<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">root<wbr>Block<wbr>Devices<span class="property-indicator"></span>
        <span class="property-type"><a href="#instancerootblockdevice">Instance<wbr>Root<wbr>Block<wbr>Device[]?</a></span>
    </dt>
    <dd>{{% md %}}Customize details about the root block
device of the instance. See Block Devices below for details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">root<wbr>Device<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Name of the type of root device instances will have by default.  Can be either `&#34;ebs&#34;` or `&#34;instance-store&#34;`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">root<wbr>Device<wbr>Volume<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">security<wbr>Group<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}The associated security groups.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ssh<wbr>Host<wbr>Dsa<wbr>Key<wbr>Fingerprint<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ssh<wbr>Host<wbr>Rsa<wbr>Key<wbr>Fingerprint<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ssh<wbr>Key<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Name of the SSH keypair that instances will have by default.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">stack<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The id of the stack the instance will belong to.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">state<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The desired state of the instance.  Can be either `&#34;running&#34;` or `&#34;stopped&#34;`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">status<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">subnet<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Subnet ID to attach to
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tenancy<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Instance tenancy to use. Can be one of `&#34;default&#34;`, `&#34;dedicated&#34;` or `&#34;host&#34;`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">virtualization<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Keyword to choose what virtualization mode created instances
will use. Can be either `&#34;paravirtual&#34;` or `&#34;hvm&#34;`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">agent_<wbr>version<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The AWS OpsWorks agent to install.  Defaults to `&#34;INHERIT&#34;`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ami_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The AMI to use for the instance.  If an AMI is specified, `os` must be `&#34;Custom&#34;`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">architecture<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Machine architecture for created instances.  Can be either `&#34;x86_64&#34;` (the default) or `&#34;i386&#34;`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">auto_<wbr>scaling_<wbr>type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Creates load-based or time-based instances.  If set, can be either: `&#34;load&#34;` or `&#34;timer&#34;`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">availability_<wbr>zone<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Name of the availability zone where instances will be created
by default.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">created_<wbr>at<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">delete_<wbr>ebs<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">delete_<wbr>eip<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ebs_<wbr>block_<wbr>devices<span class="property-indicator"></span>
        <span class="property-type"><a href="#instanceebsblockdevice">List[Instance<wbr>Ebs<wbr>Block<wbr>Device]</a></span>
    </dt>
    <dd>{{% md %}}Additional EBS block devices to attach to the
instance.  See Block Devices below for details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ebs_<wbr>optimized<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}If true, the launched EC2 instance will be EBS-optimized.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ec2_<wbr>instance_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}EC2 instance ID
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ecs_<wbr>cluster_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">elastic_<wbr>ip<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ephemeral_<wbr>block_<wbr>devices<span class="property-indicator"></span>
        <span class="property-type"><a href="#instanceephemeralblockdevice">List[Instance<wbr>Ephemeral<wbr>Block<wbr>Device]</a></span>
    </dt>
    <dd>{{% md %}}Customize Ephemeral (also known as
&#34;Instance Store&#34;) volumes on the instance. See Block Devices below for details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">hostname<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The instance&#39;s host name.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">infrastructure_<wbr>class<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">install_<wbr>updates_<wbr>on_<wbr>boot<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Controls where to install OS and package updates when the instance boots.  Defaults to `true`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">instance_<wbr>profile_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">instance_<wbr>type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The type of instance to start
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">last_<wbr>service_<wbr>error_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">layer_<wbr>ids<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}The ids of the layers the instance will belong to.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">os<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Name of operating system that will be installed.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">platform<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">private_<wbr>dns<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The private DNS name assigned to the instance. Can only be
used inside the Amazon EC2, and only available if you&#39;ve enabled DNS hostnames
for your VPC
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">private_<wbr>ip<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The private IP address assigned to the instance
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">public_<wbr>dns<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The public DNS name assigned to the instance. For EC2-VPC, this
is only available if you&#39;ve enabled DNS hostnames for your VPC
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">public_<wbr>ip<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The public IP address assigned to the instance, if applicable.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">registered_<wbr>by<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">reported_<wbr>agent_<wbr>version<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">reported_<wbr>os_<wbr>family<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">reported_<wbr>os_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">reported_<wbr>os_<wbr>version<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">root_<wbr>block_<wbr>devices<span class="property-indicator"></span>
        <span class="property-type"><a href="#instancerootblockdevice">List[Instance<wbr>Root<wbr>Block<wbr>Device]</a></span>
    </dt>
    <dd>{{% md %}}Customize details about the root block
device of the instance. See Block Devices below for details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">root_<wbr>device_<wbr>type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Name of the type of root device instances will have by default.  Can be either `&#34;ebs&#34;` or `&#34;instance-store&#34;`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">root_<wbr>device_<wbr>volume_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">security_<wbr>group_<wbr>ids<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}The associated security groups.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ssh_<wbr>host_<wbr>dsa_<wbr>key_<wbr>fingerprint<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ssh_<wbr>host_<wbr>rsa_<wbr>key_<wbr>fingerprint<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ssh_<wbr>key_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Name of the SSH keypair that instances will have by default.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">stack_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The id of the stack the instance will belong to.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">state<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The desired state of the instance.  Can be either `&#34;running&#34;` or `&#34;stopped&#34;`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">status<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">subnet_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Subnet ID to attach to
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tenancy<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Instance tenancy to use. Can be one of `&#34;default&#34;`, `&#34;dedicated&#34;` or `&#34;host&#34;`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">virtualization_<wbr>type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Keyword to choose what virtualization mode created instances
will use. Can be either `&#34;paravirtual&#34;` or `&#34;hvm&#34;`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}







## Supporting Types

#### InstanceEbsBlockDevice
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#InstanceEbsBlockDevice">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#InstanceEbsBlockDevice">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/opsworks?tab=doc#InstanceEbsBlockDeviceArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/opsworks?tab=doc#InstanceEbsBlockDeviceOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Opsworks.InstanceEbsBlockDeviceArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Opsworks.InstanceEbsBlockDevice.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Delete<wbr>On<wbr>Termination<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Device<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
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

    <dt class="property-required"
            title="Required">Device<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
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

    <dt class="property-required"
            title="Required">device<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
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

    <dt class="property-required"
            title="Required">device_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
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





#### InstanceEphemeralBlockDevice
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#InstanceEphemeralBlockDevice">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#InstanceEphemeralBlockDevice">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/opsworks?tab=doc#InstanceEphemeralBlockDeviceArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/opsworks?tab=doc#InstanceEphemeralBlockDeviceOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Opsworks.InstanceEphemeralBlockDeviceArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Opsworks.InstanceEphemeralBlockDevice.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Device<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Virtual<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Device<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Virtual<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">device<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">virtual<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">device_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">virtual<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### InstanceRootBlockDevice
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#InstanceRootBlockDevice">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#InstanceRootBlockDevice">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/opsworks?tab=doc#InstanceRootBlockDeviceArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/opsworks?tab=doc#InstanceRootBlockDeviceOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Opsworks.InstanceRootBlockDeviceArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Opsworks.InstanceRootBlockDevice.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Delete<wbr>On<wbr>Termination<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Iops<span class="property-indicator"></span>
        <span class="property-type">int?</span>
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
            title="Optional">Iops<span class="property-indicator"></span>
        <span class="property-type">*int</span>
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
            title="Optional">iops<span class="property-indicator"></span>
        <span class="property-type">number?</span>
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
            title="Optional">iops<span class="property-indicator"></span>
        <span class="property-type">float</span>
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








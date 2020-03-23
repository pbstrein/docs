
---
title: "LaunchConfiguration"
block_external_search_index: true
---

Provides a resource to create a new launch configuration, used for autoscaling groups.

## Example Usage

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const ubuntu = aws.getAmi({
    filters: [
        {
            name: "name",
            values: ["ubuntu/images/hvm-ssd/ubuntu-trusty-14.04-amd64-server-*"],
        },
        {
            name: "virtualization-type",
            values: ["hvm"],
        },
    ],
    mostRecent: true,
    owners: ["099720109477"], // Canonical
});
const asConf = new aws.ec2.LaunchConfiguration("as_conf", {
    imageId: ubuntu.id,
    instanceType: "t2.micro",
});
```

## Using with AutoScaling Groups

Launch Configurations cannot be updated after creation with the Amazon
Web Service API. In order to update a Launch Configuration, this provider will
destroy the existing resource and create a replacement. In order to effectively
use a Launch Configuration resource with an [AutoScaling Group resource][1],
it's recommended to specify `create_before_destroy` in a [lifecycle][2] block.
Either omit the Launch Configuration `name` attribute, or specify a partial name
with `name_prefix`.  Example:

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const ubuntu = aws.getAmi({
    filters: [
        {
            name: "name",
            values: ["ubuntu/images/hvm-ssd/ubuntu-trusty-14.04-amd64-server-*"],
        },
        {
            name: "virtualization-type",
            values: ["hvm"],
        },
    ],
    mostRecent: true,
    owners: ["099720109477"], // Canonical
});
const asConf = new aws.ec2.LaunchConfiguration("as_conf", {
    imageId: ubuntu.id,
    instanceType: "t2.micro",
    namePrefix: "lc-example-",
});
const bar = new aws.autoscaling.Group("bar", {
    launchConfiguration: asConf.name,
    maxSize: 2,
    minSize: 1,
});
```

With this setup this provider generates a unique name for your Launch
Configuration and can then update the AutoScaling Group without conflict before
destroying the previous Launch Configuration.

## Using with Spot Instances

Launch configurations can set the spot instance pricing to be used for the
Auto Scaling Group to reserve instances. Simply specifying the `spot_price`
parameter will set the price on the Launch Configuration which will attempt to
reserve your instances at this price.  See the [AWS Spot Instance
documentation](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/using-spot-instances.html)
for more information or how to launch [Spot Instances][3] with this provider.

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const ubuntu = aws.getAmi({
    filters: [
        {
            name: "name",
            values: ["ubuntu/images/hvm-ssd/ubuntu-trusty-14.04-amd64-server-*"],
        },
        {
            name: "virtualization-type",
            values: ["hvm"],
        },
    ],
    mostRecent: true,
    owners: ["099720109477"], // Canonical
});
const asConf = new aws.ec2.LaunchConfiguration("as_conf", {
    imageId: ubuntu.id,
    instanceType: "m4.large",
    spotPrice: "0.001",
});
const bar = new aws.autoscaling.Group("bar", {
    launchConfiguration: asConf.name,
});
```

## Block devices

Each of the `*_block_device` attributes controls a portion of the AWS
Launch Configuration's "Block Device Mapping". It's a good idea to familiarize yourself with [AWS's Block Device
Mapping docs](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/block-device-mapping-concepts.html)
to understand the implications of using these attributes.

The `root_block_device` mapping supports the following:

* `volume_type` - (Optional) The type of volume. Can be `"standard"`, `"gp2"`,
  or `"io1"`. (Default: `"standard"`).
* `volume_size` - (Optional) The size of the volume in gigabytes.
* `iops` - (Optional) The amount of provisioned
  [IOPS](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ebs-io-characteristics.html).
  This must be set with a `volume_type` of `"io1"`.
* `delete_on_termination` - (Optional) Whether the volume should be destroyed
  on instance termination (Default: `true`).
* `encrypted` - (Optional) Whether the volume should be encrypted or not. (Default: `false`).

Modifying any of the `root_block_device` settings requires resource
replacement.

Each `ebs_block_device` supports the following:

* `device_name` - (Required) The name of the device to mount.
* `snapshot_id` - (Optional) The Snapshot ID to mount.
* `volume_type` - (Optional) The type of volume. Can be `"standard"`, `"gp2"`,
  or `"io1"`. (Default: `"standard"`).
* `volume_size` - (Optional) The size of the volume in gigabytes.
* `iops` - (Optional) The amount of provisioned
  [IOPS](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ebs-io-characteristics.html).
  This must be set with a `volume_type` of `"io1"`.
* `delete_on_termination` - (Optional) Whether the volume should be destroyed
  on instance termination (Default: `true`).
* `encrypted` - (Optional) Whether the volume should be encrypted or not. Do not use this option if you are using `snapshot_id` as the encrypted flag will be determined by the snapshot. (Default: `false`).

Modifying any `ebs_block_device` currently requires resource replacement.

Each `ephemeral_block_device` supports the following:

* `device_name` - The name of the block device to mount on the instance.
* `virtual_name` - The [Instance Store Device
  Name](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/InstanceStorage.html#InstanceStoreDeviceNames)
  (e.g. `"ephemeral0"`)

Each AWS Instance type has a different set of Instance Store block devices
available for attachment. AWS [publishes a
list](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/InstanceStorage.html#StorageOnInstanceTypes)
of which ephemeral devices are available on each type. The devices are always
identified by the `virtual_name` in the format `"ephemeral{0..N}"`.

> **NOTE:** Changes to `*_block_device` configuration of _existing_ resources
cannot currently be detected by this provider. After updating to block device
configuration, resource recreation can be manually triggered by using the
[`taint` command](https://www.terraform.io/docs/commands/taint.html).

> This content is derived from https://github.com/terraform-providers/terraform-provider-aws/blob/master/website/docs/r/launch_configuration.html.markdown.



## Create a LaunchConfiguration Resource

{{< chooser language "javascript,typescript,python,go,csharp" / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/ec2/#LaunchConfiguration">LaunchConfiguration</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/ec2/#LaunchConfigurationArgs">LaunchConfigurationArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">LaunchConfiguration</span><span class="p">(resource_name, opts=None, </span>associate_public_ip_address=None<span class="p">, </span>ebs_block_devices=None<span class="p">, </span>ebs_optimized=None<span class="p">, </span>enable_monitoring=None<span class="p">, </span>ephemeral_block_devices=None<span class="p">, </span>iam_instance_profile=None<span class="p">, </span>image_id=None<span class="p">, </span>instance_type=None<span class="p">, </span>key_name=None<span class="p">, </span>name=None<span class="p">, </span>name_prefix=None<span class="p">, </span>placement_tenancy=None<span class="p">, </span>root_block_device=None<span class="p">, </span>security_groups=None<span class="p">, </span>spot_price=None<span class="p">, </span>user_data=None<span class="p">, </span>user_data_base64=None<span class="p">, </span>vpc_classic_link_id=None<span class="p">, </span>vpc_classic_link_security_groups=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewLaunchConfiguration<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ec2?tab=doc#LaunchConfigurationArgs">LaunchConfigurationArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ec2?tab=doc#LaunchConfiguration">LaunchConfiguration</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ec2.LaunchConfiguration.html">LaunchConfiguration</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ec2.LaunchConfigurationArgs.html">LaunchConfigurationArgs</a></span> <span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
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
            title="Optional">Associate<wbr>Public<wbr>Ip<wbr>Address<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Associate a public ip address with an instance in a VPC.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ebs<wbr>Block<wbr>Devices<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchconfigurationebsblockdevice">List&lt;Launch<wbr>Configuration<wbr>Ebs<wbr>Block<wbr>Device<wbr>Args&gt;?</a></span>
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
            title="Optional">Enable<wbr>Monitoring<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Enables/disables detailed monitoring. This is enabled by default.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ephemeral<wbr>Block<wbr>Devices<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchconfigurationephemeralblockdevice">List&lt;Launch<wbr>Configuration<wbr>Ephemeral<wbr>Block<wbr>Device<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}Customize Ephemeral (also known as
&#34;Instance Store&#34;) volumes on the instance. See Block Devices below for details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Iam<wbr>Instance<wbr>Profile<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name attribute of the IAM instance profile to associate
with launched instances.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Image<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The EC2 image ID to launch.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Instance<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The size of instance to launch.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Key<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The key name that should be used for the instance.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the launch configuration. If you leave
this blank, this provider will auto-generate a unique name.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<wbr>Prefix<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Creates a unique name beginning with the specified
prefix. Conflicts with `name`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Placement<wbr>Tenancy<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The tenancy of the instance. Valid values are
`&#34;default&#34;` or `&#34;dedicated&#34;`, see [AWS&#39;s Create Launch Configuration](http://docs.aws.amazon.com/AutoScaling/latest/APIReference/API_CreateLaunchConfiguration.html)
for more details
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Root<wbr>Block<wbr>Device<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchconfigurationrootblockdevice">Launch<wbr>Configuration<wbr>Root<wbr>Block<wbr>Device<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}Customize details about the root block
device of the instance. See Block Devices below for details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Security<wbr>Groups<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}A list of associated security group IDS.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Spot<wbr>Price<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The maximum price to use for reserving spot instances.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">User<wbr>Data<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The user data to provide when launching the instance. Do not pass gzip-compressed data via this argument; see `user_data_base64` instead.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">User<wbr>Data<wbr>Base64<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Can be used instead of `user_data` to pass base64-encoded binary data directly. Use this instead of `user_data` whenever the value is not a valid UTF-8 string. For example, gzip-encoded user data must be base64-encoded and passed via this argument to avoid corruption.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Vpc<wbr>Classic<wbr>Link<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ID of a ClassicLink-enabled VPC. Only applies to EC2-Classic instances. (eg. `vpc-2730681a`)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Vpc<wbr>Classic<wbr>Link<wbr>Security<wbr>Groups<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}The IDs of one or more security groups for the specified ClassicLink-enabled VPC (eg. `sg-46ae3d11`).
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Associate<wbr>Public<wbr>Ip<wbr>Address<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Associate a public ip address with an instance in a VPC.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ebs<wbr>Block<wbr>Devices<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchconfigurationebsblockdevice">[]Launch<wbr>Configuration<wbr>Ebs<wbr>Block<wbr>Device</a></span>
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
            title="Optional">Enable<wbr>Monitoring<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Enables/disables detailed monitoring. This is enabled by default.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ephemeral<wbr>Block<wbr>Devices<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchconfigurationephemeralblockdevice">[]Launch<wbr>Configuration<wbr>Ephemeral<wbr>Block<wbr>Device</a></span>
    </dt>
    <dd>{{% md %}}Customize Ephemeral (also known as
&#34;Instance Store&#34;) volumes on the instance. See Block Devices below for details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Iam<wbr>Instance<wbr>Profile<span class="property-indicator"></span>
        <span class="property-type">interface{}</span>
    </dt>
    <dd>{{% md %}}The name attribute of the IAM instance profile to associate
with launched instances.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Image<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The EC2 image ID to launch.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Instance<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The size of instance to launch.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Key<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The key name that should be used for the instance.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name of the launch configuration. If you leave
this blank, this provider will auto-generate a unique name.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<wbr>Prefix<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Creates a unique name beginning with the specified
prefix. Conflicts with `name`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Placement<wbr>Tenancy<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The tenancy of the instance. Valid values are
`&#34;default&#34;` or `&#34;dedicated&#34;`, see [AWS&#39;s Create Launch Configuration](http://docs.aws.amazon.com/AutoScaling/latest/APIReference/API_CreateLaunchConfiguration.html)
for more details
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Root<wbr>Block<wbr>Device<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchconfigurationrootblockdevice">*Launch<wbr>Configuration<wbr>Root<wbr>Block<wbr>Device</a></span>
    </dt>
    <dd>{{% md %}}Customize details about the root block
device of the instance. See Block Devices below for details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Security<wbr>Groups<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}A list of associated security group IDS.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Spot<wbr>Price<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The maximum price to use for reserving spot instances.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">User<wbr>Data<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The user data to provide when launching the instance. Do not pass gzip-compressed data via this argument; see `user_data_base64` instead.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">User<wbr>Data<wbr>Base64<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Can be used instead of `user_data` to pass base64-encoded binary data directly. Use this instead of `user_data` whenever the value is not a valid UTF-8 string. For example, gzip-encoded user data must be base64-encoded and passed via this argument to avoid corruption.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Vpc<wbr>Classic<wbr>Link<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The ID of a ClassicLink-enabled VPC. Only applies to EC2-Classic instances. (eg. `vpc-2730681a`)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Vpc<wbr>Classic<wbr>Link<wbr>Security<wbr>Groups<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}The IDs of one or more security groups for the specified ClassicLink-enabled VPC (eg. `sg-46ae3d11`).
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">associate<wbr>Public<wbr>Ip<wbr>Address<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Associate a public ip address with an instance in a VPC.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ebs<wbr>Block<wbr>Devices<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchconfigurationebsblockdevice">Launch<wbr>Configuration<wbr>Ebs<wbr>Block<wbr>Device[]?</a></span>
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
            title="Optional">enable<wbr>Monitoring<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Enables/disables detailed monitoring. This is enabled by default.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ephemeral<wbr>Block<wbr>Devices<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchconfigurationephemeralblockdevice">Launch<wbr>Configuration<wbr>Ephemeral<wbr>Block<wbr>Device[]?</a></span>
    </dt>
    <dd>{{% md %}}Customize Ephemeral (also known as
&#34;Instance Store&#34;) volumes on the instance. See Block Devices below for details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">iam<wbr>Instance<wbr>Profile<span class="property-indicator"></span>
        <span class="property-type">string | InstanceProfile</span>
    </dt>
    <dd>{{% md %}}The name attribute of the IAM instance profile to associate
with launched instances.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">image<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The EC2 image ID to launch.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">instance<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The size of instance to launch.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">key<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The key name that should be used for the instance.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the launch configuration. If you leave
this blank, this provider will auto-generate a unique name.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<wbr>Prefix<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Creates a unique name beginning with the specified
prefix. Conflicts with `name`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">placement<wbr>Tenancy<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The tenancy of the instance. Valid values are
`&#34;default&#34;` or `&#34;dedicated&#34;`, see [AWS&#39;s Create Launch Configuration](http://docs.aws.amazon.com/AutoScaling/latest/APIReference/API_CreateLaunchConfiguration.html)
for more details
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">root<wbr>Block<wbr>Device<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchconfigurationrootblockdevice">Launch<wbr>Configuration<wbr>Root<wbr>Block<wbr>Device?</a></span>
    </dt>
    <dd>{{% md %}}Customize details about the root block
device of the instance. See Block Devices below for details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">security<wbr>Groups<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}A list of associated security group IDS.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">spot<wbr>Price<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The maximum price to use for reserving spot instances.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">user<wbr>Data<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The user data to provide when launching the instance. Do not pass gzip-compressed data via this argument; see `user_data_base64` instead.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">user<wbr>Data<wbr>Base64<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Can be used instead of `user_data` to pass base64-encoded binary data directly. Use this instead of `user_data` whenever the value is not a valid UTF-8 string. For example, gzip-encoded user data must be base64-encoded and passed via this argument to avoid corruption.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">vpc<wbr>Classic<wbr>Link<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ID of a ClassicLink-enabled VPC. Only applies to EC2-Classic instances. (eg. `vpc-2730681a`)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">vpc<wbr>Classic<wbr>Link<wbr>Security<wbr>Groups<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}The IDs of one or more security groups for the specified ClassicLink-enabled VPC (eg. `sg-46ae3d11`).
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">associate_<wbr>public_<wbr>ip_<wbr>address<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Associate a public ip address with an instance in a VPC.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ebs_<wbr>block_<wbr>devices<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchconfigurationebsblockdevice">List[Launch<wbr>Configuration<wbr>Ebs<wbr>Block<wbr>Device]</a></span>
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
            title="Optional">enable_<wbr>monitoring<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Enables/disables detailed monitoring. This is enabled by default.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ephemeral_<wbr>block_<wbr>devices<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchconfigurationephemeralblockdevice">List[Launch<wbr>Configuration<wbr>Ephemeral<wbr>Block<wbr>Device]</a></span>
    </dt>
    <dd>{{% md %}}Customize Ephemeral (also known as
&#34;Instance Store&#34;) volumes on the instance. See Block Devices below for details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">iam_<wbr>instance_<wbr>profile<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}The name attribute of the IAM instance profile to associate
with launched instances.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">image_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The EC2 image ID to launch.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">instance_<wbr>type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The size of instance to launch.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">key_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The key name that should be used for the instance.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the launch configuration. If you leave
this blank, this provider will auto-generate a unique name.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name_<wbr>prefix<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Creates a unique name beginning with the specified
prefix. Conflicts with `name`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">placement_<wbr>tenancy<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The tenancy of the instance. Valid values are
`&#34;default&#34;` or `&#34;dedicated&#34;`, see [AWS&#39;s Create Launch Configuration](http://docs.aws.amazon.com/AutoScaling/latest/APIReference/API_CreateLaunchConfiguration.html)
for more details
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">root_<wbr>block_<wbr>device<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchconfigurationrootblockdevice">Dict[Launch<wbr>Configuration<wbr>Root<wbr>Block<wbr>Device]</a></span>
    </dt>
    <dd>{{% md %}}Customize details about the root block
device of the instance. See Block Devices below for details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">security_<wbr>groups<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}A list of associated security group IDS.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">spot_<wbr>price<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The maximum price to use for reserving spot instances.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">user_<wbr>data<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The user data to provide when launching the instance. Do not pass gzip-compressed data via this argument; see `user_data_base64` instead.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">user_<wbr>data_<wbr>base64<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Can be used instead of `user_data` to pass base64-encoded binary data directly. Use this instead of `user_data` whenever the value is not a valid UTF-8 string. For example, gzip-encoded user data must be base64-encoded and passed via this argument to avoid corruption.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">vpc_<wbr>classic_<wbr>link_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ID of a ClassicLink-enabled VPC. Only applies to EC2-Classic instances. (eg. `vpc-2730681a`)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">vpc_<wbr>classic_<wbr>link_<wbr>security_<wbr>groups<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}The IDs of one or more security groups for the specified ClassicLink-enabled VPC (eg. `sg-46ae3d11`).
{{% /md %}}</dd>

</dl>
{{% /choosable %}}




## LaunchConfiguration Output Properties

The following output properties are available:




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Amazon Resource Name of the launch configuration.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Associate<wbr>Public<wbr>Ip<wbr>Address<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Associate a public ip address with an instance in a VPC.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Ebs<wbr>Block<wbr>Devices<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchconfigurationebsblockdevice">List&lt;Launch<wbr>Configuration<wbr>Ebs<wbr>Block<wbr>Device&gt;</a></span>
    </dt>
    <dd>{{% md %}}Additional EBS block devices to attach to the
instance.  See Block Devices below for details.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Ebs<wbr>Optimized<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}If true, the launched EC2 instance will be EBS-optimized.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Enable<wbr>Monitoring<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Enables/disables detailed monitoring. This is enabled by default.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Ephemeral<wbr>Block<wbr>Devices<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchconfigurationephemeralblockdevice">List&lt;Launch<wbr>Configuration<wbr>Ephemeral<wbr>Block<wbr>Device&gt;?</a></span>
    </dt>
    <dd>{{% md %}}Customize Ephemeral (also known as
&#34;Instance Store&#34;) volumes on the instance. See Block Devices below for details.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Iam<wbr>Instance<wbr>Profile<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name attribute of the IAM instance profile to associate
with launched instances.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Image<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The EC2 image ID to launch.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Instance<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The size of instance to launch.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Key<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The key name that should be used for the instance.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the launch configuration. If you leave
this blank, this provider will auto-generate a unique name.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Name<wbr>Prefix<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Creates a unique name beginning with the specified
prefix. Conflicts with `name`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Placement<wbr>Tenancy<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The tenancy of the instance. Valid values are
`&#34;default&#34;` or `&#34;dedicated&#34;`, see [AWS&#39;s Create Launch Configuration](http://docs.aws.amazon.com/AutoScaling/latest/APIReference/API_CreateLaunchConfiguration.html)
for more details
{{% /md %}}</dd>

    <dt class="property-"
            title="">Root<wbr>Block<wbr>Device<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchconfigurationrootblockdevice">Launch<wbr>Configuration<wbr>Root<wbr>Block<wbr>Device</a></span>
    </dt>
    <dd>{{% md %}}Customize details about the root block
device of the instance. See Block Devices below for details.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Security<wbr>Groups<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}A list of associated security group IDS.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Spot<wbr>Price<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The maximum price to use for reserving spot instances.
{{% /md %}}</dd>

    <dt class="property-"
            title="">User<wbr>Data<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The user data to provide when launching the instance. Do not pass gzip-compressed data via this argument; see `user_data_base64` instead.
{{% /md %}}</dd>

    <dt class="property-"
            title="">User<wbr>Data<wbr>Base64<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Can be used instead of `user_data` to pass base64-encoded binary data directly. Use this instead of `user_data` whenever the value is not a valid UTF-8 string. For example, gzip-encoded user data must be base64-encoded and passed via this argument to avoid corruption.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Vpc<wbr>Classic<wbr>Link<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ID of a ClassicLink-enabled VPC. Only applies to EC2-Classic instances. (eg. `vpc-2730681a`)
{{% /md %}}</dd>

    <dt class="property-"
            title="">Vpc<wbr>Classic<wbr>Link<wbr>Security<wbr>Groups<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}The IDs of one or more security groups for the specified ClassicLink-enabled VPC (eg. `sg-46ae3d11`).
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Amazon Resource Name of the launch configuration.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Associate<wbr>Public<wbr>Ip<wbr>Address<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Associate a public ip address with an instance in a VPC.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Ebs<wbr>Block<wbr>Devices<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchconfigurationebsblockdevice">[]Launch<wbr>Configuration<wbr>Ebs<wbr>Block<wbr>Device</a></span>
    </dt>
    <dd>{{% md %}}Additional EBS block devices to attach to the
instance.  See Block Devices below for details.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Ebs<wbr>Optimized<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}If true, the launched EC2 instance will be EBS-optimized.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Enable<wbr>Monitoring<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Enables/disables detailed monitoring. This is enabled by default.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Ephemeral<wbr>Block<wbr>Devices<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchconfigurationephemeralblockdevice">[]Launch<wbr>Configuration<wbr>Ephemeral<wbr>Block<wbr>Device</a></span>
    </dt>
    <dd>{{% md %}}Customize Ephemeral (also known as
&#34;Instance Store&#34;) volumes on the instance. See Block Devices below for details.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Iam<wbr>Instance<wbr>Profile<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name attribute of the IAM instance profile to associate
with launched instances.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Image<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The EC2 image ID to launch.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Instance<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The size of instance to launch.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Key<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The key name that should be used for the instance.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the launch configuration. If you leave
this blank, this provider will auto-generate a unique name.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Name<wbr>Prefix<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Creates a unique name beginning with the specified
prefix. Conflicts with `name`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Placement<wbr>Tenancy<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The tenancy of the instance. Valid values are
`&#34;default&#34;` or `&#34;dedicated&#34;`, see [AWS&#39;s Create Launch Configuration](http://docs.aws.amazon.com/AutoScaling/latest/APIReference/API_CreateLaunchConfiguration.html)
for more details
{{% /md %}}</dd>

    <dt class="property-"
            title="">Root<wbr>Block<wbr>Device<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchconfigurationrootblockdevice">Launch<wbr>Configuration<wbr>Root<wbr>Block<wbr>Device</a></span>
    </dt>
    <dd>{{% md %}}Customize details about the root block
device of the instance. See Block Devices below for details.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Security<wbr>Groups<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}A list of associated security group IDS.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Spot<wbr>Price<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The maximum price to use for reserving spot instances.
{{% /md %}}</dd>

    <dt class="property-"
            title="">User<wbr>Data<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The user data to provide when launching the instance. Do not pass gzip-compressed data via this argument; see `user_data_base64` instead.
{{% /md %}}</dd>

    <dt class="property-"
            title="">User<wbr>Data<wbr>Base64<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Can be used instead of `user_data` to pass base64-encoded binary data directly. Use this instead of `user_data` whenever the value is not a valid UTF-8 string. For example, gzip-encoded user data must be base64-encoded and passed via this argument to avoid corruption.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Vpc<wbr>Classic<wbr>Link<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The ID of a ClassicLink-enabled VPC. Only applies to EC2-Classic instances. (eg. `vpc-2730681a`)
{{% /md %}}</dd>

    <dt class="property-"
            title="">Vpc<wbr>Classic<wbr>Link<wbr>Security<wbr>Groups<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}The IDs of one or more security groups for the specified ClassicLink-enabled VPC (eg. `sg-46ae3d11`).
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Amazon Resource Name of the launch configuration.
{{% /md %}}</dd>

    <dt class="property-"
            title="">associate<wbr>Public<wbr>Ip<wbr>Address<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Associate a public ip address with an instance in a VPC.
{{% /md %}}</dd>

    <dt class="property-"
            title="">ebs<wbr>Block<wbr>Devices<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchconfigurationebsblockdevice">Launch<wbr>Configuration<wbr>Ebs<wbr>Block<wbr>Device[]</a></span>
    </dt>
    <dd>{{% md %}}Additional EBS block devices to attach to the
instance.  See Block Devices below for details.
{{% /md %}}</dd>

    <dt class="property-"
            title="">ebs<wbr>Optimized<span class="property-indicator"></span>
        <span class="property-type">boolean</span>
    </dt>
    <dd>{{% md %}}If true, the launched EC2 instance will be EBS-optimized.
{{% /md %}}</dd>

    <dt class="property-"
            title="">enable<wbr>Monitoring<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Enables/disables detailed monitoring. This is enabled by default.
{{% /md %}}</dd>

    <dt class="property-"
            title="">ephemeral<wbr>Block<wbr>Devices<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchconfigurationephemeralblockdevice">Launch<wbr>Configuration<wbr>Ephemeral<wbr>Block<wbr>Device[]?</a></span>
    </dt>
    <dd>{{% md %}}Customize Ephemeral (also known as
&#34;Instance Store&#34;) volumes on the instance. See Block Devices below for details.
{{% /md %}}</dd>

    <dt class="property-"
            title="">iam<wbr>Instance<wbr>Profile<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name attribute of the IAM instance profile to associate
with launched instances.
{{% /md %}}</dd>

    <dt class="property-"
            title="">image<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The EC2 image ID to launch.
{{% /md %}}</dd>

    <dt class="property-"
            title="">instance<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The size of instance to launch.
{{% /md %}}</dd>

    <dt class="property-"
            title="">key<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The key name that should be used for the instance.
{{% /md %}}</dd>

    <dt class="property-"
            title="">name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the launch configuration. If you leave
this blank, this provider will auto-generate a unique name.
{{% /md %}}</dd>

    <dt class="property-"
            title="">name<wbr>Prefix<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Creates a unique name beginning with the specified
prefix. Conflicts with `name`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">placement<wbr>Tenancy<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The tenancy of the instance. Valid values are
`&#34;default&#34;` or `&#34;dedicated&#34;`, see [AWS&#39;s Create Launch Configuration](http://docs.aws.amazon.com/AutoScaling/latest/APIReference/API_CreateLaunchConfiguration.html)
for more details
{{% /md %}}</dd>

    <dt class="property-"
            title="">root<wbr>Block<wbr>Device<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchconfigurationrootblockdevice">Launch<wbr>Configuration<wbr>Root<wbr>Block<wbr>Device</a></span>
    </dt>
    <dd>{{% md %}}Customize details about the root block
device of the instance. See Block Devices below for details.
{{% /md %}}</dd>

    <dt class="property-"
            title="">security<wbr>Groups<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}A list of associated security group IDS.
{{% /md %}}</dd>

    <dt class="property-"
            title="">spot<wbr>Price<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The maximum price to use for reserving spot instances.
{{% /md %}}</dd>

    <dt class="property-"
            title="">user<wbr>Data<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The user data to provide when launching the instance. Do not pass gzip-compressed data via this argument; see `user_data_base64` instead.
{{% /md %}}</dd>

    <dt class="property-"
            title="">user<wbr>Data<wbr>Base64<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Can be used instead of `user_data` to pass base64-encoded binary data directly. Use this instead of `user_data` whenever the value is not a valid UTF-8 string. For example, gzip-encoded user data must be base64-encoded and passed via this argument to avoid corruption.
{{% /md %}}</dd>

    <dt class="property-"
            title="">vpc<wbr>Classic<wbr>Link<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ID of a ClassicLink-enabled VPC. Only applies to EC2-Classic instances. (eg. `vpc-2730681a`)
{{% /md %}}</dd>

    <dt class="property-"
            title="">vpc<wbr>Classic<wbr>Link<wbr>Security<wbr>Groups<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}The IDs of one or more security groups for the specified ClassicLink-enabled VPC (eg. `sg-46ae3d11`).
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The Amazon Resource Name of the launch configuration.
{{% /md %}}</dd>

    <dt class="property-"
            title="">associate_<wbr>public_<wbr>ip_<wbr>address<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Associate a public ip address with an instance in a VPC.
{{% /md %}}</dd>

    <dt class="property-"
            title="">ebs_<wbr>block_<wbr>devices<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchconfigurationebsblockdevice">List[Launch<wbr>Configuration<wbr>Ebs<wbr>Block<wbr>Device]</a></span>
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
            title="">enable_<wbr>monitoring<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Enables/disables detailed monitoring. This is enabled by default.
{{% /md %}}</dd>

    <dt class="property-"
            title="">ephemeral_<wbr>block_<wbr>devices<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchconfigurationephemeralblockdevice">List[Launch<wbr>Configuration<wbr>Ephemeral<wbr>Block<wbr>Device]</a></span>
    </dt>
    <dd>{{% md %}}Customize Ephemeral (also known as
&#34;Instance Store&#34;) volumes on the instance. See Block Devices below for details.
{{% /md %}}</dd>

    <dt class="property-"
            title="">iam_<wbr>instance_<wbr>profile<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name attribute of the IAM instance profile to associate
with launched instances.
{{% /md %}}</dd>

    <dt class="property-"
            title="">image_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The EC2 image ID to launch.
{{% /md %}}</dd>

    <dt class="property-"
            title="">instance_<wbr>type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The size of instance to launch.
{{% /md %}}</dd>

    <dt class="property-"
            title="">key_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The key name that should be used for the instance.
{{% /md %}}</dd>

    <dt class="property-"
            title="">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the launch configuration. If you leave
this blank, this provider will auto-generate a unique name.
{{% /md %}}</dd>

    <dt class="property-"
            title="">name_<wbr>prefix<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Creates a unique name beginning with the specified
prefix. Conflicts with `name`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">placement_<wbr>tenancy<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The tenancy of the instance. Valid values are
`&#34;default&#34;` or `&#34;dedicated&#34;`, see [AWS&#39;s Create Launch Configuration](http://docs.aws.amazon.com/AutoScaling/latest/APIReference/API_CreateLaunchConfiguration.html)
for more details
{{% /md %}}</dd>

    <dt class="property-"
            title="">root_<wbr>block_<wbr>device<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchconfigurationrootblockdevice">Dict[Launch<wbr>Configuration<wbr>Root<wbr>Block<wbr>Device]</a></span>
    </dt>
    <dd>{{% md %}}Customize details about the root block
device of the instance. See Block Devices below for details.
{{% /md %}}</dd>

    <dt class="property-"
            title="">security_<wbr>groups<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}A list of associated security group IDS.
{{% /md %}}</dd>

    <dt class="property-"
            title="">spot_<wbr>price<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The maximum price to use for reserving spot instances.
{{% /md %}}</dd>

    <dt class="property-"
            title="">user_<wbr>data<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The user data to provide when launching the instance. Do not pass gzip-compressed data via this argument; see `user_data_base64` instead.
{{% /md %}}</dd>

    <dt class="property-"
            title="">user_<wbr>data_<wbr>base64<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Can be used instead of `user_data` to pass base64-encoded binary data directly. Use this instead of `user_data` whenever the value is not a valid UTF-8 string. For example, gzip-encoded user data must be base64-encoded and passed via this argument to avoid corruption.
{{% /md %}}</dd>

    <dt class="property-"
            title="">vpc_<wbr>classic_<wbr>link_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ID of a ClassicLink-enabled VPC. Only applies to EC2-Classic instances. (eg. `vpc-2730681a`)
{{% /md %}}</dd>

    <dt class="property-"
            title="">vpc_<wbr>classic_<wbr>link_<wbr>security_<wbr>groups<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}The IDs of one or more security groups for the specified ClassicLink-enabled VPC (eg. `sg-46ae3d11`).
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





## Look up an Existing LaunchConfiguration Resource

{{< chooser language "javascript,typescript,python,go,csharp  " / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">pulumi.Input&lt;pulumi.ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/ec2/#LaunchConfigurationState">LaunchConfigurationState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/ec2/#LaunchConfiguration">LaunchConfiguration</a></span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>arn=None<span class="p">, </span>associate_public_ip_address=None<span class="p">, </span>ebs_block_devices=None<span class="p">, </span>ebs_optimized=None<span class="p">, </span>enable_monitoring=None<span class="p">, </span>ephemeral_block_devices=None<span class="p">, </span>iam_instance_profile=None<span class="p">, </span>image_id=None<span class="p">, </span>instance_type=None<span class="p">, </span>key_name=None<span class="p">, </span>name=None<span class="p">, </span>name_prefix=None<span class="p">, </span>placement_tenancy=None<span class="p">, </span>root_block_device=None<span class="p">, </span>security_groups=None<span class="p">, </span>spot_price=None<span class="p">, </span>user_data=None<span class="p">, </span>user_data_base64=None<span class="p">, </span>vpc_classic_link_id=None<span class="p">, </span>vpc_classic_link_security_groups=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetLaunchConfiguration<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">pulumi.IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ec2?tab=doc#LaunchConfigurationState">LaunchConfigurationState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ec2?tab=doc#LaunchConfiguration">LaunchConfiguration</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ec2.LaunchConfiguration.html">LaunchConfiguration</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Pulumi.Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ec2.LaunchConfigurationState.html">LaunchConfigurationState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
{{% /choosable %}}

Get an existing LaunchConfiguration resource's state with the given name, ID, and optional extra properties used to qualify the lookup.

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
    <dd>{{% md %}}The Amazon Resource Name of the launch configuration.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Associate<wbr>Public<wbr>Ip<wbr>Address<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Associate a public ip address with an instance in a VPC.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ebs<wbr>Block<wbr>Devices<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchconfigurationebsblockdevice">List&lt;Launch<wbr>Configuration<wbr>Ebs<wbr>Block<wbr>Device<wbr>Args&gt;?</a></span>
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
            title="Optional">Enable<wbr>Monitoring<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Enables/disables detailed monitoring. This is enabled by default.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ephemeral<wbr>Block<wbr>Devices<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchconfigurationephemeralblockdevice">List&lt;Launch<wbr>Configuration<wbr>Ephemeral<wbr>Block<wbr>Device<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}Customize Ephemeral (also known as
&#34;Instance Store&#34;) volumes on the instance. See Block Devices below for details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Iam<wbr>Instance<wbr>Profile<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name attribute of the IAM instance profile to associate
with launched instances.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Image<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The EC2 image ID to launch.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Instance<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The size of instance to launch.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Key<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The key name that should be used for the instance.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the launch configuration. If you leave
this blank, this provider will auto-generate a unique name.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<wbr>Prefix<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Creates a unique name beginning with the specified
prefix. Conflicts with `name`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Placement<wbr>Tenancy<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The tenancy of the instance. Valid values are
`&#34;default&#34;` or `&#34;dedicated&#34;`, see [AWS&#39;s Create Launch Configuration](http://docs.aws.amazon.com/AutoScaling/latest/APIReference/API_CreateLaunchConfiguration.html)
for more details
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Root<wbr>Block<wbr>Device<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchconfigurationrootblockdevice">Launch<wbr>Configuration<wbr>Root<wbr>Block<wbr>Device<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}Customize details about the root block
device of the instance. See Block Devices below for details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Security<wbr>Groups<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}A list of associated security group IDS.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Spot<wbr>Price<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The maximum price to use for reserving spot instances.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">User<wbr>Data<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The user data to provide when launching the instance. Do not pass gzip-compressed data via this argument; see `user_data_base64` instead.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">User<wbr>Data<wbr>Base64<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Can be used instead of `user_data` to pass base64-encoded binary data directly. Use this instead of `user_data` whenever the value is not a valid UTF-8 string. For example, gzip-encoded user data must be base64-encoded and passed via this argument to avoid corruption.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Vpc<wbr>Classic<wbr>Link<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ID of a ClassicLink-enabled VPC. Only applies to EC2-Classic instances. (eg. `vpc-2730681a`)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Vpc<wbr>Classic<wbr>Link<wbr>Security<wbr>Groups<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}The IDs of one or more security groups for the specified ClassicLink-enabled VPC (eg. `sg-46ae3d11`).
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The Amazon Resource Name of the launch configuration.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Associate<wbr>Public<wbr>Ip<wbr>Address<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Associate a public ip address with an instance in a VPC.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ebs<wbr>Block<wbr>Devices<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchconfigurationebsblockdevice">[]Launch<wbr>Configuration<wbr>Ebs<wbr>Block<wbr>Device</a></span>
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
            title="Optional">Enable<wbr>Monitoring<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Enables/disables detailed monitoring. This is enabled by default.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ephemeral<wbr>Block<wbr>Devices<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchconfigurationephemeralblockdevice">[]Launch<wbr>Configuration<wbr>Ephemeral<wbr>Block<wbr>Device</a></span>
    </dt>
    <dd>{{% md %}}Customize Ephemeral (also known as
&#34;Instance Store&#34;) volumes on the instance. See Block Devices below for details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Iam<wbr>Instance<wbr>Profile<span class="property-indicator"></span>
        <span class="property-type">interface{}</span>
    </dt>
    <dd>{{% md %}}The name attribute of the IAM instance profile to associate
with launched instances.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Image<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The EC2 image ID to launch.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Instance<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The size of instance to launch.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Key<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The key name that should be used for the instance.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name of the launch configuration. If you leave
this blank, this provider will auto-generate a unique name.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<wbr>Prefix<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Creates a unique name beginning with the specified
prefix. Conflicts with `name`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Placement<wbr>Tenancy<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The tenancy of the instance. Valid values are
`&#34;default&#34;` or `&#34;dedicated&#34;`, see [AWS&#39;s Create Launch Configuration](http://docs.aws.amazon.com/AutoScaling/latest/APIReference/API_CreateLaunchConfiguration.html)
for more details
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Root<wbr>Block<wbr>Device<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchconfigurationrootblockdevice">*Launch<wbr>Configuration<wbr>Root<wbr>Block<wbr>Device</a></span>
    </dt>
    <dd>{{% md %}}Customize details about the root block
device of the instance. See Block Devices below for details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Security<wbr>Groups<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}A list of associated security group IDS.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Spot<wbr>Price<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The maximum price to use for reserving spot instances.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">User<wbr>Data<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The user data to provide when launching the instance. Do not pass gzip-compressed data via this argument; see `user_data_base64` instead.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">User<wbr>Data<wbr>Base64<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Can be used instead of `user_data` to pass base64-encoded binary data directly. Use this instead of `user_data` whenever the value is not a valid UTF-8 string. For example, gzip-encoded user data must be base64-encoded and passed via this argument to avoid corruption.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Vpc<wbr>Classic<wbr>Link<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The ID of a ClassicLink-enabled VPC. Only applies to EC2-Classic instances. (eg. `vpc-2730681a`)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Vpc<wbr>Classic<wbr>Link<wbr>Security<wbr>Groups<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}The IDs of one or more security groups for the specified ClassicLink-enabled VPC (eg. `sg-46ae3d11`).
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The Amazon Resource Name of the launch configuration.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">associate<wbr>Public<wbr>Ip<wbr>Address<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Associate a public ip address with an instance in a VPC.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ebs<wbr>Block<wbr>Devices<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchconfigurationebsblockdevice">Launch<wbr>Configuration<wbr>Ebs<wbr>Block<wbr>Device[]?</a></span>
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
            title="Optional">enable<wbr>Monitoring<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Enables/disables detailed monitoring. This is enabled by default.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ephemeral<wbr>Block<wbr>Devices<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchconfigurationephemeralblockdevice">Launch<wbr>Configuration<wbr>Ephemeral<wbr>Block<wbr>Device[]?</a></span>
    </dt>
    <dd>{{% md %}}Customize Ephemeral (also known as
&#34;Instance Store&#34;) volumes on the instance. See Block Devices below for details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">iam<wbr>Instance<wbr>Profile<span class="property-indicator"></span>
        <span class="property-type">string | InstanceProfile</span>
    </dt>
    <dd>{{% md %}}The name attribute of the IAM instance profile to associate
with launched instances.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">image<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The EC2 image ID to launch.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">instance<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The size of instance to launch.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">key<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The key name that should be used for the instance.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the launch configuration. If you leave
this blank, this provider will auto-generate a unique name.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<wbr>Prefix<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Creates a unique name beginning with the specified
prefix. Conflicts with `name`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">placement<wbr>Tenancy<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The tenancy of the instance. Valid values are
`&#34;default&#34;` or `&#34;dedicated&#34;`, see [AWS&#39;s Create Launch Configuration](http://docs.aws.amazon.com/AutoScaling/latest/APIReference/API_CreateLaunchConfiguration.html)
for more details
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">root<wbr>Block<wbr>Device<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchconfigurationrootblockdevice">Launch<wbr>Configuration<wbr>Root<wbr>Block<wbr>Device?</a></span>
    </dt>
    <dd>{{% md %}}Customize details about the root block
device of the instance. See Block Devices below for details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">security<wbr>Groups<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}A list of associated security group IDS.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">spot<wbr>Price<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The maximum price to use for reserving spot instances.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">user<wbr>Data<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The user data to provide when launching the instance. Do not pass gzip-compressed data via this argument; see `user_data_base64` instead.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">user<wbr>Data<wbr>Base64<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Can be used instead of `user_data` to pass base64-encoded binary data directly. Use this instead of `user_data` whenever the value is not a valid UTF-8 string. For example, gzip-encoded user data must be base64-encoded and passed via this argument to avoid corruption.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">vpc<wbr>Classic<wbr>Link<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ID of a ClassicLink-enabled VPC. Only applies to EC2-Classic instances. (eg. `vpc-2730681a`)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">vpc<wbr>Classic<wbr>Link<wbr>Security<wbr>Groups<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}The IDs of one or more security groups for the specified ClassicLink-enabled VPC (eg. `sg-46ae3d11`).
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The Amazon Resource Name of the launch configuration.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">associate_<wbr>public_<wbr>ip_<wbr>address<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Associate a public ip address with an instance in a VPC.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ebs_<wbr>block_<wbr>devices<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchconfigurationebsblockdevice">List[Launch<wbr>Configuration<wbr>Ebs<wbr>Block<wbr>Device]</a></span>
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
            title="Optional">enable_<wbr>monitoring<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Enables/disables detailed monitoring. This is enabled by default.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ephemeral_<wbr>block_<wbr>devices<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchconfigurationephemeralblockdevice">List[Launch<wbr>Configuration<wbr>Ephemeral<wbr>Block<wbr>Device]</a></span>
    </dt>
    <dd>{{% md %}}Customize Ephemeral (also known as
&#34;Instance Store&#34;) volumes on the instance. See Block Devices below for details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">iam_<wbr>instance_<wbr>profile<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}The name attribute of the IAM instance profile to associate
with launched instances.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">image_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The EC2 image ID to launch.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">instance_<wbr>type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The size of instance to launch.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">key_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The key name that should be used for the instance.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the launch configuration. If you leave
this blank, this provider will auto-generate a unique name.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name_<wbr>prefix<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Creates a unique name beginning with the specified
prefix. Conflicts with `name`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">placement_<wbr>tenancy<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The tenancy of the instance. Valid values are
`&#34;default&#34;` or `&#34;dedicated&#34;`, see [AWS&#39;s Create Launch Configuration](http://docs.aws.amazon.com/AutoScaling/latest/APIReference/API_CreateLaunchConfiguration.html)
for more details
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">root_<wbr>block_<wbr>device<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchconfigurationrootblockdevice">Dict[Launch<wbr>Configuration<wbr>Root<wbr>Block<wbr>Device]</a></span>
    </dt>
    <dd>{{% md %}}Customize details about the root block
device of the instance. See Block Devices below for details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">security_<wbr>groups<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}A list of associated security group IDS.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">spot_<wbr>price<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The maximum price to use for reserving spot instances.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">user_<wbr>data<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The user data to provide when launching the instance. Do not pass gzip-compressed data via this argument; see `user_data_base64` instead.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">user_<wbr>data_<wbr>base64<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Can be used instead of `user_data` to pass base64-encoded binary data directly. Use this instead of `user_data` whenever the value is not a valid UTF-8 string. For example, gzip-encoded user data must be base64-encoded and passed via this argument to avoid corruption.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">vpc_<wbr>classic_<wbr>link_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ID of a ClassicLink-enabled VPC. Only applies to EC2-Classic instances. (eg. `vpc-2730681a`)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">vpc_<wbr>classic_<wbr>link_<wbr>security_<wbr>groups<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}The IDs of one or more security groups for the specified ClassicLink-enabled VPC (eg. `sg-46ae3d11`).
{{% /md %}}</dd>

</dl>
{{% /choosable %}}







## Supporting Types

#### LaunchConfigurationEbsBlockDevice
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#LaunchConfigurationEbsBlockDevice">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#LaunchConfigurationEbsBlockDevice">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ec2?tab=doc#LaunchConfigurationEbsBlockDeviceArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ec2?tab=doc#LaunchConfigurationEbsBlockDeviceOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ec2.LaunchConfigurationEbsBlockDeviceArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ec2.LaunchConfigurationEbsBlockDevice.html">output</a> API doc for this type.
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
            title="Optional">No<wbr>Device<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
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
            title="Optional">No<wbr>Device<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
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
            title="Optional">no<wbr>Device<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
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
            title="Optional">no<wbr>Device<span class="property-indicator"></span>
        <span class="property-type">bool</span>
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





#### LaunchConfigurationEphemeralBlockDevice
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#LaunchConfigurationEphemeralBlockDevice">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#LaunchConfigurationEphemeralBlockDevice">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ec2?tab=doc#LaunchConfigurationEphemeralBlockDeviceArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ec2?tab=doc#LaunchConfigurationEphemeralBlockDeviceOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ec2.LaunchConfigurationEphemeralBlockDeviceArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ec2.LaunchConfigurationEphemeralBlockDevice.html">output</a> API doc for this type.
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





#### LaunchConfigurationRootBlockDevice
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#LaunchConfigurationRootBlockDevice">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#LaunchConfigurationRootBlockDevice">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ec2?tab=doc#LaunchConfigurationRootBlockDeviceArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ec2?tab=doc#LaunchConfigurationRootBlockDeviceOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ec2.LaunchConfigurationRootBlockDeviceArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ec2.LaunchConfigurationRootBlockDevice.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Delete<wbr>On<wbr>Termination<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
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








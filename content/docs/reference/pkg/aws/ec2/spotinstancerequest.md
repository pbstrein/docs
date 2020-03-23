
---
title: "SpotInstanceRequest"
block_external_search_index: true
---

Provides an EC2 Spot Instance Request resource. This allows instances to be
requested on the spot market.

By default this provider creates Spot Instance Requests with a `persistent` type,
which means that for the duration of their lifetime, AWS will launch an
instance with the configured details if and when the spot market will accept
the requested price.

On destruction, this provider will make an attempt to terminate the associated Spot
Instance if there is one present.

Spot Instances requests with a `one-time` type will close the spot request
when the instance is terminated either by the request being below the current spot
price availability or by a user.

> **NOTE:** Because their behavior depends on the live status of the spot
market, Spot Instance Requests have a unique lifecycle that makes them behave
differently than other resources. Most importantly: there is __no
guarantee__ that a Spot Instance exists to fulfill the request at any given
point in time. See the [AWS Spot Instance
documentation](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/using-spot-instances.html)
for more information.


## Example Usage

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

// Request a spot instance at $0.03
const cheapWorker = new aws.ec2.SpotInstanceRequest("cheap_worker", {
    ami: "ami-1234",
    instanceType: "c4.xlarge",
    spotPrice: "0.03",
    tags: {
        Name: "CheapWorker",
    },
});
```

> This content is derived from https://github.com/terraform-providers/terraform-provider-aws/blob/master/website/docs/r/spot_instance_request.html.markdown.



## Create a SpotInstanceRequest Resource

{{< chooser language "javascript,typescript,python,go,csharp" / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/ec2/#SpotInstanceRequest">SpotInstanceRequest</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/ec2/#SpotInstanceRequestArgs">SpotInstanceRequestArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">SpotInstanceRequest</span><span class="p">(resource_name, opts=None, </span>ami=None<span class="p">, </span>associate_public_ip_address=None<span class="p">, </span>availability_zone=None<span class="p">, </span>block_duration_minutes=None<span class="p">, </span>cpu_core_count=None<span class="p">, </span>cpu_threads_per_core=None<span class="p">, </span>credit_specification=None<span class="p">, </span>disable_api_termination=None<span class="p">, </span>ebs_block_devices=None<span class="p">, </span>ebs_optimized=None<span class="p">, </span>ephemeral_block_devices=None<span class="p">, </span>get_password_data=None<span class="p">, </span>hibernation=None<span class="p">, </span>host_id=None<span class="p">, </span>iam_instance_profile=None<span class="p">, </span>instance_initiated_shutdown_behavior=None<span class="p">, </span>instance_interruption_behaviour=None<span class="p">, </span>instance_type=None<span class="p">, </span>ipv6_address_count=None<span class="p">, </span>ipv6_addresses=None<span class="p">, </span>key_name=None<span class="p">, </span>launch_group=None<span class="p">, </span>monitoring=None<span class="p">, </span>network_interfaces=None<span class="p">, </span>placement_group=None<span class="p">, </span>private_ip=None<span class="p">, </span>root_block_device=None<span class="p">, </span>security_groups=None<span class="p">, </span>source_dest_check=None<span class="p">, </span>spot_price=None<span class="p">, </span>spot_type=None<span class="p">, </span>subnet_id=None<span class="p">, </span>tags=None<span class="p">, </span>tenancy=None<span class="p">, </span>user_data=None<span class="p">, </span>user_data_base64=None<span class="p">, </span>valid_from=None<span class="p">, </span>valid_until=None<span class="p">, </span>volume_tags=None<span class="p">, </span>vpc_security_group_ids=None<span class="p">, </span>wait_for_fulfillment=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewSpotInstanceRequest<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ec2?tab=doc#SpotInstanceRequestArgs">SpotInstanceRequestArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ec2?tab=doc#SpotInstanceRequest">SpotInstanceRequest</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ec2.SpotInstanceRequest.html">SpotInstanceRequest</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ec2.SpotInstanceRequestArgs.html">SpotInstanceRequestArgs</a></span> <span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
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

    <dt class="property-required"
            title="Required">Ami<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The AMI to use for the instance.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Associate<wbr>Public<wbr>Ip<wbr>Address<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Associate a public ip address with an instance in a VPC.  Boolean value.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Availability<wbr>Zone<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The AZ to start the instance in.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Block<wbr>Duration<wbr>Minutes<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The required duration for the Spot instances, in minutes. This value must be a multiple of 60 (60, 120, 180, 240, 300, or 360).
The duration period starts as soon as your Spot instance receives its instance ID. At the end of the duration period, Amazon EC2 marks the Spot instance for termination and provides a Spot instance termination notice, which gives the instance a two-minute warning before it terminates.
Note that you can&#39;t specify an Availability Zone group or a launch group if you specify a duration.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Cpu<wbr>Core<wbr>Count<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}Sets the number of CPU cores for an instance. This option is
only supported on creation of instance type that support CPU Options
[CPU Cores and Threads Per CPU Core Per Instance Type](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/instance-optimize-cpu.html#cpu-options-supported-instances-values) - specifying this option for unsupported instance types will return an error from the EC2 API.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Cpu<wbr>Threads<wbr>Per<wbr>Core<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}If set to to 1, hyperthreading is disabled on the launched instance. Defaults to 2 if not set. See [Optimizing CPU Options](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/instance-optimize-cpu.html) for more information.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Credit<wbr>Specification<span class="property-indicator"></span>
        <span class="property-type"><a href="#spotinstancerequestcreditspecification">Spot<wbr>Instance<wbr>Request<wbr>Credit<wbr>Specification<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}Customize the credit specification of the instance. See Credit Specification below for more details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Disable<wbr>Api<wbr>Termination<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}If true, enables [EC2 Instance
Termination Protection](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/terminating-instances.html#Using_ChangingDisableAPITermination)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ebs<wbr>Block<wbr>Devices<span class="property-indicator"></span>
        <span class="property-type"><a href="#spotinstancerequestebsblockdevice">List&lt;Spot<wbr>Instance<wbr>Request<wbr>Ebs<wbr>Block<wbr>Device<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}Additional EBS block devices to attach to the
instance.  Block device configurations only apply on resource creation. See Block Devices below for details on attributes and drift detection.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ebs<wbr>Optimized<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}If true, the launched EC2 instance will be EBS-optimized.
Note that if this is not set on an instance type that is optimized by default then
this will show as disabled but if the instance type is optimized by default then
there is no need to set this and there is no effect to disabling it.
See the [EBS Optimized section](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/EBSOptimized.html) of the AWS User Guide for more information.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ephemeral<wbr>Block<wbr>Devices<span class="property-indicator"></span>
        <span class="property-type"><a href="#spotinstancerequestephemeralblockdevice">List&lt;Spot<wbr>Instance<wbr>Request<wbr>Ephemeral<wbr>Block<wbr>Device<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}Customize Ephemeral (also known as
&#34;Instance Store&#34;) volumes on the instance. See Block Devices below for details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Get<wbr>Password<wbr>Data<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}If true, wait for password data to become available and retrieve it. Useful for getting the administrator password for instances running Microsoft Windows. The password data is exported to the `password_data` attribute. See [GetPasswordData](https://docs.aws.amazon.com/AWSEC2/latest/APIReference/API_GetPasswordData.html) for more information.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Hibernation<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}If true, the launched EC2 instance will support hibernation.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Host<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The Id of a dedicated host that the instance will be assigned to. Use when an instance is to be launched on a specific dedicated host.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Iam<wbr>Instance<wbr>Profile<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The IAM Instance Profile to
launch the instance with. Specified as the name of the Instance Profile. Ensure your credentials have the correct permission to assign the instance profile according to the [EC2 documentation](http://docs.aws.amazon.com/IAM/latest/UserGuide/id_roles_use_switch-role-ec2.html#roles-usingrole-ec2instance-permissions), notably `iam:PassRole`.
* `ipv6_address_count`- (Optional) A number of IPv6 addresses to associate with the primary network interface. Amazon EC2 chooses the IPv6 addresses from the range of your subnet.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Instance<wbr>Initiated<wbr>Shutdown<wbr>Behavior<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Shutdown behavior for the
instance. Amazon defaults this to `stop` for EBS-backed instances and
`terminate` for instance-store instances. Cannot be set on instance-store
instances. See [Shutdown Behavior](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/terminating-instances.html#Using_ChangingInstanceInitiatedShutdownBehavior) for more information.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Instance<wbr>Interruption<wbr>Behaviour<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Indicates whether a Spot instance stops or terminates when it is interrupted. Default is `terminate` as this is the current AWS behaviour.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Instance<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type of instance to start. Updates to this field will trigger a stop/start of the EC2 instance.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ipv6Address<wbr>Count<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ipv6Addresses<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}Specify one or more IPv6 addresses from the range of the subnet to associate with the primary network interface
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Key<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The key name of the Key Pair to use for the instance; which can be managed using the `aws.ec2.KeyPair` resource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Launch<wbr>Group<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A launch group is a group of spot instances that launch together and terminate together.
If left empty instances are launched and terminated individually.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Monitoring<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}If true, the launched EC2 instance will have detailed monitoring enabled. (Available since v0.6.0)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Network<wbr>Interfaces<span class="property-indicator"></span>
        <span class="property-type"><a href="#spotinstancerequestnetworkinterface">List&lt;Spot<wbr>Instance<wbr>Request<wbr>Network<wbr>Interface<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}Customize network interfaces to be attached at instance boot time. See Network Interfaces below for more details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Placement<wbr>Group<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The Placement Group to start the instance in.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Private<wbr>Ip<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Private IP address to associate with the
instance in a VPC.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Root<wbr>Block<wbr>Device<span class="property-indicator"></span>
        <span class="property-type"><a href="#spotinstancerequestrootblockdevice">Spot<wbr>Instance<wbr>Request<wbr>Root<wbr>Block<wbr>Device<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}Customize details about the root block
device of the instance. See Block Devices below for details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Security<wbr>Groups<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}A list of security group names (EC2-Classic) or IDs (default VPC) to associate with.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Source<wbr>Dest<wbr>Check<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Controls if traffic is routed to the instance when
the destination address does not match the instance. Used for NAT or VPNs. Defaults true.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Spot<wbr>Price<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The maximum price to request on the spot market.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Spot<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}If set to `one-time`, after
the instance is terminated, the spot request will be closed.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Subnet<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The VPC Subnet ID to launch in.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tenancy<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The tenancy of the instance (if the instance is running in a VPC). An instance with a tenancy of dedicated runs on single-tenant hardware. The host tenancy is not supported for the import-instance command.
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
            title="Optional">Valid<wbr>From<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The start date and time of the request, in UTC [RFC3339](https://tools.ietf.org/html/rfc3339#section-5.8) format(for example, YYYY-MM-DDTHH:MM:SSZ). The default is to start fulfilling the request immediately.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Valid<wbr>Until<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The end date and time of the request, in UTC [RFC3339](https://tools.ietf.org/html/rfc3339#section-5.8) format(for example, YYYY-MM-DDTHH:MM:SSZ). At this point, no new Spot instance requests are placed or enabled to fulfill the request. The default end date is 7 days from the current date.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Volume<wbr>Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the devices created by the instance at launch time.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Vpc<wbr>Security<wbr>Group<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}A list of security group IDs to associate with.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Wait<wbr>For<wbr>Fulfillment<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}If set, this provider will
wait for the Spot Request to be fulfilled, and will throw an error if the
timeout of 10m is reached.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Ami<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The AMI to use for the instance.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Associate<wbr>Public<wbr>Ip<wbr>Address<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Associate a public ip address with an instance in a VPC.  Boolean value.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Availability<wbr>Zone<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The AZ to start the instance in.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Block<wbr>Duration<wbr>Minutes<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The required duration for the Spot instances, in minutes. This value must be a multiple of 60 (60, 120, 180, 240, 300, or 360).
The duration period starts as soon as your Spot instance receives its instance ID. At the end of the duration period, Amazon EC2 marks the Spot instance for termination and provides a Spot instance termination notice, which gives the instance a two-minute warning before it terminates.
Note that you can&#39;t specify an Availability Zone group or a launch group if you specify a duration.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Cpu<wbr>Core<wbr>Count<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}Sets the number of CPU cores for an instance. This option is
only supported on creation of instance type that support CPU Options
[CPU Cores and Threads Per CPU Core Per Instance Type](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/instance-optimize-cpu.html#cpu-options-supported-instances-values) - specifying this option for unsupported instance types will return an error from the EC2 API.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Cpu<wbr>Threads<wbr>Per<wbr>Core<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}If set to to 1, hyperthreading is disabled on the launched instance. Defaults to 2 if not set. See [Optimizing CPU Options](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/instance-optimize-cpu.html) for more information.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Credit<wbr>Specification<span class="property-indicator"></span>
        <span class="property-type"><a href="#spotinstancerequestcreditspecification">*Spot<wbr>Instance<wbr>Request<wbr>Credit<wbr>Specification</a></span>
    </dt>
    <dd>{{% md %}}Customize the credit specification of the instance. See Credit Specification below for more details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Disable<wbr>Api<wbr>Termination<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}If true, enables [EC2 Instance
Termination Protection](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/terminating-instances.html#Using_ChangingDisableAPITermination)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ebs<wbr>Block<wbr>Devices<span class="property-indicator"></span>
        <span class="property-type"><a href="#spotinstancerequestebsblockdevice">[]Spot<wbr>Instance<wbr>Request<wbr>Ebs<wbr>Block<wbr>Device</a></span>
    </dt>
    <dd>{{% md %}}Additional EBS block devices to attach to the
instance.  Block device configurations only apply on resource creation. See Block Devices below for details on attributes and drift detection.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ebs<wbr>Optimized<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}If true, the launched EC2 instance will be EBS-optimized.
Note that if this is not set on an instance type that is optimized by default then
this will show as disabled but if the instance type is optimized by default then
there is no need to set this and there is no effect to disabling it.
See the [EBS Optimized section](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/EBSOptimized.html) of the AWS User Guide for more information.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ephemeral<wbr>Block<wbr>Devices<span class="property-indicator"></span>
        <span class="property-type"><a href="#spotinstancerequestephemeralblockdevice">[]Spot<wbr>Instance<wbr>Request<wbr>Ephemeral<wbr>Block<wbr>Device</a></span>
    </dt>
    <dd>{{% md %}}Customize Ephemeral (also known as
&#34;Instance Store&#34;) volumes on the instance. See Block Devices below for details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Get<wbr>Password<wbr>Data<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}If true, wait for password data to become available and retrieve it. Useful for getting the administrator password for instances running Microsoft Windows. The password data is exported to the `password_data` attribute. See [GetPasswordData](https://docs.aws.amazon.com/AWSEC2/latest/APIReference/API_GetPasswordData.html) for more information.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Hibernation<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}If true, the launched EC2 instance will support hibernation.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Host<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The Id of a dedicated host that the instance will be assigned to. Use when an instance is to be launched on a specific dedicated host.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Iam<wbr>Instance<wbr>Profile<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The IAM Instance Profile to
launch the instance with. Specified as the name of the Instance Profile. Ensure your credentials have the correct permission to assign the instance profile according to the [EC2 documentation](http://docs.aws.amazon.com/IAM/latest/UserGuide/id_roles_use_switch-role-ec2.html#roles-usingrole-ec2instance-permissions), notably `iam:PassRole`.
* `ipv6_address_count`- (Optional) A number of IPv6 addresses to associate with the primary network interface. Amazon EC2 chooses the IPv6 addresses from the range of your subnet.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Instance<wbr>Initiated<wbr>Shutdown<wbr>Behavior<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Shutdown behavior for the
instance. Amazon defaults this to `stop` for EBS-backed instances and
`terminate` for instance-store instances. Cannot be set on instance-store
instances. See [Shutdown Behavior](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/terminating-instances.html#Using_ChangingInstanceInitiatedShutdownBehavior) for more information.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Instance<wbr>Interruption<wbr>Behaviour<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Indicates whether a Spot instance stops or terminates when it is interrupted. Default is `terminate` as this is the current AWS behaviour.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Instance<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type of instance to start. Updates to this field will trigger a stop/start of the EC2 instance.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ipv6Address<wbr>Count<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ipv6Addresses<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}Specify one or more IPv6 addresses from the range of the subnet to associate with the primary network interface
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Key<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The key name of the Key Pair to use for the instance; which can be managed using the `aws.ec2.KeyPair` resource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Launch<wbr>Group<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}A launch group is a group of spot instances that launch together and terminate together.
If left empty instances are launched and terminated individually.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Monitoring<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}If true, the launched EC2 instance will have detailed monitoring enabled. (Available since v0.6.0)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Network<wbr>Interfaces<span class="property-indicator"></span>
        <span class="property-type"><a href="#spotinstancerequestnetworkinterface">[]Spot<wbr>Instance<wbr>Request<wbr>Network<wbr>Interface</a></span>
    </dt>
    <dd>{{% md %}}Customize network interfaces to be attached at instance boot time. See Network Interfaces below for more details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Placement<wbr>Group<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The Placement Group to start the instance in.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Private<wbr>Ip<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Private IP address to associate with the
instance in a VPC.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Root<wbr>Block<wbr>Device<span class="property-indicator"></span>
        <span class="property-type"><a href="#spotinstancerequestrootblockdevice">*Spot<wbr>Instance<wbr>Request<wbr>Root<wbr>Block<wbr>Device</a></span>
    </dt>
    <dd>{{% md %}}Customize details about the root block
device of the instance. See Block Devices below for details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Security<wbr>Groups<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}A list of security group names (EC2-Classic) or IDs (default VPC) to associate with.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Source<wbr>Dest<wbr>Check<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Controls if traffic is routed to the instance when
the destination address does not match the instance. Used for NAT or VPNs. Defaults true.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Spot<wbr>Price<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The maximum price to request on the spot market.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Spot<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}If set to `one-time`, after
the instance is terminated, the spot request will be closed.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Subnet<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The VPC Subnet ID to launch in.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tenancy<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The tenancy of the instance (if the instance is running in a VPC). An instance with a tenancy of dedicated runs on single-tenant hardware. The host tenancy is not supported for the import-instance command.
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
            title="Optional">Valid<wbr>From<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The start date and time of the request, in UTC [RFC3339](https://tools.ietf.org/html/rfc3339#section-5.8) format(for example, YYYY-MM-DDTHH:MM:SSZ). The default is to start fulfilling the request immediately.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Valid<wbr>Until<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The end date and time of the request, in UTC [RFC3339](https://tools.ietf.org/html/rfc3339#section-5.8) format(for example, YYYY-MM-DDTHH:MM:SSZ). At this point, no new Spot instance requests are placed or enabled to fulfill the request. The default end date is 7 days from the current date.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Volume<wbr>Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the devices created by the instance at launch time.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Vpc<wbr>Security<wbr>Group<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}A list of security group IDs to associate with.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Wait<wbr>For<wbr>Fulfillment<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}If set, this provider will
wait for the Spot Request to be fulfilled, and will throw an error if the
timeout of 10m is reached.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">ami<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The AMI to use for the instance.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">associate<wbr>Public<wbr>Ip<wbr>Address<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Associate a public ip address with an instance in a VPC.  Boolean value.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">availability<wbr>Zone<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The AZ to start the instance in.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">block<wbr>Duration<wbr>Minutes<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The required duration for the Spot instances, in minutes. This value must be a multiple of 60 (60, 120, 180, 240, 300, or 360).
The duration period starts as soon as your Spot instance receives its instance ID. At the end of the duration period, Amazon EC2 marks the Spot instance for termination and provides a Spot instance termination notice, which gives the instance a two-minute warning before it terminates.
Note that you can&#39;t specify an Availability Zone group or a launch group if you specify a duration.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">cpu<wbr>Core<wbr>Count<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}Sets the number of CPU cores for an instance. This option is
only supported on creation of instance type that support CPU Options
[CPU Cores and Threads Per CPU Core Per Instance Type](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/instance-optimize-cpu.html#cpu-options-supported-instances-values) - specifying this option for unsupported instance types will return an error from the EC2 API.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">cpu<wbr>Threads<wbr>Per<wbr>Core<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}If set to to 1, hyperthreading is disabled on the launched instance. Defaults to 2 if not set. See [Optimizing CPU Options](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/instance-optimize-cpu.html) for more information.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">credit<wbr>Specification<span class="property-indicator"></span>
        <span class="property-type"><a href="#spotinstancerequestcreditspecification">Spot<wbr>Instance<wbr>Request<wbr>Credit<wbr>Specification?</a></span>
    </dt>
    <dd>{{% md %}}Customize the credit specification of the instance. See Credit Specification below for more details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">disable<wbr>Api<wbr>Termination<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}If true, enables [EC2 Instance
Termination Protection](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/terminating-instances.html#Using_ChangingDisableAPITermination)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ebs<wbr>Block<wbr>Devices<span class="property-indicator"></span>
        <span class="property-type"><a href="#spotinstancerequestebsblockdevice">Spot<wbr>Instance<wbr>Request<wbr>Ebs<wbr>Block<wbr>Device[]?</a></span>
    </dt>
    <dd>{{% md %}}Additional EBS block devices to attach to the
instance.  Block device configurations only apply on resource creation. See Block Devices below for details on attributes and drift detection.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ebs<wbr>Optimized<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}If true, the launched EC2 instance will be EBS-optimized.
Note that if this is not set on an instance type that is optimized by default then
this will show as disabled but if the instance type is optimized by default then
there is no need to set this and there is no effect to disabling it.
See the [EBS Optimized section](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/EBSOptimized.html) of the AWS User Guide for more information.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ephemeral<wbr>Block<wbr>Devices<span class="property-indicator"></span>
        <span class="property-type"><a href="#spotinstancerequestephemeralblockdevice">Spot<wbr>Instance<wbr>Request<wbr>Ephemeral<wbr>Block<wbr>Device[]?</a></span>
    </dt>
    <dd>{{% md %}}Customize Ephemeral (also known as
&#34;Instance Store&#34;) volumes on the instance. See Block Devices below for details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">get<wbr>Password<wbr>Data<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}If true, wait for password data to become available and retrieve it. Useful for getting the administrator password for instances running Microsoft Windows. The password data is exported to the `password_data` attribute. See [GetPasswordData](https://docs.aws.amazon.com/AWSEC2/latest/APIReference/API_GetPasswordData.html) for more information.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">hibernation<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}If true, the launched EC2 instance will support hibernation.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">host<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The Id of a dedicated host that the instance will be assigned to. Use when an instance is to be launched on a specific dedicated host.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">iam<wbr>Instance<wbr>Profile<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The IAM Instance Profile to
launch the instance with. Specified as the name of the Instance Profile. Ensure your credentials have the correct permission to assign the instance profile according to the [EC2 documentation](http://docs.aws.amazon.com/IAM/latest/UserGuide/id_roles_use_switch-role-ec2.html#roles-usingrole-ec2instance-permissions), notably `iam:PassRole`.
* `ipv6_address_count`- (Optional) A number of IPv6 addresses to associate with the primary network interface. Amazon EC2 chooses the IPv6 addresses from the range of your subnet.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">instance<wbr>Initiated<wbr>Shutdown<wbr>Behavior<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Shutdown behavior for the
instance. Amazon defaults this to `stop` for EBS-backed instances and
`terminate` for instance-store instances. Cannot be set on instance-store
instances. See [Shutdown Behavior](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/terminating-instances.html#Using_ChangingInstanceInitiatedShutdownBehavior) for more information.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">instance<wbr>Interruption<wbr>Behaviour<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Indicates whether a Spot instance stops or terminates when it is interrupted. Default is `terminate` as this is the current AWS behaviour.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">instance<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type of instance to start. Updates to this field will trigger a stop/start of the EC2 instance.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ipv6Address<wbr>Count<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ipv6Addresses<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}Specify one or more IPv6 addresses from the range of the subnet to associate with the primary network interface
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">key<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The key name of the Key Pair to use for the instance; which can be managed using the `aws.ec2.KeyPair` resource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">launch<wbr>Group<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A launch group is a group of spot instances that launch together and terminate together.
If left empty instances are launched and terminated individually.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">monitoring<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}If true, the launched EC2 instance will have detailed monitoring enabled. (Available since v0.6.0)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">network<wbr>Interfaces<span class="property-indicator"></span>
        <span class="property-type"><a href="#spotinstancerequestnetworkinterface">Spot<wbr>Instance<wbr>Request<wbr>Network<wbr>Interface[]?</a></span>
    </dt>
    <dd>{{% md %}}Customize network interfaces to be attached at instance boot time. See Network Interfaces below for more details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">placement<wbr>Group<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The Placement Group to start the instance in.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">private<wbr>Ip<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Private IP address to associate with the
instance in a VPC.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">root<wbr>Block<wbr>Device<span class="property-indicator"></span>
        <span class="property-type"><a href="#spotinstancerequestrootblockdevice">Spot<wbr>Instance<wbr>Request<wbr>Root<wbr>Block<wbr>Device?</a></span>
    </dt>
    <dd>{{% md %}}Customize details about the root block
device of the instance. See Block Devices below for details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">security<wbr>Groups<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}A list of security group names (EC2-Classic) or IDs (default VPC) to associate with.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">source<wbr>Dest<wbr>Check<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Controls if traffic is routed to the instance when
the destination address does not match the instance. Used for NAT or VPNs. Defaults true.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">spot<wbr>Price<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The maximum price to request on the spot market.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">spot<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}If set to `one-time`, after
the instance is terminated, the spot request will be closed.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">subnet<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The VPC Subnet ID to launch in.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tenancy<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The tenancy of the instance (if the instance is running in a VPC). An instance with a tenancy of dedicated runs on single-tenant hardware. The host tenancy is not supported for the import-instance command.
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
            title="Optional">valid<wbr>From<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The start date and time of the request, in UTC [RFC3339](https://tools.ietf.org/html/rfc3339#section-5.8) format(for example, YYYY-MM-DDTHH:MM:SSZ). The default is to start fulfilling the request immediately.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">valid<wbr>Until<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The end date and time of the request, in UTC [RFC3339](https://tools.ietf.org/html/rfc3339#section-5.8) format(for example, YYYY-MM-DDTHH:MM:SSZ). At this point, no new Spot instance requests are placed or enabled to fulfill the request. The default end date is 7 days from the current date.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">volume<wbr>Tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the devices created by the instance at launch time.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">vpc<wbr>Security<wbr>Group<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}A list of security group IDs to associate with.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">wait<wbr>For<wbr>Fulfillment<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}If set, this provider will
wait for the Spot Request to be fulfilled, and will throw an error if the
timeout of 10m is reached.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">ami<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The AMI to use for the instance.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">associate_<wbr>public_<wbr>ip_<wbr>address<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Associate a public ip address with an instance in a VPC.  Boolean value.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">availability_<wbr>zone<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The AZ to start the instance in.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">block_<wbr>duration_<wbr>minutes<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The required duration for the Spot instances, in minutes. This value must be a multiple of 60 (60, 120, 180, 240, 300, or 360).
The duration period starts as soon as your Spot instance receives its instance ID. At the end of the duration period, Amazon EC2 marks the Spot instance for termination and provides a Spot instance termination notice, which gives the instance a two-minute warning before it terminates.
Note that you can&#39;t specify an Availability Zone group or a launch group if you specify a duration.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">cpu_<wbr>core_<wbr>count<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}Sets the number of CPU cores for an instance. This option is
only supported on creation of instance type that support CPU Options
[CPU Cores and Threads Per CPU Core Per Instance Type](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/instance-optimize-cpu.html#cpu-options-supported-instances-values) - specifying this option for unsupported instance types will return an error from the EC2 API.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">cpu_<wbr>threads_<wbr>per_<wbr>core<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}If set to to 1, hyperthreading is disabled on the launched instance. Defaults to 2 if not set. See [Optimizing CPU Options](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/instance-optimize-cpu.html) for more information.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">credit_<wbr>specification<span class="property-indicator"></span>
        <span class="property-type"><a href="#spotinstancerequestcreditspecification">Dict[Spot<wbr>Instance<wbr>Request<wbr>Credit<wbr>Specification]</a></span>
    </dt>
    <dd>{{% md %}}Customize the credit specification of the instance. See Credit Specification below for more details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">disable_<wbr>api_<wbr>termination<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}If true, enables [EC2 Instance
Termination Protection](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/terminating-instances.html#Using_ChangingDisableAPITermination)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ebs_<wbr>block_<wbr>devices<span class="property-indicator"></span>
        <span class="property-type"><a href="#spotinstancerequestebsblockdevice">List[Spot<wbr>Instance<wbr>Request<wbr>Ebs<wbr>Block<wbr>Device]</a></span>
    </dt>
    <dd>{{% md %}}Additional EBS block devices to attach to the
instance.  Block device configurations only apply on resource creation. See Block Devices below for details on attributes and drift detection.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ebs_<wbr>optimized<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}If true, the launched EC2 instance will be EBS-optimized.
Note that if this is not set on an instance type that is optimized by default then
this will show as disabled but if the instance type is optimized by default then
there is no need to set this and there is no effect to disabling it.
See the [EBS Optimized section](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/EBSOptimized.html) of the AWS User Guide for more information.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ephemeral_<wbr>block_<wbr>devices<span class="property-indicator"></span>
        <span class="property-type"><a href="#spotinstancerequestephemeralblockdevice">List[Spot<wbr>Instance<wbr>Request<wbr>Ephemeral<wbr>Block<wbr>Device]</a></span>
    </dt>
    <dd>{{% md %}}Customize Ephemeral (also known as
&#34;Instance Store&#34;) volumes on the instance. See Block Devices below for details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">get_<wbr>password_<wbr>data<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}If true, wait for password data to become available and retrieve it. Useful for getting the administrator password for instances running Microsoft Windows. The password data is exported to the `password_data` attribute. See [GetPasswordData](https://docs.aws.amazon.com/AWSEC2/latest/APIReference/API_GetPasswordData.html) for more information.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">hibernation<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}If true, the launched EC2 instance will support hibernation.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">host_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The Id of a dedicated host that the instance will be assigned to. Use when an instance is to be launched on a specific dedicated host.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">iam_<wbr>instance_<wbr>profile<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The IAM Instance Profile to
launch the instance with. Specified as the name of the Instance Profile. Ensure your credentials have the correct permission to assign the instance profile according to the [EC2 documentation](http://docs.aws.amazon.com/IAM/latest/UserGuide/id_roles_use_switch-role-ec2.html#roles-usingrole-ec2instance-permissions), notably `iam:PassRole`.
* `ipv6_address_count`- (Optional) A number of IPv6 addresses to associate with the primary network interface. Amazon EC2 chooses the IPv6 addresses from the range of your subnet.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">instance_<wbr>initiated_<wbr>shutdown_<wbr>behavior<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Shutdown behavior for the
instance. Amazon defaults this to `stop` for EBS-backed instances and
`terminate` for instance-store instances. Cannot be set on instance-store
instances. See [Shutdown Behavior](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/terminating-instances.html#Using_ChangingInstanceInitiatedShutdownBehavior) for more information.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">instance_<wbr>interruption_<wbr>behaviour<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Indicates whether a Spot instance stops or terminates when it is interrupted. Default is `terminate` as this is the current AWS behaviour.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">instance_<wbr>type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The type of instance to start. Updates to this field will trigger a stop/start of the EC2 instance.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ipv6_<wbr>address_<wbr>count<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ipv6_<wbr>addresses<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}Specify one or more IPv6 addresses from the range of the subnet to associate with the primary network interface
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">key_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The key name of the Key Pair to use for the instance; which can be managed using the `aws.ec2.KeyPair` resource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">launch_<wbr>group<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A launch group is a group of spot instances that launch together and terminate together.
If left empty instances are launched and terminated individually.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">monitoring<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}If true, the launched EC2 instance will have detailed monitoring enabled. (Available since v0.6.0)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">network_<wbr>interfaces<span class="property-indicator"></span>
        <span class="property-type"><a href="#spotinstancerequestnetworkinterface">List[Spot<wbr>Instance<wbr>Request<wbr>Network<wbr>Interface]</a></span>
    </dt>
    <dd>{{% md %}}Customize network interfaces to be attached at instance boot time. See Network Interfaces below for more details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">placement_<wbr>group<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The Placement Group to start the instance in.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">private_<wbr>ip<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Private IP address to associate with the
instance in a VPC.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">root_<wbr>block_<wbr>device<span class="property-indicator"></span>
        <span class="property-type"><a href="#spotinstancerequestrootblockdevice">Dict[Spot<wbr>Instance<wbr>Request<wbr>Root<wbr>Block<wbr>Device]</a></span>
    </dt>
    <dd>{{% md %}}Customize details about the root block
device of the instance. See Block Devices below for details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">security_<wbr>groups<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}A list of security group names (EC2-Classic) or IDs (default VPC) to associate with.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">source_<wbr>dest_<wbr>check<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Controls if traffic is routed to the instance when
the destination address does not match the instance. Used for NAT or VPNs. Defaults true.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">spot_<wbr>price<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The maximum price to request on the spot market.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">spot_<wbr>type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}If set to `one-time`, after
the instance is terminated, the spot request will be closed.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">subnet_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The VPC Subnet ID to launch in.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tenancy<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The tenancy of the instance (if the instance is running in a VPC). An instance with a tenancy of dedicated runs on single-tenant hardware. The host tenancy is not supported for the import-instance command.
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
            title="Optional">valid_<wbr>from<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The start date and time of the request, in UTC [RFC3339](https://tools.ietf.org/html/rfc3339#section-5.8) format(for example, YYYY-MM-DDTHH:MM:SSZ). The default is to start fulfilling the request immediately.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">valid_<wbr>until<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The end date and time of the request, in UTC [RFC3339](https://tools.ietf.org/html/rfc3339#section-5.8) format(for example, YYYY-MM-DDTHH:MM:SSZ). At this point, no new Spot instance requests are placed or enabled to fulfill the request. The default end date is 7 days from the current date.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">volume_<wbr>tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the devices created by the instance at launch time.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">vpc_<wbr>security_<wbr>group_<wbr>ids<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}A list of security group IDs to associate with.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">wait_<wbr>for_<wbr>fulfillment<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}If set, this provider will
wait for the Spot Request to be fulfilled, and will throw an error if the
timeout of 10m is reached.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}




## SpotInstanceRequest Output Properties

The following output properties are available:




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Ami<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The AMI to use for the instance.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">Associate<wbr>Public<wbr>Ip<wbr>Address<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Associate a public ip address with an instance in a VPC.  Boolean value.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Availability<wbr>Zone<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The AZ to start the instance in.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Block<wbr>Duration<wbr>Minutes<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The required duration for the Spot instances, in minutes. This value must be a multiple of 60 (60, 120, 180, 240, 300, or 360).
The duration period starts as soon as your Spot instance receives its instance ID. At the end of the duration period, Amazon EC2 marks the Spot instance for termination and provides a Spot instance termination notice, which gives the instance a two-minute warning before it terminates.
Note that you can&#39;t specify an Availability Zone group or a launch group if you specify a duration.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Cpu<wbr>Core<wbr>Count<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}Sets the number of CPU cores for an instance. This option is
only supported on creation of instance type that support CPU Options
[CPU Cores and Threads Per CPU Core Per Instance Type](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/instance-optimize-cpu.html#cpu-options-supported-instances-values) - specifying this option for unsupported instance types will return an error from the EC2 API.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Cpu<wbr>Threads<wbr>Per<wbr>Core<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}If set to to 1, hyperthreading is disabled on the launched instance. Defaults to 2 if not set. See [Optimizing CPU Options](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/instance-optimize-cpu.html) for more information.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Credit<wbr>Specification<span class="property-indicator"></span>
        <span class="property-type"><a href="#spotinstancerequestcreditspecification">Spot<wbr>Instance<wbr>Request<wbr>Credit<wbr>Specification?</a></span>
    </dt>
    <dd>{{% md %}}Customize the credit specification of the instance. See Credit Specification below for more details.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Disable<wbr>Api<wbr>Termination<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}If true, enables [EC2 Instance
Termination Protection](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/terminating-instances.html#Using_ChangingDisableAPITermination)
{{% /md %}}</dd>

    <dt class="property-"
            title="">Ebs<wbr>Block<wbr>Devices<span class="property-indicator"></span>
        <span class="property-type"><a href="#spotinstancerequestebsblockdevice">List&lt;Spot<wbr>Instance<wbr>Request<wbr>Ebs<wbr>Block<wbr>Device&gt;</a></span>
    </dt>
    <dd>{{% md %}}Additional EBS block devices to attach to the
instance.  Block device configurations only apply on resource creation. See Block Devices below for details on attributes and drift detection.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Ebs<wbr>Optimized<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}If true, the launched EC2 instance will be EBS-optimized.
Note that if this is not set on an instance type that is optimized by default then
this will show as disabled but if the instance type is optimized by default then
there is no need to set this and there is no effect to disabling it.
See the [EBS Optimized section](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/EBSOptimized.html) of the AWS User Guide for more information.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Ephemeral<wbr>Block<wbr>Devices<span class="property-indicator"></span>
        <span class="property-type"><a href="#spotinstancerequestephemeralblockdevice">List&lt;Spot<wbr>Instance<wbr>Request<wbr>Ephemeral<wbr>Block<wbr>Device&gt;</a></span>
    </dt>
    <dd>{{% md %}}Customize Ephemeral (also known as
&#34;Instance Store&#34;) volumes on the instance. See Block Devices below for details.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Get<wbr>Password<wbr>Data<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}If true, wait for password data to become available and retrieve it. Useful for getting the administrator password for instances running Microsoft Windows. The password data is exported to the `password_data` attribute. See [GetPasswordData](https://docs.aws.amazon.com/AWSEC2/latest/APIReference/API_GetPasswordData.html) for more information.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Hibernation<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}If true, the launched EC2 instance will support hibernation.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Host<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Id of a dedicated host that the instance will be assigned to. Use when an instance is to be launched on a specific dedicated host.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Iam<wbr>Instance<wbr>Profile<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The IAM Instance Profile to
launch the instance with. Specified as the name of the Instance Profile. Ensure your credentials have the correct permission to assign the instance profile according to the [EC2 documentation](http://docs.aws.amazon.com/IAM/latest/UserGuide/id_roles_use_switch-role-ec2.html#roles-usingrole-ec2instance-permissions), notably `iam:PassRole`.
* `ipv6_address_count`- (Optional) A number of IPv6 addresses to associate with the primary network interface. Amazon EC2 chooses the IPv6 addresses from the range of your subnet.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Instance<wbr>Initiated<wbr>Shutdown<wbr>Behavior<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Shutdown behavior for the
instance. Amazon defaults this to `stop` for EBS-backed instances and
`terminate` for instance-store instances. Cannot be set on instance-store
instances. See [Shutdown Behavior](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/terminating-instances.html#Using_ChangingInstanceInitiatedShutdownBehavior) for more information.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Instance<wbr>Interruption<wbr>Behaviour<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Indicates whether a Spot instance stops or terminates when it is interrupted. Default is `terminate` as this is the current AWS behaviour.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Instance<wbr>State<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">Instance<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type of instance to start. Updates to this field will trigger a stop/start of the EC2 instance.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Ipv6Address<wbr>Count<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">Ipv6Addresses<span class="property-indicator"></span>
        <span class="property-type">List<string></span>
    </dt>
    <dd>{{% md %}}Specify one or more IPv6 addresses from the range of the subnet to associate with the primary network interface
{{% /md %}}</dd>

    <dt class="property-"
            title="">Key<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The key name of the Key Pair to use for the instance; which can be managed using the `aws.ec2.KeyPair` resource.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Launch<wbr>Group<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A launch group is a group of spot instances that launch together and terminate together.
If left empty instances are launched and terminated individually.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Monitoring<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}If true, the launched EC2 instance will have detailed monitoring enabled. (Available since v0.6.0)
{{% /md %}}</dd>

    <dt class="property-"
            title="">Network<wbr>Interfaces<span class="property-indicator"></span>
        <span class="property-type"><a href="#spotinstancerequestnetworkinterface">List&lt;Spot<wbr>Instance<wbr>Request<wbr>Network<wbr>Interface&gt;</a></span>
    </dt>
    <dd>{{% md %}}Customize network interfaces to be attached at instance boot time. See Network Interfaces below for more details.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Password<wbr>Data<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">Placement<wbr>Group<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Placement Group to start the instance in.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Primary<wbr>Network<wbr>Interface<wbr>Id<span class="property-indicator"></span>
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
    <dd>{{% md %}}Private IP address to associate with the
instance in a VPC.
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
            title="">Root<wbr>Block<wbr>Device<span class="property-indicator"></span>
        <span class="property-type"><a href="#spotinstancerequestrootblockdevice">Spot<wbr>Instance<wbr>Request<wbr>Root<wbr>Block<wbr>Device</a></span>
    </dt>
    <dd>{{% md %}}Customize details about the root block
device of the instance. See Block Devices below for details.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Security<wbr>Groups<span class="property-indicator"></span>
        <span class="property-type">List<string></span>
    </dt>
    <dd>{{% md %}}A list of security group names (EC2-Classic) or IDs (default VPC) to associate with.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Source<wbr>Dest<wbr>Check<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Controls if traffic is routed to the instance when
the destination address does not match the instance. Used for NAT or VPNs. Defaults true.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Spot<wbr>Bid<wbr>Status<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The current [bid
status](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/spot-bid-status.html)
of the Spot Instance Request.
* `spot_request_state` The current [request
state](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/spot-requests.html#creating-spot-request-status)
of the Spot Instance Request.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Spot<wbr>Instance<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Instance ID (if any) that is currently fulfilling
the Spot Instance request.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Spot<wbr>Price<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The maximum price to request on the spot market.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Spot<wbr>Request<wbr>State<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">Spot<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}If set to `one-time`, after
the instance is terminated, the spot request will be closed.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Subnet<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The VPC Subnet ID to launch in.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Tenancy<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The tenancy of the instance (if the instance is running in a VPC). An instance with a tenancy of dedicated runs on single-tenant hardware. The host tenancy is not supported for the import-instance command.
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
            title="">Valid<wbr>From<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The start date and time of the request, in UTC [RFC3339](https://tools.ietf.org/html/rfc3339#section-5.8) format(for example, YYYY-MM-DDTHH:MM:SSZ). The default is to start fulfilling the request immediately.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Valid<wbr>Until<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The end date and time of the request, in UTC [RFC3339](https://tools.ietf.org/html/rfc3339#section-5.8) format(for example, YYYY-MM-DDTHH:MM:SSZ). At this point, no new Spot instance requests are placed or enabled to fulfill the request. The default end date is 7 days from the current date.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Volume<wbr>Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the devices created by the instance at launch time.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Vpc<wbr>Security<wbr>Group<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">List<string></span>
    </dt>
    <dd>{{% md %}}A list of security group IDs to associate with.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Wait<wbr>For<wbr>Fulfillment<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}If set, this provider will
wait for the Spot Request to be fulfilled, and will throw an error if the
timeout of 10m is reached.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Ami<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The AMI to use for the instance.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">Associate<wbr>Public<wbr>Ip<wbr>Address<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Associate a public ip address with an instance in a VPC.  Boolean value.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Availability<wbr>Zone<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The AZ to start the instance in.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Block<wbr>Duration<wbr>Minutes<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The required duration for the Spot instances, in minutes. This value must be a multiple of 60 (60, 120, 180, 240, 300, or 360).
The duration period starts as soon as your Spot instance receives its instance ID. At the end of the duration period, Amazon EC2 marks the Spot instance for termination and provides a Spot instance termination notice, which gives the instance a two-minute warning before it terminates.
Note that you can&#39;t specify an Availability Zone group or a launch group if you specify a duration.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Cpu<wbr>Core<wbr>Count<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}Sets the number of CPU cores for an instance. This option is
only supported on creation of instance type that support CPU Options
[CPU Cores and Threads Per CPU Core Per Instance Type](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/instance-optimize-cpu.html#cpu-options-supported-instances-values) - specifying this option for unsupported instance types will return an error from the EC2 API.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Cpu<wbr>Threads<wbr>Per<wbr>Core<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}If set to to 1, hyperthreading is disabled on the launched instance. Defaults to 2 if not set. See [Optimizing CPU Options](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/instance-optimize-cpu.html) for more information.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Credit<wbr>Specification<span class="property-indicator"></span>
        <span class="property-type"><a href="#spotinstancerequestcreditspecification">*Spot<wbr>Instance<wbr>Request<wbr>Credit<wbr>Specification</a></span>
    </dt>
    <dd>{{% md %}}Customize the credit specification of the instance. See Credit Specification below for more details.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Disable<wbr>Api<wbr>Termination<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}If true, enables [EC2 Instance
Termination Protection](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/terminating-instances.html#Using_ChangingDisableAPITermination)
{{% /md %}}</dd>

    <dt class="property-"
            title="">Ebs<wbr>Block<wbr>Devices<span class="property-indicator"></span>
        <span class="property-type"><a href="#spotinstancerequestebsblockdevice">[]Spot<wbr>Instance<wbr>Request<wbr>Ebs<wbr>Block<wbr>Device</a></span>
    </dt>
    <dd>{{% md %}}Additional EBS block devices to attach to the
instance.  Block device configurations only apply on resource creation. See Block Devices below for details on attributes and drift detection.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Ebs<wbr>Optimized<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}If true, the launched EC2 instance will be EBS-optimized.
Note that if this is not set on an instance type that is optimized by default then
this will show as disabled but if the instance type is optimized by default then
there is no need to set this and there is no effect to disabling it.
See the [EBS Optimized section](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/EBSOptimized.html) of the AWS User Guide for more information.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Ephemeral<wbr>Block<wbr>Devices<span class="property-indicator"></span>
        <span class="property-type"><a href="#spotinstancerequestephemeralblockdevice">[]Spot<wbr>Instance<wbr>Request<wbr>Ephemeral<wbr>Block<wbr>Device</a></span>
    </dt>
    <dd>{{% md %}}Customize Ephemeral (also known as
&#34;Instance Store&#34;) volumes on the instance. See Block Devices below for details.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Get<wbr>Password<wbr>Data<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}If true, wait for password data to become available and retrieve it. Useful for getting the administrator password for instances running Microsoft Windows. The password data is exported to the `password_data` attribute. See [GetPasswordData](https://docs.aws.amazon.com/AWSEC2/latest/APIReference/API_GetPasswordData.html) for more information.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Hibernation<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}If true, the launched EC2 instance will support hibernation.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Host<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Id of a dedicated host that the instance will be assigned to. Use when an instance is to be launched on a specific dedicated host.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Iam<wbr>Instance<wbr>Profile<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The IAM Instance Profile to
launch the instance with. Specified as the name of the Instance Profile. Ensure your credentials have the correct permission to assign the instance profile according to the [EC2 documentation](http://docs.aws.amazon.com/IAM/latest/UserGuide/id_roles_use_switch-role-ec2.html#roles-usingrole-ec2instance-permissions), notably `iam:PassRole`.
* `ipv6_address_count`- (Optional) A number of IPv6 addresses to associate with the primary network interface. Amazon EC2 chooses the IPv6 addresses from the range of your subnet.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Instance<wbr>Initiated<wbr>Shutdown<wbr>Behavior<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Shutdown behavior for the
instance. Amazon defaults this to `stop` for EBS-backed instances and
`terminate` for instance-store instances. Cannot be set on instance-store
instances. See [Shutdown Behavior](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/terminating-instances.html#Using_ChangingInstanceInitiatedShutdownBehavior) for more information.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Instance<wbr>Interruption<wbr>Behaviour<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Indicates whether a Spot instance stops or terminates when it is interrupted. Default is `terminate` as this is the current AWS behaviour.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Instance<wbr>State<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">Instance<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type of instance to start. Updates to this field will trigger a stop/start of the EC2 instance.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Ipv6Address<wbr>Count<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">Ipv6Addresses<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}Specify one or more IPv6 addresses from the range of the subnet to associate with the primary network interface
{{% /md %}}</dd>

    <dt class="property-"
            title="">Key<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The key name of the Key Pair to use for the instance; which can be managed using the `aws.ec2.KeyPair` resource.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Launch<wbr>Group<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}A launch group is a group of spot instances that launch together and terminate together.
If left empty instances are launched and terminated individually.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Monitoring<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}If true, the launched EC2 instance will have detailed monitoring enabled. (Available since v0.6.0)
{{% /md %}}</dd>

    <dt class="property-"
            title="">Network<wbr>Interfaces<span class="property-indicator"></span>
        <span class="property-type"><a href="#spotinstancerequestnetworkinterface">[]Spot<wbr>Instance<wbr>Request<wbr>Network<wbr>Interface</a></span>
    </dt>
    <dd>{{% md %}}Customize network interfaces to be attached at instance boot time. See Network Interfaces below for more details.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Password<wbr>Data<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">Placement<wbr>Group<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Placement Group to start the instance in.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Primary<wbr>Network<wbr>Interface<wbr>Id<span class="property-indicator"></span>
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
    <dd>{{% md %}}Private IP address to associate with the
instance in a VPC.
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
            title="">Root<wbr>Block<wbr>Device<span class="property-indicator"></span>
        <span class="property-type"><a href="#spotinstancerequestrootblockdevice">Spot<wbr>Instance<wbr>Request<wbr>Root<wbr>Block<wbr>Device</a></span>
    </dt>
    <dd>{{% md %}}Customize details about the root block
device of the instance. See Block Devices below for details.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Security<wbr>Groups<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}A list of security group names (EC2-Classic) or IDs (default VPC) to associate with.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Source<wbr>Dest<wbr>Check<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Controls if traffic is routed to the instance when
the destination address does not match the instance. Used for NAT or VPNs. Defaults true.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Spot<wbr>Bid<wbr>Status<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The current [bid
status](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/spot-bid-status.html)
of the Spot Instance Request.
* `spot_request_state` The current [request
state](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/spot-requests.html#creating-spot-request-status)
of the Spot Instance Request.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Spot<wbr>Instance<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Instance ID (if any) that is currently fulfilling
the Spot Instance request.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Spot<wbr>Price<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The maximum price to request on the spot market.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Spot<wbr>Request<wbr>State<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">Spot<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}If set to `one-time`, after
the instance is terminated, the spot request will be closed.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Subnet<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The VPC Subnet ID to launch in.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Tenancy<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The tenancy of the instance (if the instance is running in a VPC). An instance with a tenancy of dedicated runs on single-tenant hardware. The host tenancy is not supported for the import-instance command.
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
            title="">Valid<wbr>From<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The start date and time of the request, in UTC [RFC3339](https://tools.ietf.org/html/rfc3339#section-5.8) format(for example, YYYY-MM-DDTHH:MM:SSZ). The default is to start fulfilling the request immediately.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Valid<wbr>Until<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The end date and time of the request, in UTC [RFC3339](https://tools.ietf.org/html/rfc3339#section-5.8) format(for example, YYYY-MM-DDTHH:MM:SSZ). At this point, no new Spot instance requests are placed or enabled to fulfill the request. The default end date is 7 days from the current date.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Volume<wbr>Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the devices created by the instance at launch time.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Vpc<wbr>Security<wbr>Group<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}A list of security group IDs to associate with.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Wait<wbr>For<wbr>Fulfillment<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}If set, this provider will
wait for the Spot Request to be fulfilled, and will throw an error if the
timeout of 10m is reached.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">ami<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The AMI to use for the instance.
{{% /md %}}</dd>

    <dt class="property-"
            title="">arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">associate<wbr>Public<wbr>Ip<wbr>Address<span class="property-indicator"></span>
        <span class="property-type">boolean</span>
    </dt>
    <dd>{{% md %}}Associate a public ip address with an instance in a VPC.  Boolean value.
{{% /md %}}</dd>

    <dt class="property-"
            title="">availability<wbr>Zone<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The AZ to start the instance in.
{{% /md %}}</dd>

    <dt class="property-"
            title="">block<wbr>Duration<wbr>Minutes<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The required duration for the Spot instances, in minutes. This value must be a multiple of 60 (60, 120, 180, 240, 300, or 360).
The duration period starts as soon as your Spot instance receives its instance ID. At the end of the duration period, Amazon EC2 marks the Spot instance for termination and provides a Spot instance termination notice, which gives the instance a two-minute warning before it terminates.
Note that you can&#39;t specify an Availability Zone group or a launch group if you specify a duration.
{{% /md %}}</dd>

    <dt class="property-"
            title="">cpu<wbr>Core<wbr>Count<span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}Sets the number of CPU cores for an instance. This option is
only supported on creation of instance type that support CPU Options
[CPU Cores and Threads Per CPU Core Per Instance Type](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/instance-optimize-cpu.html#cpu-options-supported-instances-values) - specifying this option for unsupported instance types will return an error from the EC2 API.
{{% /md %}}</dd>

    <dt class="property-"
            title="">cpu<wbr>Threads<wbr>Per<wbr>Core<span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}If set to to 1, hyperthreading is disabled on the launched instance. Defaults to 2 if not set. See [Optimizing CPU Options](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/instance-optimize-cpu.html) for more information.
{{% /md %}}</dd>

    <dt class="property-"
            title="">credit<wbr>Specification<span class="property-indicator"></span>
        <span class="property-type"><a href="#spotinstancerequestcreditspecification">Spot<wbr>Instance<wbr>Request<wbr>Credit<wbr>Specification?</a></span>
    </dt>
    <dd>{{% md %}}Customize the credit specification of the instance. See Credit Specification below for more details.
{{% /md %}}</dd>

    <dt class="property-"
            title="">disable<wbr>Api<wbr>Termination<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}If true, enables [EC2 Instance
Termination Protection](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/terminating-instances.html#Using_ChangingDisableAPITermination)
{{% /md %}}</dd>

    <dt class="property-"
            title="">ebs<wbr>Block<wbr>Devices<span class="property-indicator"></span>
        <span class="property-type"><a href="#spotinstancerequestebsblockdevice">Spot<wbr>Instance<wbr>Request<wbr>Ebs<wbr>Block<wbr>Device[]</a></span>
    </dt>
    <dd>{{% md %}}Additional EBS block devices to attach to the
instance.  Block device configurations only apply on resource creation. See Block Devices below for details on attributes and drift detection.
{{% /md %}}</dd>

    <dt class="property-"
            title="">ebs<wbr>Optimized<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}If true, the launched EC2 instance will be EBS-optimized.
Note that if this is not set on an instance type that is optimized by default then
this will show as disabled but if the instance type is optimized by default then
there is no need to set this and there is no effect to disabling it.
See the [EBS Optimized section](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/EBSOptimized.html) of the AWS User Guide for more information.
{{% /md %}}</dd>

    <dt class="property-"
            title="">ephemeral<wbr>Block<wbr>Devices<span class="property-indicator"></span>
        <span class="property-type"><a href="#spotinstancerequestephemeralblockdevice">Spot<wbr>Instance<wbr>Request<wbr>Ephemeral<wbr>Block<wbr>Device[]</a></span>
    </dt>
    <dd>{{% md %}}Customize Ephemeral (also known as
&#34;Instance Store&#34;) volumes on the instance. See Block Devices below for details.
{{% /md %}}</dd>

    <dt class="property-"
            title="">get<wbr>Password<wbr>Data<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}If true, wait for password data to become available and retrieve it. Useful for getting the administrator password for instances running Microsoft Windows. The password data is exported to the `password_data` attribute. See [GetPasswordData](https://docs.aws.amazon.com/AWSEC2/latest/APIReference/API_GetPasswordData.html) for more information.
{{% /md %}}</dd>

    <dt class="property-"
            title="">hibernation<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}If true, the launched EC2 instance will support hibernation.
{{% /md %}}</dd>

    <dt class="property-"
            title="">host<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Id of a dedicated host that the instance will be assigned to. Use when an instance is to be launched on a specific dedicated host.
{{% /md %}}</dd>

    <dt class="property-"
            title="">iam<wbr>Instance<wbr>Profile<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The IAM Instance Profile to
launch the instance with. Specified as the name of the Instance Profile. Ensure your credentials have the correct permission to assign the instance profile according to the [EC2 documentation](http://docs.aws.amazon.com/IAM/latest/UserGuide/id_roles_use_switch-role-ec2.html#roles-usingrole-ec2instance-permissions), notably `iam:PassRole`.
* `ipv6_address_count`- (Optional) A number of IPv6 addresses to associate with the primary network interface. Amazon EC2 chooses the IPv6 addresses from the range of your subnet.
{{% /md %}}</dd>

    <dt class="property-"
            title="">instance<wbr>Initiated<wbr>Shutdown<wbr>Behavior<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Shutdown behavior for the
instance. Amazon defaults this to `stop` for EBS-backed instances and
`terminate` for instance-store instances. Cannot be set on instance-store
instances. See [Shutdown Behavior](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/terminating-instances.html#Using_ChangingInstanceInitiatedShutdownBehavior) for more information.
{{% /md %}}</dd>

    <dt class="property-"
            title="">instance<wbr>Interruption<wbr>Behaviour<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Indicates whether a Spot instance stops or terminates when it is interrupted. Default is `terminate` as this is the current AWS behaviour.
{{% /md %}}</dd>

    <dt class="property-"
            title="">instance<wbr>State<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">instance<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type of instance to start. Updates to this field will trigger a stop/start of the EC2 instance.
{{% /md %}}</dd>

    <dt class="property-"
            title="">ipv6Address<wbr>Count<span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">ipv6Addresses<span class="property-indicator"></span>
        <span class="property-type">string[]</span>
    </dt>
    <dd>{{% md %}}Specify one or more IPv6 addresses from the range of the subnet to associate with the primary network interface
{{% /md %}}</dd>

    <dt class="property-"
            title="">key<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The key name of the Key Pair to use for the instance; which can be managed using the `aws.ec2.KeyPair` resource.
{{% /md %}}</dd>

    <dt class="property-"
            title="">launch<wbr>Group<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A launch group is a group of spot instances that launch together and terminate together.
If left empty instances are launched and terminated individually.
{{% /md %}}</dd>

    <dt class="property-"
            title="">monitoring<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}If true, the launched EC2 instance will have detailed monitoring enabled. (Available since v0.6.0)
{{% /md %}}</dd>

    <dt class="property-"
            title="">network<wbr>Interfaces<span class="property-indicator"></span>
        <span class="property-type"><a href="#spotinstancerequestnetworkinterface">Spot<wbr>Instance<wbr>Request<wbr>Network<wbr>Interface[]</a></span>
    </dt>
    <dd>{{% md %}}Customize network interfaces to be attached at instance boot time. See Network Interfaces below for more details.
{{% /md %}}</dd>

    <dt class="property-"
            title="">password<wbr>Data<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">placement<wbr>Group<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Placement Group to start the instance in.
{{% /md %}}</dd>

    <dt class="property-"
            title="">primary<wbr>Network<wbr>Interface<wbr>Id<span class="property-indicator"></span>
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
    <dd>{{% md %}}Private IP address to associate with the
instance in a VPC.
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
            title="">root<wbr>Block<wbr>Device<span class="property-indicator"></span>
        <span class="property-type"><a href="#spotinstancerequestrootblockdevice">Spot<wbr>Instance<wbr>Request<wbr>Root<wbr>Block<wbr>Device</a></span>
    </dt>
    <dd>{{% md %}}Customize details about the root block
device of the instance. See Block Devices below for details.
{{% /md %}}</dd>

    <dt class="property-"
            title="">security<wbr>Groups<span class="property-indicator"></span>
        <span class="property-type">string[]</span>
    </dt>
    <dd>{{% md %}}A list of security group names (EC2-Classic) or IDs (default VPC) to associate with.
{{% /md %}}</dd>

    <dt class="property-"
            title="">source<wbr>Dest<wbr>Check<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Controls if traffic is routed to the instance when
the destination address does not match the instance. Used for NAT or VPNs. Defaults true.
{{% /md %}}</dd>

    <dt class="property-"
            title="">spot<wbr>Bid<wbr>Status<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The current [bid
status](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/spot-bid-status.html)
of the Spot Instance Request.
* `spot_request_state` The current [request
state](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/spot-requests.html#creating-spot-request-status)
of the Spot Instance Request.
{{% /md %}}</dd>

    <dt class="property-"
            title="">spot<wbr>Instance<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Instance ID (if any) that is currently fulfilling
the Spot Instance request.
{{% /md %}}</dd>

    <dt class="property-"
            title="">spot<wbr>Price<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The maximum price to request on the spot market.
{{% /md %}}</dd>

    <dt class="property-"
            title="">spot<wbr>Request<wbr>State<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">spot<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}If set to `one-time`, after
the instance is terminated, the spot request will be closed.
{{% /md %}}</dd>

    <dt class="property-"
            title="">subnet<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The VPC Subnet ID to launch in.
{{% /md %}}</dd>

    <dt class="property-"
            title="">tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-"
            title="">tenancy<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The tenancy of the instance (if the instance is running in a VPC). An instance with a tenancy of dedicated runs on single-tenant hardware. The host tenancy is not supported for the import-instance command.
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
            title="">valid<wbr>From<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The start date and time of the request, in UTC [RFC3339](https://tools.ietf.org/html/rfc3339#section-5.8) format(for example, YYYY-MM-DDTHH:MM:SSZ). The default is to start fulfilling the request immediately.
{{% /md %}}</dd>

    <dt class="property-"
            title="">valid<wbr>Until<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The end date and time of the request, in UTC [RFC3339](https://tools.ietf.org/html/rfc3339#section-5.8) format(for example, YYYY-MM-DDTHH:MM:SSZ). At this point, no new Spot instance requests are placed or enabled to fulfill the request. The default end date is 7 days from the current date.
{{% /md %}}</dd>

    <dt class="property-"
            title="">volume<wbr>Tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the devices created by the instance at launch time.
{{% /md %}}</dd>

    <dt class="property-"
            title="">vpc<wbr>Security<wbr>Group<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">string[]</span>
    </dt>
    <dd>{{% md %}}A list of security group IDs to associate with.
{{% /md %}}</dd>

    <dt class="property-"
            title="">wait<wbr>For<wbr>Fulfillment<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}If set, this provider will
wait for the Spot Request to be fulfilled, and will throw an error if the
timeout of 10m is reached.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">ami<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The AMI to use for the instance.
{{% /md %}}</dd>

    <dt class="property-"
            title="">arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">associate_<wbr>public_<wbr>ip_<wbr>address<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Associate a public ip address with an instance in a VPC.  Boolean value.
{{% /md %}}</dd>

    <dt class="property-"
            title="">availability_<wbr>zone<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The AZ to start the instance in.
{{% /md %}}</dd>

    <dt class="property-"
            title="">block_<wbr>duration_<wbr>minutes<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The required duration for the Spot instances, in minutes. This value must be a multiple of 60 (60, 120, 180, 240, 300, or 360).
The duration period starts as soon as your Spot instance receives its instance ID. At the end of the duration period, Amazon EC2 marks the Spot instance for termination and provides a Spot instance termination notice, which gives the instance a two-minute warning before it terminates.
Note that you can&#39;t specify an Availability Zone group or a launch group if you specify a duration.
{{% /md %}}</dd>

    <dt class="property-"
            title="">cpu_<wbr>core_<wbr>count<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}Sets the number of CPU cores for an instance. This option is
only supported on creation of instance type that support CPU Options
[CPU Cores and Threads Per CPU Core Per Instance Type](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/instance-optimize-cpu.html#cpu-options-supported-instances-values) - specifying this option for unsupported instance types will return an error from the EC2 API.
{{% /md %}}</dd>

    <dt class="property-"
            title="">cpu_<wbr>threads_<wbr>per_<wbr>core<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}If set to to 1, hyperthreading is disabled on the launched instance. Defaults to 2 if not set. See [Optimizing CPU Options](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/instance-optimize-cpu.html) for more information.
{{% /md %}}</dd>

    <dt class="property-"
            title="">credit_<wbr>specification<span class="property-indicator"></span>
        <span class="property-type"><a href="#spotinstancerequestcreditspecification">Dict[Spot<wbr>Instance<wbr>Request<wbr>Credit<wbr>Specification]</a></span>
    </dt>
    <dd>{{% md %}}Customize the credit specification of the instance. See Credit Specification below for more details.
{{% /md %}}</dd>

    <dt class="property-"
            title="">disable_<wbr>api_<wbr>termination<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}If true, enables [EC2 Instance
Termination Protection](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/terminating-instances.html#Using_ChangingDisableAPITermination)
{{% /md %}}</dd>

    <dt class="property-"
            title="">ebs_<wbr>block_<wbr>devices<span class="property-indicator"></span>
        <span class="property-type"><a href="#spotinstancerequestebsblockdevice">List[Spot<wbr>Instance<wbr>Request<wbr>Ebs<wbr>Block<wbr>Device]</a></span>
    </dt>
    <dd>{{% md %}}Additional EBS block devices to attach to the
instance.  Block device configurations only apply on resource creation. See Block Devices below for details on attributes and drift detection.
{{% /md %}}</dd>

    <dt class="property-"
            title="">ebs_<wbr>optimized<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}If true, the launched EC2 instance will be EBS-optimized.
Note that if this is not set on an instance type that is optimized by default then
this will show as disabled but if the instance type is optimized by default then
there is no need to set this and there is no effect to disabling it.
See the [EBS Optimized section](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/EBSOptimized.html) of the AWS User Guide for more information.
{{% /md %}}</dd>

    <dt class="property-"
            title="">ephemeral_<wbr>block_<wbr>devices<span class="property-indicator"></span>
        <span class="property-type"><a href="#spotinstancerequestephemeralblockdevice">List[Spot<wbr>Instance<wbr>Request<wbr>Ephemeral<wbr>Block<wbr>Device]</a></span>
    </dt>
    <dd>{{% md %}}Customize Ephemeral (also known as
&#34;Instance Store&#34;) volumes on the instance. See Block Devices below for details.
{{% /md %}}</dd>

    <dt class="property-"
            title="">get_<wbr>password_<wbr>data<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}If true, wait for password data to become available and retrieve it. Useful for getting the administrator password for instances running Microsoft Windows. The password data is exported to the `password_data` attribute. See [GetPasswordData](https://docs.aws.amazon.com/AWSEC2/latest/APIReference/API_GetPasswordData.html) for more information.
{{% /md %}}</dd>

    <dt class="property-"
            title="">hibernation<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}If true, the launched EC2 instance will support hibernation.
{{% /md %}}</dd>

    <dt class="property-"
            title="">host_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The Id of a dedicated host that the instance will be assigned to. Use when an instance is to be launched on a specific dedicated host.
{{% /md %}}</dd>

    <dt class="property-"
            title="">iam_<wbr>instance_<wbr>profile<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The IAM Instance Profile to
launch the instance with. Specified as the name of the Instance Profile. Ensure your credentials have the correct permission to assign the instance profile according to the [EC2 documentation](http://docs.aws.amazon.com/IAM/latest/UserGuide/id_roles_use_switch-role-ec2.html#roles-usingrole-ec2instance-permissions), notably `iam:PassRole`.
* `ipv6_address_count`- (Optional) A number of IPv6 addresses to associate with the primary network interface. Amazon EC2 chooses the IPv6 addresses from the range of your subnet.
{{% /md %}}</dd>

    <dt class="property-"
            title="">instance_<wbr>initiated_<wbr>shutdown_<wbr>behavior<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Shutdown behavior for the
instance. Amazon defaults this to `stop` for EBS-backed instances and
`terminate` for instance-store instances. Cannot be set on instance-store
instances. See [Shutdown Behavior](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/terminating-instances.html#Using_ChangingInstanceInitiatedShutdownBehavior) for more information.
{{% /md %}}</dd>

    <dt class="property-"
            title="">instance_<wbr>interruption_<wbr>behaviour<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Indicates whether a Spot instance stops or terminates when it is interrupted. Default is `terminate` as this is the current AWS behaviour.
{{% /md %}}</dd>

    <dt class="property-"
            title="">instance_<wbr>state<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">instance_<wbr>type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The type of instance to start. Updates to this field will trigger a stop/start of the EC2 instance.
{{% /md %}}</dd>

    <dt class="property-"
            title="">ipv6_<wbr>address_<wbr>count<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">ipv6_<wbr>addresses<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}Specify one or more IPv6 addresses from the range of the subnet to associate with the primary network interface
{{% /md %}}</dd>

    <dt class="property-"
            title="">key_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The key name of the Key Pair to use for the instance; which can be managed using the `aws.ec2.KeyPair` resource.
{{% /md %}}</dd>

    <dt class="property-"
            title="">launch_<wbr>group<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A launch group is a group of spot instances that launch together and terminate together.
If left empty instances are launched and terminated individually.
{{% /md %}}</dd>

    <dt class="property-"
            title="">monitoring<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}If true, the launched EC2 instance will have detailed monitoring enabled. (Available since v0.6.0)
{{% /md %}}</dd>

    <dt class="property-"
            title="">network_<wbr>interfaces<span class="property-indicator"></span>
        <span class="property-type"><a href="#spotinstancerequestnetworkinterface">List[Spot<wbr>Instance<wbr>Request<wbr>Network<wbr>Interface]</a></span>
    </dt>
    <dd>{{% md %}}Customize network interfaces to be attached at instance boot time. See Network Interfaces below for more details.
{{% /md %}}</dd>

    <dt class="property-"
            title="">password_<wbr>data<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">placement_<wbr>group<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The Placement Group to start the instance in.
{{% /md %}}</dd>

    <dt class="property-"
            title="">primary_<wbr>network_<wbr>interface_<wbr>id<span class="property-indicator"></span>
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
    <dd>{{% md %}}Private IP address to associate with the
instance in a VPC.
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
            title="">root_<wbr>block_<wbr>device<span class="property-indicator"></span>
        <span class="property-type"><a href="#spotinstancerequestrootblockdevice">Dict[Spot<wbr>Instance<wbr>Request<wbr>Root<wbr>Block<wbr>Device]</a></span>
    </dt>
    <dd>{{% md %}}Customize details about the root block
device of the instance. See Block Devices below for details.
{{% /md %}}</dd>

    <dt class="property-"
            title="">security_<wbr>groups<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}A list of security group names (EC2-Classic) or IDs (default VPC) to associate with.
{{% /md %}}</dd>

    <dt class="property-"
            title="">source_<wbr>dest_<wbr>check<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Controls if traffic is routed to the instance when
the destination address does not match the instance. Used for NAT or VPNs. Defaults true.
{{% /md %}}</dd>

    <dt class="property-"
            title="">spot_<wbr>bid_<wbr>status<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The current [bid
status](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/spot-bid-status.html)
of the Spot Instance Request.
* `spot_request_state` The current [request
state](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/spot-requests.html#creating-spot-request-status)
of the Spot Instance Request.
{{% /md %}}</dd>

    <dt class="property-"
            title="">spot_<wbr>instance_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The Instance ID (if any) that is currently fulfilling
the Spot Instance request.
{{% /md %}}</dd>

    <dt class="property-"
            title="">spot_<wbr>price<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The maximum price to request on the spot market.
{{% /md %}}</dd>

    <dt class="property-"
            title="">spot_<wbr>request_<wbr>state<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">spot_<wbr>type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}If set to `one-time`, after
the instance is terminated, the spot request will be closed.
{{% /md %}}</dd>

    <dt class="property-"
            title="">subnet_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The VPC Subnet ID to launch in.
{{% /md %}}</dd>

    <dt class="property-"
            title="">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-"
            title="">tenancy<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The tenancy of the instance (if the instance is running in a VPC). An instance with a tenancy of dedicated runs on single-tenant hardware. The host tenancy is not supported for the import-instance command.
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
            title="">valid_<wbr>from<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The start date and time of the request, in UTC [RFC3339](https://tools.ietf.org/html/rfc3339#section-5.8) format(for example, YYYY-MM-DDTHH:MM:SSZ). The default is to start fulfilling the request immediately.
{{% /md %}}</dd>

    <dt class="property-"
            title="">valid_<wbr>until<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The end date and time of the request, in UTC [RFC3339](https://tools.ietf.org/html/rfc3339#section-5.8) format(for example, YYYY-MM-DDTHH:MM:SSZ). At this point, no new Spot instance requests are placed or enabled to fulfill the request. The default end date is 7 days from the current date.
{{% /md %}}</dd>

    <dt class="property-"
            title="">volume_<wbr>tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the devices created by the instance at launch time.
{{% /md %}}</dd>

    <dt class="property-"
            title="">vpc_<wbr>security_<wbr>group_<wbr>ids<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}A list of security group IDs to associate with.
{{% /md %}}</dd>

    <dt class="property-"
            title="">wait_<wbr>for_<wbr>fulfillment<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}If set, this provider will
wait for the Spot Request to be fulfilled, and will throw an error if the
timeout of 10m is reached.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





## Look up an Existing SpotInstanceRequest Resource

{{< chooser language "javascript,typescript,python,go,csharp  " / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">pulumi.Input&lt;pulumi.ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/ec2/#SpotInstanceRequestState">SpotInstanceRequestState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/ec2/#SpotInstanceRequest">SpotInstanceRequest</a></span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>ami=None<span class="p">, </span>arn=None<span class="p">, </span>associate_public_ip_address=None<span class="p">, </span>availability_zone=None<span class="p">, </span>block_duration_minutes=None<span class="p">, </span>cpu_core_count=None<span class="p">, </span>cpu_threads_per_core=None<span class="p">, </span>credit_specification=None<span class="p">, </span>disable_api_termination=None<span class="p">, </span>ebs_block_devices=None<span class="p">, </span>ebs_optimized=None<span class="p">, </span>ephemeral_block_devices=None<span class="p">, </span>get_password_data=None<span class="p">, </span>hibernation=None<span class="p">, </span>host_id=None<span class="p">, </span>iam_instance_profile=None<span class="p">, </span>instance_initiated_shutdown_behavior=None<span class="p">, </span>instance_interruption_behaviour=None<span class="p">, </span>instance_state=None<span class="p">, </span>instance_type=None<span class="p">, </span>ipv6_address_count=None<span class="p">, </span>ipv6_addresses=None<span class="p">, </span>key_name=None<span class="p">, </span>launch_group=None<span class="p">, </span>monitoring=None<span class="p">, </span>network_interfaces=None<span class="p">, </span>password_data=None<span class="p">, </span>placement_group=None<span class="p">, </span>primary_network_interface_id=None<span class="p">, </span>private_dns=None<span class="p">, </span>private_ip=None<span class="p">, </span>public_dns=None<span class="p">, </span>public_ip=None<span class="p">, </span>root_block_device=None<span class="p">, </span>security_groups=None<span class="p">, </span>source_dest_check=None<span class="p">, </span>spot_bid_status=None<span class="p">, </span>spot_instance_id=None<span class="p">, </span>spot_price=None<span class="p">, </span>spot_request_state=None<span class="p">, </span>spot_type=None<span class="p">, </span>subnet_id=None<span class="p">, </span>tags=None<span class="p">, </span>tenancy=None<span class="p">, </span>user_data=None<span class="p">, </span>user_data_base64=None<span class="p">, </span>valid_from=None<span class="p">, </span>valid_until=None<span class="p">, </span>volume_tags=None<span class="p">, </span>vpc_security_group_ids=None<span class="p">, </span>wait_for_fulfillment=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetSpotInstanceRequest<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">pulumi.IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ec2?tab=doc#SpotInstanceRequestState">SpotInstanceRequestState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ec2?tab=doc#SpotInstanceRequest">SpotInstanceRequest</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ec2.SpotInstanceRequest.html">SpotInstanceRequest</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Pulumi.Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ec2.SpotInstanceRequestState.html">SpotInstanceRequestState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
{{% /choosable %}}

Get an existing SpotInstanceRequest resource's state with the given name, ID, and optional extra properties used to qualify the lookup.

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
            title="Optional">Ami<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The AMI to use for the instance.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Associate<wbr>Public<wbr>Ip<wbr>Address<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Associate a public ip address with an instance in a VPC.  Boolean value.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Availability<wbr>Zone<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The AZ to start the instance in.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Block<wbr>Duration<wbr>Minutes<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The required duration for the Spot instances, in minutes. This value must be a multiple of 60 (60, 120, 180, 240, 300, or 360).
The duration period starts as soon as your Spot instance receives its instance ID. At the end of the duration period, Amazon EC2 marks the Spot instance for termination and provides a Spot instance termination notice, which gives the instance a two-minute warning before it terminates.
Note that you can&#39;t specify an Availability Zone group or a launch group if you specify a duration.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Cpu<wbr>Core<wbr>Count<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}Sets the number of CPU cores for an instance. This option is
only supported on creation of instance type that support CPU Options
[CPU Cores and Threads Per CPU Core Per Instance Type](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/instance-optimize-cpu.html#cpu-options-supported-instances-values) - specifying this option for unsupported instance types will return an error from the EC2 API.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Cpu<wbr>Threads<wbr>Per<wbr>Core<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}If set to to 1, hyperthreading is disabled on the launched instance. Defaults to 2 if not set. See [Optimizing CPU Options](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/instance-optimize-cpu.html) for more information.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Credit<wbr>Specification<span class="property-indicator"></span>
        <span class="property-type"><a href="#spotinstancerequestcreditspecification">Spot<wbr>Instance<wbr>Request<wbr>Credit<wbr>Specification<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}Customize the credit specification of the instance. See Credit Specification below for more details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Disable<wbr>Api<wbr>Termination<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}If true, enables [EC2 Instance
Termination Protection](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/terminating-instances.html#Using_ChangingDisableAPITermination)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ebs<wbr>Block<wbr>Devices<span class="property-indicator"></span>
        <span class="property-type"><a href="#spotinstancerequestebsblockdevice">List&lt;Spot<wbr>Instance<wbr>Request<wbr>Ebs<wbr>Block<wbr>Device<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}Additional EBS block devices to attach to the
instance.  Block device configurations only apply on resource creation. See Block Devices below for details on attributes and drift detection.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ebs<wbr>Optimized<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}If true, the launched EC2 instance will be EBS-optimized.
Note that if this is not set on an instance type that is optimized by default then
this will show as disabled but if the instance type is optimized by default then
there is no need to set this and there is no effect to disabling it.
See the [EBS Optimized section](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/EBSOptimized.html) of the AWS User Guide for more information.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ephemeral<wbr>Block<wbr>Devices<span class="property-indicator"></span>
        <span class="property-type"><a href="#spotinstancerequestephemeralblockdevice">List&lt;Spot<wbr>Instance<wbr>Request<wbr>Ephemeral<wbr>Block<wbr>Device<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}Customize Ephemeral (also known as
&#34;Instance Store&#34;) volumes on the instance. See Block Devices below for details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Get<wbr>Password<wbr>Data<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}If true, wait for password data to become available and retrieve it. Useful for getting the administrator password for instances running Microsoft Windows. The password data is exported to the `password_data` attribute. See [GetPasswordData](https://docs.aws.amazon.com/AWSEC2/latest/APIReference/API_GetPasswordData.html) for more information.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Hibernation<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}If true, the launched EC2 instance will support hibernation.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Host<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The Id of a dedicated host that the instance will be assigned to. Use when an instance is to be launched on a specific dedicated host.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Iam<wbr>Instance<wbr>Profile<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The IAM Instance Profile to
launch the instance with. Specified as the name of the Instance Profile. Ensure your credentials have the correct permission to assign the instance profile according to the [EC2 documentation](http://docs.aws.amazon.com/IAM/latest/UserGuide/id_roles_use_switch-role-ec2.html#roles-usingrole-ec2instance-permissions), notably `iam:PassRole`.
* `ipv6_address_count`- (Optional) A number of IPv6 addresses to associate with the primary network interface. Amazon EC2 chooses the IPv6 addresses from the range of your subnet.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Instance<wbr>Initiated<wbr>Shutdown<wbr>Behavior<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Shutdown behavior for the
instance. Amazon defaults this to `stop` for EBS-backed instances and
`terminate` for instance-store instances. Cannot be set on instance-store
instances. See [Shutdown Behavior](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/terminating-instances.html#Using_ChangingInstanceInitiatedShutdownBehavior) for more information.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Instance<wbr>Interruption<wbr>Behaviour<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Indicates whether a Spot instance stops or terminates when it is interrupted. Default is `terminate` as this is the current AWS behaviour.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Instance<wbr>State<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Instance<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The type of instance to start. Updates to this field will trigger a stop/start of the EC2 instance.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ipv6Address<wbr>Count<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ipv6Addresses<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}Specify one or more IPv6 addresses from the range of the subnet to associate with the primary network interface
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Key<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The key name of the Key Pair to use for the instance; which can be managed using the `aws.ec2.KeyPair` resource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Launch<wbr>Group<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A launch group is a group of spot instances that launch together and terminate together.
If left empty instances are launched and terminated individually.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Monitoring<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}If true, the launched EC2 instance will have detailed monitoring enabled. (Available since v0.6.0)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Network<wbr>Interfaces<span class="property-indicator"></span>
        <span class="property-type"><a href="#spotinstancerequestnetworkinterface">List&lt;Spot<wbr>Instance<wbr>Request<wbr>Network<wbr>Interface<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}Customize network interfaces to be attached at instance boot time. See Network Interfaces below for more details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Password<wbr>Data<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Placement<wbr>Group<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The Placement Group to start the instance in.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Primary<wbr>Network<wbr>Interface<wbr>Id<span class="property-indicator"></span>
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
    <dd>{{% md %}}Private IP address to associate with the
instance in a VPC.
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
            title="Optional">Root<wbr>Block<wbr>Device<span class="property-indicator"></span>
        <span class="property-type"><a href="#spotinstancerequestrootblockdevice">Spot<wbr>Instance<wbr>Request<wbr>Root<wbr>Block<wbr>Device<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}Customize details about the root block
device of the instance. See Block Devices below for details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Security<wbr>Groups<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}A list of security group names (EC2-Classic) or IDs (default VPC) to associate with.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Source<wbr>Dest<wbr>Check<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Controls if traffic is routed to the instance when
the destination address does not match the instance. Used for NAT or VPNs. Defaults true.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Spot<wbr>Bid<wbr>Status<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The current [bid
status](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/spot-bid-status.html)
of the Spot Instance Request.
* `spot_request_state` The current [request
state](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/spot-requests.html#creating-spot-request-status)
of the Spot Instance Request.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Spot<wbr>Instance<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The Instance ID (if any) that is currently fulfilling
the Spot Instance request.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Spot<wbr>Price<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The maximum price to request on the spot market.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Spot<wbr>Request<wbr>State<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Spot<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}If set to `one-time`, after
the instance is terminated, the spot request will be closed.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Subnet<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The VPC Subnet ID to launch in.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tenancy<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The tenancy of the instance (if the instance is running in a VPC). An instance with a tenancy of dedicated runs on single-tenant hardware. The host tenancy is not supported for the import-instance command.
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
            title="Optional">Valid<wbr>From<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The start date and time of the request, in UTC [RFC3339](https://tools.ietf.org/html/rfc3339#section-5.8) format(for example, YYYY-MM-DDTHH:MM:SSZ). The default is to start fulfilling the request immediately.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Valid<wbr>Until<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The end date and time of the request, in UTC [RFC3339](https://tools.ietf.org/html/rfc3339#section-5.8) format(for example, YYYY-MM-DDTHH:MM:SSZ). At this point, no new Spot instance requests are placed or enabled to fulfill the request. The default end date is 7 days from the current date.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Volume<wbr>Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the devices created by the instance at launch time.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Vpc<wbr>Security<wbr>Group<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}A list of security group IDs to associate with.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Wait<wbr>For<wbr>Fulfillment<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}If set, this provider will
wait for the Spot Request to be fulfilled, and will throw an error if the
timeout of 10m is reached.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Ami<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The AMI to use for the instance.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Associate<wbr>Public<wbr>Ip<wbr>Address<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Associate a public ip address with an instance in a VPC.  Boolean value.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Availability<wbr>Zone<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The AZ to start the instance in.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Block<wbr>Duration<wbr>Minutes<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The required duration for the Spot instances, in minutes. This value must be a multiple of 60 (60, 120, 180, 240, 300, or 360).
The duration period starts as soon as your Spot instance receives its instance ID. At the end of the duration period, Amazon EC2 marks the Spot instance for termination and provides a Spot instance termination notice, which gives the instance a two-minute warning before it terminates.
Note that you can&#39;t specify an Availability Zone group or a launch group if you specify a duration.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Cpu<wbr>Core<wbr>Count<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}Sets the number of CPU cores for an instance. This option is
only supported on creation of instance type that support CPU Options
[CPU Cores and Threads Per CPU Core Per Instance Type](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/instance-optimize-cpu.html#cpu-options-supported-instances-values) - specifying this option for unsupported instance types will return an error from the EC2 API.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Cpu<wbr>Threads<wbr>Per<wbr>Core<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}If set to to 1, hyperthreading is disabled on the launched instance. Defaults to 2 if not set. See [Optimizing CPU Options](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/instance-optimize-cpu.html) for more information.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Credit<wbr>Specification<span class="property-indicator"></span>
        <span class="property-type"><a href="#spotinstancerequestcreditspecification">*Spot<wbr>Instance<wbr>Request<wbr>Credit<wbr>Specification</a></span>
    </dt>
    <dd>{{% md %}}Customize the credit specification of the instance. See Credit Specification below for more details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Disable<wbr>Api<wbr>Termination<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}If true, enables [EC2 Instance
Termination Protection](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/terminating-instances.html#Using_ChangingDisableAPITermination)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ebs<wbr>Block<wbr>Devices<span class="property-indicator"></span>
        <span class="property-type"><a href="#spotinstancerequestebsblockdevice">[]Spot<wbr>Instance<wbr>Request<wbr>Ebs<wbr>Block<wbr>Device</a></span>
    </dt>
    <dd>{{% md %}}Additional EBS block devices to attach to the
instance.  Block device configurations only apply on resource creation. See Block Devices below for details on attributes and drift detection.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ebs<wbr>Optimized<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}If true, the launched EC2 instance will be EBS-optimized.
Note that if this is not set on an instance type that is optimized by default then
this will show as disabled but if the instance type is optimized by default then
there is no need to set this and there is no effect to disabling it.
See the [EBS Optimized section](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/EBSOptimized.html) of the AWS User Guide for more information.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ephemeral<wbr>Block<wbr>Devices<span class="property-indicator"></span>
        <span class="property-type"><a href="#spotinstancerequestephemeralblockdevice">[]Spot<wbr>Instance<wbr>Request<wbr>Ephemeral<wbr>Block<wbr>Device</a></span>
    </dt>
    <dd>{{% md %}}Customize Ephemeral (also known as
&#34;Instance Store&#34;) volumes on the instance. See Block Devices below for details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Get<wbr>Password<wbr>Data<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}If true, wait for password data to become available and retrieve it. Useful for getting the administrator password for instances running Microsoft Windows. The password data is exported to the `password_data` attribute. See [GetPasswordData](https://docs.aws.amazon.com/AWSEC2/latest/APIReference/API_GetPasswordData.html) for more information.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Hibernation<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}If true, the launched EC2 instance will support hibernation.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Host<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The Id of a dedicated host that the instance will be assigned to. Use when an instance is to be launched on a specific dedicated host.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Iam<wbr>Instance<wbr>Profile<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The IAM Instance Profile to
launch the instance with. Specified as the name of the Instance Profile. Ensure your credentials have the correct permission to assign the instance profile according to the [EC2 documentation](http://docs.aws.amazon.com/IAM/latest/UserGuide/id_roles_use_switch-role-ec2.html#roles-usingrole-ec2instance-permissions), notably `iam:PassRole`.
* `ipv6_address_count`- (Optional) A number of IPv6 addresses to associate with the primary network interface. Amazon EC2 chooses the IPv6 addresses from the range of your subnet.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Instance<wbr>Initiated<wbr>Shutdown<wbr>Behavior<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Shutdown behavior for the
instance. Amazon defaults this to `stop` for EBS-backed instances and
`terminate` for instance-store instances. Cannot be set on instance-store
instances. See [Shutdown Behavior](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/terminating-instances.html#Using_ChangingInstanceInitiatedShutdownBehavior) for more information.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Instance<wbr>Interruption<wbr>Behaviour<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Indicates whether a Spot instance stops or terminates when it is interrupted. Default is `terminate` as this is the current AWS behaviour.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Instance<wbr>State<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Instance<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The type of instance to start. Updates to this field will trigger a stop/start of the EC2 instance.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ipv6Address<wbr>Count<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ipv6Addresses<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}Specify one or more IPv6 addresses from the range of the subnet to associate with the primary network interface
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Key<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The key name of the Key Pair to use for the instance; which can be managed using the `aws.ec2.KeyPair` resource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Launch<wbr>Group<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}A launch group is a group of spot instances that launch together and terminate together.
If left empty instances are launched and terminated individually.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Monitoring<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}If true, the launched EC2 instance will have detailed monitoring enabled. (Available since v0.6.0)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Network<wbr>Interfaces<span class="property-indicator"></span>
        <span class="property-type"><a href="#spotinstancerequestnetworkinterface">[]Spot<wbr>Instance<wbr>Request<wbr>Network<wbr>Interface</a></span>
    </dt>
    <dd>{{% md %}}Customize network interfaces to be attached at instance boot time. See Network Interfaces below for more details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Password<wbr>Data<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Placement<wbr>Group<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The Placement Group to start the instance in.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Primary<wbr>Network<wbr>Interface<wbr>Id<span class="property-indicator"></span>
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
    <dd>{{% md %}}Private IP address to associate with the
instance in a VPC.
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
            title="Optional">Root<wbr>Block<wbr>Device<span class="property-indicator"></span>
        <span class="property-type"><a href="#spotinstancerequestrootblockdevice">*Spot<wbr>Instance<wbr>Request<wbr>Root<wbr>Block<wbr>Device</a></span>
    </dt>
    <dd>{{% md %}}Customize details about the root block
device of the instance. See Block Devices below for details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Security<wbr>Groups<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}A list of security group names (EC2-Classic) or IDs (default VPC) to associate with.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Source<wbr>Dest<wbr>Check<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Controls if traffic is routed to the instance when
the destination address does not match the instance. Used for NAT or VPNs. Defaults true.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Spot<wbr>Bid<wbr>Status<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The current [bid
status](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/spot-bid-status.html)
of the Spot Instance Request.
* `spot_request_state` The current [request
state](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/spot-requests.html#creating-spot-request-status)
of the Spot Instance Request.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Spot<wbr>Instance<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The Instance ID (if any) that is currently fulfilling
the Spot Instance request.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Spot<wbr>Price<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The maximum price to request on the spot market.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Spot<wbr>Request<wbr>State<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Spot<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}If set to `one-time`, after
the instance is terminated, the spot request will be closed.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Subnet<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The VPC Subnet ID to launch in.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tenancy<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The tenancy of the instance (if the instance is running in a VPC). An instance with a tenancy of dedicated runs on single-tenant hardware. The host tenancy is not supported for the import-instance command.
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
            title="Optional">Valid<wbr>From<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The start date and time of the request, in UTC [RFC3339](https://tools.ietf.org/html/rfc3339#section-5.8) format(for example, YYYY-MM-DDTHH:MM:SSZ). The default is to start fulfilling the request immediately.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Valid<wbr>Until<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The end date and time of the request, in UTC [RFC3339](https://tools.ietf.org/html/rfc3339#section-5.8) format(for example, YYYY-MM-DDTHH:MM:SSZ). At this point, no new Spot instance requests are placed or enabled to fulfill the request. The default end date is 7 days from the current date.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Volume<wbr>Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the devices created by the instance at launch time.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Vpc<wbr>Security<wbr>Group<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}A list of security group IDs to associate with.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Wait<wbr>For<wbr>Fulfillment<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}If set, this provider will
wait for the Spot Request to be fulfilled, and will throw an error if the
timeout of 10m is reached.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">ami<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The AMI to use for the instance.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">associate<wbr>Public<wbr>Ip<wbr>Address<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Associate a public ip address with an instance in a VPC.  Boolean value.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">availability<wbr>Zone<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The AZ to start the instance in.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">block<wbr>Duration<wbr>Minutes<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The required duration for the Spot instances, in minutes. This value must be a multiple of 60 (60, 120, 180, 240, 300, or 360).
The duration period starts as soon as your Spot instance receives its instance ID. At the end of the duration period, Amazon EC2 marks the Spot instance for termination and provides a Spot instance termination notice, which gives the instance a two-minute warning before it terminates.
Note that you can&#39;t specify an Availability Zone group or a launch group if you specify a duration.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">cpu<wbr>Core<wbr>Count<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}Sets the number of CPU cores for an instance. This option is
only supported on creation of instance type that support CPU Options
[CPU Cores and Threads Per CPU Core Per Instance Type](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/instance-optimize-cpu.html#cpu-options-supported-instances-values) - specifying this option for unsupported instance types will return an error from the EC2 API.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">cpu<wbr>Threads<wbr>Per<wbr>Core<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}If set to to 1, hyperthreading is disabled on the launched instance. Defaults to 2 if not set. See [Optimizing CPU Options](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/instance-optimize-cpu.html) for more information.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">credit<wbr>Specification<span class="property-indicator"></span>
        <span class="property-type"><a href="#spotinstancerequestcreditspecification">Spot<wbr>Instance<wbr>Request<wbr>Credit<wbr>Specification?</a></span>
    </dt>
    <dd>{{% md %}}Customize the credit specification of the instance. See Credit Specification below for more details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">disable<wbr>Api<wbr>Termination<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}If true, enables [EC2 Instance
Termination Protection](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/terminating-instances.html#Using_ChangingDisableAPITermination)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ebs<wbr>Block<wbr>Devices<span class="property-indicator"></span>
        <span class="property-type"><a href="#spotinstancerequestebsblockdevice">Spot<wbr>Instance<wbr>Request<wbr>Ebs<wbr>Block<wbr>Device[]?</a></span>
    </dt>
    <dd>{{% md %}}Additional EBS block devices to attach to the
instance.  Block device configurations only apply on resource creation. See Block Devices below for details on attributes and drift detection.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ebs<wbr>Optimized<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}If true, the launched EC2 instance will be EBS-optimized.
Note that if this is not set on an instance type that is optimized by default then
this will show as disabled but if the instance type is optimized by default then
there is no need to set this and there is no effect to disabling it.
See the [EBS Optimized section](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/EBSOptimized.html) of the AWS User Guide for more information.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ephemeral<wbr>Block<wbr>Devices<span class="property-indicator"></span>
        <span class="property-type"><a href="#spotinstancerequestephemeralblockdevice">Spot<wbr>Instance<wbr>Request<wbr>Ephemeral<wbr>Block<wbr>Device[]?</a></span>
    </dt>
    <dd>{{% md %}}Customize Ephemeral (also known as
&#34;Instance Store&#34;) volumes on the instance. See Block Devices below for details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">get<wbr>Password<wbr>Data<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}If true, wait for password data to become available and retrieve it. Useful for getting the administrator password for instances running Microsoft Windows. The password data is exported to the `password_data` attribute. See [GetPasswordData](https://docs.aws.amazon.com/AWSEC2/latest/APIReference/API_GetPasswordData.html) for more information.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">hibernation<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}If true, the launched EC2 instance will support hibernation.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">host<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The Id of a dedicated host that the instance will be assigned to. Use when an instance is to be launched on a specific dedicated host.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">iam<wbr>Instance<wbr>Profile<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The IAM Instance Profile to
launch the instance with. Specified as the name of the Instance Profile. Ensure your credentials have the correct permission to assign the instance profile according to the [EC2 documentation](http://docs.aws.amazon.com/IAM/latest/UserGuide/id_roles_use_switch-role-ec2.html#roles-usingrole-ec2instance-permissions), notably `iam:PassRole`.
* `ipv6_address_count`- (Optional) A number of IPv6 addresses to associate with the primary network interface. Amazon EC2 chooses the IPv6 addresses from the range of your subnet.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">instance<wbr>Initiated<wbr>Shutdown<wbr>Behavior<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Shutdown behavior for the
instance. Amazon defaults this to `stop` for EBS-backed instances and
`terminate` for instance-store instances. Cannot be set on instance-store
instances. See [Shutdown Behavior](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/terminating-instances.html#Using_ChangingInstanceInitiatedShutdownBehavior) for more information.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">instance<wbr>Interruption<wbr>Behaviour<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Indicates whether a Spot instance stops or terminates when it is interrupted. Default is `terminate` as this is the current AWS behaviour.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">instance<wbr>State<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">instance<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The type of instance to start. Updates to this field will trigger a stop/start of the EC2 instance.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ipv6Address<wbr>Count<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ipv6Addresses<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}Specify one or more IPv6 addresses from the range of the subnet to associate with the primary network interface
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">key<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The key name of the Key Pair to use for the instance; which can be managed using the `aws.ec2.KeyPair` resource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">launch<wbr>Group<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A launch group is a group of spot instances that launch together and terminate together.
If left empty instances are launched and terminated individually.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">monitoring<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}If true, the launched EC2 instance will have detailed monitoring enabled. (Available since v0.6.0)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">network<wbr>Interfaces<span class="property-indicator"></span>
        <span class="property-type"><a href="#spotinstancerequestnetworkinterface">Spot<wbr>Instance<wbr>Request<wbr>Network<wbr>Interface[]?</a></span>
    </dt>
    <dd>{{% md %}}Customize network interfaces to be attached at instance boot time. See Network Interfaces below for more details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">password<wbr>Data<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">placement<wbr>Group<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The Placement Group to start the instance in.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">primary<wbr>Network<wbr>Interface<wbr>Id<span class="property-indicator"></span>
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
    <dd>{{% md %}}Private IP address to associate with the
instance in a VPC.
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
            title="Optional">root<wbr>Block<wbr>Device<span class="property-indicator"></span>
        <span class="property-type"><a href="#spotinstancerequestrootblockdevice">Spot<wbr>Instance<wbr>Request<wbr>Root<wbr>Block<wbr>Device?</a></span>
    </dt>
    <dd>{{% md %}}Customize details about the root block
device of the instance. See Block Devices below for details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">security<wbr>Groups<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}A list of security group names (EC2-Classic) or IDs (default VPC) to associate with.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">source<wbr>Dest<wbr>Check<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Controls if traffic is routed to the instance when
the destination address does not match the instance. Used for NAT or VPNs. Defaults true.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">spot<wbr>Bid<wbr>Status<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The current [bid
status](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/spot-bid-status.html)
of the Spot Instance Request.
* `spot_request_state` The current [request
state](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/spot-requests.html#creating-spot-request-status)
of the Spot Instance Request.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">spot<wbr>Instance<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The Instance ID (if any) that is currently fulfilling
the Spot Instance request.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">spot<wbr>Price<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The maximum price to request on the spot market.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">spot<wbr>Request<wbr>State<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">spot<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}If set to `one-time`, after
the instance is terminated, the spot request will be closed.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">subnet<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The VPC Subnet ID to launch in.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tenancy<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The tenancy of the instance (if the instance is running in a VPC). An instance with a tenancy of dedicated runs on single-tenant hardware. The host tenancy is not supported for the import-instance command.
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
            title="Optional">valid<wbr>From<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The start date and time of the request, in UTC [RFC3339](https://tools.ietf.org/html/rfc3339#section-5.8) format(for example, YYYY-MM-DDTHH:MM:SSZ). The default is to start fulfilling the request immediately.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">valid<wbr>Until<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The end date and time of the request, in UTC [RFC3339](https://tools.ietf.org/html/rfc3339#section-5.8) format(for example, YYYY-MM-DDTHH:MM:SSZ). At this point, no new Spot instance requests are placed or enabled to fulfill the request. The default end date is 7 days from the current date.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">volume<wbr>Tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the devices created by the instance at launch time.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">vpc<wbr>Security<wbr>Group<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}A list of security group IDs to associate with.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">wait<wbr>For<wbr>Fulfillment<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}If set, this provider will
wait for the Spot Request to be fulfilled, and will throw an error if the
timeout of 10m is reached.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">ami<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The AMI to use for the instance.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">associate_<wbr>public_<wbr>ip_<wbr>address<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Associate a public ip address with an instance in a VPC.  Boolean value.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">availability_<wbr>zone<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The AZ to start the instance in.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">block_<wbr>duration_<wbr>minutes<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The required duration for the Spot instances, in minutes. This value must be a multiple of 60 (60, 120, 180, 240, 300, or 360).
The duration period starts as soon as your Spot instance receives its instance ID. At the end of the duration period, Amazon EC2 marks the Spot instance for termination and provides a Spot instance termination notice, which gives the instance a two-minute warning before it terminates.
Note that you can&#39;t specify an Availability Zone group or a launch group if you specify a duration.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">cpu_<wbr>core_<wbr>count<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}Sets the number of CPU cores for an instance. This option is
only supported on creation of instance type that support CPU Options
[CPU Cores and Threads Per CPU Core Per Instance Type](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/instance-optimize-cpu.html#cpu-options-supported-instances-values) - specifying this option for unsupported instance types will return an error from the EC2 API.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">cpu_<wbr>threads_<wbr>per_<wbr>core<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}If set to to 1, hyperthreading is disabled on the launched instance. Defaults to 2 if not set. See [Optimizing CPU Options](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/instance-optimize-cpu.html) for more information.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">credit_<wbr>specification<span class="property-indicator"></span>
        <span class="property-type"><a href="#spotinstancerequestcreditspecification">Dict[Spot<wbr>Instance<wbr>Request<wbr>Credit<wbr>Specification]</a></span>
    </dt>
    <dd>{{% md %}}Customize the credit specification of the instance. See Credit Specification below for more details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">disable_<wbr>api_<wbr>termination<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}If true, enables [EC2 Instance
Termination Protection](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/terminating-instances.html#Using_ChangingDisableAPITermination)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ebs_<wbr>block_<wbr>devices<span class="property-indicator"></span>
        <span class="property-type"><a href="#spotinstancerequestebsblockdevice">List[Spot<wbr>Instance<wbr>Request<wbr>Ebs<wbr>Block<wbr>Device]</a></span>
    </dt>
    <dd>{{% md %}}Additional EBS block devices to attach to the
instance.  Block device configurations only apply on resource creation. See Block Devices below for details on attributes and drift detection.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ebs_<wbr>optimized<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}If true, the launched EC2 instance will be EBS-optimized.
Note that if this is not set on an instance type that is optimized by default then
this will show as disabled but if the instance type is optimized by default then
there is no need to set this and there is no effect to disabling it.
See the [EBS Optimized section](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/EBSOptimized.html) of the AWS User Guide for more information.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ephemeral_<wbr>block_<wbr>devices<span class="property-indicator"></span>
        <span class="property-type"><a href="#spotinstancerequestephemeralblockdevice">List[Spot<wbr>Instance<wbr>Request<wbr>Ephemeral<wbr>Block<wbr>Device]</a></span>
    </dt>
    <dd>{{% md %}}Customize Ephemeral (also known as
&#34;Instance Store&#34;) volumes on the instance. See Block Devices below for details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">get_<wbr>password_<wbr>data<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}If true, wait for password data to become available and retrieve it. Useful for getting the administrator password for instances running Microsoft Windows. The password data is exported to the `password_data` attribute. See [GetPasswordData](https://docs.aws.amazon.com/AWSEC2/latest/APIReference/API_GetPasswordData.html) for more information.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">hibernation<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}If true, the launched EC2 instance will support hibernation.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">host_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The Id of a dedicated host that the instance will be assigned to. Use when an instance is to be launched on a specific dedicated host.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">iam_<wbr>instance_<wbr>profile<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The IAM Instance Profile to
launch the instance with. Specified as the name of the Instance Profile. Ensure your credentials have the correct permission to assign the instance profile according to the [EC2 documentation](http://docs.aws.amazon.com/IAM/latest/UserGuide/id_roles_use_switch-role-ec2.html#roles-usingrole-ec2instance-permissions), notably `iam:PassRole`.
* `ipv6_address_count`- (Optional) A number of IPv6 addresses to associate with the primary network interface. Amazon EC2 chooses the IPv6 addresses from the range of your subnet.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">instance_<wbr>initiated_<wbr>shutdown_<wbr>behavior<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Shutdown behavior for the
instance. Amazon defaults this to `stop` for EBS-backed instances and
`terminate` for instance-store instances. Cannot be set on instance-store
instances. See [Shutdown Behavior](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/terminating-instances.html#Using_ChangingInstanceInitiatedShutdownBehavior) for more information.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">instance_<wbr>interruption_<wbr>behaviour<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Indicates whether a Spot instance stops or terminates when it is interrupted. Default is `terminate` as this is the current AWS behaviour.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">instance_<wbr>state<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">instance_<wbr>type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The type of instance to start. Updates to this field will trigger a stop/start of the EC2 instance.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ipv6_<wbr>address_<wbr>count<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ipv6_<wbr>addresses<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}Specify one or more IPv6 addresses from the range of the subnet to associate with the primary network interface
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">key_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The key name of the Key Pair to use for the instance; which can be managed using the `aws.ec2.KeyPair` resource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">launch_<wbr>group<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A launch group is a group of spot instances that launch together and terminate together.
If left empty instances are launched and terminated individually.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">monitoring<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}If true, the launched EC2 instance will have detailed monitoring enabled. (Available since v0.6.0)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">network_<wbr>interfaces<span class="property-indicator"></span>
        <span class="property-type"><a href="#spotinstancerequestnetworkinterface">List[Spot<wbr>Instance<wbr>Request<wbr>Network<wbr>Interface]</a></span>
    </dt>
    <dd>{{% md %}}Customize network interfaces to be attached at instance boot time. See Network Interfaces below for more details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">password_<wbr>data<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">placement_<wbr>group<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The Placement Group to start the instance in.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">primary_<wbr>network_<wbr>interface_<wbr>id<span class="property-indicator"></span>
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
    <dd>{{% md %}}Private IP address to associate with the
instance in a VPC.
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
            title="Optional">root_<wbr>block_<wbr>device<span class="property-indicator"></span>
        <span class="property-type"><a href="#spotinstancerequestrootblockdevice">Dict[Spot<wbr>Instance<wbr>Request<wbr>Root<wbr>Block<wbr>Device]</a></span>
    </dt>
    <dd>{{% md %}}Customize details about the root block
device of the instance. See Block Devices below for details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">security_<wbr>groups<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}A list of security group names (EC2-Classic) or IDs (default VPC) to associate with.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">source_<wbr>dest_<wbr>check<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Controls if traffic is routed to the instance when
the destination address does not match the instance. Used for NAT or VPNs. Defaults true.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">spot_<wbr>bid_<wbr>status<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The current [bid
status](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/spot-bid-status.html)
of the Spot Instance Request.
* `spot_request_state` The current [request
state](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/spot-requests.html#creating-spot-request-status)
of the Spot Instance Request.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">spot_<wbr>instance_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The Instance ID (if any) that is currently fulfilling
the Spot Instance request.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">spot_<wbr>price<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The maximum price to request on the spot market.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">spot_<wbr>request_<wbr>state<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">spot_<wbr>type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}If set to `one-time`, after
the instance is terminated, the spot request will be closed.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">subnet_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The VPC Subnet ID to launch in.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tenancy<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The tenancy of the instance (if the instance is running in a VPC). An instance with a tenancy of dedicated runs on single-tenant hardware. The host tenancy is not supported for the import-instance command.
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
            title="Optional">valid_<wbr>from<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The start date and time of the request, in UTC [RFC3339](https://tools.ietf.org/html/rfc3339#section-5.8) format(for example, YYYY-MM-DDTHH:MM:SSZ). The default is to start fulfilling the request immediately.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">valid_<wbr>until<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The end date and time of the request, in UTC [RFC3339](https://tools.ietf.org/html/rfc3339#section-5.8) format(for example, YYYY-MM-DDTHH:MM:SSZ). At this point, no new Spot instance requests are placed or enabled to fulfill the request. The default end date is 7 days from the current date.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">volume_<wbr>tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the devices created by the instance at launch time.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">vpc_<wbr>security_<wbr>group_<wbr>ids<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}A list of security group IDs to associate with.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">wait_<wbr>for_<wbr>fulfillment<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}If set, this provider will
wait for the Spot Request to be fulfilled, and will throw an error if the
timeout of 10m is reached.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}







## Supporting Types

#### SpotInstanceRequestCreditSpecification
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#SpotInstanceRequestCreditSpecification">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#SpotInstanceRequestCreditSpecification">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ec2?tab=doc#SpotInstanceRequestCreditSpecificationArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ec2?tab=doc#SpotInstanceRequestCreditSpecificationOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ec2.SpotInstanceRequestCreditSpecificationArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ec2.SpotInstanceRequestCreditSpecification.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Cpu<wbr>Credits<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Cpu<wbr>Credits<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">cpu<wbr>Credits<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">cpu<wbr>Credits<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### SpotInstanceRequestEbsBlockDevice
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#SpotInstanceRequestEbsBlockDevice">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#SpotInstanceRequestEbsBlockDevice">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ec2?tab=doc#SpotInstanceRequestEbsBlockDeviceArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ec2?tab=doc#SpotInstanceRequestEbsBlockDeviceOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ec2.SpotInstanceRequestEbsBlockDeviceArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ec2.SpotInstanceRequestEbsBlockDevice.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Delete<wbr>On<wbr>Termination<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Whether the volume should be destroyed
on instance termination (Default: `true`).
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Device<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the block device to mount on the instance.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Encrypted<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Enables [EBS
encryption](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/EBSEncryption.html)
on the volume (Default: `false`). Cannot be used with `snapshot_id`. Must be configured to perform drift detection.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Iops<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The amount of provisioned
[IOPS](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ebs-io-characteristics.html).
This must be set with a `volume_type` of `&#34;io1&#34;`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Kms<wbr>Key<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of the KMS Key to use when encrypting the volume. Must be configured to perform drift detection.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Snapshot<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The Snapshot ID to mount.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Volume<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Volume<wbr>Size<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The size of the volume in gibibytes (GiB).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Volume<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The type of volume. Can be `&#34;standard&#34;`, `&#34;gp2&#34;`,
or `&#34;io1&#34;`. (Default: `&#34;gp2&#34;`).
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Delete<wbr>On<wbr>Termination<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Whether the volume should be destroyed
on instance termination (Default: `true`).
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Device<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the block device to mount on the instance.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Encrypted<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Enables [EBS
encryption](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/EBSEncryption.html)
on the volume (Default: `false`). Cannot be used with `snapshot_id`. Must be configured to perform drift detection.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Iops<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The amount of provisioned
[IOPS](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ebs-io-characteristics.html).
This must be set with a `volume_type` of `&#34;io1&#34;`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Kms<wbr>Key<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of the KMS Key to use when encrypting the volume. Must be configured to perform drift detection.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Snapshot<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The Snapshot ID to mount.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Volume<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Volume<wbr>Size<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The size of the volume in gibibytes (GiB).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Volume<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The type of volume. Can be `&#34;standard&#34;`, `&#34;gp2&#34;`,
or `&#34;io1&#34;`. (Default: `&#34;gp2&#34;`).
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">delete<wbr>On<wbr>Termination<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Whether the volume should be destroyed
on instance termination (Default: `true`).
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">device<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the block device to mount on the instance.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">encrypted<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Enables [EBS
encryption](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/EBSEncryption.html)
on the volume (Default: `false`). Cannot be used with `snapshot_id`. Must be configured to perform drift detection.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">iops<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The amount of provisioned
[IOPS](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ebs-io-characteristics.html).
This must be set with a `volume_type` of `&#34;io1&#34;`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">kms<wbr>Key<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of the KMS Key to use when encrypting the volume. Must be configured to perform drift detection.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">snapshot<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The Snapshot ID to mount.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">volume<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">volume<wbr>Size<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The size of the volume in gibibytes (GiB).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">volume<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The type of volume. Can be `&#34;standard&#34;`, `&#34;gp2&#34;`,
or `&#34;io1&#34;`. (Default: `&#34;gp2&#34;`).
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">delete<wbr>On<wbr>Termination<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Whether the volume should be destroyed
on instance termination (Default: `true`).
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">device_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the block device to mount on the instance.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">encrypted<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Enables [EBS
encryption](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/EBSEncryption.html)
on the volume (Default: `false`). Cannot be used with `snapshot_id`. Must be configured to perform drift detection.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">iops<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The amount of provisioned
[IOPS](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ebs-io-characteristics.html).
This must be set with a `volume_type` of `&#34;io1&#34;`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">kms_<wbr>key_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of the KMS Key to use when encrypting the volume. Must be configured to perform drift detection.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">snapshot_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The Snapshot ID to mount.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">volume_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">volume_<wbr>size<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The size of the volume in gibibytes (GiB).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">volume<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The type of volume. Can be `&#34;standard&#34;`, `&#34;gp2&#34;`,
or `&#34;io1&#34;`. (Default: `&#34;gp2&#34;`).
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### SpotInstanceRequestEphemeralBlockDevice
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#SpotInstanceRequestEphemeralBlockDevice">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#SpotInstanceRequestEphemeralBlockDevice">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ec2?tab=doc#SpotInstanceRequestEphemeralBlockDeviceArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ec2?tab=doc#SpotInstanceRequestEphemeralBlockDeviceOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ec2.SpotInstanceRequestEphemeralBlockDeviceArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ec2.SpotInstanceRequestEphemeralBlockDevice.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Device<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the block device to mount on the instance.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">No<wbr>Device<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Suppresses the specified device included in the AMI&#39;s block device mapping.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Virtual<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The [Instance Store Device
Name](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/InstanceStorage.html#InstanceStoreDeviceNames)
(e.g. `&#34;ephemeral0&#34;`).
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Device<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the block device to mount on the instance.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">No<wbr>Device<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Suppresses the specified device included in the AMI&#39;s block device mapping.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Virtual<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The [Instance Store Device
Name](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/InstanceStorage.html#InstanceStoreDeviceNames)
(e.g. `&#34;ephemeral0&#34;`).
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">device<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the block device to mount on the instance.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">no<wbr>Device<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Suppresses the specified device included in the AMI&#39;s block device mapping.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">virtual<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The [Instance Store Device
Name](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/InstanceStorage.html#InstanceStoreDeviceNames)
(e.g. `&#34;ephemeral0&#34;`).
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">device_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the block device to mount on the instance.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">no<wbr>Device<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Suppresses the specified device included in the AMI&#39;s block device mapping.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">virtual<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The [Instance Store Device
Name](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/InstanceStorage.html#InstanceStoreDeviceNames)
(e.g. `&#34;ephemeral0&#34;`).
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### SpotInstanceRequestNetworkInterface
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#SpotInstanceRequestNetworkInterface">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#SpotInstanceRequestNetworkInterface">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ec2?tab=doc#SpotInstanceRequestNetworkInterfaceArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ec2?tab=doc#SpotInstanceRequestNetworkInterfaceOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ec2.SpotInstanceRequestNetworkInterfaceArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ec2.SpotInstanceRequestNetworkInterface.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Delete<wbr>On<wbr>Termination<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Whether the volume should be destroyed
on instance termination (Default: `true`).
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Device<wbr>Index<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Network<wbr>Interface<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
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
    <dd>{{% md %}}Whether the volume should be destroyed
on instance termination (Default: `true`).
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Device<wbr>Index<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Network<wbr>Interface<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
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
    <dd>{{% md %}}Whether the volume should be destroyed
on instance termination (Default: `true`).
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">device<wbr>Index<span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">network<wbr>Interface<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
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
    <dd>{{% md %}}Whether the volume should be destroyed
on instance termination (Default: `true`).
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">device_<wbr>index<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">network_<wbr>interface_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### SpotInstanceRequestRootBlockDevice
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#SpotInstanceRequestRootBlockDevice">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#SpotInstanceRequestRootBlockDevice">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ec2?tab=doc#SpotInstanceRequestRootBlockDeviceArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ec2?tab=doc#SpotInstanceRequestRootBlockDeviceOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ec2.SpotInstanceRequestRootBlockDeviceArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ec2.SpotInstanceRequestRootBlockDevice.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Delete<wbr>On<wbr>Termination<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Whether the volume should be destroyed
on instance termination (Default: `true`).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Encrypted<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Enables [EBS
encryption](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/EBSEncryption.html)
on the volume (Default: `false`). Cannot be used with `snapshot_id`. Must be configured to perform drift detection.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Iops<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The amount of provisioned
[IOPS](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ebs-io-characteristics.html).
This must be set with a `volume_type` of `&#34;io1&#34;`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Kms<wbr>Key<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of the KMS Key to use when encrypting the volume. Must be configured to perform drift detection.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Volume<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Volume<wbr>Size<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The size of the volume in gibibytes (GiB).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Volume<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The type of volume. Can be `&#34;standard&#34;`, `&#34;gp2&#34;`,
or `&#34;io1&#34;`. (Default: `&#34;gp2&#34;`).
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Delete<wbr>On<wbr>Termination<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Whether the volume should be destroyed
on instance termination (Default: `true`).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Encrypted<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Enables [EBS
encryption](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/EBSEncryption.html)
on the volume (Default: `false`). Cannot be used with `snapshot_id`. Must be configured to perform drift detection.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Iops<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The amount of provisioned
[IOPS](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ebs-io-characteristics.html).
This must be set with a `volume_type` of `&#34;io1&#34;`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Kms<wbr>Key<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of the KMS Key to use when encrypting the volume. Must be configured to perform drift detection.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Volume<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Volume<wbr>Size<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The size of the volume in gibibytes (GiB).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Volume<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The type of volume. Can be `&#34;standard&#34;`, `&#34;gp2&#34;`,
or `&#34;io1&#34;`. (Default: `&#34;gp2&#34;`).
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">delete<wbr>On<wbr>Termination<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Whether the volume should be destroyed
on instance termination (Default: `true`).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">encrypted<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Enables [EBS
encryption](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/EBSEncryption.html)
on the volume (Default: `false`). Cannot be used with `snapshot_id`. Must be configured to perform drift detection.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">iops<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The amount of provisioned
[IOPS](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ebs-io-characteristics.html).
This must be set with a `volume_type` of `&#34;io1&#34;`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">kms<wbr>Key<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of the KMS Key to use when encrypting the volume. Must be configured to perform drift detection.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">volume<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">volume<wbr>Size<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The size of the volume in gibibytes (GiB).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">volume<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The type of volume. Can be `&#34;standard&#34;`, `&#34;gp2&#34;`,
or `&#34;io1&#34;`. (Default: `&#34;gp2&#34;`).
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">delete<wbr>On<wbr>Termination<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Whether the volume should be destroyed
on instance termination (Default: `true`).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">encrypted<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Enables [EBS
encryption](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/EBSEncryption.html)
on the volume (Default: `false`). Cannot be used with `snapshot_id`. Must be configured to perform drift detection.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">iops<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The amount of provisioned
[IOPS](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ebs-io-characteristics.html).
This must be set with a `volume_type` of `&#34;io1&#34;`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">kms_<wbr>key_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of the KMS Key to use when encrypting the volume. Must be configured to perform drift detection.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">volume_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">volume_<wbr>size<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The size of the volume in gibibytes (GiB).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">volume<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The type of volume. Can be `&#34;standard&#34;`, `&#34;gp2&#34;`,
or `&#34;io1&#34;`. (Default: `&#34;gp2&#34;`).
{{% /md %}}</dd>

</dl>
{{% /choosable %}}








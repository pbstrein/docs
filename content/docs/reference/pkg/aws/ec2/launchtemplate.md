
---
title: "LaunchTemplate"
block_external_search_index: true
---

Provides an EC2 launch template resource. Can be used to create instances or auto scaling groups.

> This content is derived from https://github.com/terraform-providers/terraform-provider-aws/blob/master/website/docs/r/launch_template.html.markdown.



## Create a LaunchTemplate Resource

{{< chooser language "javascript,typescript,python,go,csharp" / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/ec2/#LaunchTemplate">LaunchTemplate</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/ec2/#LaunchTemplateArgs">LaunchTemplateArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">LaunchTemplate</span><span class="p">(resource_name, opts=None, </span>block_device_mappings=None<span class="p">, </span>capacity_reservation_specification=None<span class="p">, </span>cpu_options=None<span class="p">, </span>credit_specification=None<span class="p">, </span>description=None<span class="p">, </span>disable_api_termination=None<span class="p">, </span>ebs_optimized=None<span class="p">, </span>elastic_gpu_specifications=None<span class="p">, </span>elastic_inference_accelerator=None<span class="p">, </span>iam_instance_profile=None<span class="p">, </span>image_id=None<span class="p">, </span>instance_initiated_shutdown_behavior=None<span class="p">, </span>instance_market_options=None<span class="p">, </span>instance_type=None<span class="p">, </span>kernel_id=None<span class="p">, </span>key_name=None<span class="p">, </span>license_specifications=None<span class="p">, </span>monitoring=None<span class="p">, </span>name=None<span class="p">, </span>name_prefix=None<span class="p">, </span>network_interfaces=None<span class="p">, </span>placement=None<span class="p">, </span>ram_disk_id=None<span class="p">, </span>security_group_names=None<span class="p">, </span>tag_specifications=None<span class="p">, </span>tags=None<span class="p">, </span>user_data=None<span class="p">, </span>vpc_security_group_ids=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewLaunchTemplate<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ec2?tab=doc#LaunchTemplateArgs">LaunchTemplateArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ec2?tab=doc#LaunchTemplate">LaunchTemplate</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ec2.LaunchTemplate.html">LaunchTemplate</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ec2.LaunchTemplateArgs.html">LaunchTemplateArgs</a></span>? <span class="nx">args = null<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
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
            title="Optional">Block<wbr>Device<wbr>Mappings<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchtemplateblockdevicemapping">List&lt;Launch<wbr>Template<wbr>Block<wbr>Device<wbr>Mapping<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}Specify volumes to attach to the instance besides the volumes specified by the AMI.
See Block Devices below for details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Capacity<wbr>Reservation<wbr>Specification<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchtemplatecapacityreservationspecification">Launch<wbr>Template<wbr>Capacity<wbr>Reservation<wbr>Specification<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}Targeting for EC2 capacity reservations. See Capacity Reservation Specification below for more details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Cpu<wbr>Options<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchtemplatecpuoptions">Launch<wbr>Template<wbr>Cpu<wbr>Options<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}The CPU options for the instance. See CPU Options below for more details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Credit<wbr>Specification<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchtemplatecreditspecification">Launch<wbr>Template<wbr>Credit<wbr>Specification<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}Customize the credit specification of the instance. See Credit
Specification below for more details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Description<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Description of the launch template.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Disable<wbr>Api<wbr>Termination<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}If `true`, enables [EC2 Instance
Termination Protection](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/terminating-instances.html#Using_ChangingDisableAPITermination)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ebs<wbr>Optimized<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}If `true`, the launched EC2 instance will be EBS-optimized.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Elastic<wbr>Gpu<wbr>Specifications<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchtemplateelasticgpuspecification">List&lt;Launch<wbr>Template<wbr>Elastic<wbr>Gpu<wbr>Specification<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}The elastic GPU to attach to the instance. See Elastic GPU
below for more details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Elastic<wbr>Inference<wbr>Accelerator<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchtemplateelasticinferenceaccelerator">Launch<wbr>Template<wbr>Elastic<wbr>Inference<wbr>Accelerator<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}Configuration block containing an Elastic Inference Accelerator to attach to the instance. See Elastic Inference Accelerator below for more details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Iam<wbr>Instance<wbr>Profile<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchtemplateiaminstanceprofile">Launch<wbr>Template<wbr>Iam<wbr>Instance<wbr>Profile<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}The IAM Instance Profile to launch the instance with. See Instance Profile
below for more details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Image<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The AMI from which to launch the instance.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Instance<wbr>Initiated<wbr>Shutdown<wbr>Behavior<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Shutdown behavior for the instance. Can be `stop` or `terminate`.
(Default: `stop`).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Instance<wbr>Market<wbr>Options<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchtemplateinstancemarketoptions">Launch<wbr>Template<wbr>Instance<wbr>Market<wbr>Options<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}The market (purchasing) option for the instance. See Market Options
below for details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Instance<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The type of the instance.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Kernel<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The kernel ID.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Key<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The key name to use for the instance.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">License<wbr>Specifications<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchtemplatelicensespecification">List&lt;Launch<wbr>Template<wbr>License<wbr>Specification<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}A list of license specifications to associate with. See License Specification below for more details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Monitoring<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchtemplatemonitoring">Launch<wbr>Template<wbr>Monitoring<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}The monitoring option for the instance. See Monitoring below for more details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the launch template. If you leave this blank, this provider will auto-generate a unique name.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<wbr>Prefix<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Creates a unique name beginning with the specified prefix. Conflicts with `name`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Network<wbr>Interfaces<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchtemplatenetworkinterface">List&lt;Launch<wbr>Template<wbr>Network<wbr>Interface<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}Customize network interfaces to be attached at instance boot time. See Network
Interfaces below for more details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Placement<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchtemplateplacement">Launch<wbr>Template<wbr>Placement<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}The placement of the instance. See Placement below for more details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ram<wbr>Disk<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ID of the RAM disk.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Security<wbr>Group<wbr>Names<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}A list of security group names to associate with. If you are creating Instances in a VPC, use
`vpc_security_group_ids` instead.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tag<wbr>Specifications<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchtemplatetagspecification">List&lt;Launch<wbr>Template<wbr>Tag<wbr>Specification<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}The tags to apply to the resources during launch. See Tag Specifications below for more details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the launch template.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">User<wbr>Data<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The Base64-encoded user data to provide when launching the instance.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Vpc<wbr>Security<wbr>Group<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}A list of security group IDs to associate with.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Block<wbr>Device<wbr>Mappings<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchtemplateblockdevicemapping">[]Launch<wbr>Template<wbr>Block<wbr>Device<wbr>Mapping</a></span>
    </dt>
    <dd>{{% md %}}Specify volumes to attach to the instance besides the volumes specified by the AMI.
See Block Devices below for details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Capacity<wbr>Reservation<wbr>Specification<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchtemplatecapacityreservationspecification">*Launch<wbr>Template<wbr>Capacity<wbr>Reservation<wbr>Specification</a></span>
    </dt>
    <dd>{{% md %}}Targeting for EC2 capacity reservations. See Capacity Reservation Specification below for more details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Cpu<wbr>Options<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchtemplatecpuoptions">*Launch<wbr>Template<wbr>Cpu<wbr>Options</a></span>
    </dt>
    <dd>{{% md %}}The CPU options for the instance. See CPU Options below for more details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Credit<wbr>Specification<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchtemplatecreditspecification">*Launch<wbr>Template<wbr>Credit<wbr>Specification</a></span>
    </dt>
    <dd>{{% md %}}Customize the credit specification of the instance. See Credit
Specification below for more details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Description<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Description of the launch template.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Disable<wbr>Api<wbr>Termination<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}If `true`, enables [EC2 Instance
Termination Protection](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/terminating-instances.html#Using_ChangingDisableAPITermination)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ebs<wbr>Optimized<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}If `true`, the launched EC2 instance will be EBS-optimized.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Elastic<wbr>Gpu<wbr>Specifications<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchtemplateelasticgpuspecification">[]Launch<wbr>Template<wbr>Elastic<wbr>Gpu<wbr>Specification</a></span>
    </dt>
    <dd>{{% md %}}The elastic GPU to attach to the instance. See Elastic GPU
below for more details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Elastic<wbr>Inference<wbr>Accelerator<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchtemplateelasticinferenceaccelerator">*Launch<wbr>Template<wbr>Elastic<wbr>Inference<wbr>Accelerator</a></span>
    </dt>
    <dd>{{% md %}}Configuration block containing an Elastic Inference Accelerator to attach to the instance. See Elastic Inference Accelerator below for more details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Iam<wbr>Instance<wbr>Profile<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchtemplateiaminstanceprofile">*Launch<wbr>Template<wbr>Iam<wbr>Instance<wbr>Profile</a></span>
    </dt>
    <dd>{{% md %}}The IAM Instance Profile to launch the instance with. See Instance Profile
below for more details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Image<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The AMI from which to launch the instance.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Instance<wbr>Initiated<wbr>Shutdown<wbr>Behavior<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Shutdown behavior for the instance. Can be `stop` or `terminate`.
(Default: `stop`).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Instance<wbr>Market<wbr>Options<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchtemplateinstancemarketoptions">*Launch<wbr>Template<wbr>Instance<wbr>Market<wbr>Options</a></span>
    </dt>
    <dd>{{% md %}}The market (purchasing) option for the instance. See Market Options
below for details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Instance<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The type of the instance.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Kernel<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The kernel ID.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Key<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The key name to use for the instance.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">License<wbr>Specifications<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchtemplatelicensespecification">[]Launch<wbr>Template<wbr>License<wbr>Specification</a></span>
    </dt>
    <dd>{{% md %}}A list of license specifications to associate with. See License Specification below for more details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Monitoring<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchtemplatemonitoring">*Launch<wbr>Template<wbr>Monitoring</a></span>
    </dt>
    <dd>{{% md %}}The monitoring option for the instance. See Monitoring below for more details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name of the launch template. If you leave this blank, this provider will auto-generate a unique name.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<wbr>Prefix<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Creates a unique name beginning with the specified prefix. Conflicts with `name`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Network<wbr>Interfaces<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchtemplatenetworkinterface">[]Launch<wbr>Template<wbr>Network<wbr>Interface</a></span>
    </dt>
    <dd>{{% md %}}Customize network interfaces to be attached at instance boot time. See Network
Interfaces below for more details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Placement<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchtemplateplacement">*Launch<wbr>Template<wbr>Placement</a></span>
    </dt>
    <dd>{{% md %}}The placement of the instance. See Placement below for more details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ram<wbr>Disk<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The ID of the RAM disk.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Security<wbr>Group<wbr>Names<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}A list of security group names to associate with. If you are creating Instances in a VPC, use
`vpc_security_group_ids` instead.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tag<wbr>Specifications<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchtemplatetagspecification">[]Launch<wbr>Template<wbr>Tag<wbr>Specification</a></span>
    </dt>
    <dd>{{% md %}}The tags to apply to the resources during launch. See Tag Specifications below for more details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the launch template.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">User<wbr>Data<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The Base64-encoded user data to provide when launching the instance.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Vpc<wbr>Security<wbr>Group<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}A list of security group IDs to associate with.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">block<wbr>Device<wbr>Mappings<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchtemplateblockdevicemapping">Launch<wbr>Template<wbr>Block<wbr>Device<wbr>Mapping[]?</a></span>
    </dt>
    <dd>{{% md %}}Specify volumes to attach to the instance besides the volumes specified by the AMI.
See Block Devices below for details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">capacity<wbr>Reservation<wbr>Specification<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchtemplatecapacityreservationspecification">Launch<wbr>Template<wbr>Capacity<wbr>Reservation<wbr>Specification?</a></span>
    </dt>
    <dd>{{% md %}}Targeting for EC2 capacity reservations. See Capacity Reservation Specification below for more details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">cpu<wbr>Options<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchtemplatecpuoptions">Launch<wbr>Template<wbr>Cpu<wbr>Options?</a></span>
    </dt>
    <dd>{{% md %}}The CPU options for the instance. See CPU Options below for more details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">credit<wbr>Specification<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchtemplatecreditspecification">Launch<wbr>Template<wbr>Credit<wbr>Specification?</a></span>
    </dt>
    <dd>{{% md %}}Customize the credit specification of the instance. See Credit
Specification below for more details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">description<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Description of the launch template.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">disable<wbr>Api<wbr>Termination<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}If `true`, enables [EC2 Instance
Termination Protection](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/terminating-instances.html#Using_ChangingDisableAPITermination)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ebs<wbr>Optimized<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}If `true`, the launched EC2 instance will be EBS-optimized.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">elastic<wbr>Gpu<wbr>Specifications<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchtemplateelasticgpuspecification">Launch<wbr>Template<wbr>Elastic<wbr>Gpu<wbr>Specification[]?</a></span>
    </dt>
    <dd>{{% md %}}The elastic GPU to attach to the instance. See Elastic GPU
below for more details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">elastic<wbr>Inference<wbr>Accelerator<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchtemplateelasticinferenceaccelerator">Launch<wbr>Template<wbr>Elastic<wbr>Inference<wbr>Accelerator?</a></span>
    </dt>
    <dd>{{% md %}}Configuration block containing an Elastic Inference Accelerator to attach to the instance. See Elastic Inference Accelerator below for more details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">iam<wbr>Instance<wbr>Profile<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchtemplateiaminstanceprofile">Launch<wbr>Template<wbr>Iam<wbr>Instance<wbr>Profile?</a></span>
    </dt>
    <dd>{{% md %}}The IAM Instance Profile to launch the instance with. See Instance Profile
below for more details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">image<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The AMI from which to launch the instance.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">instance<wbr>Initiated<wbr>Shutdown<wbr>Behavior<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Shutdown behavior for the instance. Can be `stop` or `terminate`.
(Default: `stop`).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">instance<wbr>Market<wbr>Options<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchtemplateinstancemarketoptions">Launch<wbr>Template<wbr>Instance<wbr>Market<wbr>Options?</a></span>
    </dt>
    <dd>{{% md %}}The market (purchasing) option for the instance. See Market Options
below for details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">instance<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The type of the instance.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">kernel<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The kernel ID.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">key<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The key name to use for the instance.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">license<wbr>Specifications<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchtemplatelicensespecification">Launch<wbr>Template<wbr>License<wbr>Specification[]?</a></span>
    </dt>
    <dd>{{% md %}}A list of license specifications to associate with. See License Specification below for more details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">monitoring<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchtemplatemonitoring">Launch<wbr>Template<wbr>Monitoring?</a></span>
    </dt>
    <dd>{{% md %}}The monitoring option for the instance. See Monitoring below for more details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the launch template. If you leave this blank, this provider will auto-generate a unique name.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<wbr>Prefix<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Creates a unique name beginning with the specified prefix. Conflicts with `name`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">network<wbr>Interfaces<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchtemplatenetworkinterface">Launch<wbr>Template<wbr>Network<wbr>Interface[]?</a></span>
    </dt>
    <dd>{{% md %}}Customize network interfaces to be attached at instance boot time. See Network
Interfaces below for more details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">placement<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchtemplateplacement">Launch<wbr>Template<wbr>Placement?</a></span>
    </dt>
    <dd>{{% md %}}The placement of the instance. See Placement below for more details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ram<wbr>Disk<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ID of the RAM disk.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">security<wbr>Group<wbr>Names<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}A list of security group names to associate with. If you are creating Instances in a VPC, use
`vpc_security_group_ids` instead.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tag<wbr>Specifications<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchtemplatetagspecification">Launch<wbr>Template<wbr>Tag<wbr>Specification[]?</a></span>
    </dt>
    <dd>{{% md %}}The tags to apply to the resources during launch. See Tag Specifications below for more details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the launch template.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">user<wbr>Data<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The Base64-encoded user data to provide when launching the instance.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">vpc<wbr>Security<wbr>Group<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}A list of security group IDs to associate with.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">block_<wbr>device_<wbr>mappings<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchtemplateblockdevicemapping">List[Launch<wbr>Template<wbr>Block<wbr>Device<wbr>Mapping]</a></span>
    </dt>
    <dd>{{% md %}}Specify volumes to attach to the instance besides the volumes specified by the AMI.
See Block Devices below for details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">capacity_<wbr>reservation_<wbr>specification<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchtemplatecapacityreservationspecification">Dict[Launch<wbr>Template<wbr>Capacity<wbr>Reservation<wbr>Specification]</a></span>
    </dt>
    <dd>{{% md %}}Targeting for EC2 capacity reservations. See Capacity Reservation Specification below for more details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">cpu_<wbr>options<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchtemplatecpuoptions">Dict[Launch<wbr>Template<wbr>Cpu<wbr>Options]</a></span>
    </dt>
    <dd>{{% md %}}The CPU options for the instance. See CPU Options below for more details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">credit_<wbr>specification<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchtemplatecreditspecification">Dict[Launch<wbr>Template<wbr>Credit<wbr>Specification]</a></span>
    </dt>
    <dd>{{% md %}}Customize the credit specification of the instance. See Credit
Specification below for more details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">description<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Description of the launch template.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">disable_<wbr>api_<wbr>termination<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}If `true`, enables [EC2 Instance
Termination Protection](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/terminating-instances.html#Using_ChangingDisableAPITermination)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ebs_<wbr>optimized<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}If `true`, the launched EC2 instance will be EBS-optimized.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">elastic_<wbr>gpu_<wbr>specifications<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchtemplateelasticgpuspecification">List[Launch<wbr>Template<wbr>Elastic<wbr>Gpu<wbr>Specification]</a></span>
    </dt>
    <dd>{{% md %}}The elastic GPU to attach to the instance. See Elastic GPU
below for more details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">elastic_<wbr>inference_<wbr>accelerator<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchtemplateelasticinferenceaccelerator">Dict[Launch<wbr>Template<wbr>Elastic<wbr>Inference<wbr>Accelerator]</a></span>
    </dt>
    <dd>{{% md %}}Configuration block containing an Elastic Inference Accelerator to attach to the instance. See Elastic Inference Accelerator below for more details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">iam_<wbr>instance_<wbr>profile<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchtemplateiaminstanceprofile">Dict[Launch<wbr>Template<wbr>Iam<wbr>Instance<wbr>Profile]</a></span>
    </dt>
    <dd>{{% md %}}The IAM Instance Profile to launch the instance with. See Instance Profile
below for more details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">image_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The AMI from which to launch the instance.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">instance_<wbr>initiated_<wbr>shutdown_<wbr>behavior<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Shutdown behavior for the instance. Can be `stop` or `terminate`.
(Default: `stop`).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">instance_<wbr>market_<wbr>options<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchtemplateinstancemarketoptions">Dict[Launch<wbr>Template<wbr>Instance<wbr>Market<wbr>Options]</a></span>
    </dt>
    <dd>{{% md %}}The market (purchasing) option for the instance. See Market Options
below for details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">instance_<wbr>type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The type of the instance.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">kernel_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The kernel ID.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">key_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The key name to use for the instance.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">license_<wbr>specifications<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchtemplatelicensespecification">List[Launch<wbr>Template<wbr>License<wbr>Specification]</a></span>
    </dt>
    <dd>{{% md %}}A list of license specifications to associate with. See License Specification below for more details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">monitoring<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchtemplatemonitoring">Dict[Launch<wbr>Template<wbr>Monitoring]</a></span>
    </dt>
    <dd>{{% md %}}The monitoring option for the instance. See Monitoring below for more details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the launch template. If you leave this blank, this provider will auto-generate a unique name.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name_<wbr>prefix<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Creates a unique name beginning with the specified prefix. Conflicts with `name`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">network_<wbr>interfaces<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchtemplatenetworkinterface">List[Launch<wbr>Template<wbr>Network<wbr>Interface]</a></span>
    </dt>
    <dd>{{% md %}}Customize network interfaces to be attached at instance boot time. See Network
Interfaces below for more details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">placement<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchtemplateplacement">Dict[Launch<wbr>Template<wbr>Placement]</a></span>
    </dt>
    <dd>{{% md %}}The placement of the instance. See Placement below for more details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ram_<wbr>disk_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ID of the RAM disk.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">security_<wbr>group_<wbr>names<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}A list of security group names to associate with. If you are creating Instances in a VPC, use
`vpc_security_group_ids` instead.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tag_<wbr>specifications<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchtemplatetagspecification">List[Launch<wbr>Template<wbr>Tag<wbr>Specification]</a></span>
    </dt>
    <dd>{{% md %}}The tags to apply to the resources during launch. See Tag Specifications below for more details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the launch template.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">user_<wbr>data<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The Base64-encoded user data to provide when launching the instance.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">vpc_<wbr>security_<wbr>group_<wbr>ids<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}A list of security group IDs to associate with.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}




## LaunchTemplate Output Properties

The following output properties are available:




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of the launch template.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Block<wbr>Device<wbr>Mappings<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchtemplateblockdevicemapping">List&lt;Launch<wbr>Template<wbr>Block<wbr>Device<wbr>Mapping&gt;?</a></span>
    </dt>
    <dd>{{% md %}}Specify volumes to attach to the instance besides the volumes specified by the AMI.
See Block Devices below for details.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Capacity<wbr>Reservation<wbr>Specification<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchtemplatecapacityreservationspecification">Launch<wbr>Template<wbr>Capacity<wbr>Reservation<wbr>Specification?</a></span>
    </dt>
    <dd>{{% md %}}Targeting for EC2 capacity reservations. See Capacity Reservation Specification below for more details.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Cpu<wbr>Options<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchtemplatecpuoptions">Launch<wbr>Template<wbr>Cpu<wbr>Options?</a></span>
    </dt>
    <dd>{{% md %}}The CPU options for the instance. See CPU Options below for more details.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Credit<wbr>Specification<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchtemplatecreditspecification">Launch<wbr>Template<wbr>Credit<wbr>Specification?</a></span>
    </dt>
    <dd>{{% md %}}Customize the credit specification of the instance. See Credit
Specification below for more details.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Default<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The default version of the launch template.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Description<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Description of the launch template.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Disable<wbr>Api<wbr>Termination<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}If `true`, enables [EC2 Instance
Termination Protection](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/terminating-instances.html#Using_ChangingDisableAPITermination)
{{% /md %}}</dd>

    <dt class="property-"
            title="">Ebs<wbr>Optimized<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}If `true`, the launched EC2 instance will be EBS-optimized.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Elastic<wbr>Gpu<wbr>Specifications<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchtemplateelasticgpuspecification">List&lt;Launch<wbr>Template<wbr>Elastic<wbr>Gpu<wbr>Specification&gt;?</a></span>
    </dt>
    <dd>{{% md %}}The elastic GPU to attach to the instance. See Elastic GPU
below for more details.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Elastic<wbr>Inference<wbr>Accelerator<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchtemplateelasticinferenceaccelerator">Launch<wbr>Template<wbr>Elastic<wbr>Inference<wbr>Accelerator?</a></span>
    </dt>
    <dd>{{% md %}}Configuration block containing an Elastic Inference Accelerator to attach to the instance. See Elastic Inference Accelerator below for more details.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Iam<wbr>Instance<wbr>Profile<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchtemplateiaminstanceprofile">Launch<wbr>Template<wbr>Iam<wbr>Instance<wbr>Profile?</a></span>
    </dt>
    <dd>{{% md %}}The IAM Instance Profile to launch the instance with. See Instance Profile
below for more details.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Image<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The AMI from which to launch the instance.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Instance<wbr>Initiated<wbr>Shutdown<wbr>Behavior<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Shutdown behavior for the instance. Can be `stop` or `terminate`.
(Default: `stop`).
{{% /md %}}</dd>

    <dt class="property-"
            title="">Instance<wbr>Market<wbr>Options<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchtemplateinstancemarketoptions">Launch<wbr>Template<wbr>Instance<wbr>Market<wbr>Options?</a></span>
    </dt>
    <dd>{{% md %}}The market (purchasing) option for the instance. See Market Options
below for details.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Instance<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The type of the instance.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Kernel<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The kernel ID.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Key<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The key name to use for the instance.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Latest<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The latest version of the launch template.
{{% /md %}}</dd>

    <dt class="property-"
            title="">License<wbr>Specifications<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchtemplatelicensespecification">List&lt;Launch<wbr>Template<wbr>License<wbr>Specification&gt;?</a></span>
    </dt>
    <dd>{{% md %}}A list of license specifications to associate with. See License Specification below for more details.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Monitoring<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchtemplatemonitoring">Launch<wbr>Template<wbr>Monitoring?</a></span>
    </dt>
    <dd>{{% md %}}The monitoring option for the instance. See Monitoring below for more details.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the launch template. If you leave this blank, this provider will auto-generate a unique name.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Name<wbr>Prefix<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Creates a unique name beginning with the specified prefix. Conflicts with `name`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Network<wbr>Interfaces<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchtemplatenetworkinterface">List&lt;Launch<wbr>Template<wbr>Network<wbr>Interface&gt;?</a></span>
    </dt>
    <dd>{{% md %}}Customize network interfaces to be attached at instance boot time. See Network
Interfaces below for more details.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Placement<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchtemplateplacement">Launch<wbr>Template<wbr>Placement?</a></span>
    </dt>
    <dd>{{% md %}}The placement of the instance. See Placement below for more details.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Ram<wbr>Disk<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ID of the RAM disk.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Security<wbr>Group<wbr>Names<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}A list of security group names to associate with. If you are creating Instances in a VPC, use
`vpc_security_group_ids` instead.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Tag<wbr>Specifications<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchtemplatetagspecification">List&lt;Launch<wbr>Template<wbr>Tag<wbr>Specification&gt;?</a></span>
    </dt>
    <dd>{{% md %}}The tags to apply to the resources during launch. See Tag Specifications below for more details.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the launch template.
{{% /md %}}</dd>

    <dt class="property-"
            title="">User<wbr>Data<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The Base64-encoded user data to provide when launching the instance.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Vpc<wbr>Security<wbr>Group<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}A list of security group IDs to associate with.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of the launch template.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Block<wbr>Device<wbr>Mappings<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchtemplateblockdevicemapping">[]Launch<wbr>Template<wbr>Block<wbr>Device<wbr>Mapping</a></span>
    </dt>
    <dd>{{% md %}}Specify volumes to attach to the instance besides the volumes specified by the AMI.
See Block Devices below for details.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Capacity<wbr>Reservation<wbr>Specification<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchtemplatecapacityreservationspecification">*Launch<wbr>Template<wbr>Capacity<wbr>Reservation<wbr>Specification</a></span>
    </dt>
    <dd>{{% md %}}Targeting for EC2 capacity reservations. See Capacity Reservation Specification below for more details.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Cpu<wbr>Options<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchtemplatecpuoptions">*Launch<wbr>Template<wbr>Cpu<wbr>Options</a></span>
    </dt>
    <dd>{{% md %}}The CPU options for the instance. See CPU Options below for more details.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Credit<wbr>Specification<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchtemplatecreditspecification">*Launch<wbr>Template<wbr>Credit<wbr>Specification</a></span>
    </dt>
    <dd>{{% md %}}Customize the credit specification of the instance. See Credit
Specification below for more details.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Default<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The default version of the launch template.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Description<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Description of the launch template.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Disable<wbr>Api<wbr>Termination<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}If `true`, enables [EC2 Instance
Termination Protection](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/terminating-instances.html#Using_ChangingDisableAPITermination)
{{% /md %}}</dd>

    <dt class="property-"
            title="">Ebs<wbr>Optimized<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}If `true`, the launched EC2 instance will be EBS-optimized.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Elastic<wbr>Gpu<wbr>Specifications<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchtemplateelasticgpuspecification">[]Launch<wbr>Template<wbr>Elastic<wbr>Gpu<wbr>Specification</a></span>
    </dt>
    <dd>{{% md %}}The elastic GPU to attach to the instance. See Elastic GPU
below for more details.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Elastic<wbr>Inference<wbr>Accelerator<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchtemplateelasticinferenceaccelerator">*Launch<wbr>Template<wbr>Elastic<wbr>Inference<wbr>Accelerator</a></span>
    </dt>
    <dd>{{% md %}}Configuration block containing an Elastic Inference Accelerator to attach to the instance. See Elastic Inference Accelerator below for more details.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Iam<wbr>Instance<wbr>Profile<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchtemplateiaminstanceprofile">*Launch<wbr>Template<wbr>Iam<wbr>Instance<wbr>Profile</a></span>
    </dt>
    <dd>{{% md %}}The IAM Instance Profile to launch the instance with. See Instance Profile
below for more details.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Image<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The AMI from which to launch the instance.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Instance<wbr>Initiated<wbr>Shutdown<wbr>Behavior<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Shutdown behavior for the instance. Can be `stop` or `terminate`.
(Default: `stop`).
{{% /md %}}</dd>

    <dt class="property-"
            title="">Instance<wbr>Market<wbr>Options<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchtemplateinstancemarketoptions">*Launch<wbr>Template<wbr>Instance<wbr>Market<wbr>Options</a></span>
    </dt>
    <dd>{{% md %}}The market (purchasing) option for the instance. See Market Options
below for details.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Instance<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The type of the instance.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Kernel<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The kernel ID.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Key<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The key name to use for the instance.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Latest<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The latest version of the launch template.
{{% /md %}}</dd>

    <dt class="property-"
            title="">License<wbr>Specifications<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchtemplatelicensespecification">[]Launch<wbr>Template<wbr>License<wbr>Specification</a></span>
    </dt>
    <dd>{{% md %}}A list of license specifications to associate with. See License Specification below for more details.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Monitoring<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchtemplatemonitoring">*Launch<wbr>Template<wbr>Monitoring</a></span>
    </dt>
    <dd>{{% md %}}The monitoring option for the instance. See Monitoring below for more details.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the launch template. If you leave this blank, this provider will auto-generate a unique name.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Name<wbr>Prefix<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Creates a unique name beginning with the specified prefix. Conflicts with `name`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Network<wbr>Interfaces<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchtemplatenetworkinterface">[]Launch<wbr>Template<wbr>Network<wbr>Interface</a></span>
    </dt>
    <dd>{{% md %}}Customize network interfaces to be attached at instance boot time. See Network
Interfaces below for more details.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Placement<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchtemplateplacement">*Launch<wbr>Template<wbr>Placement</a></span>
    </dt>
    <dd>{{% md %}}The placement of the instance. See Placement below for more details.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Ram<wbr>Disk<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The ID of the RAM disk.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Security<wbr>Group<wbr>Names<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}A list of security group names to associate with. If you are creating Instances in a VPC, use
`vpc_security_group_ids` instead.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Tag<wbr>Specifications<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchtemplatetagspecification">[]Launch<wbr>Template<wbr>Tag<wbr>Specification</a></span>
    </dt>
    <dd>{{% md %}}The tags to apply to the resources during launch. See Tag Specifications below for more details.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the launch template.
{{% /md %}}</dd>

    <dt class="property-"
            title="">User<wbr>Data<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The Base64-encoded user data to provide when launching the instance.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Vpc<wbr>Security<wbr>Group<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}A list of security group IDs to associate with.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of the launch template.
{{% /md %}}</dd>

    <dt class="property-"
            title="">block<wbr>Device<wbr>Mappings<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchtemplateblockdevicemapping">Launch<wbr>Template<wbr>Block<wbr>Device<wbr>Mapping[]?</a></span>
    </dt>
    <dd>{{% md %}}Specify volumes to attach to the instance besides the volumes specified by the AMI.
See Block Devices below for details.
{{% /md %}}</dd>

    <dt class="property-"
            title="">capacity<wbr>Reservation<wbr>Specification<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchtemplatecapacityreservationspecification">Launch<wbr>Template<wbr>Capacity<wbr>Reservation<wbr>Specification?</a></span>
    </dt>
    <dd>{{% md %}}Targeting for EC2 capacity reservations. See Capacity Reservation Specification below for more details.
{{% /md %}}</dd>

    <dt class="property-"
            title="">cpu<wbr>Options<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchtemplatecpuoptions">Launch<wbr>Template<wbr>Cpu<wbr>Options?</a></span>
    </dt>
    <dd>{{% md %}}The CPU options for the instance. See CPU Options below for more details.
{{% /md %}}</dd>

    <dt class="property-"
            title="">credit<wbr>Specification<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchtemplatecreditspecification">Launch<wbr>Template<wbr>Credit<wbr>Specification?</a></span>
    </dt>
    <dd>{{% md %}}Customize the credit specification of the instance. See Credit
Specification below for more details.
{{% /md %}}</dd>

    <dt class="property-"
            title="">default<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}The default version of the launch template.
{{% /md %}}</dd>

    <dt class="property-"
            title="">description<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Description of the launch template.
{{% /md %}}</dd>

    <dt class="property-"
            title="">disable<wbr>Api<wbr>Termination<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}If `true`, enables [EC2 Instance
Termination Protection](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/terminating-instances.html#Using_ChangingDisableAPITermination)
{{% /md %}}</dd>

    <dt class="property-"
            title="">ebs<wbr>Optimized<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}If `true`, the launched EC2 instance will be EBS-optimized.
{{% /md %}}</dd>

    <dt class="property-"
            title="">elastic<wbr>Gpu<wbr>Specifications<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchtemplateelasticgpuspecification">Launch<wbr>Template<wbr>Elastic<wbr>Gpu<wbr>Specification[]?</a></span>
    </dt>
    <dd>{{% md %}}The elastic GPU to attach to the instance. See Elastic GPU
below for more details.
{{% /md %}}</dd>

    <dt class="property-"
            title="">elastic<wbr>Inference<wbr>Accelerator<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchtemplateelasticinferenceaccelerator">Launch<wbr>Template<wbr>Elastic<wbr>Inference<wbr>Accelerator?</a></span>
    </dt>
    <dd>{{% md %}}Configuration block containing an Elastic Inference Accelerator to attach to the instance. See Elastic Inference Accelerator below for more details.
{{% /md %}}</dd>

    <dt class="property-"
            title="">iam<wbr>Instance<wbr>Profile<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchtemplateiaminstanceprofile">Launch<wbr>Template<wbr>Iam<wbr>Instance<wbr>Profile?</a></span>
    </dt>
    <dd>{{% md %}}The IAM Instance Profile to launch the instance with. See Instance Profile
below for more details.
{{% /md %}}</dd>

    <dt class="property-"
            title="">image<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The AMI from which to launch the instance.
{{% /md %}}</dd>

    <dt class="property-"
            title="">instance<wbr>Initiated<wbr>Shutdown<wbr>Behavior<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Shutdown behavior for the instance. Can be `stop` or `terminate`.
(Default: `stop`).
{{% /md %}}</dd>

    <dt class="property-"
            title="">instance<wbr>Market<wbr>Options<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchtemplateinstancemarketoptions">Launch<wbr>Template<wbr>Instance<wbr>Market<wbr>Options?</a></span>
    </dt>
    <dd>{{% md %}}The market (purchasing) option for the instance. See Market Options
below for details.
{{% /md %}}</dd>

    <dt class="property-"
            title="">instance<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The type of the instance.
{{% /md %}}</dd>

    <dt class="property-"
            title="">kernel<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The kernel ID.
{{% /md %}}</dd>

    <dt class="property-"
            title="">key<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The key name to use for the instance.
{{% /md %}}</dd>

    <dt class="property-"
            title="">latest<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}The latest version of the launch template.
{{% /md %}}</dd>

    <dt class="property-"
            title="">license<wbr>Specifications<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchtemplatelicensespecification">Launch<wbr>Template<wbr>License<wbr>Specification[]?</a></span>
    </dt>
    <dd>{{% md %}}A list of license specifications to associate with. See License Specification below for more details.
{{% /md %}}</dd>

    <dt class="property-"
            title="">monitoring<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchtemplatemonitoring">Launch<wbr>Template<wbr>Monitoring?</a></span>
    </dt>
    <dd>{{% md %}}The monitoring option for the instance. See Monitoring below for more details.
{{% /md %}}</dd>

    <dt class="property-"
            title="">name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the launch template. If you leave this blank, this provider will auto-generate a unique name.
{{% /md %}}</dd>

    <dt class="property-"
            title="">name<wbr>Prefix<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Creates a unique name beginning with the specified prefix. Conflicts with `name`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">network<wbr>Interfaces<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchtemplatenetworkinterface">Launch<wbr>Template<wbr>Network<wbr>Interface[]?</a></span>
    </dt>
    <dd>{{% md %}}Customize network interfaces to be attached at instance boot time. See Network
Interfaces below for more details.
{{% /md %}}</dd>

    <dt class="property-"
            title="">placement<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchtemplateplacement">Launch<wbr>Template<wbr>Placement?</a></span>
    </dt>
    <dd>{{% md %}}The placement of the instance. See Placement below for more details.
{{% /md %}}</dd>

    <dt class="property-"
            title="">ram<wbr>Disk<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ID of the RAM disk.
{{% /md %}}</dd>

    <dt class="property-"
            title="">security<wbr>Group<wbr>Names<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}A list of security group names to associate with. If you are creating Instances in a VPC, use
`vpc_security_group_ids` instead.
{{% /md %}}</dd>

    <dt class="property-"
            title="">tag<wbr>Specifications<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchtemplatetagspecification">Launch<wbr>Template<wbr>Tag<wbr>Specification[]?</a></span>
    </dt>
    <dd>{{% md %}}The tags to apply to the resources during launch. See Tag Specifications below for more details.
{{% /md %}}</dd>

    <dt class="property-"
            title="">tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the launch template.
{{% /md %}}</dd>

    <dt class="property-"
            title="">user<wbr>Data<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The Base64-encoded user data to provide when launching the instance.
{{% /md %}}</dd>

    <dt class="property-"
            title="">vpc<wbr>Security<wbr>Group<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}A list of security group IDs to associate with.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of the launch template.
{{% /md %}}</dd>

    <dt class="property-"
            title="">block_<wbr>device_<wbr>mappings<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchtemplateblockdevicemapping">List[Launch<wbr>Template<wbr>Block<wbr>Device<wbr>Mapping]</a></span>
    </dt>
    <dd>{{% md %}}Specify volumes to attach to the instance besides the volumes specified by the AMI.
See Block Devices below for details.
{{% /md %}}</dd>

    <dt class="property-"
            title="">capacity_<wbr>reservation_<wbr>specification<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchtemplatecapacityreservationspecification">Dict[Launch<wbr>Template<wbr>Capacity<wbr>Reservation<wbr>Specification]</a></span>
    </dt>
    <dd>{{% md %}}Targeting for EC2 capacity reservations. See Capacity Reservation Specification below for more details.
{{% /md %}}</dd>

    <dt class="property-"
            title="">cpu_<wbr>options<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchtemplatecpuoptions">Dict[Launch<wbr>Template<wbr>Cpu<wbr>Options]</a></span>
    </dt>
    <dd>{{% md %}}The CPU options for the instance. See CPU Options below for more details.
{{% /md %}}</dd>

    <dt class="property-"
            title="">credit_<wbr>specification<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchtemplatecreditspecification">Dict[Launch<wbr>Template<wbr>Credit<wbr>Specification]</a></span>
    </dt>
    <dd>{{% md %}}Customize the credit specification of the instance. See Credit
Specification below for more details.
{{% /md %}}</dd>

    <dt class="property-"
            title="">default_<wbr>version<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The default version of the launch template.
{{% /md %}}</dd>

    <dt class="property-"
            title="">description<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Description of the launch template.
{{% /md %}}</dd>

    <dt class="property-"
            title="">disable_<wbr>api_<wbr>termination<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}If `true`, enables [EC2 Instance
Termination Protection](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/terminating-instances.html#Using_ChangingDisableAPITermination)
{{% /md %}}</dd>

    <dt class="property-"
            title="">ebs_<wbr>optimized<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}If `true`, the launched EC2 instance will be EBS-optimized.
{{% /md %}}</dd>

    <dt class="property-"
            title="">elastic_<wbr>gpu_<wbr>specifications<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchtemplateelasticgpuspecification">List[Launch<wbr>Template<wbr>Elastic<wbr>Gpu<wbr>Specification]</a></span>
    </dt>
    <dd>{{% md %}}The elastic GPU to attach to the instance. See Elastic GPU
below for more details.
{{% /md %}}</dd>

    <dt class="property-"
            title="">elastic_<wbr>inference_<wbr>accelerator<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchtemplateelasticinferenceaccelerator">Dict[Launch<wbr>Template<wbr>Elastic<wbr>Inference<wbr>Accelerator]</a></span>
    </dt>
    <dd>{{% md %}}Configuration block containing an Elastic Inference Accelerator to attach to the instance. See Elastic Inference Accelerator below for more details.
{{% /md %}}</dd>

    <dt class="property-"
            title="">iam_<wbr>instance_<wbr>profile<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchtemplateiaminstanceprofile">Dict[Launch<wbr>Template<wbr>Iam<wbr>Instance<wbr>Profile]</a></span>
    </dt>
    <dd>{{% md %}}The IAM Instance Profile to launch the instance with. See Instance Profile
below for more details.
{{% /md %}}</dd>

    <dt class="property-"
            title="">image_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The AMI from which to launch the instance.
{{% /md %}}</dd>

    <dt class="property-"
            title="">instance_<wbr>initiated_<wbr>shutdown_<wbr>behavior<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Shutdown behavior for the instance. Can be `stop` or `terminate`.
(Default: `stop`).
{{% /md %}}</dd>

    <dt class="property-"
            title="">instance_<wbr>market_<wbr>options<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchtemplateinstancemarketoptions">Dict[Launch<wbr>Template<wbr>Instance<wbr>Market<wbr>Options]</a></span>
    </dt>
    <dd>{{% md %}}The market (purchasing) option for the instance. See Market Options
below for details.
{{% /md %}}</dd>

    <dt class="property-"
            title="">instance_<wbr>type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The type of the instance.
{{% /md %}}</dd>

    <dt class="property-"
            title="">kernel_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The kernel ID.
{{% /md %}}</dd>

    <dt class="property-"
            title="">key_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The key name to use for the instance.
{{% /md %}}</dd>

    <dt class="property-"
            title="">latest_<wbr>version<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The latest version of the launch template.
{{% /md %}}</dd>

    <dt class="property-"
            title="">license_<wbr>specifications<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchtemplatelicensespecification">List[Launch<wbr>Template<wbr>License<wbr>Specification]</a></span>
    </dt>
    <dd>{{% md %}}A list of license specifications to associate with. See License Specification below for more details.
{{% /md %}}</dd>

    <dt class="property-"
            title="">monitoring<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchtemplatemonitoring">Dict[Launch<wbr>Template<wbr>Monitoring]</a></span>
    </dt>
    <dd>{{% md %}}The monitoring option for the instance. See Monitoring below for more details.
{{% /md %}}</dd>

    <dt class="property-"
            title="">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the launch template. If you leave this blank, this provider will auto-generate a unique name.
{{% /md %}}</dd>

    <dt class="property-"
            title="">name_<wbr>prefix<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Creates a unique name beginning with the specified prefix. Conflicts with `name`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">network_<wbr>interfaces<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchtemplatenetworkinterface">List[Launch<wbr>Template<wbr>Network<wbr>Interface]</a></span>
    </dt>
    <dd>{{% md %}}Customize network interfaces to be attached at instance boot time. See Network
Interfaces below for more details.
{{% /md %}}</dd>

    <dt class="property-"
            title="">placement<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchtemplateplacement">Dict[Launch<wbr>Template<wbr>Placement]</a></span>
    </dt>
    <dd>{{% md %}}The placement of the instance. See Placement below for more details.
{{% /md %}}</dd>

    <dt class="property-"
            title="">ram_<wbr>disk_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ID of the RAM disk.
{{% /md %}}</dd>

    <dt class="property-"
            title="">security_<wbr>group_<wbr>names<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}A list of security group names to associate with. If you are creating Instances in a VPC, use
`vpc_security_group_ids` instead.
{{% /md %}}</dd>

    <dt class="property-"
            title="">tag_<wbr>specifications<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchtemplatetagspecification">List[Launch<wbr>Template<wbr>Tag<wbr>Specification]</a></span>
    </dt>
    <dd>{{% md %}}The tags to apply to the resources during launch. See Tag Specifications below for more details.
{{% /md %}}</dd>

    <dt class="property-"
            title="">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the launch template.
{{% /md %}}</dd>

    <dt class="property-"
            title="">user_<wbr>data<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The Base64-encoded user data to provide when launching the instance.
{{% /md %}}</dd>

    <dt class="property-"
            title="">vpc_<wbr>security_<wbr>group_<wbr>ids<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}A list of security group IDs to associate with.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





## Look up an Existing LaunchTemplate Resource

{{< chooser language "javascript,typescript,python,go,csharp  " / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">pulumi.Input&lt;pulumi.ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/ec2/#LaunchTemplateState">LaunchTemplateState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/ec2/#LaunchTemplate">LaunchTemplate</a></span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>arn=None<span class="p">, </span>block_device_mappings=None<span class="p">, </span>capacity_reservation_specification=None<span class="p">, </span>cpu_options=None<span class="p">, </span>credit_specification=None<span class="p">, </span>default_version=None<span class="p">, </span>description=None<span class="p">, </span>disable_api_termination=None<span class="p">, </span>ebs_optimized=None<span class="p">, </span>elastic_gpu_specifications=None<span class="p">, </span>elastic_inference_accelerator=None<span class="p">, </span>iam_instance_profile=None<span class="p">, </span>image_id=None<span class="p">, </span>instance_initiated_shutdown_behavior=None<span class="p">, </span>instance_market_options=None<span class="p">, </span>instance_type=None<span class="p">, </span>kernel_id=None<span class="p">, </span>key_name=None<span class="p">, </span>latest_version=None<span class="p">, </span>license_specifications=None<span class="p">, </span>monitoring=None<span class="p">, </span>name=None<span class="p">, </span>name_prefix=None<span class="p">, </span>network_interfaces=None<span class="p">, </span>placement=None<span class="p">, </span>ram_disk_id=None<span class="p">, </span>security_group_names=None<span class="p">, </span>tag_specifications=None<span class="p">, </span>tags=None<span class="p">, </span>user_data=None<span class="p">, </span>vpc_security_group_ids=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetLaunchTemplate<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">pulumi.IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ec2?tab=doc#LaunchTemplateState">LaunchTemplateState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ec2?tab=doc#LaunchTemplate">LaunchTemplate</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ec2.LaunchTemplate.html">LaunchTemplate</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Pulumi.Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ec2.LaunchTemplateState.html">LaunchTemplateState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
{{% /choosable %}}

Get an existing LaunchTemplate resource's state with the given name, ID, and optional extra properties used to qualify the lookup.

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
    <dd>{{% md %}}Amazon Resource Name (ARN) of the launch template.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Block<wbr>Device<wbr>Mappings<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchtemplateblockdevicemapping">List&lt;Launch<wbr>Template<wbr>Block<wbr>Device<wbr>Mapping<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}Specify volumes to attach to the instance besides the volumes specified by the AMI.
See Block Devices below for details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Capacity<wbr>Reservation<wbr>Specification<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchtemplatecapacityreservationspecification">Launch<wbr>Template<wbr>Capacity<wbr>Reservation<wbr>Specification<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}Targeting for EC2 capacity reservations. See Capacity Reservation Specification below for more details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Cpu<wbr>Options<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchtemplatecpuoptions">Launch<wbr>Template<wbr>Cpu<wbr>Options<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}The CPU options for the instance. See CPU Options below for more details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Credit<wbr>Specification<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchtemplatecreditspecification">Launch<wbr>Template<wbr>Credit<wbr>Specification<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}Customize the credit specification of the instance. See Credit
Specification below for more details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Default<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The default version of the launch template.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Description<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Description of the launch template.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Disable<wbr>Api<wbr>Termination<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}If `true`, enables [EC2 Instance
Termination Protection](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/terminating-instances.html#Using_ChangingDisableAPITermination)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ebs<wbr>Optimized<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}If `true`, the launched EC2 instance will be EBS-optimized.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Elastic<wbr>Gpu<wbr>Specifications<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchtemplateelasticgpuspecification">List&lt;Launch<wbr>Template<wbr>Elastic<wbr>Gpu<wbr>Specification<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}The elastic GPU to attach to the instance. See Elastic GPU
below for more details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Elastic<wbr>Inference<wbr>Accelerator<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchtemplateelasticinferenceaccelerator">Launch<wbr>Template<wbr>Elastic<wbr>Inference<wbr>Accelerator<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}Configuration block containing an Elastic Inference Accelerator to attach to the instance. See Elastic Inference Accelerator below for more details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Iam<wbr>Instance<wbr>Profile<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchtemplateiaminstanceprofile">Launch<wbr>Template<wbr>Iam<wbr>Instance<wbr>Profile<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}The IAM Instance Profile to launch the instance with. See Instance Profile
below for more details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Image<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The AMI from which to launch the instance.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Instance<wbr>Initiated<wbr>Shutdown<wbr>Behavior<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Shutdown behavior for the instance. Can be `stop` or `terminate`.
(Default: `stop`).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Instance<wbr>Market<wbr>Options<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchtemplateinstancemarketoptions">Launch<wbr>Template<wbr>Instance<wbr>Market<wbr>Options<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}The market (purchasing) option for the instance. See Market Options
below for details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Instance<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The type of the instance.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Kernel<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The kernel ID.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Key<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The key name to use for the instance.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Latest<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The latest version of the launch template.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">License<wbr>Specifications<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchtemplatelicensespecification">List&lt;Launch<wbr>Template<wbr>License<wbr>Specification<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}A list of license specifications to associate with. See License Specification below for more details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Monitoring<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchtemplatemonitoring">Launch<wbr>Template<wbr>Monitoring<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}The monitoring option for the instance. See Monitoring below for more details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the launch template. If you leave this blank, this provider will auto-generate a unique name.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<wbr>Prefix<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Creates a unique name beginning with the specified prefix. Conflicts with `name`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Network<wbr>Interfaces<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchtemplatenetworkinterface">List&lt;Launch<wbr>Template<wbr>Network<wbr>Interface<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}Customize network interfaces to be attached at instance boot time. See Network
Interfaces below for more details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Placement<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchtemplateplacement">Launch<wbr>Template<wbr>Placement<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}The placement of the instance. See Placement below for more details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ram<wbr>Disk<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ID of the RAM disk.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Security<wbr>Group<wbr>Names<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}A list of security group names to associate with. If you are creating Instances in a VPC, use
`vpc_security_group_ids` instead.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tag<wbr>Specifications<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchtemplatetagspecification">List&lt;Launch<wbr>Template<wbr>Tag<wbr>Specification<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}The tags to apply to the resources during launch. See Tag Specifications below for more details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the launch template.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">User<wbr>Data<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The Base64-encoded user data to provide when launching the instance.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Vpc<wbr>Security<wbr>Group<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}A list of security group IDs to associate with.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of the launch template.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Block<wbr>Device<wbr>Mappings<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchtemplateblockdevicemapping">[]Launch<wbr>Template<wbr>Block<wbr>Device<wbr>Mapping</a></span>
    </dt>
    <dd>{{% md %}}Specify volumes to attach to the instance besides the volumes specified by the AMI.
See Block Devices below for details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Capacity<wbr>Reservation<wbr>Specification<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchtemplatecapacityreservationspecification">*Launch<wbr>Template<wbr>Capacity<wbr>Reservation<wbr>Specification</a></span>
    </dt>
    <dd>{{% md %}}Targeting for EC2 capacity reservations. See Capacity Reservation Specification below for more details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Cpu<wbr>Options<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchtemplatecpuoptions">*Launch<wbr>Template<wbr>Cpu<wbr>Options</a></span>
    </dt>
    <dd>{{% md %}}The CPU options for the instance. See CPU Options below for more details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Credit<wbr>Specification<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchtemplatecreditspecification">*Launch<wbr>Template<wbr>Credit<wbr>Specification</a></span>
    </dt>
    <dd>{{% md %}}Customize the credit specification of the instance. See Credit
Specification below for more details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Default<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The default version of the launch template.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Description<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Description of the launch template.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Disable<wbr>Api<wbr>Termination<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}If `true`, enables [EC2 Instance
Termination Protection](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/terminating-instances.html#Using_ChangingDisableAPITermination)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ebs<wbr>Optimized<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}If `true`, the launched EC2 instance will be EBS-optimized.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Elastic<wbr>Gpu<wbr>Specifications<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchtemplateelasticgpuspecification">[]Launch<wbr>Template<wbr>Elastic<wbr>Gpu<wbr>Specification</a></span>
    </dt>
    <dd>{{% md %}}The elastic GPU to attach to the instance. See Elastic GPU
below for more details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Elastic<wbr>Inference<wbr>Accelerator<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchtemplateelasticinferenceaccelerator">*Launch<wbr>Template<wbr>Elastic<wbr>Inference<wbr>Accelerator</a></span>
    </dt>
    <dd>{{% md %}}Configuration block containing an Elastic Inference Accelerator to attach to the instance. See Elastic Inference Accelerator below for more details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Iam<wbr>Instance<wbr>Profile<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchtemplateiaminstanceprofile">*Launch<wbr>Template<wbr>Iam<wbr>Instance<wbr>Profile</a></span>
    </dt>
    <dd>{{% md %}}The IAM Instance Profile to launch the instance with. See Instance Profile
below for more details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Image<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The AMI from which to launch the instance.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Instance<wbr>Initiated<wbr>Shutdown<wbr>Behavior<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Shutdown behavior for the instance. Can be `stop` or `terminate`.
(Default: `stop`).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Instance<wbr>Market<wbr>Options<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchtemplateinstancemarketoptions">*Launch<wbr>Template<wbr>Instance<wbr>Market<wbr>Options</a></span>
    </dt>
    <dd>{{% md %}}The market (purchasing) option for the instance. See Market Options
below for details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Instance<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The type of the instance.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Kernel<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The kernel ID.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Key<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The key name to use for the instance.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Latest<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The latest version of the launch template.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">License<wbr>Specifications<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchtemplatelicensespecification">[]Launch<wbr>Template<wbr>License<wbr>Specification</a></span>
    </dt>
    <dd>{{% md %}}A list of license specifications to associate with. See License Specification below for more details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Monitoring<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchtemplatemonitoring">*Launch<wbr>Template<wbr>Monitoring</a></span>
    </dt>
    <dd>{{% md %}}The monitoring option for the instance. See Monitoring below for more details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name of the launch template. If you leave this blank, this provider will auto-generate a unique name.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<wbr>Prefix<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Creates a unique name beginning with the specified prefix. Conflicts with `name`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Network<wbr>Interfaces<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchtemplatenetworkinterface">[]Launch<wbr>Template<wbr>Network<wbr>Interface</a></span>
    </dt>
    <dd>{{% md %}}Customize network interfaces to be attached at instance boot time. See Network
Interfaces below for more details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Placement<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchtemplateplacement">*Launch<wbr>Template<wbr>Placement</a></span>
    </dt>
    <dd>{{% md %}}The placement of the instance. See Placement below for more details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ram<wbr>Disk<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The ID of the RAM disk.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Security<wbr>Group<wbr>Names<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}A list of security group names to associate with. If you are creating Instances in a VPC, use
`vpc_security_group_ids` instead.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tag<wbr>Specifications<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchtemplatetagspecification">[]Launch<wbr>Template<wbr>Tag<wbr>Specification</a></span>
    </dt>
    <dd>{{% md %}}The tags to apply to the resources during launch. See Tag Specifications below for more details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the launch template.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">User<wbr>Data<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The Base64-encoded user data to provide when launching the instance.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Vpc<wbr>Security<wbr>Group<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}A list of security group IDs to associate with.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of the launch template.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">block<wbr>Device<wbr>Mappings<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchtemplateblockdevicemapping">Launch<wbr>Template<wbr>Block<wbr>Device<wbr>Mapping[]?</a></span>
    </dt>
    <dd>{{% md %}}Specify volumes to attach to the instance besides the volumes specified by the AMI.
See Block Devices below for details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">capacity<wbr>Reservation<wbr>Specification<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchtemplatecapacityreservationspecification">Launch<wbr>Template<wbr>Capacity<wbr>Reservation<wbr>Specification?</a></span>
    </dt>
    <dd>{{% md %}}Targeting for EC2 capacity reservations. See Capacity Reservation Specification below for more details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">cpu<wbr>Options<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchtemplatecpuoptions">Launch<wbr>Template<wbr>Cpu<wbr>Options?</a></span>
    </dt>
    <dd>{{% md %}}The CPU options for the instance. See CPU Options below for more details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">credit<wbr>Specification<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchtemplatecreditspecification">Launch<wbr>Template<wbr>Credit<wbr>Specification?</a></span>
    </dt>
    <dd>{{% md %}}Customize the credit specification of the instance. See Credit
Specification below for more details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">default<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The default version of the launch template.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">description<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Description of the launch template.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">disable<wbr>Api<wbr>Termination<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}If `true`, enables [EC2 Instance
Termination Protection](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/terminating-instances.html#Using_ChangingDisableAPITermination)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ebs<wbr>Optimized<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}If `true`, the launched EC2 instance will be EBS-optimized.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">elastic<wbr>Gpu<wbr>Specifications<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchtemplateelasticgpuspecification">Launch<wbr>Template<wbr>Elastic<wbr>Gpu<wbr>Specification[]?</a></span>
    </dt>
    <dd>{{% md %}}The elastic GPU to attach to the instance. See Elastic GPU
below for more details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">elastic<wbr>Inference<wbr>Accelerator<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchtemplateelasticinferenceaccelerator">Launch<wbr>Template<wbr>Elastic<wbr>Inference<wbr>Accelerator?</a></span>
    </dt>
    <dd>{{% md %}}Configuration block containing an Elastic Inference Accelerator to attach to the instance. See Elastic Inference Accelerator below for more details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">iam<wbr>Instance<wbr>Profile<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchtemplateiaminstanceprofile">Launch<wbr>Template<wbr>Iam<wbr>Instance<wbr>Profile?</a></span>
    </dt>
    <dd>{{% md %}}The IAM Instance Profile to launch the instance with. See Instance Profile
below for more details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">image<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The AMI from which to launch the instance.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">instance<wbr>Initiated<wbr>Shutdown<wbr>Behavior<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Shutdown behavior for the instance. Can be `stop` or `terminate`.
(Default: `stop`).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">instance<wbr>Market<wbr>Options<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchtemplateinstancemarketoptions">Launch<wbr>Template<wbr>Instance<wbr>Market<wbr>Options?</a></span>
    </dt>
    <dd>{{% md %}}The market (purchasing) option for the instance. See Market Options
below for details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">instance<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The type of the instance.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">kernel<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The kernel ID.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">key<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The key name to use for the instance.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">latest<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The latest version of the launch template.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">license<wbr>Specifications<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchtemplatelicensespecification">Launch<wbr>Template<wbr>License<wbr>Specification[]?</a></span>
    </dt>
    <dd>{{% md %}}A list of license specifications to associate with. See License Specification below for more details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">monitoring<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchtemplatemonitoring">Launch<wbr>Template<wbr>Monitoring?</a></span>
    </dt>
    <dd>{{% md %}}The monitoring option for the instance. See Monitoring below for more details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the launch template. If you leave this blank, this provider will auto-generate a unique name.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<wbr>Prefix<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Creates a unique name beginning with the specified prefix. Conflicts with `name`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">network<wbr>Interfaces<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchtemplatenetworkinterface">Launch<wbr>Template<wbr>Network<wbr>Interface[]?</a></span>
    </dt>
    <dd>{{% md %}}Customize network interfaces to be attached at instance boot time. See Network
Interfaces below for more details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">placement<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchtemplateplacement">Launch<wbr>Template<wbr>Placement?</a></span>
    </dt>
    <dd>{{% md %}}The placement of the instance. See Placement below for more details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ram<wbr>Disk<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ID of the RAM disk.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">security<wbr>Group<wbr>Names<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}A list of security group names to associate with. If you are creating Instances in a VPC, use
`vpc_security_group_ids` instead.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tag<wbr>Specifications<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchtemplatetagspecification">Launch<wbr>Template<wbr>Tag<wbr>Specification[]?</a></span>
    </dt>
    <dd>{{% md %}}The tags to apply to the resources during launch. See Tag Specifications below for more details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the launch template.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">user<wbr>Data<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The Base64-encoded user data to provide when launching the instance.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">vpc<wbr>Security<wbr>Group<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}A list of security group IDs to associate with.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of the launch template.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">block_<wbr>device_<wbr>mappings<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchtemplateblockdevicemapping">List[Launch<wbr>Template<wbr>Block<wbr>Device<wbr>Mapping]</a></span>
    </dt>
    <dd>{{% md %}}Specify volumes to attach to the instance besides the volumes specified by the AMI.
See Block Devices below for details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">capacity_<wbr>reservation_<wbr>specification<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchtemplatecapacityreservationspecification">Dict[Launch<wbr>Template<wbr>Capacity<wbr>Reservation<wbr>Specification]</a></span>
    </dt>
    <dd>{{% md %}}Targeting for EC2 capacity reservations. See Capacity Reservation Specification below for more details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">cpu_<wbr>options<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchtemplatecpuoptions">Dict[Launch<wbr>Template<wbr>Cpu<wbr>Options]</a></span>
    </dt>
    <dd>{{% md %}}The CPU options for the instance. See CPU Options below for more details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">credit_<wbr>specification<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchtemplatecreditspecification">Dict[Launch<wbr>Template<wbr>Credit<wbr>Specification]</a></span>
    </dt>
    <dd>{{% md %}}Customize the credit specification of the instance. See Credit
Specification below for more details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">default_<wbr>version<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The default version of the launch template.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">description<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Description of the launch template.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">disable_<wbr>api_<wbr>termination<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}If `true`, enables [EC2 Instance
Termination Protection](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/terminating-instances.html#Using_ChangingDisableAPITermination)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ebs_<wbr>optimized<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}If `true`, the launched EC2 instance will be EBS-optimized.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">elastic_<wbr>gpu_<wbr>specifications<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchtemplateelasticgpuspecification">List[Launch<wbr>Template<wbr>Elastic<wbr>Gpu<wbr>Specification]</a></span>
    </dt>
    <dd>{{% md %}}The elastic GPU to attach to the instance. See Elastic GPU
below for more details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">elastic_<wbr>inference_<wbr>accelerator<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchtemplateelasticinferenceaccelerator">Dict[Launch<wbr>Template<wbr>Elastic<wbr>Inference<wbr>Accelerator]</a></span>
    </dt>
    <dd>{{% md %}}Configuration block containing an Elastic Inference Accelerator to attach to the instance. See Elastic Inference Accelerator below for more details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">iam_<wbr>instance_<wbr>profile<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchtemplateiaminstanceprofile">Dict[Launch<wbr>Template<wbr>Iam<wbr>Instance<wbr>Profile]</a></span>
    </dt>
    <dd>{{% md %}}The IAM Instance Profile to launch the instance with. See Instance Profile
below for more details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">image_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The AMI from which to launch the instance.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">instance_<wbr>initiated_<wbr>shutdown_<wbr>behavior<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Shutdown behavior for the instance. Can be `stop` or `terminate`.
(Default: `stop`).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">instance_<wbr>market_<wbr>options<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchtemplateinstancemarketoptions">Dict[Launch<wbr>Template<wbr>Instance<wbr>Market<wbr>Options]</a></span>
    </dt>
    <dd>{{% md %}}The market (purchasing) option for the instance. See Market Options
below for details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">instance_<wbr>type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The type of the instance.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">kernel_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The kernel ID.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">key_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The key name to use for the instance.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">latest_<wbr>version<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The latest version of the launch template.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">license_<wbr>specifications<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchtemplatelicensespecification">List[Launch<wbr>Template<wbr>License<wbr>Specification]</a></span>
    </dt>
    <dd>{{% md %}}A list of license specifications to associate with. See License Specification below for more details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">monitoring<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchtemplatemonitoring">Dict[Launch<wbr>Template<wbr>Monitoring]</a></span>
    </dt>
    <dd>{{% md %}}The monitoring option for the instance. See Monitoring below for more details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the launch template. If you leave this blank, this provider will auto-generate a unique name.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name_<wbr>prefix<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Creates a unique name beginning with the specified prefix. Conflicts with `name`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">network_<wbr>interfaces<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchtemplatenetworkinterface">List[Launch<wbr>Template<wbr>Network<wbr>Interface]</a></span>
    </dt>
    <dd>{{% md %}}Customize network interfaces to be attached at instance boot time. See Network
Interfaces below for more details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">placement<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchtemplateplacement">Dict[Launch<wbr>Template<wbr>Placement]</a></span>
    </dt>
    <dd>{{% md %}}The placement of the instance. See Placement below for more details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ram_<wbr>disk_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ID of the RAM disk.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">security_<wbr>group_<wbr>names<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}A list of security group names to associate with. If you are creating Instances in a VPC, use
`vpc_security_group_ids` instead.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tag_<wbr>specifications<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchtemplatetagspecification">List[Launch<wbr>Template<wbr>Tag<wbr>Specification]</a></span>
    </dt>
    <dd>{{% md %}}The tags to apply to the resources during launch. See Tag Specifications below for more details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the launch template.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">user_<wbr>data<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The Base64-encoded user data to provide when launching the instance.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">vpc_<wbr>security_<wbr>group_<wbr>ids<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}A list of security group IDs to associate with.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}







## Supporting Types

#### LaunchTemplateBlockDeviceMapping
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#LaunchTemplateBlockDeviceMapping">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#LaunchTemplateBlockDeviceMapping">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ec2?tab=doc#LaunchTemplateBlockDeviceMappingArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ec2?tab=doc#LaunchTemplateBlockDeviceMappingOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ec2.LaunchTemplateBlockDeviceMappingArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ec2.LaunchTemplateBlockDeviceMapping.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Device<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the device to mount.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ebs<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchtemplateblockdevicemappingebs">Launch<wbr>Template<wbr>Block<wbr>Device<wbr>Mapping<wbr>Ebs<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}Configure EBS volume properties.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">No<wbr>Device<span class="property-indicator"></span>
        <span class="property-type">string?</span>
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

    <dt class="property-optional"
            title="Optional">Device<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name of the device to mount.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ebs<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchtemplateblockdevicemappingebs">*Launch<wbr>Template<wbr>Block<wbr>Device<wbr>Mapping<wbr>Ebs</a></span>
    </dt>
    <dd>{{% md %}}Configure EBS volume properties.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">No<wbr>Device<span class="property-indicator"></span>
        <span class="property-type">*string</span>
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

    <dt class="property-optional"
            title="Optional">device<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the device to mount.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ebs<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchtemplateblockdevicemappingebs">Launch<wbr>Template<wbr>Block<wbr>Device<wbr>Mapping<wbr>Ebs?</a></span>
    </dt>
    <dd>{{% md %}}Configure EBS volume properties.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">no<wbr>Device<span class="property-indicator"></span>
        <span class="property-type">string?</span>
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

    <dt class="property-optional"
            title="Optional">device_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the device to mount.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ebs<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchtemplateblockdevicemappingebs">Dict[Launch<wbr>Template<wbr>Block<wbr>Device<wbr>Mapping<wbr>Ebs]</a></span>
    </dt>
    <dd>{{% md %}}Configure EBS volume properties.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">no<wbr>Device<span class="property-indicator"></span>
        <span class="property-type">str</span>
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





#### LaunchTemplateBlockDeviceMappingEbs
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#LaunchTemplateBlockDeviceMappingEbs">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#LaunchTemplateBlockDeviceMappingEbs">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ec2?tab=doc#LaunchTemplateBlockDeviceMappingEbsArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ec2?tab=doc#LaunchTemplateBlockDeviceMappingEbsOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ec2.LaunchTemplateBlockDeviceMappingEbsArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ec2.LaunchTemplateBlockDeviceMappingEbs.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Delete<wbr>On<wbr>Termination<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Encrypted<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Iops<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Kms<wbr>Key<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
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
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Encrypted<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Iops<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Kms<wbr>Key<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
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
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">encrypted<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">iops<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">kms<wbr>Key<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
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
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">encrypted<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">iops<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">kms_<wbr>key_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
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





#### LaunchTemplateCapacityReservationSpecification
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#LaunchTemplateCapacityReservationSpecification">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#LaunchTemplateCapacityReservationSpecification">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ec2?tab=doc#LaunchTemplateCapacityReservationSpecificationArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ec2?tab=doc#LaunchTemplateCapacityReservationSpecificationOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ec2.LaunchTemplateCapacityReservationSpecificationArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ec2.LaunchTemplateCapacityReservationSpecification.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Capacity<wbr>Reservation<wbr>Preference<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Capacity<wbr>Reservation<wbr>Target<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchtemplatecapacityreservationspecificationcapacityreservationtarget">Launch<wbr>Template<wbr>Capacity<wbr>Reservation<wbr>Specification<wbr>Capacity<wbr>Reservation<wbr>Target<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Capacity<wbr>Reservation<wbr>Preference<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Capacity<wbr>Reservation<wbr>Target<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchtemplatecapacityreservationspecificationcapacityreservationtarget">*Launch<wbr>Template<wbr>Capacity<wbr>Reservation<wbr>Specification<wbr>Capacity<wbr>Reservation<wbr>Target</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">capacity<wbr>Reservation<wbr>Preference<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">capacity<wbr>Reservation<wbr>Target<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchtemplatecapacityreservationspecificationcapacityreservationtarget">Launch<wbr>Template<wbr>Capacity<wbr>Reservation<wbr>Specification<wbr>Capacity<wbr>Reservation<wbr>Target?</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">capacity<wbr>Reservation<wbr>Preference<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">capacity<wbr>Reservation<wbr>Target<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchtemplatecapacityreservationspecificationcapacityreservationtarget">Dict[Launch<wbr>Template<wbr>Capacity<wbr>Reservation<wbr>Specification<wbr>Capacity<wbr>Reservation<wbr>Target]</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### LaunchTemplateCapacityReservationSpecificationCapacityReservationTarget
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#LaunchTemplateCapacityReservationSpecificationCapacityReservationTarget">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#LaunchTemplateCapacityReservationSpecificationCapacityReservationTarget">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ec2?tab=doc#LaunchTemplateCapacityReservationSpecificationCapacityReservationTargetArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ec2?tab=doc#LaunchTemplateCapacityReservationSpecificationCapacityReservationTargetOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ec2.LaunchTemplateCapacityReservationSpecificationCapacityReservationTargetArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ec2.LaunchTemplateCapacityReservationSpecificationCapacityReservationTarget.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Capacity<wbr>Reservation<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Capacity<wbr>Reservation<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">capacity<wbr>Reservation<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">capacity<wbr>Reservation<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### LaunchTemplateCpuOptions
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#LaunchTemplateCpuOptions">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#LaunchTemplateCpuOptions">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ec2?tab=doc#LaunchTemplateCpuOptionsArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ec2?tab=doc#LaunchTemplateCpuOptionsOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ec2.LaunchTemplateCpuOptionsArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ec2.LaunchTemplateCpuOptions.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Core<wbr>Count<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Threads<wbr>Per<wbr>Core<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Core<wbr>Count<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Threads<wbr>Per<wbr>Core<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">core<wbr>Count<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">threads<wbr>Per<wbr>Core<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">core<wbr>Count<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">threads<wbr>Per<wbr>Core<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### LaunchTemplateCreditSpecification
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#LaunchTemplateCreditSpecification">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#LaunchTemplateCreditSpecification">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ec2?tab=doc#LaunchTemplateCreditSpecificationArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ec2?tab=doc#LaunchTemplateCreditSpecificationOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ec2.LaunchTemplateCreditSpecificationArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ec2.LaunchTemplateCreditSpecification.html">output</a> API doc for this type.
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





#### LaunchTemplateElasticGpuSpecification
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#LaunchTemplateElasticGpuSpecification">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#LaunchTemplateElasticGpuSpecification">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ec2?tab=doc#LaunchTemplateElasticGpuSpecificationArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ec2?tab=doc#LaunchTemplateElasticGpuSpecificationOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ec2.LaunchTemplateElasticGpuSpecificationArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ec2.LaunchTemplateElasticGpuSpecification.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Accelerator type.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Accelerator type.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Accelerator type.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Accelerator type.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### LaunchTemplateElasticInferenceAccelerator
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#LaunchTemplateElasticInferenceAccelerator">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#LaunchTemplateElasticInferenceAccelerator">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ec2?tab=doc#LaunchTemplateElasticInferenceAcceleratorArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ec2?tab=doc#LaunchTemplateElasticInferenceAcceleratorOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ec2.LaunchTemplateElasticInferenceAcceleratorArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ec2.LaunchTemplateElasticInferenceAccelerator.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Accelerator type.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Accelerator type.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Accelerator type.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Accelerator type.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### LaunchTemplateIamInstanceProfile
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#LaunchTemplateIamInstanceProfile">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#LaunchTemplateIamInstanceProfile">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ec2?tab=doc#LaunchTemplateIamInstanceProfileArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ec2?tab=doc#LaunchTemplateIamInstanceProfileOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ec2.LaunchTemplateIamInstanceProfileArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ec2.LaunchTemplateIamInstanceProfile.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of the launch template.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the launch template. If you leave this blank, this provider will auto-generate a unique name.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of the launch template.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name of the launch template. If you leave this blank, this provider will auto-generate a unique name.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of the launch template.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the launch template. If you leave this blank, this provider will auto-generate a unique name.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of the launch template.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the launch template. If you leave this blank, this provider will auto-generate a unique name.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### LaunchTemplateInstanceMarketOptions
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#LaunchTemplateInstanceMarketOptions">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#LaunchTemplateInstanceMarketOptions">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ec2?tab=doc#LaunchTemplateInstanceMarketOptionsArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ec2?tab=doc#LaunchTemplateInstanceMarketOptionsOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ec2.LaunchTemplateInstanceMarketOptionsArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ec2.LaunchTemplateInstanceMarketOptions.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Market<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Spot<wbr>Options<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchtemplateinstancemarketoptionsspotoptions">Launch<wbr>Template<wbr>Instance<wbr>Market<wbr>Options<wbr>Spot<wbr>Options<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Market<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Spot<wbr>Options<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchtemplateinstancemarketoptionsspotoptions">*Launch<wbr>Template<wbr>Instance<wbr>Market<wbr>Options<wbr>Spot<wbr>Options</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">market<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">spot<wbr>Options<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchtemplateinstancemarketoptionsspotoptions">Launch<wbr>Template<wbr>Instance<wbr>Market<wbr>Options<wbr>Spot<wbr>Options?</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">market<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">spot_<wbr>options<span class="property-indicator"></span>
        <span class="property-type"><a href="#launchtemplateinstancemarketoptionsspotoptions">Dict[Launch<wbr>Template<wbr>Instance<wbr>Market<wbr>Options<wbr>Spot<wbr>Options]</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### LaunchTemplateInstanceMarketOptionsSpotOptions
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#LaunchTemplateInstanceMarketOptionsSpotOptions">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#LaunchTemplateInstanceMarketOptionsSpotOptions">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ec2?tab=doc#LaunchTemplateInstanceMarketOptionsSpotOptionsArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ec2?tab=doc#LaunchTemplateInstanceMarketOptionsSpotOptionsOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ec2.LaunchTemplateInstanceMarketOptionsSpotOptionsArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ec2.LaunchTemplateInstanceMarketOptionsSpotOptions.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Block<wbr>Duration<wbr>Minutes<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Instance<wbr>Interruption<wbr>Behavior<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Max<wbr>Price<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Spot<wbr>Instance<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Valid<wbr>Until<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Block<wbr>Duration<wbr>Minutes<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Instance<wbr>Interruption<wbr>Behavior<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Max<wbr>Price<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Spot<wbr>Instance<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Valid<wbr>Until<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">block<wbr>Duration<wbr>Minutes<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">instance<wbr>Interruption<wbr>Behavior<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">max<wbr>Price<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">spot<wbr>Instance<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">valid<wbr>Until<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">block_<wbr>duration_<wbr>minutes<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">instance<wbr>Interruption<wbr>Behavior<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">max<wbr>Price<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">spot<wbr>Instance<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">valid_<wbr>until<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### LaunchTemplateLicenseSpecification
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#LaunchTemplateLicenseSpecification">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#LaunchTemplateLicenseSpecification">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ec2?tab=doc#LaunchTemplateLicenseSpecificationArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ec2?tab=doc#LaunchTemplateLicenseSpecificationOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ec2.LaunchTemplateLicenseSpecificationArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ec2.LaunchTemplateLicenseSpecification.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">License<wbr>Configuration<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">License<wbr>Configuration<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">license<wbr>Configuration<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">license_<wbr>configuration_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### LaunchTemplateMonitoring
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#LaunchTemplateMonitoring">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#LaunchTemplateMonitoring">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ec2?tab=doc#LaunchTemplateMonitoringArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ec2?tab=doc#LaunchTemplateMonitoringOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ec2.LaunchTemplateMonitoringArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ec2.LaunchTemplateMonitoring.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Enabled<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Enabled<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">enabled<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">enabled<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### LaunchTemplateNetworkInterface
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#LaunchTemplateNetworkInterface">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#LaunchTemplateNetworkInterface">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ec2?tab=doc#LaunchTemplateNetworkInterfaceArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ec2?tab=doc#LaunchTemplateNetworkInterfaceOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ec2.LaunchTemplateNetworkInterfaceArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ec2.LaunchTemplateNetworkInterface.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Associate<wbr>Public<wbr>Ip<wbr>Address<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Delete<wbr>On<wbr>Termination<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Description<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Description of the launch template.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Device<wbr>Index<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ipv4Address<wbr>Count<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ipv4Addresses<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ipv6Address<wbr>Count<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ipv6Addresses<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Network<wbr>Interface<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Private<wbr>Ip<wbr>Address<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Security<wbr>Groups<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Subnet<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Associate<wbr>Public<wbr>Ip<wbr>Address<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Delete<wbr>On<wbr>Termination<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Description<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Description of the launch template.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Device<wbr>Index<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ipv4Address<wbr>Count<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ipv4Addresses<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ipv6Address<wbr>Count<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ipv6Addresses<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Network<wbr>Interface<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Private<wbr>Ip<wbr>Address<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Security<wbr>Groups<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Subnet<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">associate<wbr>Public<wbr>Ip<wbr>Address<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">delete<wbr>On<wbr>Termination<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">description<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Description of the launch template.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">device<wbr>Index<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ipv4Address<wbr>Count<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ipv4Addresses<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ipv6Address<wbr>Count<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ipv6Addresses<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">network<wbr>Interface<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">private<wbr>Ip<wbr>Address<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">security<wbr>Groups<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">subnet<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">associate_<wbr>public_<wbr>ip_<wbr>address<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">delete<wbr>On<wbr>Termination<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">description<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Description of the launch template.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">device_<wbr>index<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ipv4Address<wbr>Count<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ipv4Addresses<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ipv6_<wbr>address_<wbr>count<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ipv6_<wbr>addresses<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">network_<wbr>interface_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">private_<wbr>ip_<wbr>address<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">security_<wbr>groups<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">subnet_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### LaunchTemplatePlacement
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#LaunchTemplatePlacement">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#LaunchTemplatePlacement">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ec2?tab=doc#LaunchTemplatePlacementArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ec2?tab=doc#LaunchTemplatePlacementOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ec2.LaunchTemplatePlacementArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ec2.LaunchTemplatePlacement.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Affinity<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Availability<wbr>Zone<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Group<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Host<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Spread<wbr>Domain<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tenancy<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Affinity<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Availability<wbr>Zone<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Group<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Host<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Spread<wbr>Domain<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tenancy<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">affinity<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">availability<wbr>Zone<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">group<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">host<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">spread<wbr>Domain<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tenancy<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">affinity<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">availability_<wbr>zone<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">group_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">host_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">spread<wbr>Domain<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tenancy<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### LaunchTemplateTagSpecification
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#LaunchTemplateTagSpecification">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#LaunchTemplateTagSpecification">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ec2?tab=doc#LaunchTemplateTagSpecificationArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ec2?tab=doc#LaunchTemplateTagSpecificationOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ec2.LaunchTemplateTagSpecificationArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ec2.LaunchTemplateTagSpecification.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Resource<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the launch template.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Resource<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the launch template.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">resource<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the launch template.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">resource_<wbr>type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the launch template.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}








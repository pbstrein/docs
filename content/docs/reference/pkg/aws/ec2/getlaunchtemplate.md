
---
title: "GetLaunchTemplate"
block_external_search_index: true
---

Provides information about a Launch Template.

## Example Usage

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const defaultLaunchTemplate = aws.ec2.getLaunchTemplate({
    name: "my-launch-template",
});
```

> This content is derived from https://github.com/terraform-providers/terraform-provider-aws/blob/master/website/docs/d/launch_template.html.markdown.





## Using GetLaunchTemplate

{{< chooser language "typescript,python,go,csharp" >}}

{{% choosable language typescript %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">function </span>getLaunchTemplate<span class="p">(</span><span class="nx">args</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/ec2/#GetLaunchTemplateArgs">GetLaunchTemplateArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#InvokeOptions">pulumi.InvokeOptions</a></span><span class="p">): Promise&lt;<span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/ec2/#GetLaunchTemplateResult">GetLaunchTemplateResult</a></span>></span></code></pre></div>
{{% /choosable %}}" }}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">function </span> get_launch_template(</span>name=None<span class="p">, </span>tags=None<span class="p">, </span>opts=None<span class="p">)</span></code></pre></div>
{{% /choosable %}}" }}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>LookupLaunchTemplate<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">args</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ec2?tab=doc#LookupLaunchTemplateArgs">LookupLaunchTemplateArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#InvokeOption">pulumi.InvokeOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ec2?tab=doc#LookupLaunchTemplateResult">LookupLaunchTemplateResult</a></span>, error)</span></code></pre></div>
{{% /choosable %}}" }}

{{% choosable language csharp %}}
<div class="highlight">
<pre class="chroma">
<code class="language-csharp" data-lang="csharp"><span class="k">public static class </span><span class="nx">GetLaunchTemplate </span><span class="p">{</span>
    <span class="k">public static </span>Task&lt;<span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ec2.GetLaunchTemplateResult.html">GetLaunchTemplateResult</a></span>> <span class="p">InvokeAsync(</span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ec2.GetLaunchTemplateArgs.html">GetLaunchTemplateArgs</a></span> <span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/InvokeOptions.html">InvokeOptions</a></span>? <span class="nx">opts = null<span class="p">)</span>
<span class="p">}</span></code></pre>
</div>
{{% /choosable %}}" }}



The following arguments are supported:



{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the launch template.
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
            title="Required">Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the launch template.
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
            title="Required">name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the launch template.
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
            title="Required">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the launch template.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}








## GetLaunchTemplate Result

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
        <span class="property-type"><a href="#getlaunchtemplateblockdevicemapping">List&lt;Get<wbr>Launch<wbr>Template<wbr>Block<wbr>Device<wbr>Mapping&gt;</a></span>
    </dt>
    <dd>{{% md %}}Specify volumes to attach to the instance besides the volumes specified by the AMI.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Credit<wbr>Specifications<span class="property-indicator"></span>
        <span class="property-type"><a href="#getlaunchtemplatecreditspecification">List&lt;Get<wbr>Launch<wbr>Template<wbr>Credit<wbr>Specification&gt;</a></span>
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
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Description of the launch template.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Disable<wbr>Api<wbr>Termination<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}If `true`, enables [EC2 Instance
Termination Protection](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/terminating-instances.html#Using_ChangingDisableAPITermination)
{{% /md %}}</dd>

    <dt class="property-"
            title="">Ebs<wbr>Optimized<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}If `true`, the launched EC2 instance will be EBS-optimized.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Elastic<wbr>Gpu<wbr>Specifications<span class="property-indicator"></span>
        <span class="property-type"><a href="#getlaunchtemplateelasticgpuspecification">List&lt;Get<wbr>Launch<wbr>Template<wbr>Elastic<wbr>Gpu<wbr>Specification&gt;</a></span>
    </dt>
    <dd>{{% md %}}The elastic GPU to attach to the instance. See Elastic GPU
below for more details.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Iam<wbr>Instance<wbr>Profiles<span class="property-indicator"></span>
        <span class="property-type"><a href="#getlaunchtemplateiaminstanceprofile">List&lt;Get<wbr>Launch<wbr>Template<wbr>Iam<wbr>Instance<wbr>Profile&gt;</a></span>
    </dt>
    <dd>{{% md %}}The IAM Instance Profile to launch the instance with. See Instance Profile
below for more details.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}id is the provider-assigned unique ID for this managed resource.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Image<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The AMI from which to launch the instance.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Instance<wbr>Initiated<wbr>Shutdown<wbr>Behavior<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Shutdown behavior for the instance. Can be `stop` or `terminate`.
(Default: `stop`).
{{% /md %}}</dd>

    <dt class="property-"
            title="">Instance<wbr>Market<wbr>Options<span class="property-indicator"></span>
        <span class="property-type"><a href="#getlaunchtemplateinstancemarketoption">List&lt;Get<wbr>Launch<wbr>Template<wbr>Instance<wbr>Market<wbr>Option&gt;</a></span>
    </dt>
    <dd>{{% md %}}The market (purchasing) option for the instance.
below for details.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Instance<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type of the instance.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Kernel<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The kernel ID.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Key<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
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
            title="">Monitorings<span class="property-indicator"></span>
        <span class="property-type"><a href="#getlaunchtemplatemonitoring">List&lt;Get<wbr>Launch<wbr>Template<wbr>Monitoring&gt;</a></span>
    </dt>
    <dd>{{% md %}}The monitoring option for the instance.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">Network<wbr>Interfaces<span class="property-indicator"></span>
        <span class="property-type"><a href="#getlaunchtemplatenetworkinterface">List&lt;Get<wbr>Launch<wbr>Template<wbr>Network<wbr>Interface&gt;</a></span>
    </dt>
    <dd>{{% md %}}Customize network interfaces to be attached at instance boot time. See Network
Interfaces below for more details.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Placements<span class="property-indicator"></span>
        <span class="property-type"><a href="#getlaunchtemplateplacement">List&lt;Get<wbr>Launch<wbr>Template<wbr>Placement&gt;</a></span>
    </dt>
    <dd>{{% md %}}The placement of the instance.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Ram<wbr>Disk<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the RAM disk.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Security<wbr>Group<wbr>Names<span class="property-indicator"></span>
        <span class="property-type">List<string></span>
    </dt>
    <dd>{{% md %}}A list of security group names to associate with. If you are creating Instances in a VPC, use
`vpc_security_group_ids` instead.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Tag<wbr>Specifications<span class="property-indicator"></span>
        <span class="property-type"><a href="#getlaunchtemplatetagspecification">List&lt;Get<wbr>Launch<wbr>Template<wbr>Tag<wbr>Specification&gt;</a></span>
    </dt>
    <dd>{{% md %}}The tags to apply to the resources during launch.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object></span>
    </dt>
    <dd>{{% md %}}(Optional) A mapping of tags to assign to the launch template.
{{% /md %}}</dd>

    <dt class="property-"
            title="">User<wbr>Data<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Base64-encoded user data to provide when launching the instance.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Vpc<wbr>Security<wbr>Group<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">List<string></span>
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
        <span class="property-type"><a href="#getlaunchtemplateblockdevicemapping">[]Get<wbr>Launch<wbr>Template<wbr>Block<wbr>Device<wbr>Mapping</a></span>
    </dt>
    <dd>{{% md %}}Specify volumes to attach to the instance besides the volumes specified by the AMI.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Credit<wbr>Specifications<span class="property-indicator"></span>
        <span class="property-type"><a href="#getlaunchtemplatecreditspecification">[]Get<wbr>Launch<wbr>Template<wbr>Credit<wbr>Specification</a></span>
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
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Description of the launch template.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Disable<wbr>Api<wbr>Termination<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}If `true`, enables [EC2 Instance
Termination Protection](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/terminating-instances.html#Using_ChangingDisableAPITermination)
{{% /md %}}</dd>

    <dt class="property-"
            title="">Ebs<wbr>Optimized<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}If `true`, the launched EC2 instance will be EBS-optimized.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Elastic<wbr>Gpu<wbr>Specifications<span class="property-indicator"></span>
        <span class="property-type"><a href="#getlaunchtemplateelasticgpuspecification">[]Get<wbr>Launch<wbr>Template<wbr>Elastic<wbr>Gpu<wbr>Specification</a></span>
    </dt>
    <dd>{{% md %}}The elastic GPU to attach to the instance. See Elastic GPU
below for more details.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Iam<wbr>Instance<wbr>Profiles<span class="property-indicator"></span>
        <span class="property-type"><a href="#getlaunchtemplateiaminstanceprofile">[]Get<wbr>Launch<wbr>Template<wbr>Iam<wbr>Instance<wbr>Profile</a></span>
    </dt>
    <dd>{{% md %}}The IAM Instance Profile to launch the instance with. See Instance Profile
below for more details.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}id is the provider-assigned unique ID for this managed resource.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Image<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The AMI from which to launch the instance.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Instance<wbr>Initiated<wbr>Shutdown<wbr>Behavior<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Shutdown behavior for the instance. Can be `stop` or `terminate`.
(Default: `stop`).
{{% /md %}}</dd>

    <dt class="property-"
            title="">Instance<wbr>Market<wbr>Options<span class="property-indicator"></span>
        <span class="property-type"><a href="#getlaunchtemplateinstancemarketoption">[]Get<wbr>Launch<wbr>Template<wbr>Instance<wbr>Market<wbr>Option</a></span>
    </dt>
    <dd>{{% md %}}The market (purchasing) option for the instance.
below for details.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Instance<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type of the instance.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Kernel<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The kernel ID.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Key<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
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
            title="">Monitorings<span class="property-indicator"></span>
        <span class="property-type"><a href="#getlaunchtemplatemonitoring">[]Get<wbr>Launch<wbr>Template<wbr>Monitoring</a></span>
    </dt>
    <dd>{{% md %}}The monitoring option for the instance.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">Network<wbr>Interfaces<span class="property-indicator"></span>
        <span class="property-type"><a href="#getlaunchtemplatenetworkinterface">[]Get<wbr>Launch<wbr>Template<wbr>Network<wbr>Interface</a></span>
    </dt>
    <dd>{{% md %}}Customize network interfaces to be attached at instance boot time. See Network
Interfaces below for more details.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Placements<span class="property-indicator"></span>
        <span class="property-type"><a href="#getlaunchtemplateplacement">[]Get<wbr>Launch<wbr>Template<wbr>Placement</a></span>
    </dt>
    <dd>{{% md %}}The placement of the instance.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Ram<wbr>Disk<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
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
        <span class="property-type"><a href="#getlaunchtemplatetagspecification">[]Get<wbr>Launch<wbr>Template<wbr>Tag<wbr>Specification</a></span>
    </dt>
    <dd>{{% md %}}The tags to apply to the resources during launch.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}(Optional) A mapping of tags to assign to the launch template.
{{% /md %}}</dd>

    <dt class="property-"
            title="">User<wbr>Data<span class="property-indicator"></span>
        <span class="property-type">string</span>
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
        <span class="property-type"><a href="#getlaunchtemplateblockdevicemapping">Get<wbr>Launch<wbr>Template<wbr>Block<wbr>Device<wbr>Mapping[]</a></span>
    </dt>
    <dd>{{% md %}}Specify volumes to attach to the instance besides the volumes specified by the AMI.
{{% /md %}}</dd>

    <dt class="property-"
            title="">credit<wbr>Specifications<span class="property-indicator"></span>
        <span class="property-type"><a href="#getlaunchtemplatecreditspecification">Get<wbr>Launch<wbr>Template<wbr>Credit<wbr>Specification[]</a></span>
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
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Description of the launch template.
{{% /md %}}</dd>

    <dt class="property-"
            title="">disable<wbr>Api<wbr>Termination<span class="property-indicator"></span>
        <span class="property-type">boolean</span>
    </dt>
    <dd>{{% md %}}If `true`, enables [EC2 Instance
Termination Protection](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/terminating-instances.html#Using_ChangingDisableAPITermination)
{{% /md %}}</dd>

    <dt class="property-"
            title="">ebs<wbr>Optimized<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}If `true`, the launched EC2 instance will be EBS-optimized.
{{% /md %}}</dd>

    <dt class="property-"
            title="">elastic<wbr>Gpu<wbr>Specifications<span class="property-indicator"></span>
        <span class="property-type"><a href="#getlaunchtemplateelasticgpuspecification">Get<wbr>Launch<wbr>Template<wbr>Elastic<wbr>Gpu<wbr>Specification[]</a></span>
    </dt>
    <dd>{{% md %}}The elastic GPU to attach to the instance. See Elastic GPU
below for more details.
{{% /md %}}</dd>

    <dt class="property-"
            title="">iam<wbr>Instance<wbr>Profiles<span class="property-indicator"></span>
        <span class="property-type"><a href="#getlaunchtemplateiaminstanceprofile">Get<wbr>Launch<wbr>Template<wbr>Iam<wbr>Instance<wbr>Profile[]</a></span>
    </dt>
    <dd>{{% md %}}The IAM Instance Profile to launch the instance with. See Instance Profile
below for more details.
{{% /md %}}</dd>

    <dt class="property-"
            title="">id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}id is the provider-assigned unique ID for this managed resource.
{{% /md %}}</dd>

    <dt class="property-"
            title="">image<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The AMI from which to launch the instance.
{{% /md %}}</dd>

    <dt class="property-"
            title="">instance<wbr>Initiated<wbr>Shutdown<wbr>Behavior<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Shutdown behavior for the instance. Can be `stop` or `terminate`.
(Default: `stop`).
{{% /md %}}</dd>

    <dt class="property-"
            title="">instance<wbr>Market<wbr>Options<span class="property-indicator"></span>
        <span class="property-type"><a href="#getlaunchtemplateinstancemarketoption">Get<wbr>Launch<wbr>Template<wbr>Instance<wbr>Market<wbr>Option[]</a></span>
    </dt>
    <dd>{{% md %}}The market (purchasing) option for the instance.
below for details.
{{% /md %}}</dd>

    <dt class="property-"
            title="">instance<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type of the instance.
{{% /md %}}</dd>

    <dt class="property-"
            title="">kernel<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The kernel ID.
{{% /md %}}</dd>

    <dt class="property-"
            title="">key<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
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
            title="">monitorings<span class="property-indicator"></span>
        <span class="property-type"><a href="#getlaunchtemplatemonitoring">Get<wbr>Launch<wbr>Template<wbr>Monitoring[]</a></span>
    </dt>
    <dd>{{% md %}}The monitoring option for the instance.
{{% /md %}}</dd>

    <dt class="property-"
            title="">name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">network<wbr>Interfaces<span class="property-indicator"></span>
        <span class="property-type"><a href="#getlaunchtemplatenetworkinterface">Get<wbr>Launch<wbr>Template<wbr>Network<wbr>Interface[]</a></span>
    </dt>
    <dd>{{% md %}}Customize network interfaces to be attached at instance boot time. See Network
Interfaces below for more details.
{{% /md %}}</dd>

    <dt class="property-"
            title="">placements<span class="property-indicator"></span>
        <span class="property-type"><a href="#getlaunchtemplateplacement">Get<wbr>Launch<wbr>Template<wbr>Placement[]</a></span>
    </dt>
    <dd>{{% md %}}The placement of the instance.
{{% /md %}}</dd>

    <dt class="property-"
            title="">ram<wbr>Disk<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the RAM disk.
{{% /md %}}</dd>

    <dt class="property-"
            title="">security<wbr>Group<wbr>Names<span class="property-indicator"></span>
        <span class="property-type">string[]</span>
    </dt>
    <dd>{{% md %}}A list of security group names to associate with. If you are creating Instances in a VPC, use
`vpc_security_group_ids` instead.
{{% /md %}}</dd>

    <dt class="property-"
            title="">tag<wbr>Specifications<span class="property-indicator"></span>
        <span class="property-type"><a href="#getlaunchtemplatetagspecification">Get<wbr>Launch<wbr>Template<wbr>Tag<wbr>Specification[]</a></span>
    </dt>
    <dd>{{% md %}}The tags to apply to the resources during launch.
{{% /md %}}</dd>

    <dt class="property-"
            title="">tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}</span>
    </dt>
    <dd>{{% md %}}(Optional) A mapping of tags to assign to the launch template.
{{% /md %}}</dd>

    <dt class="property-"
            title="">user<wbr>Data<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Base64-encoded user data to provide when launching the instance.
{{% /md %}}</dd>

    <dt class="property-"
            title="">vpc<wbr>Security<wbr>Group<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">string[]</span>
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
        <span class="property-type"><a href="#getlaunchtemplateblockdevicemapping">List[Get<wbr>Launch<wbr>Template<wbr>Block<wbr>Device<wbr>Mapping]</a></span>
    </dt>
    <dd>{{% md %}}Specify volumes to attach to the instance besides the volumes specified by the AMI.
{{% /md %}}</dd>

    <dt class="property-"
            title="">credit_<wbr>specifications<span class="property-indicator"></span>
        <span class="property-type"><a href="#getlaunchtemplatecreditspecification">List[Get<wbr>Launch<wbr>Template<wbr>Credit<wbr>Specification]</a></span>
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
        <span class="property-type"><a href="#getlaunchtemplateelasticgpuspecification">List[Get<wbr>Launch<wbr>Template<wbr>Elastic<wbr>Gpu<wbr>Specification]</a></span>
    </dt>
    <dd>{{% md %}}The elastic GPU to attach to the instance. See Elastic GPU
below for more details.
{{% /md %}}</dd>

    <dt class="property-"
            title="">iam_<wbr>instance_<wbr>profiles<span class="property-indicator"></span>
        <span class="property-type"><a href="#getlaunchtemplateiaminstanceprofile">List[Get<wbr>Launch<wbr>Template<wbr>Iam<wbr>Instance<wbr>Profile]</a></span>
    </dt>
    <dd>{{% md %}}The IAM Instance Profile to launch the instance with. See Instance Profile
below for more details.
{{% /md %}}</dd>

    <dt class="property-"
            title="">id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}id is the provider-assigned unique ID for this managed resource.
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
        <span class="property-type"><a href="#getlaunchtemplateinstancemarketoption">List[Get<wbr>Launch<wbr>Template<wbr>Instance<wbr>Market<wbr>Option]</a></span>
    </dt>
    <dd>{{% md %}}The market (purchasing) option for the instance.
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
            title="">monitorings<span class="property-indicator"></span>
        <span class="property-type"><a href="#getlaunchtemplatemonitoring">List[Get<wbr>Launch<wbr>Template<wbr>Monitoring]</a></span>
    </dt>
    <dd>{{% md %}}The monitoring option for the instance.
{{% /md %}}</dd>

    <dt class="property-"
            title="">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">network_<wbr>interfaces<span class="property-indicator"></span>
        <span class="property-type"><a href="#getlaunchtemplatenetworkinterface">List[Get<wbr>Launch<wbr>Template<wbr>Network<wbr>Interface]</a></span>
    </dt>
    <dd>{{% md %}}Customize network interfaces to be attached at instance boot time. See Network
Interfaces below for more details.
{{% /md %}}</dd>

    <dt class="property-"
            title="">placements<span class="property-indicator"></span>
        <span class="property-type"><a href="#getlaunchtemplateplacement">List[Get<wbr>Launch<wbr>Template<wbr>Placement]</a></span>
    </dt>
    <dd>{{% md %}}The placement of the instance.
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
        <span class="property-type"><a href="#getlaunchtemplatetagspecification">List[Get<wbr>Launch<wbr>Template<wbr>Tag<wbr>Specification]</a></span>
    </dt>
    <dd>{{% md %}}The tags to apply to the resources during launch.
{{% /md %}}</dd>

    <dt class="property-"
            title="">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}(Optional) A mapping of tags to assign to the launch template.
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








## Supporting Types

#### GetLaunchTemplateBlockDeviceMapping
{{% lang nodejs %}}
> See the   <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#GetLaunchTemplateBlockDeviceMapping">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the   <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ec2?tab=doc#GetLaunchTemplateBlockDeviceMapping">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the   <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ec2.GetLaunchTemplateBlockDeviceMapping.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Device<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Ebs<span class="property-indicator"></span>
        <span class="property-type"><a href="#getlaunchtemplateblockdevicemappingeb">List&lt;Get<wbr>Launch<wbr>Template<wbr>Block<wbr>Device<wbr>Mapping<wbr>Eb<wbr>Args&gt;</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">No<wbr>Device<span class="property-indicator"></span>
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
            title="Required">Ebs<span class="property-indicator"></span>
        <span class="property-type"><a href="#getlaunchtemplateblockdevicemappingeb">[]Get<wbr>Launch<wbr>Template<wbr>Block<wbr>Device<wbr>Mapping<wbr>Eb</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">No<wbr>Device<span class="property-indicator"></span>
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
            title="Required">ebs<span class="property-indicator"></span>
        <span class="property-type"><a href="#getlaunchtemplateblockdevicemappingeb">Get<wbr>Launch<wbr>Template<wbr>Block<wbr>Device<wbr>Mapping<wbr>Eb[]</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">no<wbr>Device<span class="property-indicator"></span>
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
            title="Required">ebs<span class="property-indicator"></span>
        <span class="property-type"><a href="#getlaunchtemplateblockdevicemappingeb">List[Get<wbr>Launch<wbr>Template<wbr>Block<wbr>Device<wbr>Mapping<wbr>Eb]</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">no<wbr>Device<span class="property-indicator"></span>
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





#### GetLaunchTemplateBlockDeviceMappingEb
{{% lang nodejs %}}
> See the   <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#GetLaunchTemplateBlockDeviceMappingEb">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the   <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ec2?tab=doc#GetLaunchTemplateBlockDeviceMappingEb">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the   <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ec2.GetLaunchTemplateBlockDeviceMappingEb.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Delete<wbr>On<wbr>Termination<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Encrypted<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Iops<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Kms<wbr>Key<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Snapshot<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Volume<wbr>Size<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Volume<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Delete<wbr>On<wbr>Termination<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Encrypted<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Iops<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Kms<wbr>Key<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Snapshot<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Volume<wbr>Size<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Volume<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">delete<wbr>On<wbr>Termination<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">encrypted<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">iops<span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">kms<wbr>Key<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">snapshot<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">volume<wbr>Size<span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">volume<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">delete<wbr>On<wbr>Termination<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">encrypted<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">iops<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">kms_<wbr>key_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">snapshot_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">volume_<wbr>size<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">volume<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### GetLaunchTemplateCreditSpecification
{{% lang nodejs %}}
> See the   <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#GetLaunchTemplateCreditSpecification">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the   <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ec2?tab=doc#GetLaunchTemplateCreditSpecification">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the   <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ec2.GetLaunchTemplateCreditSpecification.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Cpu<wbr>Credits<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Cpu<wbr>Credits<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">cpu<wbr>Credits<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">cpu<wbr>Credits<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### GetLaunchTemplateElasticGpuSpecification
{{% lang nodejs %}}
> See the   <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#GetLaunchTemplateElasticGpuSpecification">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the   <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ec2?tab=doc#GetLaunchTemplateElasticGpuSpecification">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the   <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ec2.GetLaunchTemplateElasticGpuSpecification.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### GetLaunchTemplateIamInstanceProfile
{{% lang nodejs %}}
> See the   <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#GetLaunchTemplateIamInstanceProfile">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the   <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ec2?tab=doc#GetLaunchTemplateIamInstanceProfile">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the   <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ec2.GetLaunchTemplateIamInstanceProfile.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of the launch template.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the launch template.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of the launch template.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the launch template.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of the launch template.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the launch template.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of the launch template.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the launch template.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### GetLaunchTemplateInstanceMarketOption
{{% lang nodejs %}}
> See the   <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#GetLaunchTemplateInstanceMarketOption">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the   <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ec2?tab=doc#GetLaunchTemplateInstanceMarketOption">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the   <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ec2.GetLaunchTemplateInstanceMarketOption.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Market<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Spot<wbr>Options<span class="property-indicator"></span>
        <span class="property-type"><a href="#getlaunchtemplateinstancemarketoptionspotoption">List&lt;Get<wbr>Launch<wbr>Template<wbr>Instance<wbr>Market<wbr>Option<wbr>Spot<wbr>Option<wbr>Args&gt;</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Market<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Spot<wbr>Options<span class="property-indicator"></span>
        <span class="property-type"><a href="#getlaunchtemplateinstancemarketoptionspotoption">[]Get<wbr>Launch<wbr>Template<wbr>Instance<wbr>Market<wbr>Option<wbr>Spot<wbr>Option</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">market<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">spot<wbr>Options<span class="property-indicator"></span>
        <span class="property-type"><a href="#getlaunchtemplateinstancemarketoptionspotoption">Get<wbr>Launch<wbr>Template<wbr>Instance<wbr>Market<wbr>Option<wbr>Spot<wbr>Option[]</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">market<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">spot_<wbr>options<span class="property-indicator"></span>
        <span class="property-type"><a href="#getlaunchtemplateinstancemarketoptionspotoption">List[Get<wbr>Launch<wbr>Template<wbr>Instance<wbr>Market<wbr>Option<wbr>Spot<wbr>Option]</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### GetLaunchTemplateInstanceMarketOptionSpotOption
{{% lang nodejs %}}
> See the   <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#GetLaunchTemplateInstanceMarketOptionSpotOption">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the   <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ec2?tab=doc#GetLaunchTemplateInstanceMarketOptionSpotOption">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the   <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ec2.GetLaunchTemplateInstanceMarketOptionSpotOption.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Block<wbr>Duration<wbr>Minutes<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Instance<wbr>Interruption<wbr>Behavior<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Max<wbr>Price<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Spot<wbr>Instance<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Valid<wbr>Until<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Block<wbr>Duration<wbr>Minutes<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Instance<wbr>Interruption<wbr>Behavior<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Max<wbr>Price<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Spot<wbr>Instance<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Valid<wbr>Until<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">block<wbr>Duration<wbr>Minutes<span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">instance<wbr>Interruption<wbr>Behavior<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">max<wbr>Price<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">spot<wbr>Instance<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">valid<wbr>Until<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">block_<wbr>duration_<wbr>minutes<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">instance<wbr>Interruption<wbr>Behavior<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">max<wbr>Price<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">spot<wbr>Instance<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">valid_<wbr>until<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### GetLaunchTemplateMonitoring
{{% lang nodejs %}}
> See the   <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#GetLaunchTemplateMonitoring">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the   <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ec2?tab=doc#GetLaunchTemplateMonitoring">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the   <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ec2.GetLaunchTemplateMonitoring.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Enabled<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Enabled<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">enabled<span class="property-indicator"></span>
        <span class="property-type">boolean</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">enabled<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### GetLaunchTemplateNetworkInterface
{{% lang nodejs %}}
> See the   <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#GetLaunchTemplateNetworkInterface">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the   <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ec2?tab=doc#GetLaunchTemplateNetworkInterface">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the   <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ec2.GetLaunchTemplateNetworkInterface.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Associate<wbr>Public<wbr>Ip<wbr>Address<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Delete<wbr>On<wbr>Termination<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Description<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Description of the launch template.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Device<wbr>Index<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Ipv4Address<wbr>Count<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Ipv4Addresses<span class="property-indicator"></span>
        <span class="property-type">List<string></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Ipv6Address<wbr>Count<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Ipv6Addresses<span class="property-indicator"></span>
        <span class="property-type">List<string></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Network<wbr>Interface<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Private<wbr>Ip<wbr>Address<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Security<wbr>Groups<span class="property-indicator"></span>
        <span class="property-type">List<string></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Subnet<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Associate<wbr>Public<wbr>Ip<wbr>Address<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Delete<wbr>On<wbr>Termination<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Description<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Description of the launch template.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Device<wbr>Index<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Ipv4Address<wbr>Count<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Ipv4Addresses<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Ipv6Address<wbr>Count<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Ipv6Addresses<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Network<wbr>Interface<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Private<wbr>Ip<wbr>Address<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Security<wbr>Groups<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Subnet<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">associate<wbr>Public<wbr>Ip<wbr>Address<span class="property-indicator"></span>
        <span class="property-type">boolean</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">delete<wbr>On<wbr>Termination<span class="property-indicator"></span>
        <span class="property-type">boolean</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">description<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Description of the launch template.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">device<wbr>Index<span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">ipv4Address<wbr>Count<span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">ipv4Addresses<span class="property-indicator"></span>
        <span class="property-type">string[]</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">ipv6Address<wbr>Count<span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">ipv6Addresses<span class="property-indicator"></span>
        <span class="property-type">string[]</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">network<wbr>Interface<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">private<wbr>Ip<wbr>Address<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">security<wbr>Groups<span class="property-indicator"></span>
        <span class="property-type">string[]</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">subnet<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">associate_<wbr>public_<wbr>ip_<wbr>address<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">delete<wbr>On<wbr>Termination<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">description<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Description of the launch template.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">device_<wbr>index<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">ipv4Address<wbr>Count<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">ipv4Addresses<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">ipv6_<wbr>address_<wbr>count<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">ipv6_<wbr>addresses<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">network_<wbr>interface_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">private_<wbr>ip_<wbr>address<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">security_<wbr>groups<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">subnet_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### GetLaunchTemplatePlacement
{{% lang nodejs %}}
> See the   <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#GetLaunchTemplatePlacement">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the   <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ec2?tab=doc#GetLaunchTemplatePlacement">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the   <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ec2.GetLaunchTemplatePlacement.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Affinity<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Availability<wbr>Zone<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Group<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Host<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Spread<wbr>Domain<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Tenancy<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Affinity<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Availability<wbr>Zone<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Group<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Host<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Spread<wbr>Domain<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Tenancy<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">affinity<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">availability<wbr>Zone<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">group<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">host<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">spread<wbr>Domain<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">tenancy<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">affinity<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">availability_<wbr>zone<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">group_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">host_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">spread<wbr>Domain<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">tenancy<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### GetLaunchTemplateTagSpecification
{{% lang nodejs %}}
> See the   <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#GetLaunchTemplateTagSpecification">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the   <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ec2?tab=doc#GetLaunchTemplateTagSpecification">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the   <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ec2.GetLaunchTemplateTagSpecification.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Resource<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object></span>
    </dt>
    <dd>{{% md %}}(Optional) A mapping of tags to assign to the launch template.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Resource<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}(Optional) A mapping of tags to assign to the launch template.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">resource<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}</span>
    </dt>
    <dd>{{% md %}}(Optional) A mapping of tags to assign to the launch template.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">resource_<wbr>type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}(Optional) A mapping of tags to assign to the launch template.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}








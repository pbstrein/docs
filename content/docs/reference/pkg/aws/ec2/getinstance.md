
---
title: "GetInstance"
block_external_search_index: true
---

Use this data source to get the ID of an Amazon EC2 Instance for use in other
resources.

## Example Usage

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const foo = aws.ec2.getInstance({
    filters: [
        {
            name: "image-id",
            values: ["ami-xxxxxxxx"],
        },
        {
            name: "tag:Name",
            values: ["instance-name-tag"],
        },
    ],
    instanceId: "i-instanceid",
});
```

> This content is derived from https://github.com/terraform-providers/terraform-provider-aws/blob/master/website/docs/d/instance.html.markdown.





## Using GetInstance

{{< chooser language "typescript,python,go,csharp" >}}

{{% choosable language typescript %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">function </span>getInstance<span class="p">(</span><span class="nx">args</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/ec2/#GetInstanceArgs">GetInstanceArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#InvokeOptions">pulumi.InvokeOptions</a></span><span class="p">): Promise&lt;<span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/ec2/#GetInstanceResult">GetInstanceResult</a></span>></span></code></pre></div>
{{% /choosable %}}" }}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">function </span> get_instance(</span>filters=None<span class="p">, </span>get_password_data=None<span class="p">, </span>get_user_data=None<span class="p">, </span>instance_id=None<span class="p">, </span>instance_tags=None<span class="p">, </span>tags=None<span class="p">, </span>opts=None<span class="p">)</span></code></pre></div>
{{% /choosable %}}" }}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>LookupInstance<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">args</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ec2?tab=doc#LookupInstanceArgs">LookupInstanceArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#InvokeOption">pulumi.InvokeOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ec2?tab=doc#LookupInstanceResult">LookupInstanceResult</a></span>, error)</span></code></pre></div>
{{% /choosable %}}" }}

{{% choosable language csharp %}}
<div class="highlight">
<pre class="chroma">
<code class="language-csharp" data-lang="csharp"><span class="k">public static class </span><span class="nx">GetInstance </span><span class="p">{</span>
    <span class="k">public static </span>Task&lt;<span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ec2.GetInstanceResult.html">GetInstanceResult</a></span>> <span class="p">InvokeAsync(</span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ec2.GetInstanceArgs.html">GetInstanceArgs</a></span> <span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/InvokeOptions.html">InvokeOptions</a></span>? <span class="nx">opts = null<span class="p">)</span>
<span class="p">}</span></code></pre>
</div>
{{% /choosable %}}" }}



The following arguments are supported:



{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Filters<span class="property-indicator"></span>
        <span class="property-type"><a href="#getinstancefilter">List&lt;Get<wbr>Instance<wbr>Filter<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}One or more name/value pairs to use as filters. There are
several valid keys, for a full reference, check out
[describe-instances in the AWS CLI reference][1].
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Get<wbr>Password<wbr>Data<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}If true, wait for password data to become available and retrieve it. Useful for getting the administrator password for instances running Microsoft Windows. The password data is exported to the `password_data` attribute. See [GetPasswordData](https://docs.aws.amazon.com/AWSEC2/latest/APIReference/API_GetPasswordData.html) for more information.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Get<wbr>User<wbr>Data<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Retrieve Base64 encoded User Data contents into the `user_data_base64` attribute. A SHA-1 hash of the User Data contents will always be present in the `user_data` attribute. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Instance<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Specify the exact Instance ID with which to populate the data source.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Instance<wbr>Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags, each pair of which must
exactly match a pair on the desired Instance.
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

    <dt class="property-optional"
            title="Optional">Filters<span class="property-indicator"></span>
        <span class="property-type"><a href="#getinstancefilter">[]Get<wbr>Instance<wbr>Filter</a></span>
    </dt>
    <dd>{{% md %}}One or more name/value pairs to use as filters. There are
several valid keys, for a full reference, check out
[describe-instances in the AWS CLI reference][1].
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Get<wbr>Password<wbr>Data<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}If true, wait for password data to become available and retrieve it. Useful for getting the administrator password for instances running Microsoft Windows. The password data is exported to the `password_data` attribute. See [GetPasswordData](https://docs.aws.amazon.com/AWSEC2/latest/APIReference/API_GetPasswordData.html) for more information.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Get<wbr>User<wbr>Data<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Retrieve Base64 encoded User Data contents into the `user_data_base64` attribute. A SHA-1 hash of the User Data contents will always be present in the `user_data` attribute. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Instance<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Specify the exact Instance ID with which to populate the data source.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Instance<wbr>Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}A mapping of tags, each pair of which must
exactly match a pair on the desired Instance.
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

    <dt class="property-optional"
            title="Optional">filters<span class="property-indicator"></span>
        <span class="property-type"><a href="#getinstancefilter">Get<wbr>Instance<wbr>Filter[]?</a></span>
    </dt>
    <dd>{{% md %}}One or more name/value pairs to use as filters. There are
several valid keys, for a full reference, check out
[describe-instances in the AWS CLI reference][1].
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">get<wbr>Password<wbr>Data<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}If true, wait for password data to become available and retrieve it. Useful for getting the administrator password for instances running Microsoft Windows. The password data is exported to the `password_data` attribute. See [GetPasswordData](https://docs.aws.amazon.com/AWSEC2/latest/APIReference/API_GetPasswordData.html) for more information.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">get<wbr>User<wbr>Data<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Retrieve Base64 encoded User Data contents into the `user_data_base64` attribute. A SHA-1 hash of the User Data contents will always be present in the `user_data` attribute. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">instance<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Specify the exact Instance ID with which to populate the data source.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">instance<wbr>Tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags, each pair of which must
exactly match a pair on the desired Instance.
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

    <dt class="property-optional"
            title="Optional">filters<span class="property-indicator"></span>
        <span class="property-type"><a href="#getinstancefilter">List[Get<wbr>Instance<wbr>Filter]</a></span>
    </dt>
    <dd>{{% md %}}One or more name/value pairs to use as filters. There are
several valid keys, for a full reference, check out
[describe-instances in the AWS CLI reference][1].
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">get_<wbr>password_<wbr>data<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}If true, wait for password data to become available and retrieve it. Useful for getting the administrator password for instances running Microsoft Windows. The password data is exported to the `password_data` attribute. See [GetPasswordData](https://docs.aws.amazon.com/AWSEC2/latest/APIReference/API_GetPasswordData.html) for more information.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">get_<wbr>user_<wbr>data<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Retrieve Base64 encoded User Data contents into the `user_data_base64` attribute. A SHA-1 hash of the User Data contents will always be present in the `user_data` attribute. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">instance_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Specify the exact Instance ID with which to populate the data source.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">instance_<wbr>tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}A mapping of tags, each pair of which must
exactly match a pair on the desired Instance.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}








## GetInstance Result

The following output properties are available:




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Ami<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the AMI used to launch the instance.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of the instance.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Associate<wbr>Public<wbr>Ip<wbr>Address<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Whether or not the Instance is associated with a public IP address or not (Boolean).
{{% /md %}}</dd>

    <dt class="property-"
            title="">Availability<wbr>Zone<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The availability zone of the Instance.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Credit<wbr>Specifications<span class="property-indicator"></span>
        <span class="property-type"><a href="#getinstancecreditspecification">List&lt;Get<wbr>Instance<wbr>Credit<wbr>Specification&gt;</a></span>
    </dt>
    <dd>{{% md %}}The credit specification of the Instance.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Disable<wbr>Api<wbr>Termination<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">Ebs<wbr>Block<wbr>Devices<span class="property-indicator"></span>
        <span class="property-type"><a href="#getinstanceebsblockdevice">List&lt;Get<wbr>Instance<wbr>Ebs<wbr>Block<wbr>Device&gt;</a></span>
    </dt>
    <dd>{{% md %}}The EBS block device mappings of the Instance.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Ebs<wbr>Optimized<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Whether the Instance is EBS optimized or not (Boolean).
{{% /md %}}</dd>

    <dt class="property-"
            title="">Ephemeral<wbr>Block<wbr>Devices<span class="property-indicator"></span>
        <span class="property-type"><a href="#getinstanceephemeralblockdevice">List&lt;Get<wbr>Instance<wbr>Ephemeral<wbr>Block<wbr>Device&gt;</a></span>
    </dt>
    <dd>{{% md %}}The ephemeral block device mappings of the Instance.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Filters<span class="property-indicator"></span>
        <span class="property-type"><a href="#getinstancefilter">List&lt;Get<wbr>Instance<wbr>Filter&gt;?</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">Get<wbr>Password<wbr>Data<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">Get<wbr>User<wbr>Data<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">Host<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Id of the dedicated host the instance will be assigned to.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Iam<wbr>Instance<wbr>Profile<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the instance profile associated with the Instance.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}id is the provider-assigned unique ID for this managed resource.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Instance<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">Instance<wbr>State<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The state of the instance. One of: `pending`, `running`, `shutting-down`, `terminated`, `stopping`, `stopped`. See [Instance Lifecycle](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ec2-instance-lifecycle.html) for more information.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Instance<wbr>Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">Instance<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type of the Instance.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Key<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The key name of the Instance.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Monitoring<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Whether detailed monitoring is enabled or disabled for the Instance (Boolean).
{{% /md %}}</dd>

    <dt class="property-"
            title="">Network<wbr>Interface<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the network interface that was created with the Instance.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Password<wbr>Data<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Base-64 encoded encrypted password data for the instance.
Useful for getting the administrator password for instances running Microsoft Windows.
This attribute is only exported if `get_password_data` is true.
See [GetPasswordData](https://docs.aws.amazon.com/AWSEC2/latest/APIReference/API_GetPasswordData.html) for more information.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Placement<wbr>Group<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The placement group of the Instance.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Private<wbr>Dns<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The private DNS name assigned to the Instance. Can only be
used inside the Amazon EC2, and only available if you&#39;ve enabled DNS hostnames
for your VPC.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Private<wbr>Ip<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The private IP address assigned to the Instance.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Public<wbr>Dns<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The public DNS name assigned to the Instance. For EC2-VPC, this
is only available if you&#39;ve enabled DNS hostnames for your VPC.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Public<wbr>Ip<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The public IP address assigned to the Instance, if applicable. **NOTE**: If you are using an [`aws.ec2.Eip`](https://www.terraform.io/docs/providers/aws/r/eip.html) with your instance, you should refer to the EIP&#39;s address directly and not use `public_ip`, as this field will change after the EIP is attached.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Root<wbr>Block<wbr>Devices<span class="property-indicator"></span>
        <span class="property-type"><a href="#getinstancerootblockdevice">List&lt;Get<wbr>Instance<wbr>Root<wbr>Block<wbr>Device&gt;</a></span>
    </dt>
    <dd>{{% md %}}The root block device mappings of the Instance
{{% /md %}}</dd>

    <dt class="property-"
            title="">Security<wbr>Groups<span class="property-indicator"></span>
        <span class="property-type">List<string></span>
    </dt>
    <dd>{{% md %}}The associated security groups.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Source<wbr>Dest<wbr>Check<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Whether the network interface performs source/destination checking (Boolean).
{{% /md %}}</dd>

    <dt class="property-"
            title="">Subnet<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The VPC subnet ID.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object></span>
    </dt>
    <dd>{{% md %}}A mapping of tags assigned to the Instance.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Tenancy<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The tenancy of the instance: `dedicated`, `default`, `host`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">User<wbr>Data<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}SHA-1 hash of User Data supplied to the Instance.
{{% /md %}}</dd>

    <dt class="property-"
            title="">User<wbr>Data<wbr>Base64<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Base64 encoded contents of User Data supplied to the Instance. Valid UTF-8 contents can be decoded with the [`base64decode` function](https://www.terraform.io/docs/configuration/functions/base64decode.html). This attribute is only exported if `get_user_data` is true.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Vpc<wbr>Security<wbr>Group<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">List<string></span>
    </dt>
    <dd>{{% md %}}The associated security groups in a non-default VPC.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Ami<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the AMI used to launch the instance.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of the instance.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Associate<wbr>Public<wbr>Ip<wbr>Address<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Whether or not the Instance is associated with a public IP address or not (Boolean).
{{% /md %}}</dd>

    <dt class="property-"
            title="">Availability<wbr>Zone<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The availability zone of the Instance.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Credit<wbr>Specifications<span class="property-indicator"></span>
        <span class="property-type"><a href="#getinstancecreditspecification">[]Get<wbr>Instance<wbr>Credit<wbr>Specification</a></span>
    </dt>
    <dd>{{% md %}}The credit specification of the Instance.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Disable<wbr>Api<wbr>Termination<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">Ebs<wbr>Block<wbr>Devices<span class="property-indicator"></span>
        <span class="property-type"><a href="#getinstanceebsblockdevice">[]Get<wbr>Instance<wbr>Ebs<wbr>Block<wbr>Device</a></span>
    </dt>
    <dd>{{% md %}}The EBS block device mappings of the Instance.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Ebs<wbr>Optimized<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Whether the Instance is EBS optimized or not (Boolean).
{{% /md %}}</dd>

    <dt class="property-"
            title="">Ephemeral<wbr>Block<wbr>Devices<span class="property-indicator"></span>
        <span class="property-type"><a href="#getinstanceephemeralblockdevice">[]Get<wbr>Instance<wbr>Ephemeral<wbr>Block<wbr>Device</a></span>
    </dt>
    <dd>{{% md %}}The ephemeral block device mappings of the Instance.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Filters<span class="property-indicator"></span>
        <span class="property-type"><a href="#getinstancefilter">[]Get<wbr>Instance<wbr>Filter</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">Get<wbr>Password<wbr>Data<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">Get<wbr>User<wbr>Data<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">Host<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Id of the dedicated host the instance will be assigned to.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Iam<wbr>Instance<wbr>Profile<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the instance profile associated with the Instance.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}id is the provider-assigned unique ID for this managed resource.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Instance<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">Instance<wbr>State<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The state of the instance. One of: `pending`, `running`, `shutting-down`, `terminated`, `stopping`, `stopped`. See [Instance Lifecycle](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ec2-instance-lifecycle.html) for more information.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Instance<wbr>Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">Instance<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type of the Instance.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Key<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The key name of the Instance.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Monitoring<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Whether detailed monitoring is enabled or disabled for the Instance (Boolean).
{{% /md %}}</dd>

    <dt class="property-"
            title="">Network<wbr>Interface<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the network interface that was created with the Instance.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Password<wbr>Data<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Base-64 encoded encrypted password data for the instance.
Useful for getting the administrator password for instances running Microsoft Windows.
This attribute is only exported if `get_password_data` is true.
See [GetPasswordData](https://docs.aws.amazon.com/AWSEC2/latest/APIReference/API_GetPasswordData.html) for more information.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Placement<wbr>Group<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The placement group of the Instance.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Private<wbr>Dns<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The private DNS name assigned to the Instance. Can only be
used inside the Amazon EC2, and only available if you&#39;ve enabled DNS hostnames
for your VPC.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Private<wbr>Ip<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The private IP address assigned to the Instance.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Public<wbr>Dns<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The public DNS name assigned to the Instance. For EC2-VPC, this
is only available if you&#39;ve enabled DNS hostnames for your VPC.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Public<wbr>Ip<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The public IP address assigned to the Instance, if applicable. **NOTE**: If you are using an [`aws.ec2.Eip`](https://www.terraform.io/docs/providers/aws/r/eip.html) with your instance, you should refer to the EIP&#39;s address directly and not use `public_ip`, as this field will change after the EIP is attached.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Root<wbr>Block<wbr>Devices<span class="property-indicator"></span>
        <span class="property-type"><a href="#getinstancerootblockdevice">[]Get<wbr>Instance<wbr>Root<wbr>Block<wbr>Device</a></span>
    </dt>
    <dd>{{% md %}}The root block device mappings of the Instance
{{% /md %}}</dd>

    <dt class="property-"
            title="">Security<wbr>Groups<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}The associated security groups.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Source<wbr>Dest<wbr>Check<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Whether the network interface performs source/destination checking (Boolean).
{{% /md %}}</dd>

    <dt class="property-"
            title="">Subnet<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The VPC subnet ID.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}A mapping of tags assigned to the Instance.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Tenancy<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The tenancy of the instance: `dedicated`, `default`, `host`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">User<wbr>Data<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}SHA-1 hash of User Data supplied to the Instance.
{{% /md %}}</dd>

    <dt class="property-"
            title="">User<wbr>Data<wbr>Base64<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Base64 encoded contents of User Data supplied to the Instance. Valid UTF-8 contents can be decoded with the [`base64decode` function](https://www.terraform.io/docs/configuration/functions/base64decode.html). This attribute is only exported if `get_user_data` is true.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Vpc<wbr>Security<wbr>Group<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}The associated security groups in a non-default VPC.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">ami<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the AMI used to launch the instance.
{{% /md %}}</dd>

    <dt class="property-"
            title="">arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of the instance.
{{% /md %}}</dd>

    <dt class="property-"
            title="">associate<wbr>Public<wbr>Ip<wbr>Address<span class="property-indicator"></span>
        <span class="property-type">boolean</span>
    </dt>
    <dd>{{% md %}}Whether or not the Instance is associated with a public IP address or not (Boolean).
{{% /md %}}</dd>

    <dt class="property-"
            title="">availability<wbr>Zone<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The availability zone of the Instance.
{{% /md %}}</dd>

    <dt class="property-"
            title="">credit<wbr>Specifications<span class="property-indicator"></span>
        <span class="property-type"><a href="#getinstancecreditspecification">Get<wbr>Instance<wbr>Credit<wbr>Specification[]</a></span>
    </dt>
    <dd>{{% md %}}The credit specification of the Instance.
{{% /md %}}</dd>

    <dt class="property-"
            title="">disable<wbr>Api<wbr>Termination<span class="property-indicator"></span>
        <span class="property-type">boolean</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">ebs<wbr>Block<wbr>Devices<span class="property-indicator"></span>
        <span class="property-type"><a href="#getinstanceebsblockdevice">Get<wbr>Instance<wbr>Ebs<wbr>Block<wbr>Device[]</a></span>
    </dt>
    <dd>{{% md %}}The EBS block device mappings of the Instance.
{{% /md %}}</dd>

    <dt class="property-"
            title="">ebs<wbr>Optimized<span class="property-indicator"></span>
        <span class="property-type">boolean</span>
    </dt>
    <dd>{{% md %}}Whether the Instance is EBS optimized or not (Boolean).
{{% /md %}}</dd>

    <dt class="property-"
            title="">ephemeral<wbr>Block<wbr>Devices<span class="property-indicator"></span>
        <span class="property-type"><a href="#getinstanceephemeralblockdevice">Get<wbr>Instance<wbr>Ephemeral<wbr>Block<wbr>Device[]</a></span>
    </dt>
    <dd>{{% md %}}The ephemeral block device mappings of the Instance.
{{% /md %}}</dd>

    <dt class="property-"
            title="">filters<span class="property-indicator"></span>
        <span class="property-type"><a href="#getinstancefilter">Get<wbr>Instance<wbr>Filter[]?</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">get<wbr>Password<wbr>Data<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">get<wbr>User<wbr>Data<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">host<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Id of the dedicated host the instance will be assigned to.
{{% /md %}}</dd>

    <dt class="property-"
            title="">iam<wbr>Instance<wbr>Profile<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the instance profile associated with the Instance.
{{% /md %}}</dd>

    <dt class="property-"
            title="">id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}id is the provider-assigned unique ID for this managed resource.
{{% /md %}}</dd>

    <dt class="property-"
            title="">instance<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">instance<wbr>State<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The state of the instance. One of: `pending`, `running`, `shutting-down`, `terminated`, `stopping`, `stopped`. See [Instance Lifecycle](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ec2-instance-lifecycle.html) for more information.
{{% /md %}}</dd>

    <dt class="property-"
            title="">instance<wbr>Tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">instance<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type of the Instance.
{{% /md %}}</dd>

    <dt class="property-"
            title="">key<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The key name of the Instance.
{{% /md %}}</dd>

    <dt class="property-"
            title="">monitoring<span class="property-indicator"></span>
        <span class="property-type">boolean</span>
    </dt>
    <dd>{{% md %}}Whether detailed monitoring is enabled or disabled for the Instance (Boolean).
{{% /md %}}</dd>

    <dt class="property-"
            title="">network<wbr>Interface<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the network interface that was created with the Instance.
{{% /md %}}</dd>

    <dt class="property-"
            title="">password<wbr>Data<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Base-64 encoded encrypted password data for the instance.
Useful for getting the administrator password for instances running Microsoft Windows.
This attribute is only exported if `get_password_data` is true.
See [GetPasswordData](https://docs.aws.amazon.com/AWSEC2/latest/APIReference/API_GetPasswordData.html) for more information.
{{% /md %}}</dd>

    <dt class="property-"
            title="">placement<wbr>Group<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The placement group of the Instance.
{{% /md %}}</dd>

    <dt class="property-"
            title="">private<wbr>Dns<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The private DNS name assigned to the Instance. Can only be
used inside the Amazon EC2, and only available if you&#39;ve enabled DNS hostnames
for your VPC.
{{% /md %}}</dd>

    <dt class="property-"
            title="">private<wbr>Ip<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The private IP address assigned to the Instance.
{{% /md %}}</dd>

    <dt class="property-"
            title="">public<wbr>Dns<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The public DNS name assigned to the Instance. For EC2-VPC, this
is only available if you&#39;ve enabled DNS hostnames for your VPC.
{{% /md %}}</dd>

    <dt class="property-"
            title="">public<wbr>Ip<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The public IP address assigned to the Instance, if applicable. **NOTE**: If you are using an [`aws.ec2.Eip`](https://www.terraform.io/docs/providers/aws/r/eip.html) with your instance, you should refer to the EIP&#39;s address directly and not use `public_ip`, as this field will change after the EIP is attached.
{{% /md %}}</dd>

    <dt class="property-"
            title="">root<wbr>Block<wbr>Devices<span class="property-indicator"></span>
        <span class="property-type"><a href="#getinstancerootblockdevice">Get<wbr>Instance<wbr>Root<wbr>Block<wbr>Device[]</a></span>
    </dt>
    <dd>{{% md %}}The root block device mappings of the Instance
{{% /md %}}</dd>

    <dt class="property-"
            title="">security<wbr>Groups<span class="property-indicator"></span>
        <span class="property-type">string[]</span>
    </dt>
    <dd>{{% md %}}The associated security groups.
{{% /md %}}</dd>

    <dt class="property-"
            title="">source<wbr>Dest<wbr>Check<span class="property-indicator"></span>
        <span class="property-type">boolean</span>
    </dt>
    <dd>{{% md %}}Whether the network interface performs source/destination checking (Boolean).
{{% /md %}}</dd>

    <dt class="property-"
            title="">subnet<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The VPC subnet ID.
{{% /md %}}</dd>

    <dt class="property-"
            title="">tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}</span>
    </dt>
    <dd>{{% md %}}A mapping of tags assigned to the Instance.
{{% /md %}}</dd>

    <dt class="property-"
            title="">tenancy<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The tenancy of the instance: `dedicated`, `default`, `host`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">user<wbr>Data<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}SHA-1 hash of User Data supplied to the Instance.
{{% /md %}}</dd>

    <dt class="property-"
            title="">user<wbr>Data<wbr>Base64<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Base64 encoded contents of User Data supplied to the Instance. Valid UTF-8 contents can be decoded with the [`base64decode` function](https://www.terraform.io/docs/configuration/functions/base64decode.html). This attribute is only exported if `get_user_data` is true.
{{% /md %}}</dd>

    <dt class="property-"
            title="">vpc<wbr>Security<wbr>Group<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">string[]</span>
    </dt>
    <dd>{{% md %}}The associated security groups in a non-default VPC.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">ami<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ID of the AMI used to launch the instance.
{{% /md %}}</dd>

    <dt class="property-"
            title="">arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ARN of the instance.
{{% /md %}}</dd>

    <dt class="property-"
            title="">associate_<wbr>public_<wbr>ip_<wbr>address<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Whether or not the Instance is associated with a public IP address or not (Boolean).
{{% /md %}}</dd>

    <dt class="property-"
            title="">availability_<wbr>zone<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The availability zone of the Instance.
{{% /md %}}</dd>

    <dt class="property-"
            title="">credit_<wbr>specifications<span class="property-indicator"></span>
        <span class="property-type"><a href="#getinstancecreditspecification">List[Get<wbr>Instance<wbr>Credit<wbr>Specification]</a></span>
    </dt>
    <dd>{{% md %}}The credit specification of the Instance.
{{% /md %}}</dd>

    <dt class="property-"
            title="">disable_<wbr>api_<wbr>termination<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">ebs_<wbr>block_<wbr>devices<span class="property-indicator"></span>
        <span class="property-type"><a href="#getinstanceebsblockdevice">List[Get<wbr>Instance<wbr>Ebs<wbr>Block<wbr>Device]</a></span>
    </dt>
    <dd>{{% md %}}The EBS block device mappings of the Instance.
{{% /md %}}</dd>

    <dt class="property-"
            title="">ebs_<wbr>optimized<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Whether the Instance is EBS optimized or not (Boolean).
{{% /md %}}</dd>

    <dt class="property-"
            title="">ephemeral_<wbr>block_<wbr>devices<span class="property-indicator"></span>
        <span class="property-type"><a href="#getinstanceephemeralblockdevice">List[Get<wbr>Instance<wbr>Ephemeral<wbr>Block<wbr>Device]</a></span>
    </dt>
    <dd>{{% md %}}The ephemeral block device mappings of the Instance.
{{% /md %}}</dd>

    <dt class="property-"
            title="">filters<span class="property-indicator"></span>
        <span class="property-type"><a href="#getinstancefilter">List[Get<wbr>Instance<wbr>Filter]</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">get_<wbr>password_<wbr>data<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">get_<wbr>user_<wbr>data<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">host_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The Id of the dedicated host the instance will be assigned to.
{{% /md %}}</dd>

    <dt class="property-"
            title="">iam_<wbr>instance_<wbr>profile<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the instance profile associated with the Instance.
{{% /md %}}</dd>

    <dt class="property-"
            title="">id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}id is the provider-assigned unique ID for this managed resource.
{{% /md %}}</dd>

    <dt class="property-"
            title="">instance_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">instance_<wbr>state<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The state of the instance. One of: `pending`, `running`, `shutting-down`, `terminated`, `stopping`, `stopped`. See [Instance Lifecycle](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ec2-instance-lifecycle.html) for more information.
{{% /md %}}</dd>

    <dt class="property-"
            title="">instance_<wbr>tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">instance_<wbr>type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The type of the Instance.
{{% /md %}}</dd>

    <dt class="property-"
            title="">key_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The key name of the Instance.
{{% /md %}}</dd>

    <dt class="property-"
            title="">monitoring<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Whether detailed monitoring is enabled or disabled for the Instance (Boolean).
{{% /md %}}</dd>

    <dt class="property-"
            title="">network_<wbr>interface_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ID of the network interface that was created with the Instance.
{{% /md %}}</dd>

    <dt class="property-"
            title="">password_<wbr>data<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Base-64 encoded encrypted password data for the instance.
Useful for getting the administrator password for instances running Microsoft Windows.
This attribute is only exported if `get_password_data` is true.
See [GetPasswordData](https://docs.aws.amazon.com/AWSEC2/latest/APIReference/API_GetPasswordData.html) for more information.
{{% /md %}}</dd>

    <dt class="property-"
            title="">placement_<wbr>group<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The placement group of the Instance.
{{% /md %}}</dd>

    <dt class="property-"
            title="">private_<wbr>dns<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The private DNS name assigned to the Instance. Can only be
used inside the Amazon EC2, and only available if you&#39;ve enabled DNS hostnames
for your VPC.
{{% /md %}}</dd>

    <dt class="property-"
            title="">private_<wbr>ip<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The private IP address assigned to the Instance.
{{% /md %}}</dd>

    <dt class="property-"
            title="">public_<wbr>dns<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The public DNS name assigned to the Instance. For EC2-VPC, this
is only available if you&#39;ve enabled DNS hostnames for your VPC.
{{% /md %}}</dd>

    <dt class="property-"
            title="">public_<wbr>ip<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The public IP address assigned to the Instance, if applicable. **NOTE**: If you are using an [`aws.ec2.Eip`](https://www.terraform.io/docs/providers/aws/r/eip.html) with your instance, you should refer to the EIP&#39;s address directly and not use `public_ip`, as this field will change after the EIP is attached.
{{% /md %}}</dd>

    <dt class="property-"
            title="">root_<wbr>block_<wbr>devices<span class="property-indicator"></span>
        <span class="property-type"><a href="#getinstancerootblockdevice">List[Get<wbr>Instance<wbr>Root<wbr>Block<wbr>Device]</a></span>
    </dt>
    <dd>{{% md %}}The root block device mappings of the Instance
{{% /md %}}</dd>

    <dt class="property-"
            title="">security_<wbr>groups<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}The associated security groups.
{{% /md %}}</dd>

    <dt class="property-"
            title="">source_<wbr>dest_<wbr>check<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Whether the network interface performs source/destination checking (Boolean).
{{% /md %}}</dd>

    <dt class="property-"
            title="">subnet_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The VPC subnet ID.
{{% /md %}}</dd>

    <dt class="property-"
            title="">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}A mapping of tags assigned to the Instance.
{{% /md %}}</dd>

    <dt class="property-"
            title="">tenancy<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The tenancy of the instance: `dedicated`, `default`, `host`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">user_<wbr>data<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}SHA-1 hash of User Data supplied to the Instance.
{{% /md %}}</dd>

    <dt class="property-"
            title="">user_<wbr>data_<wbr>base64<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Base64 encoded contents of User Data supplied to the Instance. Valid UTF-8 contents can be decoded with the [`base64decode` function](https://www.terraform.io/docs/configuration/functions/base64decode.html). This attribute is only exported if `get_user_data` is true.
{{% /md %}}</dd>

    <dt class="property-"
            title="">vpc_<wbr>security_<wbr>group_<wbr>ids<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}The associated security groups in a non-default VPC.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}








## Supporting Types

#### GetInstanceCreditSpecification
{{% lang nodejs %}}
> See the   <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#GetInstanceCreditSpecification">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the   <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ec2?tab=doc#GetInstanceCreditSpecification">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the   <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ec2.GetInstanceCreditSpecification.html">output</a> API doc for this type.
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





#### GetInstanceEbsBlockDevice
{{% lang nodejs %}}
> See the   <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#GetInstanceEbsBlockDevice">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the   <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ec2?tab=doc#GetInstanceEbsBlockDevice">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the   <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ec2.GetInstanceEbsBlockDevice.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Delete<wbr>On<wbr>Termination<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}If the root block device will be deleted on termination.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Device<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The physical name of the device.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Encrypted<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}If the EBS volume is encrypted.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Iops<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}`0` If the volume is not a provisioned IOPS image, otherwise the supported IOPS count.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Kms<wbr>Key<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Snapshot<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the snapshot.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Volume<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Volume<wbr>Size<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The size of the volume, in GiB.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Volume<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type of the volume.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Delete<wbr>On<wbr>Termination<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}If the root block device will be deleted on termination.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Device<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The physical name of the device.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Encrypted<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}If the EBS volume is encrypted.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Iops<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}`0` If the volume is not a provisioned IOPS image, otherwise the supported IOPS count.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Kms<wbr>Key<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Snapshot<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the snapshot.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Volume<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Volume<wbr>Size<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The size of the volume, in GiB.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Volume<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type of the volume.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">delete<wbr>On<wbr>Termination<span class="property-indicator"></span>
        <span class="property-type">boolean</span>
    </dt>
    <dd>{{% md %}}If the root block device will be deleted on termination.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">device<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The physical name of the device.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">encrypted<span class="property-indicator"></span>
        <span class="property-type">boolean</span>
    </dt>
    <dd>{{% md %}}If the EBS volume is encrypted.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">iops<span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}`0` If the volume is not a provisioned IOPS image, otherwise the supported IOPS count.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">kms<wbr>Key<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">snapshot<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the snapshot.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">volume<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">volume<wbr>Size<span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}The size of the volume, in GiB.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">volume<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type of the volume.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">delete<wbr>On<wbr>Termination<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}If the root block device will be deleted on termination.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">device_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The physical name of the device.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">encrypted<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}If the EBS volume is encrypted.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">iops<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}`0` If the volume is not a provisioned IOPS image, otherwise the supported IOPS count.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">kms_<wbr>key_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">snapshot_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ID of the snapshot.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">volume_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">volume_<wbr>size<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The size of the volume, in GiB.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">volume<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The type of the volume.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### GetInstanceEphemeralBlockDevice
{{% lang nodejs %}}
> See the   <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#GetInstanceEphemeralBlockDevice">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the   <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ec2?tab=doc#GetInstanceEphemeralBlockDevice">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the   <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ec2.GetInstanceEphemeralBlockDevice.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Device<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The physical name of the device.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">No<wbr>Device<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Whether the specified device included in the device mapping was suppressed or not (Boolean).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Virtual<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The virtual device name.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Device<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The physical name of the device.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">No<wbr>Device<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Whether the specified device included in the device mapping was suppressed or not (Boolean).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Virtual<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The virtual device name.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">device<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The physical name of the device.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">no<wbr>Device<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Whether the specified device included in the device mapping was suppressed or not (Boolean).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">virtual<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The virtual device name.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">device_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The physical name of the device.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">no<wbr>Device<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Whether the specified device included in the device mapping was suppressed or not (Boolean).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">virtual<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The virtual device name.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### GetInstanceFilter
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#GetInstanceFilter">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#GetInstanceFilter">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ec2?tab=doc#GetInstanceFilterArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ec2?tab=doc#GetInstanceFilter">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ec2.GetInstanceFilterArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ec2.GetInstanceFilter.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Values<span class="property-indicator"></span>
        <span class="property-type">List<string></span>
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
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Values<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
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
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">values<span class="property-indicator"></span>
        <span class="property-type">string[]</span>
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
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">values<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### GetInstanceRootBlockDevice
{{% lang nodejs %}}
> See the   <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#GetInstanceRootBlockDevice">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the   <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ec2?tab=doc#GetInstanceRootBlockDevice">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the   <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ec2.GetInstanceRootBlockDevice.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Delete<wbr>On<wbr>Termination<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}If the root block device will be deleted on termination.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Encrypted<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}If the EBS volume is encrypted.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Iops<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}`0` If the volume is not a provisioned IOPS image, otherwise the supported IOPS count.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Kms<wbr>Key<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Volume<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Volume<wbr>Size<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The size of the volume, in GiB.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Volume<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type of the volume.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Delete<wbr>On<wbr>Termination<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}If the root block device will be deleted on termination.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Encrypted<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}If the EBS volume is encrypted.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Iops<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}`0` If the volume is not a provisioned IOPS image, otherwise the supported IOPS count.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Kms<wbr>Key<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Volume<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Volume<wbr>Size<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The size of the volume, in GiB.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Volume<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type of the volume.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">delete<wbr>On<wbr>Termination<span class="property-indicator"></span>
        <span class="property-type">boolean</span>
    </dt>
    <dd>{{% md %}}If the root block device will be deleted on termination.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">encrypted<span class="property-indicator"></span>
        <span class="property-type">boolean</span>
    </dt>
    <dd>{{% md %}}If the EBS volume is encrypted.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">iops<span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}`0` If the volume is not a provisioned IOPS image, otherwise the supported IOPS count.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">kms<wbr>Key<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">volume<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">volume<wbr>Size<span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}The size of the volume, in GiB.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">volume<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type of the volume.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">delete<wbr>On<wbr>Termination<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}If the root block device will be deleted on termination.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">encrypted<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}If the EBS volume is encrypted.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">iops<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}`0` If the volume is not a provisioned IOPS image, otherwise the supported IOPS count.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">kms_<wbr>key_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">volume_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">volume_<wbr>size<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The size of the volume, in GiB.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">volume<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The type of the volume.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}








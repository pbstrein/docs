
---
title: "GetAmi"
block_external_search_index: true
---

Use this data source to get the ID of a registered AMI for use in other
resources.

## Example Usage

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const example = aws.getAmi({
    executableUsers: ["self"],
    filters: [
        {
            name: "name",
            values: ["myami-*"],
        },
        {
            name: "root-device-type",
            values: ["ebs"],
        },
        {
            name: "virtualization-type",
            values: ["hvm"],
        },
    ],
    mostRecent: true,
    nameRegex: "^myami-\\d{3}",
    owners: ["self"],
});
```

> This content is derived from https://github.com/terraform-providers/terraform-provider-aws/blob/master/website/docs/d/ami.html.markdown.





## Using GetAmi

{{< chooser language "typescript,python,go,csharp" >}}

{{% choosable language typescript %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">function </span>getAmi<span class="p">(</span><span class="nx">args</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws//#GetAmiArgs">GetAmiArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#InvokeOptions">pulumi.InvokeOptions</a></span><span class="p">): Promise&lt;<span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws//#GetAmiResult">GetAmiResult</a></span>></span></code></pre></div>
{{% /choosable %}}" }}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">function </span> get_ami(</span>executable_users=None<span class="p">, </span>filters=None<span class="p">, </span>most_recent=None<span class="p">, </span>name_regex=None<span class="p">, </span>owners=None<span class="p">, </span>tags=None<span class="p">, </span>opts=None<span class="p">)</span></code></pre></div>
{{% /choosable %}}" }}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>LookupAmi<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">args</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/?tab=doc#GetAmiArgs">GetAmiArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#InvokeOption">pulumi.InvokeOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/?tab=doc#LookupAmiResult">LookupAmiResult</a></span>, error)</span></code></pre></div>
{{% /choosable %}}" }}

{{% choosable language csharp %}}
<div class="highlight">
<pre class="chroma">
<code class="language-csharp" data-lang="csharp"><span class="k">public static class </span><span class="nx">GetAmi </span><span class="p">{</span>
    <span class="k">public static </span>Task&lt;<span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.GetAmiResult.html">GetAmiResult</a></span>> <span class="p">InvokeAsync(</span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.GetAmiArgs.html">GetAmiArgs</a></span> <span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/InvokeOptions.html">InvokeOptions</a></span>? <span class="nx">opts = null<span class="p">)</span>
<span class="p">}</span></code></pre>
</div>
{{% /choosable %}}" }}



The following arguments are supported:



{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Executable<wbr>Users<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}Limit search to users with *explicit* launch permission on
the image. Valid items are the numeric account ID or `self`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Filters<span class="property-indicator"></span>
        <span class="property-type"><a href="#getamifilter">List&lt;Pulumi.<wbr>Aws.<wbr>Get<wbr>Ami<wbr>Filter<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}One or more name/value pairs to filter off of. There are
several valid keys, for a full reference, check out
[describe-images in the AWS CLI reference][1].
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Most<wbr>Recent<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}If more than one result is returned, use the most
recent AMI.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<wbr>Regex<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A regex string to apply to the AMI list returned
by AWS. This allows more advanced filtering not supported from the AWS API. This
filtering is done locally on what AWS returns, and could have a performance
impact if the result is large. It is recommended to combine this with other
options to narrow down the list AWS returns.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Owners<span class="property-indicator"></span>
        <span class="property-type">List<string></span>
    </dt>
    <dd>{{% md %}}List of AMI owners to limit search. At least 1 value must be specified. Valid values: an AWS account ID, `self` (the current account), or an AWS owner alias (e.g. `amazon`, `aws-marketplace`, `microsoft`).
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
            title="Optional">Executable<wbr>Users<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}Limit search to users with *explicit* launch permission on
the image. Valid items are the numeric account ID or `self`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Filters<span class="property-indicator"></span>
        <span class="property-type"><a href="#getamifilter">[]Get<wbr>Ami<wbr>Filter</a></span>
    </dt>
    <dd>{{% md %}}One or more name/value pairs to filter off of. There are
several valid keys, for a full reference, check out
[describe-images in the AWS CLI reference][1].
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Most<wbr>Recent<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}If more than one result is returned, use the most
recent AMI.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<wbr>Regex<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}A regex string to apply to the AMI list returned
by AWS. This allows more advanced filtering not supported from the AWS API. This
filtering is done locally on what AWS returns, and could have a performance
impact if the result is large. It is recommended to combine this with other
options to narrow down the list AWS returns.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Owners<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}List of AMI owners to limit search. At least 1 value must be specified. Valid values: an AWS account ID, `self` (the current account), or an AWS owner alias (e.g. `amazon`, `aws-marketplace`, `microsoft`).
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
            title="Optional">executable<wbr>Users<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}Limit search to users with *explicit* launch permission on
the image. Valid items are the numeric account ID or `self`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">filters<span class="property-indicator"></span>
        <span class="property-type"><a href="#getamifilter">Get<wbr>Ami<wbr>Filter[]?</a></span>
    </dt>
    <dd>{{% md %}}One or more name/value pairs to filter off of. There are
several valid keys, for a full reference, check out
[describe-images in the AWS CLI reference][1].
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">most<wbr>Recent<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}If more than one result is returned, use the most
recent AMI.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<wbr>Regex<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A regex string to apply to the AMI list returned
by AWS. This allows more advanced filtering not supported from the AWS API. This
filtering is done locally on what AWS returns, and could have a performance
impact if the result is large. It is recommended to combine this with other
options to narrow down the list AWS returns.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">owners<span class="property-indicator"></span>
        <span class="property-type">string[]</span>
    </dt>
    <dd>{{% md %}}List of AMI owners to limit search. At least 1 value must be specified. Valid values: an AWS account ID, `self` (the current account), or an AWS owner alias (e.g. `amazon`, `aws-marketplace`, `microsoft`).
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
            title="Optional">executable_<wbr>users<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}Limit search to users with *explicit* launch permission on
the image. Valid items are the numeric account ID or `self`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">filters<span class="property-indicator"></span>
        <span class="property-type"><a href="#getamifilter">List[Get<wbr>Ami<wbr>Filter]</a></span>
    </dt>
    <dd>{{% md %}}One or more name/value pairs to filter off of. There are
several valid keys, for a full reference, check out
[describe-images in the AWS CLI reference][1].
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">most_<wbr>recent<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}If more than one result is returned, use the most
recent AMI.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name_<wbr>regex<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A regex string to apply to the AMI list returned
by AWS. This allows more advanced filtering not supported from the AWS API. This
filtering is done locally on what AWS returns, and could have a performance
impact if the result is large. It is recommended to combine this with other
options to narrow down the list AWS returns.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">owners<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}List of AMI owners to limit search. At least 1 value must be specified. Valid values: an AWS account ID, `self` (the current account), or an AWS owner alias (e.g. `amazon`, `aws-marketplace`, `microsoft`).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}








## GetAmi Result

The following output properties are available:




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Architecture<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The OS architecture of the AMI (ie: `i386` or `x86_64`).
{{% /md %}}</dd>

    <dt class="property-"
            title="">Block<wbr>Device<wbr>Mappings<span class="property-indicator"></span>
        <span class="property-type"><a href="#getamiblockdevicemapping">List&lt;Pulumi.<wbr>Aws.<wbr>Get<wbr>Ami<wbr>Block<wbr>Device<wbr>Mapping&gt;</a></span>
    </dt>
    <dd>{{% md %}}The block device mappings of the AMI.
* `block_device_mappings.#.device_name` - The physical name of the device.
* `block_device_mappings.#.ebs.delete_on_termination` - `true` if the EBS volume
will be deleted on termination.
* `block_device_mappings.#.ebs.encrypted` - `true` if the EBS volume
is encrypted.
* `block_device_mappings.#.ebs.iops` - `0` if the EBS volume is
not a provisioned IOPS image, otherwise the supported IOPS count.
* `block_device_mappings.#.ebs.snapshot_id` - The ID of the snapshot.
* `block_device_mappings.#.ebs.volume_size` - The size of the volume, in GiB.
* `block_device_mappings.#.ebs.volume_type` - The volume type.
* `block_device_mappings.#.no_device` - Suppresses the specified device
included in the block device mapping of the AMI.
* `block_device_mappings.#.virtual_name` - The virtual device name (for
instance stores).
{{% /md %}}</dd>

    <dt class="property-"
            title="">Creation<wbr>Date<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The date and time the image was created.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Description<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The description of the AMI that was provided during image
creation.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Executable<wbr>Users<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">Filters<span class="property-indicator"></span>
        <span class="property-type"><a href="#getamifilter">List&lt;Pulumi.<wbr>Aws.<wbr>Get<wbr>Ami<wbr>Filter&gt;?</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">Hypervisor<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The hypervisor type of the image.
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
    <dd>{{% md %}}The ID of the AMI. Should be the same as the resource `id`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Image<wbr>Location<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The location of the AMI.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Image<wbr>Owner<wbr>Alias<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The AWS account alias (for example, `amazon`, `self`) or
the AWS account ID of the AMI owner.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Image<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type of image.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Kernel<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The kernel associated with the image, if any. Only applicable
for machine images.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Most<wbr>Recent<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the AMI that was provided during image creation.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Name<wbr>Regex<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">Owner<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The AWS account ID of the image owner.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Owners<span class="property-indicator"></span>
        <span class="property-type">List<string></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">Platform<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The value is Windows for `Windows` AMIs; otherwise blank.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Product<wbr>Codes<span class="property-indicator"></span>
        <span class="property-type"><a href="#getamiproductcode">List&lt;Pulumi.<wbr>Aws.<wbr>Get<wbr>Ami<wbr>Product<wbr>Code&gt;</a></span>
    </dt>
    <dd>{{% md %}}Any product codes associated with the AMI.
* `product_codes.#.product_code_id` - The product code.
* `product_codes.#.product_code_type` - The type of product code.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Public<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}`true` if the image has public launch permissions.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Ramdisk<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The RAM disk associated with the image, if any. Only applicable
for machine images.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Root<wbr>Device<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The device name of the root device.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Root<wbr>Device<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type of root device (ie: `ebs` or `instance-store`).
{{% /md %}}</dd>

    <dt class="property-"
            title="">Root<wbr>Snapshot<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The snapshot id associated with the root device, if any
(only applies to `ebs` root devices).
{{% /md %}}</dd>

    <dt class="property-"
            title="">Sriov<wbr>Net<wbr>Support<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Specifies whether enhanced networking is enabled.
{{% /md %}}</dd>

    <dt class="property-"
            title="">State<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The current state of the AMI. If the state is `available`, the image
is successfully registered and can be used to launch an instance.
{{% /md %}}</dd>

    <dt class="property-"
            title="">State<wbr>Reason<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object></span>
    </dt>
    <dd>{{% md %}}Describes a state change. Fields are `UNSET` if not available.
* `state_reason.code` - The reason code for the state change.
* `state_reason.message` - The message for the state change.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object></span>
    </dt>
    <dd>{{% md %}}Any tags assigned to the image.
* `tags.#.key` - The key name of the tag.
* `tags.#.value` - The value of the tag.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Virtualization<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type of virtualization of the AMI (ie: `hvm` or
`paravirtual`).
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Architecture<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The OS architecture of the AMI (ie: `i386` or `x86_64`).
{{% /md %}}</dd>

    <dt class="property-"
            title="">Block<wbr>Device<wbr>Mappings<span class="property-indicator"></span>
        <span class="property-type"><a href="#getamiblockdevicemapping">[]Get<wbr>Ami<wbr>Block<wbr>Device<wbr>Mapping</a></span>
    </dt>
    <dd>{{% md %}}The block device mappings of the AMI.
* `block_device_mappings.#.device_name` - The physical name of the device.
* `block_device_mappings.#.ebs.delete_on_termination` - `true` if the EBS volume
will be deleted on termination.
* `block_device_mappings.#.ebs.encrypted` - `true` if the EBS volume
is encrypted.
* `block_device_mappings.#.ebs.iops` - `0` if the EBS volume is
not a provisioned IOPS image, otherwise the supported IOPS count.
* `block_device_mappings.#.ebs.snapshot_id` - The ID of the snapshot.
* `block_device_mappings.#.ebs.volume_size` - The size of the volume, in GiB.
* `block_device_mappings.#.ebs.volume_type` - The volume type.
* `block_device_mappings.#.no_device` - Suppresses the specified device
included in the block device mapping of the AMI.
* `block_device_mappings.#.virtual_name` - The virtual device name (for
instance stores).
{{% /md %}}</dd>

    <dt class="property-"
            title="">Creation<wbr>Date<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The date and time the image was created.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Description<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The description of the AMI that was provided during image
creation.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Executable<wbr>Users<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">Filters<span class="property-indicator"></span>
        <span class="property-type"><a href="#getamifilter">[]Get<wbr>Ami<wbr>Filter</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">Hypervisor<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The hypervisor type of the image.
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
    <dd>{{% md %}}The ID of the AMI. Should be the same as the resource `id`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Image<wbr>Location<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The location of the AMI.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Image<wbr>Owner<wbr>Alias<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The AWS account alias (for example, `amazon`, `self`) or
the AWS account ID of the AMI owner.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Image<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type of image.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Kernel<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The kernel associated with the image, if any. Only applicable
for machine images.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Most<wbr>Recent<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the AMI that was provided during image creation.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Name<wbr>Regex<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">Owner<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The AWS account ID of the image owner.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Owners<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">Platform<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The value is Windows for `Windows` AMIs; otherwise blank.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Product<wbr>Codes<span class="property-indicator"></span>
        <span class="property-type"><a href="#getamiproductcode">[]Get<wbr>Ami<wbr>Product<wbr>Code</a></span>
    </dt>
    <dd>{{% md %}}Any product codes associated with the AMI.
* `product_codes.#.product_code_id` - The product code.
* `product_codes.#.product_code_type` - The type of product code.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Public<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}`true` if the image has public launch permissions.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Ramdisk<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The RAM disk associated with the image, if any. Only applicable
for machine images.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Root<wbr>Device<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The device name of the root device.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Root<wbr>Device<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type of root device (ie: `ebs` or `instance-store`).
{{% /md %}}</dd>

    <dt class="property-"
            title="">Root<wbr>Snapshot<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The snapshot id associated with the root device, if any
(only applies to `ebs` root devices).
{{% /md %}}</dd>

    <dt class="property-"
            title="">Sriov<wbr>Net<wbr>Support<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Specifies whether enhanced networking is enabled.
{{% /md %}}</dd>

    <dt class="property-"
            title="">State<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The current state of the AMI. If the state is `available`, the image
is successfully registered and can be used to launch an instance.
{{% /md %}}</dd>

    <dt class="property-"
            title="">State<wbr>Reason<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}Describes a state change. Fields are `UNSET` if not available.
* `state_reason.code` - The reason code for the state change.
* `state_reason.message` - The message for the state change.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}Any tags assigned to the image.
* `tags.#.key` - The key name of the tag.
* `tags.#.value` - The value of the tag.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Virtualization<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type of virtualization of the AMI (ie: `hvm` or
`paravirtual`).
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">architecture<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The OS architecture of the AMI (ie: `i386` or `x86_64`).
{{% /md %}}</dd>

    <dt class="property-"
            title="">block<wbr>Device<wbr>Mappings<span class="property-indicator"></span>
        <span class="property-type"><a href="#getamiblockdevicemapping">Get<wbr>Ami<wbr>Block<wbr>Device<wbr>Mapping[]</a></span>
    </dt>
    <dd>{{% md %}}The block device mappings of the AMI.
* `block_device_mappings.#.device_name` - The physical name of the device.
* `block_device_mappings.#.ebs.delete_on_termination` - `true` if the EBS volume
will be deleted on termination.
* `block_device_mappings.#.ebs.encrypted` - `true` if the EBS volume
is encrypted.
* `block_device_mappings.#.ebs.iops` - `0` if the EBS volume is
not a provisioned IOPS image, otherwise the supported IOPS count.
* `block_device_mappings.#.ebs.snapshot_id` - The ID of the snapshot.
* `block_device_mappings.#.ebs.volume_size` - The size of the volume, in GiB.
* `block_device_mappings.#.ebs.volume_type` - The volume type.
* `block_device_mappings.#.no_device` - Suppresses the specified device
included in the block device mapping of the AMI.
* `block_device_mappings.#.virtual_name` - The virtual device name (for
instance stores).
{{% /md %}}</dd>

    <dt class="property-"
            title="">creation<wbr>Date<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The date and time the image was created.
{{% /md %}}</dd>

    <dt class="property-"
            title="">description<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The description of the AMI that was provided during image
creation.
{{% /md %}}</dd>

    <dt class="property-"
            title="">executable<wbr>Users<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">filters<span class="property-indicator"></span>
        <span class="property-type"><a href="#getamifilter">Get<wbr>Ami<wbr>Filter[]?</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">hypervisor<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The hypervisor type of the image.
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
    <dd>{{% md %}}The ID of the AMI. Should be the same as the resource `id`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">image<wbr>Location<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The location of the AMI.
{{% /md %}}</dd>

    <dt class="property-"
            title="">image<wbr>Owner<wbr>Alias<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The AWS account alias (for example, `amazon`, `self`) or
the AWS account ID of the AMI owner.
{{% /md %}}</dd>

    <dt class="property-"
            title="">image<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type of image.
{{% /md %}}</dd>

    <dt class="property-"
            title="">kernel<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The kernel associated with the image, if any. Only applicable
for machine images.
{{% /md %}}</dd>

    <dt class="property-"
            title="">most<wbr>Recent<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the AMI that was provided during image creation.
{{% /md %}}</dd>

    <dt class="property-"
            title="">name<wbr>Regex<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">owner<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The AWS account ID of the image owner.
{{% /md %}}</dd>

    <dt class="property-"
            title="">owners<span class="property-indicator"></span>
        <span class="property-type">string[]</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">platform<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The value is Windows for `Windows` AMIs; otherwise blank.
{{% /md %}}</dd>

    <dt class="property-"
            title="">product<wbr>Codes<span class="property-indicator"></span>
        <span class="property-type"><a href="#getamiproductcode">Get<wbr>Ami<wbr>Product<wbr>Code[]</a></span>
    </dt>
    <dd>{{% md %}}Any product codes associated with the AMI.
* `product_codes.#.product_code_id` - The product code.
* `product_codes.#.product_code_type` - The type of product code.
{{% /md %}}</dd>

    <dt class="property-"
            title="">public<span class="property-indicator"></span>
        <span class="property-type">boolean</span>
    </dt>
    <dd>{{% md %}}`true` if the image has public launch permissions.
{{% /md %}}</dd>

    <dt class="property-"
            title="">ramdisk<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The RAM disk associated with the image, if any. Only applicable
for machine images.
{{% /md %}}</dd>

    <dt class="property-"
            title="">root<wbr>Device<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The device name of the root device.
{{% /md %}}</dd>

    <dt class="property-"
            title="">root<wbr>Device<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type of root device (ie: `ebs` or `instance-store`).
{{% /md %}}</dd>

    <dt class="property-"
            title="">root<wbr>Snapshot<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The snapshot id associated with the root device, if any
(only applies to `ebs` root devices).
{{% /md %}}</dd>

    <dt class="property-"
            title="">sriov<wbr>Net<wbr>Support<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Specifies whether enhanced networking is enabled.
{{% /md %}}</dd>

    <dt class="property-"
            title="">state<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The current state of the AMI. If the state is `available`, the image
is successfully registered and can be used to launch an instance.
{{% /md %}}</dd>

    <dt class="property-"
            title="">state<wbr>Reason<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}</span>
    </dt>
    <dd>{{% md %}}Describes a state change. Fields are `UNSET` if not available.
* `state_reason.code` - The reason code for the state change.
* `state_reason.message` - The message for the state change.
{{% /md %}}</dd>

    <dt class="property-"
            title="">tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}</span>
    </dt>
    <dd>{{% md %}}Any tags assigned to the image.
* `tags.#.key` - The key name of the tag.
* `tags.#.value` - The value of the tag.
{{% /md %}}</dd>

    <dt class="property-"
            title="">virtualization<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type of virtualization of the AMI (ie: `hvm` or
`paravirtual`).
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">architecture<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The OS architecture of the AMI (ie: `i386` or `x86_64`).
{{% /md %}}</dd>

    <dt class="property-"
            title="">block_<wbr>device_<wbr>mappings<span class="property-indicator"></span>
        <span class="property-type"><a href="#getamiblockdevicemapping">List[Get<wbr>Ami<wbr>Block<wbr>Device<wbr>Mapping]</a></span>
    </dt>
    <dd>{{% md %}}The block device mappings of the AMI.
* `block_device_mappings.#.device_name` - The physical name of the device.
* `block_device_mappings.#.ebs.delete_on_termination` - `true` if the EBS volume
will be deleted on termination.
* `block_device_mappings.#.ebs.encrypted` - `true` if the EBS volume
is encrypted.
* `block_device_mappings.#.ebs.iops` - `0` if the EBS volume is
not a provisioned IOPS image, otherwise the supported IOPS count.
* `block_device_mappings.#.ebs.snapshot_id` - The ID of the snapshot.
* `block_device_mappings.#.ebs.volume_size` - The size of the volume, in GiB.
* `block_device_mappings.#.ebs.volume_type` - The volume type.
* `block_device_mappings.#.no_device` - Suppresses the specified device
included in the block device mapping of the AMI.
* `block_device_mappings.#.virtual_name` - The virtual device name (for
instance stores).
{{% /md %}}</dd>

    <dt class="property-"
            title="">creation_<wbr>date<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The date and time the image was created.
{{% /md %}}</dd>

    <dt class="property-"
            title="">description<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The description of the AMI that was provided during image
creation.
{{% /md %}}</dd>

    <dt class="property-"
            title="">executable_<wbr>users<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">filters<span class="property-indicator"></span>
        <span class="property-type"><a href="#getamifilter">List[Get<wbr>Ami<wbr>Filter]</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">hypervisor<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The hypervisor type of the image.
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
    <dd>{{% md %}}The ID of the AMI. Should be the same as the resource `id`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">image_<wbr>location<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The location of the AMI.
{{% /md %}}</dd>

    <dt class="property-"
            title="">image_<wbr>owner_<wbr>alias<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The AWS account alias (for example, `amazon`, `self`) or
the AWS account ID of the AMI owner.
{{% /md %}}</dd>

    <dt class="property-"
            title="">image_<wbr>type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The type of image.
{{% /md %}}</dd>

    <dt class="property-"
            title="">kernel_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The kernel associated with the image, if any. Only applicable
for machine images.
{{% /md %}}</dd>

    <dt class="property-"
            title="">most_<wbr>recent<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the AMI that was provided during image creation.
{{% /md %}}</dd>

    <dt class="property-"
            title="">name_<wbr>regex<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">owner_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The AWS account ID of the image owner.
{{% /md %}}</dd>

    <dt class="property-"
            title="">owners<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">platform<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The value is Windows for `Windows` AMIs; otherwise blank.
{{% /md %}}</dd>

    <dt class="property-"
            title="">product_<wbr>codes<span class="property-indicator"></span>
        <span class="property-type"><a href="#getamiproductcode">List[Get<wbr>Ami<wbr>Product<wbr>Code]</a></span>
    </dt>
    <dd>{{% md %}}Any product codes associated with the AMI.
* `product_codes.#.product_code_id` - The product code.
* `product_codes.#.product_code_type` - The type of product code.
{{% /md %}}</dd>

    <dt class="property-"
            title="">public<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}`true` if the image has public launch permissions.
{{% /md %}}</dd>

    <dt class="property-"
            title="">ramdisk_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The RAM disk associated with the image, if any. Only applicable
for machine images.
{{% /md %}}</dd>

    <dt class="property-"
            title="">root_<wbr>device_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The device name of the root device.
{{% /md %}}</dd>

    <dt class="property-"
            title="">root_<wbr>device_<wbr>type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The type of root device (ie: `ebs` or `instance-store`).
{{% /md %}}</dd>

    <dt class="property-"
            title="">root_<wbr>snapshot_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The snapshot id associated with the root device, if any
(only applies to `ebs` root devices).
{{% /md %}}</dd>

    <dt class="property-"
            title="">sriov_<wbr>net_<wbr>support<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Specifies whether enhanced networking is enabled.
{{% /md %}}</dd>

    <dt class="property-"
            title="">state<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The current state of the AMI. If the state is `available`, the image
is successfully registered and can be used to launch an instance.
{{% /md %}}</dd>

    <dt class="property-"
            title="">state_<wbr>reason<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}Describes a state change. Fields are `UNSET` if not available.
* `state_reason.code` - The reason code for the state change.
* `state_reason.message` - The message for the state change.
{{% /md %}}</dd>

    <dt class="property-"
            title="">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}Any tags assigned to the image.
* `tags.#.key` - The key name of the tag.
* `tags.#.value` - The value of the tag.
{{% /md %}}</dd>

    <dt class="property-"
            title="">virtualization_<wbr>type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The type of virtualization of the AMI (ie: `hvm` or
`paravirtual`).
{{% /md %}}</dd>

</dl>
{{% /choosable %}}








## Supporting Types

#### GetAmiBlockDeviceMapping
{{% lang nodejs %}}
> See the   <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#GetAmiBlockDeviceMapping">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the   <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/?tab=doc#GetAmiBlockDeviceMapping">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the   <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.GetAmiBlockDeviceMapping.html">output</a> API doc for this type.
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
        <span class="property-type">Dictionary<string, object></span>
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
        <span class="property-type">map[string]interface{}</span>
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
        <span class="property-type">{[key: string]: any}</span>
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
        <span class="property-type">Dict[str, Any]</span>
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





#### GetAmiFilter
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#GetAmiFilter">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#GetAmiFilter">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/?tab=doc#GetAmiFilterArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/?tab=doc#GetAmiFilter">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.GetAmiFilterArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.GetAmiFilter.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the AMI that was provided during image creation.
{{% /md %}}</dd>

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
    <dd>{{% md %}}The name of the AMI that was provided during image creation.
{{% /md %}}</dd>

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
    <dd>{{% md %}}The name of the AMI that was provided during image creation.
{{% /md %}}</dd>

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
    <dd>{{% md %}}The name of the AMI that was provided during image creation.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">values<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### GetAmiProductCode
{{% lang nodejs %}}
> See the   <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#GetAmiProductCode">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the   <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/?tab=doc#GetAmiProductCode">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the   <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.GetAmiProductCode.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Product<wbr>Code<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Product<wbr>Code<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Product<wbr>Code<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Product<wbr>Code<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">product<wbr>Code<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">product<wbr>Code<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">product<wbr>Code<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">product<wbr>Code<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}








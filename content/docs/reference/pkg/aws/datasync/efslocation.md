
---
title: "EfsLocation"
block_external_search_index: true
---

Manages an AWS DataSync EFS Location.

> **NOTE:** The EFS File System must have a mounted EFS Mount Target before creating this resource.

## Example Usage

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const example = new aws.datasync.EfsLocation("example", {
    ec2Config: {
        securityGroupArns: [aws_security_group_example.arn],
        subnetArn: aws_subnet_example.arn,
    },
    // The below example uses aws.efs.MountTarget as a reference to ensure a mount target already exists when resource creation occurs.
    // You can accomplish the same behavior with depends_on or an aws.efs.MountTarget data source reference.
    efsFileSystemArn: aws_efs_mount_target_example.fileSystemArn,
});
```

> This content is derived from https://github.com/terraform-providers/terraform-provider-aws/blob/master/website/docs/r/datasync_location_efs.html.markdown.



## Create a EfsLocation Resource

{{< chooser language "javascript,typescript,python,go,csharp" / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/datasync/#EfsLocation">EfsLocation</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/datasync/#EfsLocationArgs">EfsLocationArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">EfsLocation</span><span class="p">(resource_name, opts=None, </span>ec2_config=None<span class="p">, </span>efs_file_system_arn=None<span class="p">, </span>subdirectory=None<span class="p">, </span>tags=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewEfsLocation<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/datasync?tab=doc#EfsLocationArgs">EfsLocationArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/datasync?tab=doc#EfsLocation">EfsLocation</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Datasync.EfsLocation.html">EfsLocation</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Datasync.EfsLocationArgs.html">EfsLocationArgs</a></span> <span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
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
            title="Required">Ec2Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#efslocationec2config">Efs<wbr>Location<wbr>Ec2Config<wbr>Args</a></span>
    </dt>
    <dd>{{% md %}}Configuration block containing EC2 configurations for connecting to the EFS File System.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Efs<wbr>File<wbr>System<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of EFS File System.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Subdirectory<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Subdirectory to perform actions as source or destination. Default `/`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}Key-value pairs of resource tags to assign to the DataSync Location.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Ec2Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#efslocationec2config">Efs<wbr>Location<wbr>Ec2Config</a></span>
    </dt>
    <dd>{{% md %}}Configuration block containing EC2 configurations for connecting to the EFS File System.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Efs<wbr>File<wbr>System<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of EFS File System.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Subdirectory<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Subdirectory to perform actions as source or destination. Default `/`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}Key-value pairs of resource tags to assign to the DataSync Location.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">ec2Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#efslocationec2config">Efs<wbr>Location<wbr>Ec2Config</a></span>
    </dt>
    <dd>{{% md %}}Configuration block containing EC2 configurations for connecting to the EFS File System.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">efs<wbr>File<wbr>System<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">ARN</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of EFS File System.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">subdirectory<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Subdirectory to perform actions as source or destination. Default `/`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}Key-value pairs of resource tags to assign to the DataSync Location.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">ec2_<wbr>config<span class="property-indicator"></span>
        <span class="property-type"><a href="#efslocationec2config">Dict[Efs<wbr>Location<wbr>Ec2Config]</a></span>
    </dt>
    <dd>{{% md %}}Configuration block containing EC2 configurations for connecting to the EFS File System.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">efs_<wbr>file_<wbr>system_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of EFS File System.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">subdirectory<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Subdirectory to perform actions as source or destination. Default `/`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}Key-value pairs of resource tags to assign to the DataSync Location.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}




## EfsLocation Output Properties

The following output properties are available:




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of the DataSync Location.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Ec2Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#efslocationec2config">Efs<wbr>Location<wbr>Ec2Config</a></span>
    </dt>
    <dd>{{% md %}}Configuration block containing EC2 configurations for connecting to the EFS File System.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Efs<wbr>File<wbr>System<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of EFS File System.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Subdirectory<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Subdirectory to perform actions as source or destination. Default `/`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}Key-value pairs of resource tags to assign to the DataSync Location.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Uri<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of the DataSync Location.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Ec2Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#efslocationec2config">Efs<wbr>Location<wbr>Ec2Config</a></span>
    </dt>
    <dd>{{% md %}}Configuration block containing EC2 configurations for connecting to the EFS File System.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Efs<wbr>File<wbr>System<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of EFS File System.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Subdirectory<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Subdirectory to perform actions as source or destination. Default `/`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}Key-value pairs of resource tags to assign to the DataSync Location.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Uri<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of the DataSync Location.
{{% /md %}}</dd>

    <dt class="property-"
            title="">ec2Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#efslocationec2config">Efs<wbr>Location<wbr>Ec2Config</a></span>
    </dt>
    <dd>{{% md %}}Configuration block containing EC2 configurations for connecting to the EFS File System.
{{% /md %}}</dd>

    <dt class="property-"
            title="">efs<wbr>File<wbr>System<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">ARN</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of EFS File System.
{{% /md %}}</dd>

    <dt class="property-"
            title="">subdirectory<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Subdirectory to perform actions as source or destination. Default `/`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}Key-value pairs of resource tags to assign to the DataSync Location.
{{% /md %}}</dd>

    <dt class="property-"
            title="">uri<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of the DataSync Location.
{{% /md %}}</dd>

    <dt class="property-"
            title="">ec2_<wbr>config<span class="property-indicator"></span>
        <span class="property-type"><a href="#efslocationec2config">Dict[Efs<wbr>Location<wbr>Ec2Config]</a></span>
    </dt>
    <dd>{{% md %}}Configuration block containing EC2 configurations for connecting to the EFS File System.
{{% /md %}}</dd>

    <dt class="property-"
            title="">efs_<wbr>file_<wbr>system_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of EFS File System.
{{% /md %}}</dd>

    <dt class="property-"
            title="">subdirectory<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Subdirectory to perform actions as source or destination. Default `/`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}Key-value pairs of resource tags to assign to the DataSync Location.
{{% /md %}}</dd>

    <dt class="property-"
            title="">uri<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}





## Look up an Existing EfsLocation Resource

{{< chooser language "javascript,typescript,python,go,csharp  " / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">pulumi.Input&lt;pulumi.ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/datasync/#EfsLocationState">EfsLocationState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/datasync/#EfsLocation">EfsLocation</a></span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>arn=None<span class="p">, </span>ec2_config=None<span class="p">, </span>efs_file_system_arn=None<span class="p">, </span>subdirectory=None<span class="p">, </span>tags=None<span class="p">, </span>uri=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetEfsLocation<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">pulumi.IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/datasync?tab=doc#EfsLocationState">EfsLocationState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/datasync?tab=doc#EfsLocation">EfsLocation</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Datasync.EfsLocation.html">EfsLocation</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Pulumi.Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Datasync.EfsLocationState.html">EfsLocationState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
{{% /choosable %}}

Get an existing EfsLocation resource's state with the given name, ID, and optional extra properties used to qualify the lookup.

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
    <dd>{{% md %}}Amazon Resource Name (ARN) of the DataSync Location.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ec2Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#efslocationec2config">Efs<wbr>Location<wbr>Ec2Config<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}Configuration block containing EC2 configurations for connecting to the EFS File System.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Efs<wbr>File<wbr>System<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of EFS File System.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Subdirectory<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Subdirectory to perform actions as source or destination. Default `/`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}Key-value pairs of resource tags to assign to the DataSync Location.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Uri<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of the DataSync Location.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ec2Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#efslocationec2config">*Efs<wbr>Location<wbr>Ec2Config</a></span>
    </dt>
    <dd>{{% md %}}Configuration block containing EC2 configurations for connecting to the EFS File System.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Efs<wbr>File<wbr>System<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of EFS File System.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Subdirectory<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Subdirectory to perform actions as source or destination. Default `/`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}Key-value pairs of resource tags to assign to the DataSync Location.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Uri<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of the DataSync Location.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ec2Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#efslocationec2config">Efs<wbr>Location<wbr>Ec2Config?</a></span>
    </dt>
    <dd>{{% md %}}Configuration block containing EC2 configurations for connecting to the EFS File System.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">efs<wbr>File<wbr>System<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">ARN?</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of EFS File System.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">subdirectory<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Subdirectory to perform actions as source or destination. Default `/`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}Key-value pairs of resource tags to assign to the DataSync Location.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">uri<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of the DataSync Location.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ec2_<wbr>config<span class="property-indicator"></span>
        <span class="property-type"><a href="#efslocationec2config">Dict[Efs<wbr>Location<wbr>Ec2Config]</a></span>
    </dt>
    <dd>{{% md %}}Configuration block containing EC2 configurations for connecting to the EFS File System.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">efs_<wbr>file_<wbr>system_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of EFS File System.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">subdirectory<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Subdirectory to perform actions as source or destination. Default `/`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}Key-value pairs of resource tags to assign to the DataSync Location.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">uri<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}







## Supporting Types

#### EfsLocationEc2Config
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#EfsLocationEc2Config">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#EfsLocationEc2Config">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/datasync?tab=doc#EfsLocationEc2ConfigArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/datasync?tab=doc#EfsLocationEc2ConfigOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Datasync.EfsLocationEc2ConfigArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Datasync.EfsLocationEc2Config.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Security<wbr>Group<wbr>Arns<span class="property-indicator"></span>
        <span class="property-type">List<string></span>
    </dt>
    <dd>{{% md %}}List of Amazon Resource Names (ARNs) of the EC2 Security Groups that are associated with the EFS Mount Target.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Subnet<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of the EC2 Subnet that is associated with the EFS Mount Target.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Security<wbr>Group<wbr>Arns<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}List of Amazon Resource Names (ARNs) of the EC2 Security Groups that are associated with the EFS Mount Target.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Subnet<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of the EC2 Subnet that is associated with the EFS Mount Target.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">security<wbr>Group<wbr>Arns<span class="property-indicator"></span>
        <span class="property-type">string[]</span>
    </dt>
    <dd>{{% md %}}List of Amazon Resource Names (ARNs) of the EC2 Security Groups that are associated with the EFS Mount Target.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">subnet<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of the EC2 Subnet that is associated with the EFS Mount Target.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">security<wbr>Group<wbr>Arns<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}List of Amazon Resource Names (ARNs) of the EC2 Security Groups that are associated with the EFS Mount Target.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">subnet<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of the EC2 Subnet that is associated with the EFS Mount Target.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}








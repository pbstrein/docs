
---
title: "MaintenanceWindowTarget"
block_external_search_index: true
---

Provides an SSM Maintenance Window Target resource

## Example Usage

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const window = new aws.ssm.MaintenanceWindow("window", {
    cutoff: 1,
    duration: 3,
    schedule: "cron(0 16 ? * TUE *)",
});
const target1 = new aws.ssm.MaintenanceWindowTarget("target1", {
    description: "This is a maintenance window target",
    resourceType: "INSTANCE",
    targets: [{
        key: "tag:Name",
        values: ["acceptance_test"],
    }],
    windowId: window.id,
});
```

> This content is derived from https://github.com/terraform-providers/terraform-provider-aws/blob/master/website/docs/r/ssm_maintenance_window_target.html.markdown.



## Create a MaintenanceWindowTarget Resource

{{< chooser language "javascript,typescript,python,go,csharp" / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/ssm/#MaintenanceWindowTarget">MaintenanceWindowTarget</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/ssm/#MaintenanceWindowTargetArgs">MaintenanceWindowTargetArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">MaintenanceWindowTarget</span><span class="p">(resource_name, opts=None, </span>description=None<span class="p">, </span>name=None<span class="p">, </span>owner_information=None<span class="p">, </span>resource_type=None<span class="p">, </span>targets=None<span class="p">, </span>window_id=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewMaintenanceWindowTarget<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ssm?tab=doc#MaintenanceWindowTargetArgs">MaintenanceWindowTargetArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ssm?tab=doc#MaintenanceWindowTarget">MaintenanceWindowTarget</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ssm.MaintenanceWindowTarget.html">MaintenanceWindowTarget</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ssm.MaintenanceWindowTargetArgs.html">MaintenanceWindowTargetArgs</a></span> <span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
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
    <dd>{{% md %}}The description of the maintenance window target.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the maintenance window target.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Owner<wbr>Information<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}User-provided value that will be included in any CloudWatch events raised while running tasks for these targets in this Maintenance Window.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Resource<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type of target being registered with the Maintenance Window. Possible values `INSTANCE`.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Targets<span class="property-indicator"></span>
        <span class="property-type"><a href="#maintenancewindowtargettarget">List&lt;Maintenance<wbr>Window<wbr>Target<wbr>Target<wbr>Args&gt;</a></span>
    </dt>
    <dd>{{% md %}}The targets (either instances or tags). Instances are specified using Key=InstanceIds,Values=InstanceId1,InstanceId2. Tags are specified using Key=tag name,Values=tag value.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Window<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Id of the maintenance window to register the target with.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Description<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The description of the maintenance window target.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name of the maintenance window target.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Owner<wbr>Information<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}User-provided value that will be included in any CloudWatch events raised while running tasks for these targets in this Maintenance Window.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Resource<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type of target being registered with the Maintenance Window. Possible values `INSTANCE`.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Targets<span class="property-indicator"></span>
        <span class="property-type"><a href="#maintenancewindowtargettarget">[]Maintenance<wbr>Window<wbr>Target<wbr>Target</a></span>
    </dt>
    <dd>{{% md %}}The targets (either instances or tags). Instances are specified using Key=InstanceIds,Values=InstanceId1,InstanceId2. Tags are specified using Key=tag name,Values=tag value.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Window<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Id of the maintenance window to register the target with.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">description<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The description of the maintenance window target.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the maintenance window target.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">owner<wbr>Information<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}User-provided value that will be included in any CloudWatch events raised while running tasks for these targets in this Maintenance Window.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">resource<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type of target being registered with the Maintenance Window. Possible values `INSTANCE`.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">targets<span class="property-indicator"></span>
        <span class="property-type"><a href="#maintenancewindowtargettarget">Maintenance<wbr>Window<wbr>Target<wbr>Target[]</a></span>
    </dt>
    <dd>{{% md %}}The targets (either instances or tags). Instances are specified using Key=InstanceIds,Values=InstanceId1,InstanceId2. Tags are specified using Key=tag name,Values=tag value.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">window<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Id of the maintenance window to register the target with.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">description<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The description of the maintenance window target.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the maintenance window target.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">owner_<wbr>information<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}User-provided value that will be included in any CloudWatch events raised while running tasks for these targets in this Maintenance Window.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">resource_<wbr>type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The type of target being registered with the Maintenance Window. Possible values `INSTANCE`.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">targets<span class="property-indicator"></span>
        <span class="property-type"><a href="#maintenancewindowtargettarget">List[Maintenance<wbr>Window<wbr>Target<wbr>Target]</a></span>
    </dt>
    <dd>{{% md %}}The targets (either instances or tags). Instances are specified using Key=InstanceIds,Values=InstanceId1,InstanceId2. Tags are specified using Key=tag name,Values=tag value.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">window_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The Id of the maintenance window to register the target with.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}




## MaintenanceWindowTarget Output Properties

The following output properties are available:




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Description<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The description of the maintenance window target.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the maintenance window target.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Owner<wbr>Information<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}User-provided value that will be included in any CloudWatch events raised while running tasks for these targets in this Maintenance Window.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Resource<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type of target being registered with the Maintenance Window. Possible values `INSTANCE`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Targets<span class="property-indicator"></span>
        <span class="property-type"><a href="#maintenancewindowtargettarget">List&lt;Maintenance<wbr>Window<wbr>Target<wbr>Target&gt;</a></span>
    </dt>
    <dd>{{% md %}}The targets (either instances or tags). Instances are specified using Key=InstanceIds,Values=InstanceId1,InstanceId2. Tags are specified using Key=tag name,Values=tag value.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Window<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Id of the maintenance window to register the target with.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Description<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The description of the maintenance window target.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the maintenance window target.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Owner<wbr>Information<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}User-provided value that will be included in any CloudWatch events raised while running tasks for these targets in this Maintenance Window.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Resource<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type of target being registered with the Maintenance Window. Possible values `INSTANCE`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Targets<span class="property-indicator"></span>
        <span class="property-type"><a href="#maintenancewindowtargettarget">[]Maintenance<wbr>Window<wbr>Target<wbr>Target</a></span>
    </dt>
    <dd>{{% md %}}The targets (either instances or tags). Instances are specified using Key=InstanceIds,Values=InstanceId1,InstanceId2. Tags are specified using Key=tag name,Values=tag value.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Window<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Id of the maintenance window to register the target with.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">description<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The description of the maintenance window target.
{{% /md %}}</dd>

    <dt class="property-"
            title="">name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the maintenance window target.
{{% /md %}}</dd>

    <dt class="property-"
            title="">owner<wbr>Information<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}User-provided value that will be included in any CloudWatch events raised while running tasks for these targets in this Maintenance Window.
{{% /md %}}</dd>

    <dt class="property-"
            title="">resource<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type of target being registered with the Maintenance Window. Possible values `INSTANCE`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">targets<span class="property-indicator"></span>
        <span class="property-type"><a href="#maintenancewindowtargettarget">Maintenance<wbr>Window<wbr>Target<wbr>Target[]</a></span>
    </dt>
    <dd>{{% md %}}The targets (either instances or tags). Instances are specified using Key=InstanceIds,Values=InstanceId1,InstanceId2. Tags are specified using Key=tag name,Values=tag value.
{{% /md %}}</dd>

    <dt class="property-"
            title="">window<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Id of the maintenance window to register the target with.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">description<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The description of the maintenance window target.
{{% /md %}}</dd>

    <dt class="property-"
            title="">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the maintenance window target.
{{% /md %}}</dd>

    <dt class="property-"
            title="">owner_<wbr>information<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}User-provided value that will be included in any CloudWatch events raised while running tasks for these targets in this Maintenance Window.
{{% /md %}}</dd>

    <dt class="property-"
            title="">resource_<wbr>type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The type of target being registered with the Maintenance Window. Possible values `INSTANCE`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">targets<span class="property-indicator"></span>
        <span class="property-type"><a href="#maintenancewindowtargettarget">List[Maintenance<wbr>Window<wbr>Target<wbr>Target]</a></span>
    </dt>
    <dd>{{% md %}}The targets (either instances or tags). Instances are specified using Key=InstanceIds,Values=InstanceId1,InstanceId2. Tags are specified using Key=tag name,Values=tag value.
{{% /md %}}</dd>

    <dt class="property-"
            title="">window_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The Id of the maintenance window to register the target with.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





## Look up an Existing MaintenanceWindowTarget Resource

{{< chooser language "javascript,typescript,python,go,csharp  " / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">pulumi.Input&lt;pulumi.ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/ssm/#MaintenanceWindowTargetState">MaintenanceWindowTargetState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/ssm/#MaintenanceWindowTarget">MaintenanceWindowTarget</a></span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>description=None<span class="p">, </span>name=None<span class="p">, </span>owner_information=None<span class="p">, </span>resource_type=None<span class="p">, </span>targets=None<span class="p">, </span>window_id=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetMaintenanceWindowTarget<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">pulumi.IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ssm?tab=doc#MaintenanceWindowTargetState">MaintenanceWindowTargetState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ssm?tab=doc#MaintenanceWindowTarget">MaintenanceWindowTarget</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ssm.MaintenanceWindowTarget.html">MaintenanceWindowTarget</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Pulumi.Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ssm.MaintenanceWindowTargetState.html">MaintenanceWindowTargetState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
{{% /choosable %}}

Get an existing MaintenanceWindowTarget resource's state with the given name, ID, and optional extra properties used to qualify the lookup.

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
            title="Optional">Description<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The description of the maintenance window target.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the maintenance window target.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Owner<wbr>Information<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}User-provided value that will be included in any CloudWatch events raised while running tasks for these targets in this Maintenance Window.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Resource<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The type of target being registered with the Maintenance Window. Possible values `INSTANCE`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Targets<span class="property-indicator"></span>
        <span class="property-type"><a href="#maintenancewindowtargettarget">List&lt;Maintenance<wbr>Window<wbr>Target<wbr>Target<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}The targets (either instances or tags). Instances are specified using Key=InstanceIds,Values=InstanceId1,InstanceId2. Tags are specified using Key=tag name,Values=tag value.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Window<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The Id of the maintenance window to register the target with.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Description<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The description of the maintenance window target.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name of the maintenance window target.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Owner<wbr>Information<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}User-provided value that will be included in any CloudWatch events raised while running tasks for these targets in this Maintenance Window.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Resource<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The type of target being registered with the Maintenance Window. Possible values `INSTANCE`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Targets<span class="property-indicator"></span>
        <span class="property-type"><a href="#maintenancewindowtargettarget">[]Maintenance<wbr>Window<wbr>Target<wbr>Target</a></span>
    </dt>
    <dd>{{% md %}}The targets (either instances or tags). Instances are specified using Key=InstanceIds,Values=InstanceId1,InstanceId2. Tags are specified using Key=tag name,Values=tag value.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Window<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The Id of the maintenance window to register the target with.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">description<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The description of the maintenance window target.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the maintenance window target.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">owner<wbr>Information<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}User-provided value that will be included in any CloudWatch events raised while running tasks for these targets in this Maintenance Window.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">resource<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The type of target being registered with the Maintenance Window. Possible values `INSTANCE`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">targets<span class="property-indicator"></span>
        <span class="property-type"><a href="#maintenancewindowtargettarget">Maintenance<wbr>Window<wbr>Target<wbr>Target[]?</a></span>
    </dt>
    <dd>{{% md %}}The targets (either instances or tags). Instances are specified using Key=InstanceIds,Values=InstanceId1,InstanceId2. Tags are specified using Key=tag name,Values=tag value.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">window<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The Id of the maintenance window to register the target with.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">description<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The description of the maintenance window target.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the maintenance window target.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">owner_<wbr>information<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}User-provided value that will be included in any CloudWatch events raised while running tasks for these targets in this Maintenance Window.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">resource_<wbr>type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The type of target being registered with the Maintenance Window. Possible values `INSTANCE`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">targets<span class="property-indicator"></span>
        <span class="property-type"><a href="#maintenancewindowtargettarget">List[Maintenance<wbr>Window<wbr>Target<wbr>Target]</a></span>
    </dt>
    <dd>{{% md %}}The targets (either instances or tags). Instances are specified using Key=InstanceIds,Values=InstanceId1,InstanceId2. Tags are specified using Key=tag name,Values=tag value.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">window_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The Id of the maintenance window to register the target with.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}







## Supporting Types

#### MaintenanceWindowTargetTarget
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#MaintenanceWindowTargetTarget">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#MaintenanceWindowTargetTarget">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ssm?tab=doc#MaintenanceWindowTargetTargetArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ssm?tab=doc#MaintenanceWindowTargetTargetOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ssm.MaintenanceWindowTargetTargetArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ssm.MaintenanceWindowTargetTarget.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Key<span class="property-indicator"></span>
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
            title="Required">Key<span class="property-indicator"></span>
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
            title="Required">key<span class="property-indicator"></span>
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
            title="Required">key<span class="property-indicator"></span>
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








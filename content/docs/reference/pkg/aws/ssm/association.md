
---
title: "Association"
block_external_search_index: true
---

Associates an SSM Document to an instance or EC2 tag.

## Example Usage

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const example = new aws.ssm.Association("example", {
    targets: [{
        key: "InstanceIds",
        values: [aws_instance_example.id],
    }],
});
```

> This content is derived from https://github.com/terraform-providers/terraform-provider-aws/blob/master/website/docs/r/ssm_association.html.markdown.



## Create a Association Resource

{{< chooser language "javascript,typescript,python,go,csharp" / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/ssm/#Association">Association</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/ssm/#AssociationArgs">AssociationArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">Association</span><span class="p">(resource_name, opts=None, </span>association_name=None<span class="p">, </span>automation_target_parameter_name=None<span class="p">, </span>compliance_severity=None<span class="p">, </span>document_version=None<span class="p">, </span>instance_id=None<span class="p">, </span>max_concurrency=None<span class="p">, </span>max_errors=None<span class="p">, </span>name=None<span class="p">, </span>output_location=None<span class="p">, </span>parameters=None<span class="p">, </span>schedule_expression=None<span class="p">, </span>targets=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewAssociation<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ssm?tab=doc#AssociationArgs">AssociationArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ssm?tab=doc#Association">Association</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ssm.Association.html">Association</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ssm.AssociationArgs.html">AssociationArgs</a></span>? <span class="nx">args = null<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
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
            title="Optional">Association<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The descriptive name for the association.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Automation<wbr>Target<wbr>Parameter<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Specify the target for the association. This target is required for associations that use an `Automation` document and target resources by using rate controls.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Compliance<wbr>Severity<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The compliance severity for the association. Can be one of the following: `UNSPECIFIED`, `LOW`, `MEDIUM`, `HIGH` or `CRITICAL`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Document<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The document version you want to associate with the target(s). Can be a specific version or the default version.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Instance<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The instance ID to apply an SSM document to. Use `targets` with key `InstanceIds` for document schema versions 2.0 and above.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Max<wbr>Concurrency<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The maximum number of targets allowed to run the association at the same time. You can specify a number, for example 10, or a percentage of the target set, for example 10%.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Max<wbr>Errors<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The number of errors that are allowed before the system stops sending requests to run the association on additional targets. You can specify a number, for example 10, or a percentage of the target set, for example 10%.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the SSM document to apply.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Output<wbr>Location<span class="property-indicator"></span>
        <span class="property-type"><a href="#associationoutputlocation">Association<wbr>Output<wbr>Location<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}An output location block. Output Location is documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Parameters<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}A block of arbitrary string parameters to pass to the SSM document.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Schedule<wbr>Expression<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A cron expression when the association will be applied to the target(s).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Targets<span class="property-indicator"></span>
        <span class="property-type"><a href="#associationtarget">List&lt;Association<wbr>Target<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}A block containing the targets of the SSM association. Targets are documented below. AWS currently supports a maximum of 5 targets.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Association<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The descriptive name for the association.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Automation<wbr>Target<wbr>Parameter<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Specify the target for the association. This target is required for associations that use an `Automation` document and target resources by using rate controls.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Compliance<wbr>Severity<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The compliance severity for the association. Can be one of the following: `UNSPECIFIED`, `LOW`, `MEDIUM`, `HIGH` or `CRITICAL`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Document<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The document version you want to associate with the target(s). Can be a specific version or the default version.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Instance<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The instance ID to apply an SSM document to. Use `targets` with key `InstanceIds` for document schema versions 2.0 and above.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Max<wbr>Concurrency<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The maximum number of targets allowed to run the association at the same time. You can specify a number, for example 10, or a percentage of the target set, for example 10%.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Max<wbr>Errors<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The number of errors that are allowed before the system stops sending requests to run the association on additional targets. You can specify a number, for example 10, or a percentage of the target set, for example 10%.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name of the SSM document to apply.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Output<wbr>Location<span class="property-indicator"></span>
        <span class="property-type"><a href="#associationoutputlocation">*Association<wbr>Output<wbr>Location</a></span>
    </dt>
    <dd>{{% md %}}An output location block. Output Location is documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Parameters<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}A block of arbitrary string parameters to pass to the SSM document.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Schedule<wbr>Expression<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}A cron expression when the association will be applied to the target(s).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Targets<span class="property-indicator"></span>
        <span class="property-type"><a href="#associationtarget">[]Association<wbr>Target</a></span>
    </dt>
    <dd>{{% md %}}A block containing the targets of the SSM association. Targets are documented below. AWS currently supports a maximum of 5 targets.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">association<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The descriptive name for the association.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">automation<wbr>Target<wbr>Parameter<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Specify the target for the association. This target is required for associations that use an `Automation` document and target resources by using rate controls.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">compliance<wbr>Severity<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The compliance severity for the association. Can be one of the following: `UNSPECIFIED`, `LOW`, `MEDIUM`, `HIGH` or `CRITICAL`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">document<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The document version you want to associate with the target(s). Can be a specific version or the default version.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">instance<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The instance ID to apply an SSM document to. Use `targets` with key `InstanceIds` for document schema versions 2.0 and above.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">max<wbr>Concurrency<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The maximum number of targets allowed to run the association at the same time. You can specify a number, for example 10, or a percentage of the target set, for example 10%.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">max<wbr>Errors<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The number of errors that are allowed before the system stops sending requests to run the association on additional targets. You can specify a number, for example 10, or a percentage of the target set, for example 10%.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the SSM document to apply.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">output<wbr>Location<span class="property-indicator"></span>
        <span class="property-type"><a href="#associationoutputlocation">Association<wbr>Output<wbr>Location?</a></span>
    </dt>
    <dd>{{% md %}}An output location block. Output Location is documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">parameters<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}A block of arbitrary string parameters to pass to the SSM document.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">schedule<wbr>Expression<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A cron expression when the association will be applied to the target(s).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">targets<span class="property-indicator"></span>
        <span class="property-type"><a href="#associationtarget">Association<wbr>Target[]?</a></span>
    </dt>
    <dd>{{% md %}}A block containing the targets of the SSM association. Targets are documented below. AWS currently supports a maximum of 5 targets.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">association_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The descriptive name for the association.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">automation_<wbr>target_<wbr>parameter_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Specify the target for the association. This target is required for associations that use an `Automation` document and target resources by using rate controls.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">compliance_<wbr>severity<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The compliance severity for the association. Can be one of the following: `UNSPECIFIED`, `LOW`, `MEDIUM`, `HIGH` or `CRITICAL`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">document_<wbr>version<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The document version you want to associate with the target(s). Can be a specific version or the default version.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">instance_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The instance ID to apply an SSM document to. Use `targets` with key `InstanceIds` for document schema versions 2.0 and above.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">max_<wbr>concurrency<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The maximum number of targets allowed to run the association at the same time. You can specify a number, for example 10, or a percentage of the target set, for example 10%.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">max_<wbr>errors<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The number of errors that are allowed before the system stops sending requests to run the association on additional targets. You can specify a number, for example 10, or a percentage of the target set, for example 10%.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the SSM document to apply.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">output_<wbr>location<span class="property-indicator"></span>
        <span class="property-type"><a href="#associationoutputlocation">Dict[Association<wbr>Output<wbr>Location]</a></span>
    </dt>
    <dd>{{% md %}}An output location block. Output Location is documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">parameters<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}A block of arbitrary string parameters to pass to the SSM document.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">schedule_<wbr>expression<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A cron expression when the association will be applied to the target(s).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">targets<span class="property-indicator"></span>
        <span class="property-type"><a href="#associationtarget">List[Association<wbr>Target]</a></span>
    </dt>
    <dd>{{% md %}}A block containing the targets of the SSM association. Targets are documented below. AWS currently supports a maximum of 5 targets.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}




## Association Output Properties

The following output properties are available:




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Association<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the SSM association.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Association<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The descriptive name for the association.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Automation<wbr>Target<wbr>Parameter<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Specify the target for the association. This target is required for associations that use an `Automation` document and target resources by using rate controls.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Compliance<wbr>Severity<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The compliance severity for the association. Can be one of the following: `UNSPECIFIED`, `LOW`, `MEDIUM`, `HIGH` or `CRITICAL`
{{% /md %}}</dd>

    <dt class="property-"
            title="">Document<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The document version you want to associate with the target(s). Can be a specific version or the default version.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Instance<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The instance ID to apply an SSM document to. Use `targets` with key `InstanceIds` for document schema versions 2.0 and above.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Max<wbr>Concurrency<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The maximum number of targets allowed to run the association at the same time. You can specify a number, for example 10, or a percentage of the target set, for example 10%.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Max<wbr>Errors<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The number of errors that are allowed before the system stops sending requests to run the association on additional targets. You can specify a number, for example 10, or a percentage of the target set, for example 10%.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the SSM document to apply.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Output<wbr>Location<span class="property-indicator"></span>
        <span class="property-type"><a href="#associationoutputlocation">Association<wbr>Output<wbr>Location?</a></span>
    </dt>
    <dd>{{% md %}}An output location block. Output Location is documented below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Parameters<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object></span>
    </dt>
    <dd>{{% md %}}A block of arbitrary string parameters to pass to the SSM document.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Schedule<wbr>Expression<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A cron expression when the association will be applied to the target(s).
{{% /md %}}</dd>

    <dt class="property-"
            title="">Targets<span class="property-indicator"></span>
        <span class="property-type"><a href="#associationtarget">List&lt;Association<wbr>Target&gt;</a></span>
    </dt>
    <dd>{{% md %}}A block containing the targets of the SSM association. Targets are documented below. AWS currently supports a maximum of 5 targets.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Association<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the SSM association.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Association<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The descriptive name for the association.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Automation<wbr>Target<wbr>Parameter<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Specify the target for the association. This target is required for associations that use an `Automation` document and target resources by using rate controls.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Compliance<wbr>Severity<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The compliance severity for the association. Can be one of the following: `UNSPECIFIED`, `LOW`, `MEDIUM`, `HIGH` or `CRITICAL`
{{% /md %}}</dd>

    <dt class="property-"
            title="">Document<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The document version you want to associate with the target(s). Can be a specific version or the default version.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Instance<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The instance ID to apply an SSM document to. Use `targets` with key `InstanceIds` for document schema versions 2.0 and above.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Max<wbr>Concurrency<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The maximum number of targets allowed to run the association at the same time. You can specify a number, for example 10, or a percentage of the target set, for example 10%.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Max<wbr>Errors<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The number of errors that are allowed before the system stops sending requests to run the association on additional targets. You can specify a number, for example 10, or a percentage of the target set, for example 10%.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the SSM document to apply.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Output<wbr>Location<span class="property-indicator"></span>
        <span class="property-type"><a href="#associationoutputlocation">*Association<wbr>Output<wbr>Location</a></span>
    </dt>
    <dd>{{% md %}}An output location block. Output Location is documented below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Parameters<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}A block of arbitrary string parameters to pass to the SSM document.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Schedule<wbr>Expression<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}A cron expression when the association will be applied to the target(s).
{{% /md %}}</dd>

    <dt class="property-"
            title="">Targets<span class="property-indicator"></span>
        <span class="property-type"><a href="#associationtarget">[]Association<wbr>Target</a></span>
    </dt>
    <dd>{{% md %}}A block containing the targets of the SSM association. Targets are documented below. AWS currently supports a maximum of 5 targets.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">association<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the SSM association.
{{% /md %}}</dd>

    <dt class="property-"
            title="">association<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The descriptive name for the association.
{{% /md %}}</dd>

    <dt class="property-"
            title="">automation<wbr>Target<wbr>Parameter<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Specify the target for the association. This target is required for associations that use an `Automation` document and target resources by using rate controls.
{{% /md %}}</dd>

    <dt class="property-"
            title="">compliance<wbr>Severity<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The compliance severity for the association. Can be one of the following: `UNSPECIFIED`, `LOW`, `MEDIUM`, `HIGH` or `CRITICAL`
{{% /md %}}</dd>

    <dt class="property-"
            title="">document<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The document version you want to associate with the target(s). Can be a specific version or the default version.
{{% /md %}}</dd>

    <dt class="property-"
            title="">instance<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The instance ID to apply an SSM document to. Use `targets` with key `InstanceIds` for document schema versions 2.0 and above.
{{% /md %}}</dd>

    <dt class="property-"
            title="">max<wbr>Concurrency<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The maximum number of targets allowed to run the association at the same time. You can specify a number, for example 10, or a percentage of the target set, for example 10%.
{{% /md %}}</dd>

    <dt class="property-"
            title="">max<wbr>Errors<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The number of errors that are allowed before the system stops sending requests to run the association on additional targets. You can specify a number, for example 10, or a percentage of the target set, for example 10%.
{{% /md %}}</dd>

    <dt class="property-"
            title="">name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the SSM document to apply.
{{% /md %}}</dd>

    <dt class="property-"
            title="">output<wbr>Location<span class="property-indicator"></span>
        <span class="property-type"><a href="#associationoutputlocation">Association<wbr>Output<wbr>Location?</a></span>
    </dt>
    <dd>{{% md %}}An output location block. Output Location is documented below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">parameters<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}</span>
    </dt>
    <dd>{{% md %}}A block of arbitrary string parameters to pass to the SSM document.
{{% /md %}}</dd>

    <dt class="property-"
            title="">schedule<wbr>Expression<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A cron expression when the association will be applied to the target(s).
{{% /md %}}</dd>

    <dt class="property-"
            title="">targets<span class="property-indicator"></span>
        <span class="property-type"><a href="#associationtarget">Association<wbr>Target[]</a></span>
    </dt>
    <dd>{{% md %}}A block containing the targets of the SSM association. Targets are documented below. AWS currently supports a maximum of 5 targets.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">association_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ID of the SSM association.
{{% /md %}}</dd>

    <dt class="property-"
            title="">association_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The descriptive name for the association.
{{% /md %}}</dd>

    <dt class="property-"
            title="">automation_<wbr>target_<wbr>parameter_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Specify the target for the association. This target is required for associations that use an `Automation` document and target resources by using rate controls.
{{% /md %}}</dd>

    <dt class="property-"
            title="">compliance_<wbr>severity<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The compliance severity for the association. Can be one of the following: `UNSPECIFIED`, `LOW`, `MEDIUM`, `HIGH` or `CRITICAL`
{{% /md %}}</dd>

    <dt class="property-"
            title="">document_<wbr>version<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The document version you want to associate with the target(s). Can be a specific version or the default version.
{{% /md %}}</dd>

    <dt class="property-"
            title="">instance_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The instance ID to apply an SSM document to. Use `targets` with key `InstanceIds` for document schema versions 2.0 and above.
{{% /md %}}</dd>

    <dt class="property-"
            title="">max_<wbr>concurrency<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The maximum number of targets allowed to run the association at the same time. You can specify a number, for example 10, or a percentage of the target set, for example 10%.
{{% /md %}}</dd>

    <dt class="property-"
            title="">max_<wbr>errors<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The number of errors that are allowed before the system stops sending requests to run the association on additional targets. You can specify a number, for example 10, or a percentage of the target set, for example 10%.
{{% /md %}}</dd>

    <dt class="property-"
            title="">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the SSM document to apply.
{{% /md %}}</dd>

    <dt class="property-"
            title="">output_<wbr>location<span class="property-indicator"></span>
        <span class="property-type"><a href="#associationoutputlocation">Dict[Association<wbr>Output<wbr>Location]</a></span>
    </dt>
    <dd>{{% md %}}An output location block. Output Location is documented below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">parameters<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}A block of arbitrary string parameters to pass to the SSM document.
{{% /md %}}</dd>

    <dt class="property-"
            title="">schedule_<wbr>expression<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A cron expression when the association will be applied to the target(s).
{{% /md %}}</dd>

    <dt class="property-"
            title="">targets<span class="property-indicator"></span>
        <span class="property-type"><a href="#associationtarget">List[Association<wbr>Target]</a></span>
    </dt>
    <dd>{{% md %}}A block containing the targets of the SSM association. Targets are documented below. AWS currently supports a maximum of 5 targets.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





## Look up an Existing Association Resource

{{< chooser language "javascript,typescript,python,go,csharp  " / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">pulumi.Input&lt;pulumi.ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/ssm/#AssociationState">AssociationState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/ssm/#Association">Association</a></span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>association_id=None<span class="p">, </span>association_name=None<span class="p">, </span>automation_target_parameter_name=None<span class="p">, </span>compliance_severity=None<span class="p">, </span>document_version=None<span class="p">, </span>instance_id=None<span class="p">, </span>max_concurrency=None<span class="p">, </span>max_errors=None<span class="p">, </span>name=None<span class="p">, </span>output_location=None<span class="p">, </span>parameters=None<span class="p">, </span>schedule_expression=None<span class="p">, </span>targets=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetAssociation<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">pulumi.IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ssm?tab=doc#AssociationState">AssociationState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ssm?tab=doc#Association">Association</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ssm.Association.html">Association</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Pulumi.Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ssm.AssociationState.html">AssociationState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
{{% /choosable %}}

Get an existing Association resource's state with the given name, ID, and optional extra properties used to qualify the lookup.

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
            title="Optional">Association<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ID of the SSM association.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Association<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The descriptive name for the association.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Automation<wbr>Target<wbr>Parameter<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Specify the target for the association. This target is required for associations that use an `Automation` document and target resources by using rate controls.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Compliance<wbr>Severity<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The compliance severity for the association. Can be one of the following: `UNSPECIFIED`, `LOW`, `MEDIUM`, `HIGH` or `CRITICAL`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Document<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The document version you want to associate with the target(s). Can be a specific version or the default version.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Instance<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The instance ID to apply an SSM document to. Use `targets` with key `InstanceIds` for document schema versions 2.0 and above.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Max<wbr>Concurrency<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The maximum number of targets allowed to run the association at the same time. You can specify a number, for example 10, or a percentage of the target set, for example 10%.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Max<wbr>Errors<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The number of errors that are allowed before the system stops sending requests to run the association on additional targets. You can specify a number, for example 10, or a percentage of the target set, for example 10%.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the SSM document to apply.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Output<wbr>Location<span class="property-indicator"></span>
        <span class="property-type"><a href="#associationoutputlocation">Association<wbr>Output<wbr>Location<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}An output location block. Output Location is documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Parameters<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}A block of arbitrary string parameters to pass to the SSM document.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Schedule<wbr>Expression<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A cron expression when the association will be applied to the target(s).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Targets<span class="property-indicator"></span>
        <span class="property-type"><a href="#associationtarget">List&lt;Association<wbr>Target<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}A block containing the targets of the SSM association. Targets are documented below. AWS currently supports a maximum of 5 targets.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Association<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The ID of the SSM association.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Association<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The descriptive name for the association.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Automation<wbr>Target<wbr>Parameter<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Specify the target for the association. This target is required for associations that use an `Automation` document and target resources by using rate controls.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Compliance<wbr>Severity<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The compliance severity for the association. Can be one of the following: `UNSPECIFIED`, `LOW`, `MEDIUM`, `HIGH` or `CRITICAL`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Document<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The document version you want to associate with the target(s). Can be a specific version or the default version.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Instance<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The instance ID to apply an SSM document to. Use `targets` with key `InstanceIds` for document schema versions 2.0 and above.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Max<wbr>Concurrency<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The maximum number of targets allowed to run the association at the same time. You can specify a number, for example 10, or a percentage of the target set, for example 10%.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Max<wbr>Errors<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The number of errors that are allowed before the system stops sending requests to run the association on additional targets. You can specify a number, for example 10, or a percentage of the target set, for example 10%.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name of the SSM document to apply.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Output<wbr>Location<span class="property-indicator"></span>
        <span class="property-type"><a href="#associationoutputlocation">*Association<wbr>Output<wbr>Location</a></span>
    </dt>
    <dd>{{% md %}}An output location block. Output Location is documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Parameters<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}A block of arbitrary string parameters to pass to the SSM document.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Schedule<wbr>Expression<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}A cron expression when the association will be applied to the target(s).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Targets<span class="property-indicator"></span>
        <span class="property-type"><a href="#associationtarget">[]Association<wbr>Target</a></span>
    </dt>
    <dd>{{% md %}}A block containing the targets of the SSM association. Targets are documented below. AWS currently supports a maximum of 5 targets.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">association<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ID of the SSM association.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">association<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The descriptive name for the association.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">automation<wbr>Target<wbr>Parameter<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Specify the target for the association. This target is required for associations that use an `Automation` document and target resources by using rate controls.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">compliance<wbr>Severity<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The compliance severity for the association. Can be one of the following: `UNSPECIFIED`, `LOW`, `MEDIUM`, `HIGH` or `CRITICAL`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">document<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The document version you want to associate with the target(s). Can be a specific version or the default version.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">instance<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The instance ID to apply an SSM document to. Use `targets` with key `InstanceIds` for document schema versions 2.0 and above.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">max<wbr>Concurrency<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The maximum number of targets allowed to run the association at the same time. You can specify a number, for example 10, or a percentage of the target set, for example 10%.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">max<wbr>Errors<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The number of errors that are allowed before the system stops sending requests to run the association on additional targets. You can specify a number, for example 10, or a percentage of the target set, for example 10%.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the SSM document to apply.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">output<wbr>Location<span class="property-indicator"></span>
        <span class="property-type"><a href="#associationoutputlocation">Association<wbr>Output<wbr>Location?</a></span>
    </dt>
    <dd>{{% md %}}An output location block. Output Location is documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">parameters<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}A block of arbitrary string parameters to pass to the SSM document.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">schedule<wbr>Expression<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A cron expression when the association will be applied to the target(s).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">targets<span class="property-indicator"></span>
        <span class="property-type"><a href="#associationtarget">Association<wbr>Target[]?</a></span>
    </dt>
    <dd>{{% md %}}A block containing the targets of the SSM association. Targets are documented below. AWS currently supports a maximum of 5 targets.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">association_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ID of the SSM association.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">association_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The descriptive name for the association.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">automation_<wbr>target_<wbr>parameter_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Specify the target for the association. This target is required for associations that use an `Automation` document and target resources by using rate controls.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">compliance_<wbr>severity<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The compliance severity for the association. Can be one of the following: `UNSPECIFIED`, `LOW`, `MEDIUM`, `HIGH` or `CRITICAL`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">document_<wbr>version<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The document version you want to associate with the target(s). Can be a specific version or the default version.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">instance_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The instance ID to apply an SSM document to. Use `targets` with key `InstanceIds` for document schema versions 2.0 and above.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">max_<wbr>concurrency<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The maximum number of targets allowed to run the association at the same time. You can specify a number, for example 10, or a percentage of the target set, for example 10%.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">max_<wbr>errors<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The number of errors that are allowed before the system stops sending requests to run the association on additional targets. You can specify a number, for example 10, or a percentage of the target set, for example 10%.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the SSM document to apply.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">output_<wbr>location<span class="property-indicator"></span>
        <span class="property-type"><a href="#associationoutputlocation">Dict[Association<wbr>Output<wbr>Location]</a></span>
    </dt>
    <dd>{{% md %}}An output location block. Output Location is documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">parameters<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}A block of arbitrary string parameters to pass to the SSM document.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">schedule_<wbr>expression<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A cron expression when the association will be applied to the target(s).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">targets<span class="property-indicator"></span>
        <span class="property-type"><a href="#associationtarget">List[Association<wbr>Target]</a></span>
    </dt>
    <dd>{{% md %}}A block containing the targets of the SSM association. Targets are documented below. AWS currently supports a maximum of 5 targets.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}







## Supporting Types

#### AssociationOutputLocation
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#AssociationOutputLocation">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#AssociationOutputLocation">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ssm?tab=doc#AssociationOutputLocationArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ssm?tab=doc#AssociationOutputLocationOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ssm.AssociationOutputLocationArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ssm.AssociationOutputLocation.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">S3Bucket<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The S3 bucket name.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">S3Key<wbr>Prefix<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The S3 bucket prefix. Results stored in the root if not configured.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">S3Bucket<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The S3 bucket name.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">S3Key<wbr>Prefix<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The S3 bucket prefix. Results stored in the root if not configured.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">s3Bucket<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The S3 bucket name.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">s3Key<wbr>Prefix<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The S3 bucket prefix. Results stored in the root if not configured.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">s3_<wbr>bucket_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The S3 bucket name.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">s3_<wbr>key_<wbr>prefix<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The S3 bucket prefix. Results stored in the root if not configured.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### AssociationTarget
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#AssociationTarget">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#AssociationTarget">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ssm?tab=doc#AssociationTargetArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ssm?tab=doc#AssociationTargetOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ssm.AssociationTargetArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ssm.AssociationTarget.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Key<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Either `InstanceIds` or `tag:Tag Name` to specify an EC2 tag.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Values<span class="property-indicator"></span>
        <span class="property-type">List<string></span>
    </dt>
    <dd>{{% md %}}A list of instance IDs or tag values. AWS currently limits this list size to one value.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Key<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Either `InstanceIds` or `tag:Tag Name` to specify an EC2 tag.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Values<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}A list of instance IDs or tag values. AWS currently limits this list size to one value.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">key<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Either `InstanceIds` or `tag:Tag Name` to specify an EC2 tag.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">values<span class="property-indicator"></span>
        <span class="property-type">string[]</span>
    </dt>
    <dd>{{% md %}}A list of instance IDs or tag values. AWS currently limits this list size to one value.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">key<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Either `InstanceIds` or `tag:Tag Name` to specify an EC2 tag.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">values<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}A list of instance IDs or tag values. AWS currently limits this list size to one value.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}








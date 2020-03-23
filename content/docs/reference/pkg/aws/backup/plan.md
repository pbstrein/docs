
---
title: "Plan"
block_external_search_index: true
---

Provides an AWS Backup plan resource.

## Example Usage

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const example = new aws.backup.Plan("example", {
    rules: [{
        ruleName: "tf_example_backup_rule",
        schedule: "cron(0 12 * * ? *)",
        targetVaultName: aws_backup_vault_test.name,
    }],
});
```

> This content is derived from https://github.com/terraform-providers/terraform-provider-aws/blob/master/website/docs/r/backup_plan.html.markdown.



## Create a Plan Resource

{{< chooser language "javascript,typescript,python,go,csharp" / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/backup/#Plan">Plan</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/backup/#PlanArgs">PlanArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">Plan</span><span class="p">(resource_name, opts=None, </span>name=None<span class="p">, </span>rules=None<span class="p">, </span>tags=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewPlan<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/backup?tab=doc#PlanArgs">PlanArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/backup?tab=doc#Plan">Plan</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Backup.Plan.html">Plan</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Backup.PlanArgs.html">PlanArgs</a></span> <span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
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
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The display name of a backup plan.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Rules<span class="property-indicator"></span>
        <span class="property-type"><a href="#planrule">List&lt;Plan<wbr>Rule<wbr>Args&gt;</a></span>
    </dt>
    <dd>{{% md %}}A rule object that specifies a scheduled task that is used to back up a selection of resources.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}Metadata that you can assign to help organize the plans you create.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The display name of a backup plan.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Rules<span class="property-indicator"></span>
        <span class="property-type"><a href="#planrule">[]Plan<wbr>Rule</a></span>
    </dt>
    <dd>{{% md %}}A rule object that specifies a scheduled task that is used to back up a selection of resources.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}Metadata that you can assign to help organize the plans you create.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The display name of a backup plan.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">rules<span class="property-indicator"></span>
        <span class="property-type"><a href="#planrule">Plan<wbr>Rule[]</a></span>
    </dt>
    <dd>{{% md %}}A rule object that specifies a scheduled task that is used to back up a selection of resources.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}Metadata that you can assign to help organize the plans you create.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The display name of a backup plan.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">rules<span class="property-indicator"></span>
        <span class="property-type"><a href="#planrule">List[Plan<wbr>Rule]</a></span>
    </dt>
    <dd>{{% md %}}A rule object that specifies a scheduled task that is used to back up a selection of resources.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}Metadata that you can assign to help organize the plans you create.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}




## Plan Output Properties

The following output properties are available:




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of the backup plan.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The display name of a backup plan.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Rules<span class="property-indicator"></span>
        <span class="property-type"><a href="#planrule">List&lt;Plan<wbr>Rule&gt;</a></span>
    </dt>
    <dd>{{% md %}}A rule object that specifies a scheduled task that is used to back up a selection of resources.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}Metadata that you can assign to help organize the plans you create.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Version<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Unique, randomly generated, Unicode, UTF-8 encoded string that serves as the version ID of the backup plan.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of the backup plan.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The display name of a backup plan.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Rules<span class="property-indicator"></span>
        <span class="property-type"><a href="#planrule">[]Plan<wbr>Rule</a></span>
    </dt>
    <dd>{{% md %}}A rule object that specifies a scheduled task that is used to back up a selection of resources.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}Metadata that you can assign to help organize the plans you create.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Version<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Unique, randomly generated, Unicode, UTF-8 encoded string that serves as the version ID of the backup plan.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of the backup plan.
{{% /md %}}</dd>

    <dt class="property-"
            title="">name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The display name of a backup plan.
{{% /md %}}</dd>

    <dt class="property-"
            title="">rules<span class="property-indicator"></span>
        <span class="property-type"><a href="#planrule">Plan<wbr>Rule[]</a></span>
    </dt>
    <dd>{{% md %}}A rule object that specifies a scheduled task that is used to back up a selection of resources.
{{% /md %}}</dd>

    <dt class="property-"
            title="">tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}Metadata that you can assign to help organize the plans you create.
{{% /md %}}</dd>

    <dt class="property-"
            title="">version<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Unique, randomly generated, Unicode, UTF-8 encoded string that serves as the version ID of the backup plan.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ARN of the backup plan.
{{% /md %}}</dd>

    <dt class="property-"
            title="">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The display name of a backup plan.
{{% /md %}}</dd>

    <dt class="property-"
            title="">rules<span class="property-indicator"></span>
        <span class="property-type"><a href="#planrule">List[Plan<wbr>Rule]</a></span>
    </dt>
    <dd>{{% md %}}A rule object that specifies a scheduled task that is used to back up a selection of resources.
{{% /md %}}</dd>

    <dt class="property-"
            title="">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}Metadata that you can assign to help organize the plans you create.
{{% /md %}}</dd>

    <dt class="property-"
            title="">version<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Unique, randomly generated, Unicode, UTF-8 encoded string that serves as the version ID of the backup plan.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





## Look up an Existing Plan Resource

{{< chooser language "javascript,typescript,python,go,csharp  " / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">pulumi.Input&lt;pulumi.ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/backup/#PlanState">PlanState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/backup/#Plan">Plan</a></span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>arn=None<span class="p">, </span>name=None<span class="p">, </span>rules=None<span class="p">, </span>tags=None<span class="p">, </span>version=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetPlan<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">pulumi.IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/backup?tab=doc#PlanState">PlanState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/backup?tab=doc#Plan">Plan</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Backup.Plan.html">Plan</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Pulumi.Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Backup.PlanState.html">PlanState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
{{% /choosable %}}

Get an existing Plan resource's state with the given name, ID, and optional extra properties used to qualify the lookup.

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
    <dd>{{% md %}}The ARN of the backup plan.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The display name of a backup plan.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Rules<span class="property-indicator"></span>
        <span class="property-type"><a href="#planrule">List&lt;Plan<wbr>Rule<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}A rule object that specifies a scheduled task that is used to back up a selection of resources.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}Metadata that you can assign to help organize the plans you create.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Version<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Unique, randomly generated, Unicode, UTF-8 encoded string that serves as the version ID of the backup plan.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The ARN of the backup plan.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The display name of a backup plan.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Rules<span class="property-indicator"></span>
        <span class="property-type"><a href="#planrule">[]Plan<wbr>Rule</a></span>
    </dt>
    <dd>{{% md %}}A rule object that specifies a scheduled task that is used to back up a selection of resources.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}Metadata that you can assign to help organize the plans you create.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Version<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Unique, randomly generated, Unicode, UTF-8 encoded string that serves as the version ID of the backup plan.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ARN of the backup plan.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The display name of a backup plan.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">rules<span class="property-indicator"></span>
        <span class="property-type"><a href="#planrule">Plan<wbr>Rule[]?</a></span>
    </dt>
    <dd>{{% md %}}A rule object that specifies a scheduled task that is used to back up a selection of resources.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}Metadata that you can assign to help organize the plans you create.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">version<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Unique, randomly generated, Unicode, UTF-8 encoded string that serves as the version ID of the backup plan.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ARN of the backup plan.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The display name of a backup plan.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">rules<span class="property-indicator"></span>
        <span class="property-type"><a href="#planrule">List[Plan<wbr>Rule]</a></span>
    </dt>
    <dd>{{% md %}}A rule object that specifies a scheduled task that is used to back up a selection of resources.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}Metadata that you can assign to help organize the plans you create.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">version<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Unique, randomly generated, Unicode, UTF-8 encoded string that serves as the version ID of the backup plan.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}







## Supporting Types

#### PlanRule
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#PlanRule">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#PlanRule">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/backup?tab=doc#PlanRuleArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/backup?tab=doc#PlanRuleOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Backup.PlanRuleArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Backup.PlanRule.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Completion<wbr>Window<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The amount of time AWS Backup attempts a backup before canceling the job and returning an error.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Lifecycle<span class="property-indicator"></span>
        <span class="property-type"><a href="#planrulelifecycle">Plan<wbr>Rule<wbr>Lifecycle<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}The lifecycle defines when a protected resource is transitioned to cold storage and when it expires.  Fields documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Recovery<wbr>Point<wbr>Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}Metadata that you can assign to help organize the resources that you create.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Rule<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}An display name for a backup rule.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Schedule<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A CRON expression specifying when AWS Backup initiates a backup job.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Start<wbr>Window<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The amount of time in minutes before beginning a backup.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Target<wbr>Vault<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of a logical container where backups are stored.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Completion<wbr>Window<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The amount of time AWS Backup attempts a backup before canceling the job and returning an error.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Lifecycle<span class="property-indicator"></span>
        <span class="property-type"><a href="#planrulelifecycle">*Plan<wbr>Rule<wbr>Lifecycle</a></span>
    </dt>
    <dd>{{% md %}}The lifecycle defines when a protected resource is transitioned to cold storage and when it expires.  Fields documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Recovery<wbr>Point<wbr>Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}Metadata that you can assign to help organize the resources that you create.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Rule<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}An display name for a backup rule.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Schedule<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}A CRON expression specifying when AWS Backup initiates a backup job.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Start<wbr>Window<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The amount of time in minutes before beginning a backup.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Target<wbr>Vault<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of a logical container where backups are stored.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">completion<wbr>Window<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The amount of time AWS Backup attempts a backup before canceling the job and returning an error.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">lifecycle<span class="property-indicator"></span>
        <span class="property-type"><a href="#planrulelifecycle">Plan<wbr>Rule<wbr>Lifecycle?</a></span>
    </dt>
    <dd>{{% md %}}The lifecycle defines when a protected resource is transitioned to cold storage and when it expires.  Fields documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">recovery<wbr>Point<wbr>Tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}Metadata that you can assign to help organize the resources that you create.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">rule<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}An display name for a backup rule.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">schedule<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A CRON expression specifying when AWS Backup initiates a backup job.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">start<wbr>Window<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The amount of time in minutes before beginning a backup.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">target<wbr>Vault<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of a logical container where backups are stored.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">completion<wbr>Window<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The amount of time AWS Backup attempts a backup before canceling the job and returning an error.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">lifecycle<span class="property-indicator"></span>
        <span class="property-type"><a href="#planrulelifecycle">Dict[Plan<wbr>Rule<wbr>Lifecycle]</a></span>
    </dt>
    <dd>{{% md %}}The lifecycle defines when a protected resource is transitioned to cold storage and when it expires.  Fields documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">recovery<wbr>Point<wbr>Tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}Metadata that you can assign to help organize the resources that you create.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">rule_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}An display name for a backup rule.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">schedule<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A CRON expression specifying when AWS Backup initiates a backup job.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">start<wbr>Window<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The amount of time in minutes before beginning a backup.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">target<wbr>Vault<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of a logical container where backups are stored.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### PlanRuleLifecycle
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#PlanRuleLifecycle">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#PlanRuleLifecycle">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/backup?tab=doc#PlanRuleLifecycleArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/backup?tab=doc#PlanRuleLifecycleOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Backup.PlanRuleLifecycleArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Backup.PlanRuleLifecycle.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Cold<wbr>Storage<wbr>After<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}Specifies the number of days after creation that a recovery point is moved to cold storage.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Delete<wbr>After<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}Specifies the number of days after creation that a recovery point is deleted. Must be 90 days greater than `cold_storage_after`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Cold<wbr>Storage<wbr>After<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}Specifies the number of days after creation that a recovery point is moved to cold storage.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Delete<wbr>After<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}Specifies the number of days after creation that a recovery point is deleted. Must be 90 days greater than `cold_storage_after`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">cold<wbr>Storage<wbr>After<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}Specifies the number of days after creation that a recovery point is moved to cold storage.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">delete<wbr>After<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}Specifies the number of days after creation that a recovery point is deleted. Must be 90 days greater than `cold_storage_after`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">cold<wbr>Storage<wbr>After<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}Specifies the number of days after creation that a recovery point is moved to cold storage.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">delete<wbr>After<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}Specifies the number of days after creation that a recovery point is deleted. Must be 90 days greater than `cold_storage_after`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}








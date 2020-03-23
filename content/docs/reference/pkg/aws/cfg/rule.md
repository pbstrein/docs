
---
title: "Rule"
block_external_search_index: true
---

Provides an AWS Config Rule.

> **Note:** Config Rule requires an existing [Configuration Recorder](https://www.terraform.io/docs/providers/aws/r/config_configuration_recorder.html) to be present. Use of `depends_on` is recommended (as shown below) to avoid race conditions.

## Example Usage

### AWS Managed Rules

AWS managed rules can be used by setting the source owner to `AWS` and the source identifier to the name of the managed rule. More information about AWS managed rules can be found in the [AWS Config Developer Guide](https://docs.aws.amazon.com/config/latest/developerguide/evaluate-config_use-managed-rules.html).

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const role = new aws.iam.Role("r", {
    assumeRolePolicy: `{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Action": "sts:AssumeRole",
      "Principal": {
        "Service": "config.amazonaws.com"
      },
      "Effect": "Allow",
      "Sid": ""
    }
  ]
}
`,
});
const foo = new aws.cfg.Recorder("foo", {
    roleArn: role.arn,
});
const rule = new aws.cfg.Rule("r", {
    source: {
        owner: "AWS",
        sourceIdentifier: "S3_BUCKET_VERSIONING_ENABLED",
    },
}, {dependsOn: [foo]});
const rolePolicy = new aws.iam.RolePolicy("p", {
    policy: `{
  "Version": "2012-10-17",
  "Statement": [
  	{
  		"Action": "config:Put*",
  		"Effect": "Allow",
  		"Resource": "*"

  	}
  ]
}
`,
    role: role.id,
});
```

### Custom Rules

Custom rules can be used by setting the source owner to `CUSTOM_LAMBDA` and the source identifier to the Amazon Resource Name (ARN) of the Lambda Function. The AWS Config service must have permissions to invoke the Lambda Function, e.g. via the [`aws.lambda.Permission` resource](https://www.terraform.io/docs/providers/aws/r/lambda_permission.html). More information about custom rules can be found in the [AWS Config Developer Guide](https://docs.aws.amazon.com/config/latest/developerguide/evaluate-config_develop-rules.html).

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const exampleRecorder = new aws.cfg.Recorder("example", {});
const exampleFunction = new aws.lambda.Function("example", {});
const examplePermission = new aws.lambda.Permission("example", {
    action: "lambda:InvokeFunction",
    function: exampleFunction.arn,
    principal: "config.amazonaws.com",
});
const exampleRule = new aws.cfg.Rule("example", {
    source: {
        owner: "CUSTOM_LAMBDA",
        sourceIdentifier: exampleFunction.arn,
    },
}, {dependsOn: [exampleRecorder, examplePermission]});
```

> This content is derived from https://github.com/terraform-providers/terraform-provider-aws/blob/master/website/docs/r/config_config_rule.html.markdown.



## Create a Rule Resource

{{< chooser language "javascript,typescript,python,go,csharp" / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/cfg/#Rule">Rule</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/cfg/#RuleArgs">RuleArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">Rule</span><span class="p">(resource_name, opts=None, </span>description=None<span class="p">, </span>input_parameters=None<span class="p">, </span>maximum_execution_frequency=None<span class="p">, </span>name=None<span class="p">, </span>scope=None<span class="p">, </span>source=None<span class="p">, </span>tags=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewRule<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/cfg?tab=doc#RuleArgs">RuleArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/cfg?tab=doc#Rule">Rule</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Cfg.Rule.html">Rule</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Cfg.RuleArgs.html">RuleArgs</a></span> <span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
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
    <dd>{{% md %}}Description of the rule
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Input<wbr>Parameters<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A string in JSON format that is passed to the AWS Config rule Lambda function.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Maximum<wbr>Execution<wbr>Frequency<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The frequency that you want AWS Config to run evaluations for a rule that
is triggered periodically. If specified, requires `message_type` to be `ScheduledNotification`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the rule
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Scope<span class="property-indicator"></span>
        <span class="property-type"><a href="#rulescope">Rule<wbr>Scope<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}Scope defines which resources can trigger an evaluation for the rule as documented below.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Source<span class="property-indicator"></span>
        <span class="property-type"><a href="#rulesource">Rule<wbr>Source<wbr>Args</a></span>
    </dt>
    <dd>{{% md %}}Source specifies the rule owner, the rule identifier, and the notifications that cause
the function to evaluate your AWS resources as documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Description<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Description of the rule
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Input<wbr>Parameters<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}A string in JSON format that is passed to the AWS Config rule Lambda function.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Maximum<wbr>Execution<wbr>Frequency<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The frequency that you want AWS Config to run evaluations for a rule that
is triggered periodically. If specified, requires `message_type` to be `ScheduledNotification`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name of the rule
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Scope<span class="property-indicator"></span>
        <span class="property-type"><a href="#rulescope">*Rule<wbr>Scope</a></span>
    </dt>
    <dd>{{% md %}}Scope defines which resources can trigger an evaluation for the rule as documented below.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Source<span class="property-indicator"></span>
        <span class="property-type"><a href="#rulesource">Rule<wbr>Source</a></span>
    </dt>
    <dd>{{% md %}}Source specifies the rule owner, the rule identifier, and the notifications that cause
the function to evaluate your AWS resources as documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">description<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Description of the rule
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">input<wbr>Parameters<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A string in JSON format that is passed to the AWS Config rule Lambda function.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">maximum<wbr>Execution<wbr>Frequency<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The frequency that you want AWS Config to run evaluations for a rule that
is triggered periodically. If specified, requires `message_type` to be `ScheduledNotification`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the rule
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">scope<span class="property-indicator"></span>
        <span class="property-type"><a href="#rulescope">Rule<wbr>Scope?</a></span>
    </dt>
    <dd>{{% md %}}Scope defines which resources can trigger an evaluation for the rule as documented below.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">source<span class="property-indicator"></span>
        <span class="property-type"><a href="#rulesource">Rule<wbr>Source</a></span>
    </dt>
    <dd>{{% md %}}Source specifies the rule owner, the rule identifier, and the notifications that cause
the function to evaluate your AWS resources as documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">description<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Description of the rule
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">input_<wbr>parameters<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A string in JSON format that is passed to the AWS Config rule Lambda function.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">maximum_<wbr>execution_<wbr>frequency<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The frequency that you want AWS Config to run evaluations for a rule that
is triggered periodically. If specified, requires `message_type` to be `ScheduledNotification`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the rule
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">scope<span class="property-indicator"></span>
        <span class="property-type"><a href="#rulescope">Dict[Rule<wbr>Scope]</a></span>
    </dt>
    <dd>{{% md %}}Scope defines which resources can trigger an evaluation for the rule as documented below.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">source<span class="property-indicator"></span>
        <span class="property-type"><a href="#rulesource">Dict[Rule<wbr>Source]</a></span>
    </dt>
    <dd>{{% md %}}Source specifies the rule owner, the rule identifier, and the notifications that cause
the function to evaluate your AWS resources as documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}




## Rule Output Properties

The following output properties are available:




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of the config rule
{{% /md %}}</dd>

    <dt class="property-"
            title="">Description<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Description of the rule
{{% /md %}}</dd>

    <dt class="property-"
            title="">Input<wbr>Parameters<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A string in JSON format that is passed to the AWS Config rule Lambda function.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Maximum<wbr>Execution<wbr>Frequency<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The frequency that you want AWS Config to run evaluations for a rule that
is triggered periodically. If specified, requires `message_type` to be `ScheduledNotification`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the rule
{{% /md %}}</dd>

    <dt class="property-"
            title="">Rule<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the config rule
{{% /md %}}</dd>

    <dt class="property-"
            title="">Scope<span class="property-indicator"></span>
        <span class="property-type"><a href="#rulescope">Rule<wbr>Scope?</a></span>
    </dt>
    <dd>{{% md %}}Scope defines which resources can trigger an evaluation for the rule as documented below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Source<span class="property-indicator"></span>
        <span class="property-type"><a href="#rulesource">Rule<wbr>Source</a></span>
    </dt>
    <dd>{{% md %}}Source specifies the rule owner, the rule identifier, and the notifications that cause
the function to evaluate your AWS resources as documented below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of the config rule
{{% /md %}}</dd>

    <dt class="property-"
            title="">Description<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Description of the rule
{{% /md %}}</dd>

    <dt class="property-"
            title="">Input<wbr>Parameters<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}A string in JSON format that is passed to the AWS Config rule Lambda function.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Maximum<wbr>Execution<wbr>Frequency<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The frequency that you want AWS Config to run evaluations for a rule that
is triggered periodically. If specified, requires `message_type` to be `ScheduledNotification`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the rule
{{% /md %}}</dd>

    <dt class="property-"
            title="">Rule<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the config rule
{{% /md %}}</dd>

    <dt class="property-"
            title="">Scope<span class="property-indicator"></span>
        <span class="property-type"><a href="#rulescope">*Rule<wbr>Scope</a></span>
    </dt>
    <dd>{{% md %}}Scope defines which resources can trigger an evaluation for the rule as documented below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Source<span class="property-indicator"></span>
        <span class="property-type"><a href="#rulesource">Rule<wbr>Source</a></span>
    </dt>
    <dd>{{% md %}}Source specifies the rule owner, the rule identifier, and the notifications that cause
the function to evaluate your AWS resources as documented below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of the config rule
{{% /md %}}</dd>

    <dt class="property-"
            title="">description<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Description of the rule
{{% /md %}}</dd>

    <dt class="property-"
            title="">input<wbr>Parameters<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A string in JSON format that is passed to the AWS Config rule Lambda function.
{{% /md %}}</dd>

    <dt class="property-"
            title="">maximum<wbr>Execution<wbr>Frequency<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The frequency that you want AWS Config to run evaluations for a rule that
is triggered periodically. If specified, requires `message_type` to be `ScheduledNotification`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the rule
{{% /md %}}</dd>

    <dt class="property-"
            title="">rule<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the config rule
{{% /md %}}</dd>

    <dt class="property-"
            title="">scope<span class="property-indicator"></span>
        <span class="property-type"><a href="#rulescope">Rule<wbr>Scope?</a></span>
    </dt>
    <dd>{{% md %}}Scope defines which resources can trigger an evaluation for the rule as documented below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">source<span class="property-indicator"></span>
        <span class="property-type"><a href="#rulesource">Rule<wbr>Source</a></span>
    </dt>
    <dd>{{% md %}}Source specifies the rule owner, the rule identifier, and the notifications that cause
the function to evaluate your AWS resources as documented below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ARN of the config rule
{{% /md %}}</dd>

    <dt class="property-"
            title="">description<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Description of the rule
{{% /md %}}</dd>

    <dt class="property-"
            title="">input_<wbr>parameters<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A string in JSON format that is passed to the AWS Config rule Lambda function.
{{% /md %}}</dd>

    <dt class="property-"
            title="">maximum_<wbr>execution_<wbr>frequency<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The frequency that you want AWS Config to run evaluations for a rule that
is triggered periodically. If specified, requires `message_type` to be `ScheduledNotification`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the rule
{{% /md %}}</dd>

    <dt class="property-"
            title="">rule_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ID of the config rule
{{% /md %}}</dd>

    <dt class="property-"
            title="">scope<span class="property-indicator"></span>
        <span class="property-type"><a href="#rulescope">Dict[Rule<wbr>Scope]</a></span>
    </dt>
    <dd>{{% md %}}Scope defines which resources can trigger an evaluation for the rule as documented below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">source<span class="property-indicator"></span>
        <span class="property-type"><a href="#rulesource">Dict[Rule<wbr>Source]</a></span>
    </dt>
    <dd>{{% md %}}Source specifies the rule owner, the rule identifier, and the notifications that cause
the function to evaluate your AWS resources as documented below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





## Look up an Existing Rule Resource

{{< chooser language "javascript,typescript,python,go,csharp  " / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">pulumi.Input&lt;pulumi.ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/cfg/#RuleState">RuleState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/cfg/#Rule">Rule</a></span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>arn=None<span class="p">, </span>description=None<span class="p">, </span>input_parameters=None<span class="p">, </span>maximum_execution_frequency=None<span class="p">, </span>name=None<span class="p">, </span>rule_id=None<span class="p">, </span>scope=None<span class="p">, </span>source=None<span class="p">, </span>tags=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetRule<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">pulumi.IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/cfg?tab=doc#RuleState">RuleState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/cfg?tab=doc#Rule">Rule</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Cfg.Rule.html">Rule</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Pulumi.Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Cfg.RuleState.html">RuleState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
{{% /choosable %}}

Get an existing Rule resource's state with the given name, ID, and optional extra properties used to qualify the lookup.

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
    <dd>{{% md %}}The ARN of the config rule
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Description<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Description of the rule
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Input<wbr>Parameters<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A string in JSON format that is passed to the AWS Config rule Lambda function.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Maximum<wbr>Execution<wbr>Frequency<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The frequency that you want AWS Config to run evaluations for a rule that
is triggered periodically. If specified, requires `message_type` to be `ScheduledNotification`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the rule
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Rule<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ID of the config rule
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Scope<span class="property-indicator"></span>
        <span class="property-type"><a href="#rulescope">Rule<wbr>Scope<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}Scope defines which resources can trigger an evaluation for the rule as documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Source<span class="property-indicator"></span>
        <span class="property-type"><a href="#rulesource">Rule<wbr>Source<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}Source specifies the rule owner, the rule identifier, and the notifications that cause
the function to evaluate your AWS resources as documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The ARN of the config rule
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Description<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Description of the rule
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Input<wbr>Parameters<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}A string in JSON format that is passed to the AWS Config rule Lambda function.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Maximum<wbr>Execution<wbr>Frequency<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The frequency that you want AWS Config to run evaluations for a rule that
is triggered periodically. If specified, requires `message_type` to be `ScheduledNotification`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name of the rule
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Rule<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The ID of the config rule
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Scope<span class="property-indicator"></span>
        <span class="property-type"><a href="#rulescope">*Rule<wbr>Scope</a></span>
    </dt>
    <dd>{{% md %}}Scope defines which resources can trigger an evaluation for the rule as documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Source<span class="property-indicator"></span>
        <span class="property-type"><a href="#rulesource">*Rule<wbr>Source</a></span>
    </dt>
    <dd>{{% md %}}Source specifies the rule owner, the rule identifier, and the notifications that cause
the function to evaluate your AWS resources as documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ARN of the config rule
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">description<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Description of the rule
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">input<wbr>Parameters<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A string in JSON format that is passed to the AWS Config rule Lambda function.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">maximum<wbr>Execution<wbr>Frequency<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The frequency that you want AWS Config to run evaluations for a rule that
is triggered periodically. If specified, requires `message_type` to be `ScheduledNotification`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the rule
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">rule<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ID of the config rule
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">scope<span class="property-indicator"></span>
        <span class="property-type"><a href="#rulescope">Rule<wbr>Scope?</a></span>
    </dt>
    <dd>{{% md %}}Scope defines which resources can trigger an evaluation for the rule as documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">source<span class="property-indicator"></span>
        <span class="property-type"><a href="#rulesource">Rule<wbr>Source?</a></span>
    </dt>
    <dd>{{% md %}}Source specifies the rule owner, the rule identifier, and the notifications that cause
the function to evaluate your AWS resources as documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ARN of the config rule
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">description<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Description of the rule
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">input_<wbr>parameters<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A string in JSON format that is passed to the AWS Config rule Lambda function.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">maximum_<wbr>execution_<wbr>frequency<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The frequency that you want AWS Config to run evaluations for a rule that
is triggered periodically. If specified, requires `message_type` to be `ScheduledNotification`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the rule
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">rule_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ID of the config rule
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">scope<span class="property-indicator"></span>
        <span class="property-type"><a href="#rulescope">Dict[Rule<wbr>Scope]</a></span>
    </dt>
    <dd>{{% md %}}Scope defines which resources can trigger an evaluation for the rule as documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">source<span class="property-indicator"></span>
        <span class="property-type"><a href="#rulesource">Dict[Rule<wbr>Source]</a></span>
    </dt>
    <dd>{{% md %}}Source specifies the rule owner, the rule identifier, and the notifications that cause
the function to evaluate your AWS resources as documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}







## Supporting Types

#### RuleScope
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#RuleScope">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#RuleScope">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/cfg?tab=doc#RuleScopeArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/cfg?tab=doc#RuleScopeOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Cfg.RuleScopeArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Cfg.RuleScope.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Compliance<wbr>Resource<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The IDs of the only AWS resource that you want to trigger an evaluation for the rule.
If you specify a resource ID, you must specify one resource type for `compliance_resource_types`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Compliance<wbr>Resource<wbr>Types<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}A list of resource types of only those AWS resources that you want to trigger an
evaluation for the rule. e.g. `AWS::EC2::Instance`. You can only specify one type if you also specify
a resource ID for `compliance_resource_id`. See [relevant part of AWS Docs](http://docs.aws.amazon.com/config/latest/APIReference/API_ResourceIdentifier.html#config-Type-ResourceIdentifier-resourceType) for available types.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tag<wbr>Key<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The tag key that is applied to only those AWS resources that you want you
want to trigger an evaluation for the rule.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tag<wbr>Value<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The tag value applied to only those AWS resources that you want to trigger an evaluation for the rule.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Compliance<wbr>Resource<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The IDs of the only AWS resource that you want to trigger an evaluation for the rule.
If you specify a resource ID, you must specify one resource type for `compliance_resource_types`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Compliance<wbr>Resource<wbr>Types<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}A list of resource types of only those AWS resources that you want to trigger an
evaluation for the rule. e.g. `AWS::EC2::Instance`. You can only specify one type if you also specify
a resource ID for `compliance_resource_id`. See [relevant part of AWS Docs](http://docs.aws.amazon.com/config/latest/APIReference/API_ResourceIdentifier.html#config-Type-ResourceIdentifier-resourceType) for available types.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tag<wbr>Key<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The tag key that is applied to only those AWS resources that you want you
want to trigger an evaluation for the rule.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tag<wbr>Value<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The tag value applied to only those AWS resources that you want to trigger an evaluation for the rule.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">compliance<wbr>Resource<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The IDs of the only AWS resource that you want to trigger an evaluation for the rule.
If you specify a resource ID, you must specify one resource type for `compliance_resource_types`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">compliance<wbr>Resource<wbr>Types<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}A list of resource types of only those AWS resources that you want to trigger an
evaluation for the rule. e.g. `AWS::EC2::Instance`. You can only specify one type if you also specify
a resource ID for `compliance_resource_id`. See [relevant part of AWS Docs](http://docs.aws.amazon.com/config/latest/APIReference/API_ResourceIdentifier.html#config-Type-ResourceIdentifier-resourceType) for available types.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tag<wbr>Key<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The tag key that is applied to only those AWS resources that you want you
want to trigger an evaluation for the rule.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tag<wbr>Value<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The tag value applied to only those AWS resources that you want to trigger an evaluation for the rule.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">compliance<wbr>Resource<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The IDs of the only AWS resource that you want to trigger an evaluation for the rule.
If you specify a resource ID, you must specify one resource type for `compliance_resource_types`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">compliance<wbr>Resource<wbr>Types<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}A list of resource types of only those AWS resources that you want to trigger an
evaluation for the rule. e.g. `AWS::EC2::Instance`. You can only specify one type if you also specify
a resource ID for `compliance_resource_id`. See [relevant part of AWS Docs](http://docs.aws.amazon.com/config/latest/APIReference/API_ResourceIdentifier.html#config-Type-ResourceIdentifier-resourceType) for available types.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tag<wbr>Key<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The tag key that is applied to only those AWS resources that you want you
want to trigger an evaluation for the rule.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tag<wbr>Value<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The tag value applied to only those AWS resources that you want to trigger an evaluation for the rule.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### RuleSource
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#RuleSource">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#RuleSource">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/cfg?tab=doc#RuleSourceArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/cfg?tab=doc#RuleSourceOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Cfg.RuleSourceArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Cfg.RuleSource.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Owner<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Indicates whether AWS or the customer owns and manages the AWS Config rule. Valid values are `AWS` or `CUSTOM_LAMBDA`. For more information about managed rules, see the [AWS Config Managed Rules documentation](https://docs.aws.amazon.com/config/latest/developerguide/evaluate-config_use-managed-rules.html). For more information about custom rules, see the [AWS Config Custom Rules documentation](https://docs.aws.amazon.com/config/latest/developerguide/evaluate-config_develop-rules.html). Custom Lambda Functions require permissions to allow the AWS Config service to invoke them, e.g. via the [`aws.lambda.Permission` resource](https://www.terraform.io/docs/providers/aws/r/lambda_permission.html).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Source<wbr>Details<span class="property-indicator"></span>
        <span class="property-type"><a href="#rulesourcesourcedetail">List&lt;Rule<wbr>Source<wbr>Source<wbr>Detail<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}Provides the source and type of the event that causes AWS Config to evaluate your AWS resources. Only valid if `owner` is `CUSTOM_LAMBDA`.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Source<wbr>Identifier<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}For AWS Config managed rules, a predefined identifier, e.g `IAM_PASSWORD_POLICY`. For custom Lambda rules, the identifier is the ARN of the Lambda Function, such as `arn:aws:lambda:us-east-1:123456789012:function:custom_rule_name` or the [`arn` attribute of the `aws.lambda.Function` resource](https://www.terraform.io/docs/providers/aws/r/lambda_function.html#arn).
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Owner<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Indicates whether AWS or the customer owns and manages the AWS Config rule. Valid values are `AWS` or `CUSTOM_LAMBDA`. For more information about managed rules, see the [AWS Config Managed Rules documentation](https://docs.aws.amazon.com/config/latest/developerguide/evaluate-config_use-managed-rules.html). For more information about custom rules, see the [AWS Config Custom Rules documentation](https://docs.aws.amazon.com/config/latest/developerguide/evaluate-config_develop-rules.html). Custom Lambda Functions require permissions to allow the AWS Config service to invoke them, e.g. via the [`aws.lambda.Permission` resource](https://www.terraform.io/docs/providers/aws/r/lambda_permission.html).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Source<wbr>Details<span class="property-indicator"></span>
        <span class="property-type"><a href="#rulesourcesourcedetail">[]Rule<wbr>Source<wbr>Source<wbr>Detail</a></span>
    </dt>
    <dd>{{% md %}}Provides the source and type of the event that causes AWS Config to evaluate your AWS resources. Only valid if `owner` is `CUSTOM_LAMBDA`.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Source<wbr>Identifier<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}For AWS Config managed rules, a predefined identifier, e.g `IAM_PASSWORD_POLICY`. For custom Lambda rules, the identifier is the ARN of the Lambda Function, such as `arn:aws:lambda:us-east-1:123456789012:function:custom_rule_name` or the [`arn` attribute of the `aws.lambda.Function` resource](https://www.terraform.io/docs/providers/aws/r/lambda_function.html#arn).
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">owner<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Indicates whether AWS or the customer owns and manages the AWS Config rule. Valid values are `AWS` or `CUSTOM_LAMBDA`. For more information about managed rules, see the [AWS Config Managed Rules documentation](https://docs.aws.amazon.com/config/latest/developerguide/evaluate-config_use-managed-rules.html). For more information about custom rules, see the [AWS Config Custom Rules documentation](https://docs.aws.amazon.com/config/latest/developerguide/evaluate-config_develop-rules.html). Custom Lambda Functions require permissions to allow the AWS Config service to invoke them, e.g. via the [`aws.lambda.Permission` resource](https://www.terraform.io/docs/providers/aws/r/lambda_permission.html).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">source<wbr>Details<span class="property-indicator"></span>
        <span class="property-type"><a href="#rulesourcesourcedetail">Rule<wbr>Source<wbr>Source<wbr>Detail[]?</a></span>
    </dt>
    <dd>{{% md %}}Provides the source and type of the event that causes AWS Config to evaluate your AWS resources. Only valid if `owner` is `CUSTOM_LAMBDA`.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">source<wbr>Identifier<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}For AWS Config managed rules, a predefined identifier, e.g `IAM_PASSWORD_POLICY`. For custom Lambda rules, the identifier is the ARN of the Lambda Function, such as `arn:aws:lambda:us-east-1:123456789012:function:custom_rule_name` or the [`arn` attribute of the `aws.lambda.Function` resource](https://www.terraform.io/docs/providers/aws/r/lambda_function.html#arn).
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">owner<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Indicates whether AWS or the customer owns and manages the AWS Config rule. Valid values are `AWS` or `CUSTOM_LAMBDA`. For more information about managed rules, see the [AWS Config Managed Rules documentation](https://docs.aws.amazon.com/config/latest/developerguide/evaluate-config_use-managed-rules.html). For more information about custom rules, see the [AWS Config Custom Rules documentation](https://docs.aws.amazon.com/config/latest/developerguide/evaluate-config_develop-rules.html). Custom Lambda Functions require permissions to allow the AWS Config service to invoke them, e.g. via the [`aws.lambda.Permission` resource](https://www.terraform.io/docs/providers/aws/r/lambda_permission.html).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">source<wbr>Details<span class="property-indicator"></span>
        <span class="property-type"><a href="#rulesourcesourcedetail">List[Rule<wbr>Source<wbr>Source<wbr>Detail]</a></span>
    </dt>
    <dd>{{% md %}}Provides the source and type of the event that causes AWS Config to evaluate your AWS resources. Only valid if `owner` is `CUSTOM_LAMBDA`.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">source<wbr>Identifier<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}For AWS Config managed rules, a predefined identifier, e.g `IAM_PASSWORD_POLICY`. For custom Lambda rules, the identifier is the ARN of the Lambda Function, such as `arn:aws:lambda:us-east-1:123456789012:function:custom_rule_name` or the [`arn` attribute of the `aws.lambda.Function` resource](https://www.terraform.io/docs/providers/aws/r/lambda_function.html#arn).
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### RuleSourceSourceDetail
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#RuleSourceSourceDetail">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#RuleSourceSourceDetail">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/cfg?tab=doc#RuleSourceSourceDetailArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/cfg?tab=doc#RuleSourceSourceDetailOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Cfg.RuleSourceSourceDetailArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Cfg.RuleSourceSourceDetail.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Event<wbr>Source<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The source of the event, such as an AWS service, that triggers AWS Config
to evaluate your AWS resources. This defaults to `aws.config` and is the only valid value.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Maximum<wbr>Execution<wbr>Frequency<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The frequency that you want AWS Config to run evaluations for a rule that
is triggered periodically. If specified, requires `message_type` to be `ScheduledNotification`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Message<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The type of notification that triggers AWS Config to run an evaluation for a rule. You can specify the following notification types:
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Event<wbr>Source<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The source of the event, such as an AWS service, that triggers AWS Config
to evaluate your AWS resources. This defaults to `aws.config` and is the only valid value.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Maximum<wbr>Execution<wbr>Frequency<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The frequency that you want AWS Config to run evaluations for a rule that
is triggered periodically. If specified, requires `message_type` to be `ScheduledNotification`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Message<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The type of notification that triggers AWS Config to run an evaluation for a rule. You can specify the following notification types:
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">event<wbr>Source<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The source of the event, such as an AWS service, that triggers AWS Config
to evaluate your AWS resources. This defaults to `aws.config` and is the only valid value.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">maximum<wbr>Execution<wbr>Frequency<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The frequency that you want AWS Config to run evaluations for a rule that
is triggered periodically. If specified, requires `message_type` to be `ScheduledNotification`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">message<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The type of notification that triggers AWS Config to run an evaluation for a rule. You can specify the following notification types:
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">event<wbr>Source<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The source of the event, such as an AWS service, that triggers AWS Config
to evaluate your AWS resources. This defaults to `aws.config` and is the only valid value.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">maximum_<wbr>execution_<wbr>frequency<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The frequency that you want AWS Config to run evaluations for a rule that
is triggered periodically. If specified, requires `message_type` to be `ScheduledNotification`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">message<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The type of notification that triggers AWS Config to run an evaluation for a rule. You can specify the following notification types:
{{% /md %}}</dd>

</dl>
{{% /choosable %}}








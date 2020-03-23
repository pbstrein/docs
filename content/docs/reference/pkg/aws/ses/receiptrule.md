
---
title: "ReceiptRule"
block_external_search_index: true
---

Provides an SES receipt rule resource

## Example Usage

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

// Add a header to the email and store it in S3
const store = new aws.ses.ReceiptRule("store", {
    addHeaderActions: [{
        headerName: "Custom-Header",
        headerValue: "Added by SES",
        position: 1,
    }],
    enabled: true,
    recipients: ["karen@example.com"],
    ruleSetName: "default-rule-set",
    s3Actions: [{
        bucketName: "emails",
        position: 2,
    }],
    scanEnabled: true,
});
```

> This content is derived from https://github.com/terraform-providers/terraform-provider-aws/blob/master/website/docs/r/ses_receipt_rule.html.markdown.



## Create a ReceiptRule Resource

{{< chooser language "javascript,typescript,python,go,csharp" / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/ses/#ReceiptRule">ReceiptRule</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/ses/#ReceiptRuleArgs">ReceiptRuleArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">ReceiptRule</span><span class="p">(resource_name, opts=None, </span>add_header_actions=None<span class="p">, </span>after=None<span class="p">, </span>bounce_actions=None<span class="p">, </span>enabled=None<span class="p">, </span>lambda_actions=None<span class="p">, </span>name=None<span class="p">, </span>recipients=None<span class="p">, </span>rule_set_name=None<span class="p">, </span>s3_actions=None<span class="p">, </span>scan_enabled=None<span class="p">, </span>sns_actions=None<span class="p">, </span>stop_actions=None<span class="p">, </span>tls_policy=None<span class="p">, </span>workmail_actions=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewReceiptRule<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ses?tab=doc#ReceiptRuleArgs">ReceiptRuleArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ses?tab=doc#ReceiptRule">ReceiptRule</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ses.ReceiptRule.html">ReceiptRule</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ses.ReceiptRuleArgs.html">ReceiptRuleArgs</a></span> <span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
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
            title="Optional">Add<wbr>Header<wbr>Actions<span class="property-indicator"></span>
        <span class="property-type"><a href="#receiptruleaddheaderaction">List&lt;Receipt<wbr>Rule<wbr>Add<wbr>Header<wbr>Action<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}A list of Add Header Action blocks. Documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">After<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the rule to place this rule after
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Bounce<wbr>Actions<span class="property-indicator"></span>
        <span class="property-type"><a href="#receiptrulebounceaction">List&lt;Receipt<wbr>Rule<wbr>Bounce<wbr>Action<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}A list of Bounce Action blocks. Documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Enabled<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}If true, the rule will be enabled
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Lambda<wbr>Actions<span class="property-indicator"></span>
        <span class="property-type"><a href="#receiptrulelambdaaction">List&lt;Receipt<wbr>Rule<wbr>Lambda<wbr>Action<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}A list of Lambda Action blocks. Documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the rule
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Recipients<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}A list of email addresses
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Rule<wbr>Set<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the rule set
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">S3Actions<span class="property-indicator"></span>
        <span class="property-type"><a href="#receiptrules3action">List&lt;Receipt<wbr>Rule<wbr>S3Action<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}A list of S3 Action blocks. Documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Scan<wbr>Enabled<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}If true, incoming emails will be scanned for spam and viruses
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Sns<wbr>Actions<span class="property-indicator"></span>
        <span class="property-type"><a href="#receiptrulesnsaction">List&lt;Receipt<wbr>Rule<wbr>Sns<wbr>Action<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}A list of SNS Action blocks. Documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Stop<wbr>Actions<span class="property-indicator"></span>
        <span class="property-type"><a href="#receiptrulestopaction">List&lt;Receipt<wbr>Rule<wbr>Stop<wbr>Action<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}A list of Stop Action blocks. Documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tls<wbr>Policy<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Require or Optional
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Workmail<wbr>Actions<span class="property-indicator"></span>
        <span class="property-type"><a href="#receiptruleworkmailaction">List&lt;Receipt<wbr>Rule<wbr>Workmail<wbr>Action<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}A list of WorkMail Action blocks. Documented below.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Add<wbr>Header<wbr>Actions<span class="property-indicator"></span>
        <span class="property-type"><a href="#receiptruleaddheaderaction">[]Receipt<wbr>Rule<wbr>Add<wbr>Header<wbr>Action</a></span>
    </dt>
    <dd>{{% md %}}A list of Add Header Action blocks. Documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">After<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name of the rule to place this rule after
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Bounce<wbr>Actions<span class="property-indicator"></span>
        <span class="property-type"><a href="#receiptrulebounceaction">[]Receipt<wbr>Rule<wbr>Bounce<wbr>Action</a></span>
    </dt>
    <dd>{{% md %}}A list of Bounce Action blocks. Documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Enabled<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}If true, the rule will be enabled
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Lambda<wbr>Actions<span class="property-indicator"></span>
        <span class="property-type"><a href="#receiptrulelambdaaction">[]Receipt<wbr>Rule<wbr>Lambda<wbr>Action</a></span>
    </dt>
    <dd>{{% md %}}A list of Lambda Action blocks. Documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name of the rule
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Recipients<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}A list of email addresses
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Rule<wbr>Set<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the rule set
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">S3Actions<span class="property-indicator"></span>
        <span class="property-type"><a href="#receiptrules3action">[]Receipt<wbr>Rule<wbr>S3Action</a></span>
    </dt>
    <dd>{{% md %}}A list of S3 Action blocks. Documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Scan<wbr>Enabled<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}If true, incoming emails will be scanned for spam and viruses
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Sns<wbr>Actions<span class="property-indicator"></span>
        <span class="property-type"><a href="#receiptrulesnsaction">[]Receipt<wbr>Rule<wbr>Sns<wbr>Action</a></span>
    </dt>
    <dd>{{% md %}}A list of SNS Action blocks. Documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Stop<wbr>Actions<span class="property-indicator"></span>
        <span class="property-type"><a href="#receiptrulestopaction">[]Receipt<wbr>Rule<wbr>Stop<wbr>Action</a></span>
    </dt>
    <dd>{{% md %}}A list of Stop Action blocks. Documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tls<wbr>Policy<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Require or Optional
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Workmail<wbr>Actions<span class="property-indicator"></span>
        <span class="property-type"><a href="#receiptruleworkmailaction">[]Receipt<wbr>Rule<wbr>Workmail<wbr>Action</a></span>
    </dt>
    <dd>{{% md %}}A list of WorkMail Action blocks. Documented below.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">add<wbr>Header<wbr>Actions<span class="property-indicator"></span>
        <span class="property-type"><a href="#receiptruleaddheaderaction">Receipt<wbr>Rule<wbr>Add<wbr>Header<wbr>Action[]?</a></span>
    </dt>
    <dd>{{% md %}}A list of Add Header Action blocks. Documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">after<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the rule to place this rule after
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">bounce<wbr>Actions<span class="property-indicator"></span>
        <span class="property-type"><a href="#receiptrulebounceaction">Receipt<wbr>Rule<wbr>Bounce<wbr>Action[]?</a></span>
    </dt>
    <dd>{{% md %}}A list of Bounce Action blocks. Documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">enabled<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}If true, the rule will be enabled
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">lambda<wbr>Actions<span class="property-indicator"></span>
        <span class="property-type"><a href="#receiptrulelambdaaction">Receipt<wbr>Rule<wbr>Lambda<wbr>Action[]?</a></span>
    </dt>
    <dd>{{% md %}}A list of Lambda Action blocks. Documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the rule
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">recipients<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}A list of email addresses
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">rule<wbr>Set<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the rule set
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">s3Actions<span class="property-indicator"></span>
        <span class="property-type"><a href="#receiptrules3action">Receipt<wbr>Rule<wbr>S3Action[]?</a></span>
    </dt>
    <dd>{{% md %}}A list of S3 Action blocks. Documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">scan<wbr>Enabled<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}If true, incoming emails will be scanned for spam and viruses
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">sns<wbr>Actions<span class="property-indicator"></span>
        <span class="property-type"><a href="#receiptrulesnsaction">Receipt<wbr>Rule<wbr>Sns<wbr>Action[]?</a></span>
    </dt>
    <dd>{{% md %}}A list of SNS Action blocks. Documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">stop<wbr>Actions<span class="property-indicator"></span>
        <span class="property-type"><a href="#receiptrulestopaction">Receipt<wbr>Rule<wbr>Stop<wbr>Action[]?</a></span>
    </dt>
    <dd>{{% md %}}A list of Stop Action blocks. Documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tls<wbr>Policy<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Require or Optional
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">workmail<wbr>Actions<span class="property-indicator"></span>
        <span class="property-type"><a href="#receiptruleworkmailaction">Receipt<wbr>Rule<wbr>Workmail<wbr>Action[]?</a></span>
    </dt>
    <dd>{{% md %}}A list of WorkMail Action blocks. Documented below.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">add_<wbr>header_<wbr>actions<span class="property-indicator"></span>
        <span class="property-type"><a href="#receiptruleaddheaderaction">List[Receipt<wbr>Rule<wbr>Add<wbr>Header<wbr>Action]</a></span>
    </dt>
    <dd>{{% md %}}A list of Add Header Action blocks. Documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">after<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the rule to place this rule after
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">bounce_<wbr>actions<span class="property-indicator"></span>
        <span class="property-type"><a href="#receiptrulebounceaction">List[Receipt<wbr>Rule<wbr>Bounce<wbr>Action]</a></span>
    </dt>
    <dd>{{% md %}}A list of Bounce Action blocks. Documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">enabled<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}If true, the rule will be enabled
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">lambda_<wbr>actions<span class="property-indicator"></span>
        <span class="property-type"><a href="#receiptrulelambdaaction">List[Receipt<wbr>Rule<wbr>Lambda<wbr>Action]</a></span>
    </dt>
    <dd>{{% md %}}A list of Lambda Action blocks. Documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the rule
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">recipients<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}A list of email addresses
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">rule_<wbr>set_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the rule set
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">s3_<wbr>actions<span class="property-indicator"></span>
        <span class="property-type"><a href="#receiptrules3action">List[Receipt<wbr>Rule<wbr>S3Action]</a></span>
    </dt>
    <dd>{{% md %}}A list of S3 Action blocks. Documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">scan_<wbr>enabled<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}If true, incoming emails will be scanned for spam and viruses
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">sns_<wbr>actions<span class="property-indicator"></span>
        <span class="property-type"><a href="#receiptrulesnsaction">List[Receipt<wbr>Rule<wbr>Sns<wbr>Action]</a></span>
    </dt>
    <dd>{{% md %}}A list of SNS Action blocks. Documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">stop_<wbr>actions<span class="property-indicator"></span>
        <span class="property-type"><a href="#receiptrulestopaction">List[Receipt<wbr>Rule<wbr>Stop<wbr>Action]</a></span>
    </dt>
    <dd>{{% md %}}A list of Stop Action blocks. Documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tls_<wbr>policy<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Require or Optional
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">workmail_<wbr>actions<span class="property-indicator"></span>
        <span class="property-type"><a href="#receiptruleworkmailaction">List[Receipt<wbr>Rule<wbr>Workmail<wbr>Action]</a></span>
    </dt>
    <dd>{{% md %}}A list of WorkMail Action blocks. Documented below.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}




## ReceiptRule Output Properties

The following output properties are available:




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Add<wbr>Header<wbr>Actions<span class="property-indicator"></span>
        <span class="property-type"><a href="#receiptruleaddheaderaction">List&lt;Receipt<wbr>Rule<wbr>Add<wbr>Header<wbr>Action&gt;?</a></span>
    </dt>
    <dd>{{% md %}}A list of Add Header Action blocks. Documented below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">After<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the rule to place this rule after
{{% /md %}}</dd>

    <dt class="property-"
            title="">Bounce<wbr>Actions<span class="property-indicator"></span>
        <span class="property-type"><a href="#receiptrulebounceaction">List&lt;Receipt<wbr>Rule<wbr>Bounce<wbr>Action&gt;?</a></span>
    </dt>
    <dd>{{% md %}}A list of Bounce Action blocks. Documented below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Enabled<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}If true, the rule will be enabled
{{% /md %}}</dd>

    <dt class="property-"
            title="">Lambda<wbr>Actions<span class="property-indicator"></span>
        <span class="property-type"><a href="#receiptrulelambdaaction">List&lt;Receipt<wbr>Rule<wbr>Lambda<wbr>Action&gt;?</a></span>
    </dt>
    <dd>{{% md %}}A list of Lambda Action blocks. Documented below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the rule
{{% /md %}}</dd>

    <dt class="property-"
            title="">Recipients<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}A list of email addresses
{{% /md %}}</dd>

    <dt class="property-"
            title="">Rule<wbr>Set<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the rule set
{{% /md %}}</dd>

    <dt class="property-"
            title="">S3Actions<span class="property-indicator"></span>
        <span class="property-type"><a href="#receiptrules3action">List&lt;Receipt<wbr>Rule<wbr>S3Action&gt;?</a></span>
    </dt>
    <dd>{{% md %}}A list of S3 Action blocks. Documented below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Scan<wbr>Enabled<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}If true, incoming emails will be scanned for spam and viruses
{{% /md %}}</dd>

    <dt class="property-"
            title="">Sns<wbr>Actions<span class="property-indicator"></span>
        <span class="property-type"><a href="#receiptrulesnsaction">List&lt;Receipt<wbr>Rule<wbr>Sns<wbr>Action&gt;?</a></span>
    </dt>
    <dd>{{% md %}}A list of SNS Action blocks. Documented below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Stop<wbr>Actions<span class="property-indicator"></span>
        <span class="property-type"><a href="#receiptrulestopaction">List&lt;Receipt<wbr>Rule<wbr>Stop<wbr>Action&gt;?</a></span>
    </dt>
    <dd>{{% md %}}A list of Stop Action blocks. Documented below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Tls<wbr>Policy<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Require or Optional
{{% /md %}}</dd>

    <dt class="property-"
            title="">Workmail<wbr>Actions<span class="property-indicator"></span>
        <span class="property-type"><a href="#receiptruleworkmailaction">List&lt;Receipt<wbr>Rule<wbr>Workmail<wbr>Action&gt;?</a></span>
    </dt>
    <dd>{{% md %}}A list of WorkMail Action blocks. Documented below.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Add<wbr>Header<wbr>Actions<span class="property-indicator"></span>
        <span class="property-type"><a href="#receiptruleaddheaderaction">[]Receipt<wbr>Rule<wbr>Add<wbr>Header<wbr>Action</a></span>
    </dt>
    <dd>{{% md %}}A list of Add Header Action blocks. Documented below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">After<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name of the rule to place this rule after
{{% /md %}}</dd>

    <dt class="property-"
            title="">Bounce<wbr>Actions<span class="property-indicator"></span>
        <span class="property-type"><a href="#receiptrulebounceaction">[]Receipt<wbr>Rule<wbr>Bounce<wbr>Action</a></span>
    </dt>
    <dd>{{% md %}}A list of Bounce Action blocks. Documented below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Enabled<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}If true, the rule will be enabled
{{% /md %}}</dd>

    <dt class="property-"
            title="">Lambda<wbr>Actions<span class="property-indicator"></span>
        <span class="property-type"><a href="#receiptrulelambdaaction">[]Receipt<wbr>Rule<wbr>Lambda<wbr>Action</a></span>
    </dt>
    <dd>{{% md %}}A list of Lambda Action blocks. Documented below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the rule
{{% /md %}}</dd>

    <dt class="property-"
            title="">Recipients<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}A list of email addresses
{{% /md %}}</dd>

    <dt class="property-"
            title="">Rule<wbr>Set<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the rule set
{{% /md %}}</dd>

    <dt class="property-"
            title="">S3Actions<span class="property-indicator"></span>
        <span class="property-type"><a href="#receiptrules3action">[]Receipt<wbr>Rule<wbr>S3Action</a></span>
    </dt>
    <dd>{{% md %}}A list of S3 Action blocks. Documented below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Scan<wbr>Enabled<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}If true, incoming emails will be scanned for spam and viruses
{{% /md %}}</dd>

    <dt class="property-"
            title="">Sns<wbr>Actions<span class="property-indicator"></span>
        <span class="property-type"><a href="#receiptrulesnsaction">[]Receipt<wbr>Rule<wbr>Sns<wbr>Action</a></span>
    </dt>
    <dd>{{% md %}}A list of SNS Action blocks. Documented below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Stop<wbr>Actions<span class="property-indicator"></span>
        <span class="property-type"><a href="#receiptrulestopaction">[]Receipt<wbr>Rule<wbr>Stop<wbr>Action</a></span>
    </dt>
    <dd>{{% md %}}A list of Stop Action blocks. Documented below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Tls<wbr>Policy<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Require or Optional
{{% /md %}}</dd>

    <dt class="property-"
            title="">Workmail<wbr>Actions<span class="property-indicator"></span>
        <span class="property-type"><a href="#receiptruleworkmailaction">[]Receipt<wbr>Rule<wbr>Workmail<wbr>Action</a></span>
    </dt>
    <dd>{{% md %}}A list of WorkMail Action blocks. Documented below.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">add<wbr>Header<wbr>Actions<span class="property-indicator"></span>
        <span class="property-type"><a href="#receiptruleaddheaderaction">Receipt<wbr>Rule<wbr>Add<wbr>Header<wbr>Action[]?</a></span>
    </dt>
    <dd>{{% md %}}A list of Add Header Action blocks. Documented below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">after<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the rule to place this rule after
{{% /md %}}</dd>

    <dt class="property-"
            title="">bounce<wbr>Actions<span class="property-indicator"></span>
        <span class="property-type"><a href="#receiptrulebounceaction">Receipt<wbr>Rule<wbr>Bounce<wbr>Action[]?</a></span>
    </dt>
    <dd>{{% md %}}A list of Bounce Action blocks. Documented below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">enabled<span class="property-indicator"></span>
        <span class="property-type">boolean</span>
    </dt>
    <dd>{{% md %}}If true, the rule will be enabled
{{% /md %}}</dd>

    <dt class="property-"
            title="">lambda<wbr>Actions<span class="property-indicator"></span>
        <span class="property-type"><a href="#receiptrulelambdaaction">Receipt<wbr>Rule<wbr>Lambda<wbr>Action[]?</a></span>
    </dt>
    <dd>{{% md %}}A list of Lambda Action blocks. Documented below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the rule
{{% /md %}}</dd>

    <dt class="property-"
            title="">recipients<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}A list of email addresses
{{% /md %}}</dd>

    <dt class="property-"
            title="">rule<wbr>Set<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the rule set
{{% /md %}}</dd>

    <dt class="property-"
            title="">s3Actions<span class="property-indicator"></span>
        <span class="property-type"><a href="#receiptrules3action">Receipt<wbr>Rule<wbr>S3Action[]?</a></span>
    </dt>
    <dd>{{% md %}}A list of S3 Action blocks. Documented below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">scan<wbr>Enabled<span class="property-indicator"></span>
        <span class="property-type">boolean</span>
    </dt>
    <dd>{{% md %}}If true, incoming emails will be scanned for spam and viruses
{{% /md %}}</dd>

    <dt class="property-"
            title="">sns<wbr>Actions<span class="property-indicator"></span>
        <span class="property-type"><a href="#receiptrulesnsaction">Receipt<wbr>Rule<wbr>Sns<wbr>Action[]?</a></span>
    </dt>
    <dd>{{% md %}}A list of SNS Action blocks. Documented below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">stop<wbr>Actions<span class="property-indicator"></span>
        <span class="property-type"><a href="#receiptrulestopaction">Receipt<wbr>Rule<wbr>Stop<wbr>Action[]?</a></span>
    </dt>
    <dd>{{% md %}}A list of Stop Action blocks. Documented below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">tls<wbr>Policy<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Require or Optional
{{% /md %}}</dd>

    <dt class="property-"
            title="">workmail<wbr>Actions<span class="property-indicator"></span>
        <span class="property-type"><a href="#receiptruleworkmailaction">Receipt<wbr>Rule<wbr>Workmail<wbr>Action[]?</a></span>
    </dt>
    <dd>{{% md %}}A list of WorkMail Action blocks. Documented below.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">add_<wbr>header_<wbr>actions<span class="property-indicator"></span>
        <span class="property-type"><a href="#receiptruleaddheaderaction">List[Receipt<wbr>Rule<wbr>Add<wbr>Header<wbr>Action]</a></span>
    </dt>
    <dd>{{% md %}}A list of Add Header Action blocks. Documented below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">after<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the rule to place this rule after
{{% /md %}}</dd>

    <dt class="property-"
            title="">bounce_<wbr>actions<span class="property-indicator"></span>
        <span class="property-type"><a href="#receiptrulebounceaction">List[Receipt<wbr>Rule<wbr>Bounce<wbr>Action]</a></span>
    </dt>
    <dd>{{% md %}}A list of Bounce Action blocks. Documented below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">enabled<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}If true, the rule will be enabled
{{% /md %}}</dd>

    <dt class="property-"
            title="">lambda_<wbr>actions<span class="property-indicator"></span>
        <span class="property-type"><a href="#receiptrulelambdaaction">List[Receipt<wbr>Rule<wbr>Lambda<wbr>Action]</a></span>
    </dt>
    <dd>{{% md %}}A list of Lambda Action blocks. Documented below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the rule
{{% /md %}}</dd>

    <dt class="property-"
            title="">recipients<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}A list of email addresses
{{% /md %}}</dd>

    <dt class="property-"
            title="">rule_<wbr>set_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the rule set
{{% /md %}}</dd>

    <dt class="property-"
            title="">s3_<wbr>actions<span class="property-indicator"></span>
        <span class="property-type"><a href="#receiptrules3action">List[Receipt<wbr>Rule<wbr>S3Action]</a></span>
    </dt>
    <dd>{{% md %}}A list of S3 Action blocks. Documented below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">scan_<wbr>enabled<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}If true, incoming emails will be scanned for spam and viruses
{{% /md %}}</dd>

    <dt class="property-"
            title="">sns_<wbr>actions<span class="property-indicator"></span>
        <span class="property-type"><a href="#receiptrulesnsaction">List[Receipt<wbr>Rule<wbr>Sns<wbr>Action]</a></span>
    </dt>
    <dd>{{% md %}}A list of SNS Action blocks. Documented below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">stop_<wbr>actions<span class="property-indicator"></span>
        <span class="property-type"><a href="#receiptrulestopaction">List[Receipt<wbr>Rule<wbr>Stop<wbr>Action]</a></span>
    </dt>
    <dd>{{% md %}}A list of Stop Action blocks. Documented below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">tls_<wbr>policy<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Require or Optional
{{% /md %}}</dd>

    <dt class="property-"
            title="">workmail_<wbr>actions<span class="property-indicator"></span>
        <span class="property-type"><a href="#receiptruleworkmailaction">List[Receipt<wbr>Rule<wbr>Workmail<wbr>Action]</a></span>
    </dt>
    <dd>{{% md %}}A list of WorkMail Action blocks. Documented below.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





## Look up an Existing ReceiptRule Resource

{{< chooser language "javascript,typescript,python,go,csharp  " / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">pulumi.Input&lt;pulumi.ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/ses/#ReceiptRuleState">ReceiptRuleState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/ses/#ReceiptRule">ReceiptRule</a></span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>add_header_actions=None<span class="p">, </span>after=None<span class="p">, </span>bounce_actions=None<span class="p">, </span>enabled=None<span class="p">, </span>lambda_actions=None<span class="p">, </span>name=None<span class="p">, </span>recipients=None<span class="p">, </span>rule_set_name=None<span class="p">, </span>s3_actions=None<span class="p">, </span>scan_enabled=None<span class="p">, </span>sns_actions=None<span class="p">, </span>stop_actions=None<span class="p">, </span>tls_policy=None<span class="p">, </span>workmail_actions=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetReceiptRule<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">pulumi.IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ses?tab=doc#ReceiptRuleState">ReceiptRuleState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ses?tab=doc#ReceiptRule">ReceiptRule</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ses.ReceiptRule.html">ReceiptRule</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Pulumi.Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ses.ReceiptRuleState.html">ReceiptRuleState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
{{% /choosable %}}

Get an existing ReceiptRule resource's state with the given name, ID, and optional extra properties used to qualify the lookup.

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
            title="Optional">Add<wbr>Header<wbr>Actions<span class="property-indicator"></span>
        <span class="property-type"><a href="#receiptruleaddheaderaction">List&lt;Receipt<wbr>Rule<wbr>Add<wbr>Header<wbr>Action<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}A list of Add Header Action blocks. Documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">After<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the rule to place this rule after
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Bounce<wbr>Actions<span class="property-indicator"></span>
        <span class="property-type"><a href="#receiptrulebounceaction">List&lt;Receipt<wbr>Rule<wbr>Bounce<wbr>Action<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}A list of Bounce Action blocks. Documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Enabled<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}If true, the rule will be enabled
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Lambda<wbr>Actions<span class="property-indicator"></span>
        <span class="property-type"><a href="#receiptrulelambdaaction">List&lt;Receipt<wbr>Rule<wbr>Lambda<wbr>Action<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}A list of Lambda Action blocks. Documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the rule
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Recipients<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}A list of email addresses
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Rule<wbr>Set<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the rule set
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">S3Actions<span class="property-indicator"></span>
        <span class="property-type"><a href="#receiptrules3action">List&lt;Receipt<wbr>Rule<wbr>S3Action<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}A list of S3 Action blocks. Documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Scan<wbr>Enabled<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}If true, incoming emails will be scanned for spam and viruses
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Sns<wbr>Actions<span class="property-indicator"></span>
        <span class="property-type"><a href="#receiptrulesnsaction">List&lt;Receipt<wbr>Rule<wbr>Sns<wbr>Action<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}A list of SNS Action blocks. Documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Stop<wbr>Actions<span class="property-indicator"></span>
        <span class="property-type"><a href="#receiptrulestopaction">List&lt;Receipt<wbr>Rule<wbr>Stop<wbr>Action<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}A list of Stop Action blocks. Documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tls<wbr>Policy<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Require or Optional
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Workmail<wbr>Actions<span class="property-indicator"></span>
        <span class="property-type"><a href="#receiptruleworkmailaction">List&lt;Receipt<wbr>Rule<wbr>Workmail<wbr>Action<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}A list of WorkMail Action blocks. Documented below.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Add<wbr>Header<wbr>Actions<span class="property-indicator"></span>
        <span class="property-type"><a href="#receiptruleaddheaderaction">[]Receipt<wbr>Rule<wbr>Add<wbr>Header<wbr>Action</a></span>
    </dt>
    <dd>{{% md %}}A list of Add Header Action blocks. Documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">After<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name of the rule to place this rule after
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Bounce<wbr>Actions<span class="property-indicator"></span>
        <span class="property-type"><a href="#receiptrulebounceaction">[]Receipt<wbr>Rule<wbr>Bounce<wbr>Action</a></span>
    </dt>
    <dd>{{% md %}}A list of Bounce Action blocks. Documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Enabled<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}If true, the rule will be enabled
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Lambda<wbr>Actions<span class="property-indicator"></span>
        <span class="property-type"><a href="#receiptrulelambdaaction">[]Receipt<wbr>Rule<wbr>Lambda<wbr>Action</a></span>
    </dt>
    <dd>{{% md %}}A list of Lambda Action blocks. Documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name of the rule
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Recipients<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}A list of email addresses
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Rule<wbr>Set<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name of the rule set
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">S3Actions<span class="property-indicator"></span>
        <span class="property-type"><a href="#receiptrules3action">[]Receipt<wbr>Rule<wbr>S3Action</a></span>
    </dt>
    <dd>{{% md %}}A list of S3 Action blocks. Documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Scan<wbr>Enabled<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}If true, incoming emails will be scanned for spam and viruses
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Sns<wbr>Actions<span class="property-indicator"></span>
        <span class="property-type"><a href="#receiptrulesnsaction">[]Receipt<wbr>Rule<wbr>Sns<wbr>Action</a></span>
    </dt>
    <dd>{{% md %}}A list of SNS Action blocks. Documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Stop<wbr>Actions<span class="property-indicator"></span>
        <span class="property-type"><a href="#receiptrulestopaction">[]Receipt<wbr>Rule<wbr>Stop<wbr>Action</a></span>
    </dt>
    <dd>{{% md %}}A list of Stop Action blocks. Documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tls<wbr>Policy<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Require or Optional
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Workmail<wbr>Actions<span class="property-indicator"></span>
        <span class="property-type"><a href="#receiptruleworkmailaction">[]Receipt<wbr>Rule<wbr>Workmail<wbr>Action</a></span>
    </dt>
    <dd>{{% md %}}A list of WorkMail Action blocks. Documented below.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">add<wbr>Header<wbr>Actions<span class="property-indicator"></span>
        <span class="property-type"><a href="#receiptruleaddheaderaction">Receipt<wbr>Rule<wbr>Add<wbr>Header<wbr>Action[]?</a></span>
    </dt>
    <dd>{{% md %}}A list of Add Header Action blocks. Documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">after<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the rule to place this rule after
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">bounce<wbr>Actions<span class="property-indicator"></span>
        <span class="property-type"><a href="#receiptrulebounceaction">Receipt<wbr>Rule<wbr>Bounce<wbr>Action[]?</a></span>
    </dt>
    <dd>{{% md %}}A list of Bounce Action blocks. Documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">enabled<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}If true, the rule will be enabled
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">lambda<wbr>Actions<span class="property-indicator"></span>
        <span class="property-type"><a href="#receiptrulelambdaaction">Receipt<wbr>Rule<wbr>Lambda<wbr>Action[]?</a></span>
    </dt>
    <dd>{{% md %}}A list of Lambda Action blocks. Documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the rule
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">recipients<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}A list of email addresses
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">rule<wbr>Set<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the rule set
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">s3Actions<span class="property-indicator"></span>
        <span class="property-type"><a href="#receiptrules3action">Receipt<wbr>Rule<wbr>S3Action[]?</a></span>
    </dt>
    <dd>{{% md %}}A list of S3 Action blocks. Documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">scan<wbr>Enabled<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}If true, incoming emails will be scanned for spam and viruses
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">sns<wbr>Actions<span class="property-indicator"></span>
        <span class="property-type"><a href="#receiptrulesnsaction">Receipt<wbr>Rule<wbr>Sns<wbr>Action[]?</a></span>
    </dt>
    <dd>{{% md %}}A list of SNS Action blocks. Documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">stop<wbr>Actions<span class="property-indicator"></span>
        <span class="property-type"><a href="#receiptrulestopaction">Receipt<wbr>Rule<wbr>Stop<wbr>Action[]?</a></span>
    </dt>
    <dd>{{% md %}}A list of Stop Action blocks. Documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tls<wbr>Policy<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Require or Optional
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">workmail<wbr>Actions<span class="property-indicator"></span>
        <span class="property-type"><a href="#receiptruleworkmailaction">Receipt<wbr>Rule<wbr>Workmail<wbr>Action[]?</a></span>
    </dt>
    <dd>{{% md %}}A list of WorkMail Action blocks. Documented below.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">add_<wbr>header_<wbr>actions<span class="property-indicator"></span>
        <span class="property-type"><a href="#receiptruleaddheaderaction">List[Receipt<wbr>Rule<wbr>Add<wbr>Header<wbr>Action]</a></span>
    </dt>
    <dd>{{% md %}}A list of Add Header Action blocks. Documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">after<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the rule to place this rule after
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">bounce_<wbr>actions<span class="property-indicator"></span>
        <span class="property-type"><a href="#receiptrulebounceaction">List[Receipt<wbr>Rule<wbr>Bounce<wbr>Action]</a></span>
    </dt>
    <dd>{{% md %}}A list of Bounce Action blocks. Documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">enabled<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}If true, the rule will be enabled
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">lambda_<wbr>actions<span class="property-indicator"></span>
        <span class="property-type"><a href="#receiptrulelambdaaction">List[Receipt<wbr>Rule<wbr>Lambda<wbr>Action]</a></span>
    </dt>
    <dd>{{% md %}}A list of Lambda Action blocks. Documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the rule
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">recipients<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}A list of email addresses
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">rule_<wbr>set_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the rule set
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">s3_<wbr>actions<span class="property-indicator"></span>
        <span class="property-type"><a href="#receiptrules3action">List[Receipt<wbr>Rule<wbr>S3Action]</a></span>
    </dt>
    <dd>{{% md %}}A list of S3 Action blocks. Documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">scan_<wbr>enabled<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}If true, incoming emails will be scanned for spam and viruses
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">sns_<wbr>actions<span class="property-indicator"></span>
        <span class="property-type"><a href="#receiptrulesnsaction">List[Receipt<wbr>Rule<wbr>Sns<wbr>Action]</a></span>
    </dt>
    <dd>{{% md %}}A list of SNS Action blocks. Documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">stop_<wbr>actions<span class="property-indicator"></span>
        <span class="property-type"><a href="#receiptrulestopaction">List[Receipt<wbr>Rule<wbr>Stop<wbr>Action]</a></span>
    </dt>
    <dd>{{% md %}}A list of Stop Action blocks. Documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tls_<wbr>policy<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Require or Optional
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">workmail_<wbr>actions<span class="property-indicator"></span>
        <span class="property-type"><a href="#receiptruleworkmailaction">List[Receipt<wbr>Rule<wbr>Workmail<wbr>Action]</a></span>
    </dt>
    <dd>{{% md %}}A list of WorkMail Action blocks. Documented below.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}







## Supporting Types

#### ReceiptRuleAddHeaderAction
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#ReceiptRuleAddHeaderAction">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#ReceiptRuleAddHeaderAction">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ses?tab=doc#ReceiptRuleAddHeaderActionArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ses?tab=doc#ReceiptRuleAddHeaderActionOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ses.ReceiptRuleAddHeaderActionArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ses.ReceiptRuleAddHeaderAction.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Header<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the header to add
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Header<wbr>Value<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The value of the header to add
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Position<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The position of the action in the receipt rule
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Header<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the header to add
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Header<wbr>Value<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The value of the header to add
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Position<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The position of the action in the receipt rule
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">header<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the header to add
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">header<wbr>Value<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The value of the header to add
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">position<span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}The position of the action in the receipt rule
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">header<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the header to add
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">header<wbr>Value<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The value of the header to add
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">position<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The position of the action in the receipt rule
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### ReceiptRuleBounceAction
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#ReceiptRuleBounceAction">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#ReceiptRuleBounceAction">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ses?tab=doc#ReceiptRuleBounceActionArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ses?tab=doc#ReceiptRuleBounceActionOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ses.ReceiptRuleBounceActionArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ses.ReceiptRuleBounceAction.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Message<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The message to send
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Position<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The position of the action in the receipt rule
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Sender<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The email address of the sender
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Smtp<wbr>Reply<wbr>Code<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The RFC 5321 SMTP reply code
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Status<wbr>Code<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The RFC 3463 SMTP enhanced status code
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Topic<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ARN of an SNS topic to notify
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Message<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The message to send
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Position<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The position of the action in the receipt rule
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Sender<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The email address of the sender
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Smtp<wbr>Reply<wbr>Code<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The RFC 5321 SMTP reply code
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Status<wbr>Code<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The RFC 3463 SMTP enhanced status code
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Topic<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The ARN of an SNS topic to notify
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">message<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The message to send
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">position<span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}The position of the action in the receipt rule
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">sender<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The email address of the sender
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">smtp<wbr>Reply<wbr>Code<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The RFC 5321 SMTP reply code
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">status<wbr>Code<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The RFC 3463 SMTP enhanced status code
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">topic<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ARN of an SNS topic to notify
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">message<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The message to send
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">position<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The position of the action in the receipt rule
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">sender<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The email address of the sender
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">smtp<wbr>Reply<wbr>Code<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The RFC 5321 SMTP reply code
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">status_<wbr>code<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The RFC 3463 SMTP enhanced status code
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">topic_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ARN of an SNS topic to notify
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### ReceiptRuleLambdaAction
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#ReceiptRuleLambdaAction">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#ReceiptRuleLambdaAction">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ses?tab=doc#ReceiptRuleLambdaActionArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ses?tab=doc#ReceiptRuleLambdaActionOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ses.ReceiptRuleLambdaActionArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ses.ReceiptRuleLambdaAction.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Function<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of the Lambda function to invoke
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Invocation<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Event or RequestResponse
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Position<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The position of the action in the receipt rule
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Topic<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ARN of an SNS topic to notify
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Function<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of the Lambda function to invoke
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Invocation<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Event or RequestResponse
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Position<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The position of the action in the receipt rule
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Topic<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The ARN of an SNS topic to notify
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">function<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of the Lambda function to invoke
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">invocation<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Event or RequestResponse
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">position<span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}The position of the action in the receipt rule
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">topic<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ARN of an SNS topic to notify
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">function_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ARN of the Lambda function to invoke
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">invocation<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Event or RequestResponse
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">position<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The position of the action in the receipt rule
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">topic_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ARN of an SNS topic to notify
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### ReceiptRuleS3Action
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#ReceiptRuleS3Action">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#ReceiptRuleS3Action">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ses?tab=doc#ReceiptRuleS3ActionArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ses?tab=doc#ReceiptRuleS3ActionOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ses.ReceiptRuleS3ActionArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ses.ReceiptRuleS3Action.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Bucket<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the S3 bucket
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Kms<wbr>Key<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ARN of the KMS key
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Object<wbr>Key<wbr>Prefix<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The key prefix of the S3 bucket
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Position<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The position of the action in the receipt rule
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Topic<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ARN of an SNS topic to notify
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Bucket<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the S3 bucket
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Kms<wbr>Key<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The ARN of the KMS key
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Object<wbr>Key<wbr>Prefix<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The key prefix of the S3 bucket
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Position<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The position of the action in the receipt rule
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Topic<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The ARN of an SNS topic to notify
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">bucket<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the S3 bucket
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">kms<wbr>Key<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ARN of the KMS key
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">object<wbr>Key<wbr>Prefix<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The key prefix of the S3 bucket
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">position<span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}The position of the action in the receipt rule
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">topic<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ARN of an SNS topic to notify
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">bucket_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the S3 bucket
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">kms_<wbr>key_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ARN of the KMS key
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">object<wbr>Key<wbr>Prefix<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The key prefix of the S3 bucket
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">position<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The position of the action in the receipt rule
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">topic_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ARN of an SNS topic to notify
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### ReceiptRuleSnsAction
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#ReceiptRuleSnsAction">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#ReceiptRuleSnsAction">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ses?tab=doc#ReceiptRuleSnsActionArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ses?tab=doc#ReceiptRuleSnsActionOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ses.ReceiptRuleSnsActionArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ses.ReceiptRuleSnsAction.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Position<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The position of the action in the receipt rule
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Topic<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of an SNS topic to notify
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Position<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The position of the action in the receipt rule
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Topic<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of an SNS topic to notify
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">position<span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}The position of the action in the receipt rule
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">topic<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of an SNS topic to notify
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">position<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The position of the action in the receipt rule
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">topic_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ARN of an SNS topic to notify
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### ReceiptRuleStopAction
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#ReceiptRuleStopAction">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#ReceiptRuleStopAction">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ses?tab=doc#ReceiptRuleStopActionArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ses?tab=doc#ReceiptRuleStopActionOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ses.ReceiptRuleStopActionArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ses.ReceiptRuleStopAction.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Position<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The position of the action in the receipt rule
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Scope<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The scope to apply
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Topic<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ARN of an SNS topic to notify
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Position<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The position of the action in the receipt rule
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Scope<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The scope to apply
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Topic<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The ARN of an SNS topic to notify
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">position<span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}The position of the action in the receipt rule
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">scope<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The scope to apply
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">topic<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ARN of an SNS topic to notify
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">position<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The position of the action in the receipt rule
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">scope<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The scope to apply
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">topic_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ARN of an SNS topic to notify
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### ReceiptRuleWorkmailAction
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#ReceiptRuleWorkmailAction">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#ReceiptRuleWorkmailAction">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ses?tab=doc#ReceiptRuleWorkmailActionArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ses?tab=doc#ReceiptRuleWorkmailActionOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ses.ReceiptRuleWorkmailActionArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ses.ReceiptRuleWorkmailAction.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Organization<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of the WorkMail organization
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Position<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The position of the action in the receipt rule
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Topic<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ARN of an SNS topic to notify
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Organization<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of the WorkMail organization
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Position<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The position of the action in the receipt rule
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Topic<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The ARN of an SNS topic to notify
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">organization<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of the WorkMail organization
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">position<span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}The position of the action in the receipt rule
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">topic<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ARN of an SNS topic to notify
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">organization<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ARN of the WorkMail organization
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">position<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The position of the action in the receipt rule
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">topic_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ARN of an SNS topic to notify
{{% /md %}}</dd>

</dl>
{{% /choosable %}}








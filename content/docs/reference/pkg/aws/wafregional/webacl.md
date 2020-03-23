
---
title: "WebAcl"
block_external_search_index: true
---

Provides a WAF Regional Web ACL Resource for use with Application Load Balancer.

## Example Usage

### Regular Rule

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const ipset = new aws.wafregional.IpSet("ipset", {
    ipSetDescriptors: [{
        type: "IPV4",
        value: "192.0.7.0/24",
    }],
});
const wafrule = new aws.wafregional.Rule("wafrule", {
    metricName: "tfWAFRule",
    predicates: [{
        dataId: ipset.id,
        negated: false,
        type: "IPMatch",
    }],
});
const wafacl = new aws.wafregional.WebAcl("wafacl", {
    defaultAction: {
        type: "ALLOW",
    },
    metricName: "tfWebACL",
    rules: [{
        action: {
            type: "BLOCK",
        },
        priority: 1,
        ruleId: wafrule.id,
        type: "REGULAR",
    }],
});
```

### Group Rule

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const example = new aws.wafregional.WebAcl("example", {
    defaultAction: {
        type: "ALLOW",
    },
    metricName: "example",
    rules: [{
        overrideAction: {
            type: "NONE",
        },
        priority: 1,
        ruleId: aws_wafregional_rule_group_example.id,
        type: "GROUP",
    }],
});
```

### Logging

> *NOTE:* The Kinesis Firehose Delivery Stream name must begin with `aws-waf-logs-`. See the [AWS WAF Developer Guide](https://docs.aws.amazon.com/waf/latest/developerguide/logging.html) for more information about enabling WAF logging.

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const example = new aws.wafregional.WebAcl("example", {
    loggingConfiguration: {
        logDestination: aws_kinesis_firehose_delivery_stream_example.arn,
        redactedFields: {
            fieldToMatches: [
                {
                    type: "URI",
                },
                {
                    data: "referer",
                    type: "HEADER",
                },
            ],
        },
    },
});
```

> This content is derived from https://github.com/terraform-providers/terraform-provider-aws/blob/master/website/docs/r/wafregional_web_acl.html.markdown.



## Create a WebAcl Resource

{{< chooser language "javascript,typescript,python,go,csharp" / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/wafregional/#WebAcl">WebAcl</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/wafregional/#WebAclArgs">WebAclArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">WebAcl</span><span class="p">(resource_name, opts=None, </span>default_action=None<span class="p">, </span>logging_configuration=None<span class="p">, </span>metric_name=None<span class="p">, </span>name=None<span class="p">, </span>rules=None<span class="p">, </span>tags=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewWebAcl<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/wafregional?tab=doc#WebAclArgs">WebAclArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/wafregional?tab=doc#WebAcl">WebAcl</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Wafregional.WebAcl.html">WebAcl</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Wafregional.WebAclArgs.html">WebAclArgs</a></span> <span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
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
            title="Required">Default<wbr>Action<span class="property-indicator"></span>
        <span class="property-type"><a href="#webacldefaultaction">Web<wbr>Acl<wbr>Default<wbr>Action<wbr>Args</a></span>
    </dt>
    <dd>{{% md %}}The action that you want AWS WAF Regional to take when a request doesn&#39;t match the criteria in any of the rules that are associated with the web ACL.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Logging<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#webaclloggingconfiguration">Web<wbr>Acl<wbr>Logging<wbr>Configuration<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}Configuration block to enable WAF logging. Detailed below.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Metric<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name or description for the Amazon CloudWatch metric of this web ACL.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name or description of the web ACL.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Rules<span class="property-indicator"></span>
        <span class="property-type"><a href="#webaclrule">List&lt;Web<wbr>Acl<wbr>Rule<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}Set of configuration blocks containing rules for the web ACL. Detailed below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}Key-value mapping of resource tags
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Default<wbr>Action<span class="property-indicator"></span>
        <span class="property-type"><a href="#webacldefaultaction">Web<wbr>Acl<wbr>Default<wbr>Action</a></span>
    </dt>
    <dd>{{% md %}}The action that you want AWS WAF Regional to take when a request doesn&#39;t match the criteria in any of the rules that are associated with the web ACL.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Logging<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#webaclloggingconfiguration">*Web<wbr>Acl<wbr>Logging<wbr>Configuration</a></span>
    </dt>
    <dd>{{% md %}}Configuration block to enable WAF logging. Detailed below.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Metric<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name or description for the Amazon CloudWatch metric of this web ACL.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name or description of the web ACL.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Rules<span class="property-indicator"></span>
        <span class="property-type"><a href="#webaclrule">[]Web<wbr>Acl<wbr>Rule</a></span>
    </dt>
    <dd>{{% md %}}Set of configuration blocks containing rules for the web ACL. Detailed below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}Key-value mapping of resource tags
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">default<wbr>Action<span class="property-indicator"></span>
        <span class="property-type"><a href="#webacldefaultaction">Web<wbr>Acl<wbr>Default<wbr>Action</a></span>
    </dt>
    <dd>{{% md %}}The action that you want AWS WAF Regional to take when a request doesn&#39;t match the criteria in any of the rules that are associated with the web ACL.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">logging<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#webaclloggingconfiguration">Web<wbr>Acl<wbr>Logging<wbr>Configuration?</a></span>
    </dt>
    <dd>{{% md %}}Configuration block to enable WAF logging. Detailed below.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">metric<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name or description for the Amazon CloudWatch metric of this web ACL.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name or description of the web ACL.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">rules<span class="property-indicator"></span>
        <span class="property-type"><a href="#webaclrule">Web<wbr>Acl<wbr>Rule[]?</a></span>
    </dt>
    <dd>{{% md %}}Set of configuration blocks containing rules for the web ACL. Detailed below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}Key-value mapping of resource tags
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">default_<wbr>action<span class="property-indicator"></span>
        <span class="property-type"><a href="#webacldefaultaction">Dict[Web<wbr>Acl<wbr>Default<wbr>Action]</a></span>
    </dt>
    <dd>{{% md %}}The action that you want AWS WAF Regional to take when a request doesn&#39;t match the criteria in any of the rules that are associated with the web ACL.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">logging_<wbr>configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#webaclloggingconfiguration">Dict[Web<wbr>Acl<wbr>Logging<wbr>Configuration]</a></span>
    </dt>
    <dd>{{% md %}}Configuration block to enable WAF logging. Detailed below.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">metric_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name or description for the Amazon CloudWatch metric of this web ACL.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name or description of the web ACL.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">rules<span class="property-indicator"></span>
        <span class="property-type"><a href="#webaclrule">List[Web<wbr>Acl<wbr>Rule]</a></span>
    </dt>
    <dd>{{% md %}}Set of configuration blocks containing rules for the web ACL. Detailed below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}Key-value mapping of resource tags
{{% /md %}}</dd>

</dl>
{{% /choosable %}}




## WebAcl Output Properties

The following output properties are available:




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of the WAF Regional WebACL.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Default<wbr>Action<span class="property-indicator"></span>
        <span class="property-type"><a href="#webacldefaultaction">Web<wbr>Acl<wbr>Default<wbr>Action</a></span>
    </dt>
    <dd>{{% md %}}The action that you want AWS WAF Regional to take when a request doesn&#39;t match the criteria in any of the rules that are associated with the web ACL.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Logging<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#webaclloggingconfiguration">Web<wbr>Acl<wbr>Logging<wbr>Configuration?</a></span>
    </dt>
    <dd>{{% md %}}Configuration block to enable WAF logging. Detailed below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Metric<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name or description for the Amazon CloudWatch metric of this web ACL.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name or description of the web ACL.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Rules<span class="property-indicator"></span>
        <span class="property-type"><a href="#webaclrule">List&lt;Web<wbr>Acl<wbr>Rule&gt;?</a></span>
    </dt>
    <dd>{{% md %}}Set of configuration blocks containing rules for the web ACL. Detailed below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}Key-value mapping of resource tags
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of the WAF Regional WebACL.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Default<wbr>Action<span class="property-indicator"></span>
        <span class="property-type"><a href="#webacldefaultaction">Web<wbr>Acl<wbr>Default<wbr>Action</a></span>
    </dt>
    <dd>{{% md %}}The action that you want AWS WAF Regional to take when a request doesn&#39;t match the criteria in any of the rules that are associated with the web ACL.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Logging<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#webaclloggingconfiguration">*Web<wbr>Acl<wbr>Logging<wbr>Configuration</a></span>
    </dt>
    <dd>{{% md %}}Configuration block to enable WAF logging. Detailed below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Metric<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name or description for the Amazon CloudWatch metric of this web ACL.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name or description of the web ACL.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Rules<span class="property-indicator"></span>
        <span class="property-type"><a href="#webaclrule">[]Web<wbr>Acl<wbr>Rule</a></span>
    </dt>
    <dd>{{% md %}}Set of configuration blocks containing rules for the web ACL. Detailed below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}Key-value mapping of resource tags
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of the WAF Regional WebACL.
{{% /md %}}</dd>

    <dt class="property-"
            title="">default<wbr>Action<span class="property-indicator"></span>
        <span class="property-type"><a href="#webacldefaultaction">Web<wbr>Acl<wbr>Default<wbr>Action</a></span>
    </dt>
    <dd>{{% md %}}The action that you want AWS WAF Regional to take when a request doesn&#39;t match the criteria in any of the rules that are associated with the web ACL.
{{% /md %}}</dd>

    <dt class="property-"
            title="">logging<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#webaclloggingconfiguration">Web<wbr>Acl<wbr>Logging<wbr>Configuration?</a></span>
    </dt>
    <dd>{{% md %}}Configuration block to enable WAF logging. Detailed below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">metric<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name or description for the Amazon CloudWatch metric of this web ACL.
{{% /md %}}</dd>

    <dt class="property-"
            title="">name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name or description of the web ACL.
{{% /md %}}</dd>

    <dt class="property-"
            title="">rules<span class="property-indicator"></span>
        <span class="property-type"><a href="#webaclrule">Web<wbr>Acl<wbr>Rule[]?</a></span>
    </dt>
    <dd>{{% md %}}Set of configuration blocks containing rules for the web ACL. Detailed below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}Key-value mapping of resource tags
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of the WAF Regional WebACL.
{{% /md %}}</dd>

    <dt class="property-"
            title="">default_<wbr>action<span class="property-indicator"></span>
        <span class="property-type"><a href="#webacldefaultaction">Dict[Web<wbr>Acl<wbr>Default<wbr>Action]</a></span>
    </dt>
    <dd>{{% md %}}The action that you want AWS WAF Regional to take when a request doesn&#39;t match the criteria in any of the rules that are associated with the web ACL.
{{% /md %}}</dd>

    <dt class="property-"
            title="">logging_<wbr>configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#webaclloggingconfiguration">Dict[Web<wbr>Acl<wbr>Logging<wbr>Configuration]</a></span>
    </dt>
    <dd>{{% md %}}Configuration block to enable WAF logging. Detailed below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">metric_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name or description for the Amazon CloudWatch metric of this web ACL.
{{% /md %}}</dd>

    <dt class="property-"
            title="">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name or description of the web ACL.
{{% /md %}}</dd>

    <dt class="property-"
            title="">rules<span class="property-indicator"></span>
        <span class="property-type"><a href="#webaclrule">List[Web<wbr>Acl<wbr>Rule]</a></span>
    </dt>
    <dd>{{% md %}}Set of configuration blocks containing rules for the web ACL. Detailed below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}Key-value mapping of resource tags
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





## Look up an Existing WebAcl Resource

{{< chooser language "javascript,typescript,python,go,csharp  " / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">pulumi.Input&lt;pulumi.ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/wafregional/#WebAclState">WebAclState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/wafregional/#WebAcl">WebAcl</a></span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>arn=None<span class="p">, </span>default_action=None<span class="p">, </span>logging_configuration=None<span class="p">, </span>metric_name=None<span class="p">, </span>name=None<span class="p">, </span>rules=None<span class="p">, </span>tags=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetWebAcl<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">pulumi.IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/wafregional?tab=doc#WebAclState">WebAclState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/wafregional?tab=doc#WebAcl">WebAcl</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Wafregional.WebAcl.html">WebAcl</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Pulumi.Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Wafregional.WebAclState.html">WebAclState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
{{% /choosable %}}

Get an existing WebAcl resource's state with the given name, ID, and optional extra properties used to qualify the lookup.

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
    <dd>{{% md %}}Amazon Resource Name (ARN) of the WAF Regional WebACL.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Default<wbr>Action<span class="property-indicator"></span>
        <span class="property-type"><a href="#webacldefaultaction">Web<wbr>Acl<wbr>Default<wbr>Action<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}The action that you want AWS WAF Regional to take when a request doesn&#39;t match the criteria in any of the rules that are associated with the web ACL.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Logging<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#webaclloggingconfiguration">Web<wbr>Acl<wbr>Logging<wbr>Configuration<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}Configuration block to enable WAF logging. Detailed below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Metric<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name or description for the Amazon CloudWatch metric of this web ACL.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name or description of the web ACL.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Rules<span class="property-indicator"></span>
        <span class="property-type"><a href="#webaclrule">List&lt;Web<wbr>Acl<wbr>Rule<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}Set of configuration blocks containing rules for the web ACL. Detailed below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}Key-value mapping of resource tags
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of the WAF Regional WebACL.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Default<wbr>Action<span class="property-indicator"></span>
        <span class="property-type"><a href="#webacldefaultaction">*Web<wbr>Acl<wbr>Default<wbr>Action</a></span>
    </dt>
    <dd>{{% md %}}The action that you want AWS WAF Regional to take when a request doesn&#39;t match the criteria in any of the rules that are associated with the web ACL.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Logging<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#webaclloggingconfiguration">*Web<wbr>Acl<wbr>Logging<wbr>Configuration</a></span>
    </dt>
    <dd>{{% md %}}Configuration block to enable WAF logging. Detailed below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Metric<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name or description for the Amazon CloudWatch metric of this web ACL.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name or description of the web ACL.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Rules<span class="property-indicator"></span>
        <span class="property-type"><a href="#webaclrule">[]Web<wbr>Acl<wbr>Rule</a></span>
    </dt>
    <dd>{{% md %}}Set of configuration blocks containing rules for the web ACL. Detailed below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}Key-value mapping of resource tags
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of the WAF Regional WebACL.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">default<wbr>Action<span class="property-indicator"></span>
        <span class="property-type"><a href="#webacldefaultaction">Web<wbr>Acl<wbr>Default<wbr>Action?</a></span>
    </dt>
    <dd>{{% md %}}The action that you want AWS WAF Regional to take when a request doesn&#39;t match the criteria in any of the rules that are associated with the web ACL.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">logging<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#webaclloggingconfiguration">Web<wbr>Acl<wbr>Logging<wbr>Configuration?</a></span>
    </dt>
    <dd>{{% md %}}Configuration block to enable WAF logging. Detailed below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">metric<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name or description for the Amazon CloudWatch metric of this web ACL.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name or description of the web ACL.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">rules<span class="property-indicator"></span>
        <span class="property-type"><a href="#webaclrule">Web<wbr>Acl<wbr>Rule[]?</a></span>
    </dt>
    <dd>{{% md %}}Set of configuration blocks containing rules for the web ACL. Detailed below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}Key-value mapping of resource tags
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of the WAF Regional WebACL.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">default_<wbr>action<span class="property-indicator"></span>
        <span class="property-type"><a href="#webacldefaultaction">Dict[Web<wbr>Acl<wbr>Default<wbr>Action]</a></span>
    </dt>
    <dd>{{% md %}}The action that you want AWS WAF Regional to take when a request doesn&#39;t match the criteria in any of the rules that are associated with the web ACL.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">logging_<wbr>configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#webaclloggingconfiguration">Dict[Web<wbr>Acl<wbr>Logging<wbr>Configuration]</a></span>
    </dt>
    <dd>{{% md %}}Configuration block to enable WAF logging. Detailed below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">metric_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name or description for the Amazon CloudWatch metric of this web ACL.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name or description of the web ACL.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">rules<span class="property-indicator"></span>
        <span class="property-type"><a href="#webaclrule">List[Web<wbr>Acl<wbr>Rule]</a></span>
    </dt>
    <dd>{{% md %}}Set of configuration blocks containing rules for the web ACL. Detailed below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}Key-value mapping of resource tags
{{% /md %}}</dd>

</dl>
{{% /choosable %}}







## Supporting Types

#### WebAclDefaultAction
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#WebAclDefaultAction">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#WebAclDefaultAction">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/wafregional?tab=doc#WebAclDefaultActionArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/wafregional?tab=doc#WebAclDefaultActionOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Wafregional.WebAclDefaultActionArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Wafregional.WebAclDefaultAction.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Specifies how you want AWS WAF Regional to respond to requests that match the settings in a rule. e.g. `ALLOW`, `BLOCK` or `COUNT`
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Specifies how you want AWS WAF Regional to respond to requests that match the settings in a rule. e.g. `ALLOW`, `BLOCK` or `COUNT`
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Specifies how you want AWS WAF Regional to respond to requests that match the settings in a rule. e.g. `ALLOW`, `BLOCK` or `COUNT`
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Specifies how you want AWS WAF Regional to respond to requests that match the settings in a rule. e.g. `ALLOW`, `BLOCK` or `COUNT`
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### WebAclLoggingConfiguration
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#WebAclLoggingConfiguration">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#WebAclLoggingConfiguration">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/wafregional?tab=doc#WebAclLoggingConfigurationArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/wafregional?tab=doc#WebAclLoggingConfigurationOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Wafregional.WebAclLoggingConfigurationArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Wafregional.WebAclLoggingConfiguration.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Log<wbr>Destination<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of Kinesis Firehose Delivery Stream
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Redacted<wbr>Fields<span class="property-indicator"></span>
        <span class="property-type"><a href="#webaclloggingconfigurationredactedfields">Web<wbr>Acl<wbr>Logging<wbr>Configuration<wbr>Redacted<wbr>Fields<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}Configuration block containing parts of the request that you want redacted from the logs. Detailed below.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Log<wbr>Destination<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of Kinesis Firehose Delivery Stream
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Redacted<wbr>Fields<span class="property-indicator"></span>
        <span class="property-type"><a href="#webaclloggingconfigurationredactedfields">*Web<wbr>Acl<wbr>Logging<wbr>Configuration<wbr>Redacted<wbr>Fields</a></span>
    </dt>
    <dd>{{% md %}}Configuration block containing parts of the request that you want redacted from the logs. Detailed below.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">log<wbr>Destination<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of Kinesis Firehose Delivery Stream
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">redacted<wbr>Fields<span class="property-indicator"></span>
        <span class="property-type"><a href="#webaclloggingconfigurationredactedfields">Web<wbr>Acl<wbr>Logging<wbr>Configuration<wbr>Redacted<wbr>Fields?</a></span>
    </dt>
    <dd>{{% md %}}Configuration block containing parts of the request that you want redacted from the logs. Detailed below.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">log_<wbr>destination<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of Kinesis Firehose Delivery Stream
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">redacted<wbr>Fields<span class="property-indicator"></span>
        <span class="property-type"><a href="#webaclloggingconfigurationredactedfields">Dict[Web<wbr>Acl<wbr>Logging<wbr>Configuration<wbr>Redacted<wbr>Fields]</a></span>
    </dt>
    <dd>{{% md %}}Configuration block containing parts of the request that you want redacted from the logs. Detailed below.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### WebAclLoggingConfigurationRedactedFields
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#WebAclLoggingConfigurationRedactedFields">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#WebAclLoggingConfigurationRedactedFields">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/wafregional?tab=doc#WebAclLoggingConfigurationRedactedFieldsArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/wafregional?tab=doc#WebAclLoggingConfigurationRedactedFieldsOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Wafregional.WebAclLoggingConfigurationRedactedFieldsArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Wafregional.WebAclLoggingConfigurationRedactedFields.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Field<wbr>To<wbr>Matches<span class="property-indicator"></span>
        <span class="property-type"><a href="#webaclloggingconfigurationredactedfieldsfieldtomatch">List&lt;Web<wbr>Acl<wbr>Logging<wbr>Configuration<wbr>Redacted<wbr>Fields<wbr>Field<wbr>To<wbr>Match<wbr>Args&gt;</a></span>
    </dt>
    <dd>{{% md %}}Set of configuration blocks for fields to redact. Detailed below.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Field<wbr>To<wbr>Matches<span class="property-indicator"></span>
        <span class="property-type"><a href="#webaclloggingconfigurationredactedfieldsfieldtomatch">[]Web<wbr>Acl<wbr>Logging<wbr>Configuration<wbr>Redacted<wbr>Fields<wbr>Field<wbr>To<wbr>Match</a></span>
    </dt>
    <dd>{{% md %}}Set of configuration blocks for fields to redact. Detailed below.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">field<wbr>To<wbr>Matches<span class="property-indicator"></span>
        <span class="property-type"><a href="#webaclloggingconfigurationredactedfieldsfieldtomatch">Web<wbr>Acl<wbr>Logging<wbr>Configuration<wbr>Redacted<wbr>Fields<wbr>Field<wbr>To<wbr>Match[]</a></span>
    </dt>
    <dd>{{% md %}}Set of configuration blocks for fields to redact. Detailed below.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">field<wbr>To<wbr>Matches<span class="property-indicator"></span>
        <span class="property-type"><a href="#webaclloggingconfigurationredactedfieldsfieldtomatch">List[Web<wbr>Acl<wbr>Logging<wbr>Configuration<wbr>Redacted<wbr>Fields<wbr>Field<wbr>To<wbr>Match]</a></span>
    </dt>
    <dd>{{% md %}}Set of configuration blocks for fields to redact. Detailed below.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### WebAclLoggingConfigurationRedactedFieldsFieldToMatch
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#WebAclLoggingConfigurationRedactedFieldsFieldToMatch">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#WebAclLoggingConfigurationRedactedFieldsFieldToMatch">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/wafregional?tab=doc#WebAclLoggingConfigurationRedactedFieldsFieldToMatchArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/wafregional?tab=doc#WebAclLoggingConfigurationRedactedFieldsFieldToMatchOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Wafregional.WebAclLoggingConfigurationRedactedFieldsFieldToMatchArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Wafregional.WebAclLoggingConfigurationRedactedFieldsFieldToMatch.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Data<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}When the value of `type` is `HEADER`, enter the name of the header that you want the WAF to search, for example, `User-Agent` or `Referer`. If the value of `type` is any other value, omit `data`.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Specifies how you want AWS WAF Regional to respond to requests that match the settings in a rule. e.g. `ALLOW`, `BLOCK` or `COUNT`
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Data<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}When the value of `type` is `HEADER`, enter the name of the header that you want the WAF to search, for example, `User-Agent` or `Referer`. If the value of `type` is any other value, omit `data`.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Specifies how you want AWS WAF Regional to respond to requests that match the settings in a rule. e.g. `ALLOW`, `BLOCK` or `COUNT`
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">data<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}When the value of `type` is `HEADER`, enter the name of the header that you want the WAF to search, for example, `User-Agent` or `Referer`. If the value of `type` is any other value, omit `data`.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Specifies how you want AWS WAF Regional to respond to requests that match the settings in a rule. e.g. `ALLOW`, `BLOCK` or `COUNT`
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">data<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}When the value of `type` is `HEADER`, enter the name of the header that you want the WAF to search, for example, `User-Agent` or `Referer`. If the value of `type` is any other value, omit `data`.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Specifies how you want AWS WAF Regional to respond to requests that match the settings in a rule. e.g. `ALLOW`, `BLOCK` or `COUNT`
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### WebAclRule
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#WebAclRule">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#WebAclRule">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/wafregional?tab=doc#WebAclRuleArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/wafregional?tab=doc#WebAclRuleOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Wafregional.WebAclRuleArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Wafregional.WebAclRule.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Action<span class="property-indicator"></span>
        <span class="property-type"><a href="#webaclruleaction">Web<wbr>Acl<wbr>Rule<wbr>Action<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}Configuration block of the action that CloudFront or AWS WAF takes when a web request matches the conditions in the rule.  Not used if `type` is `GROUP`. Detailed below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Override<wbr>Action<span class="property-indicator"></span>
        <span class="property-type"><a href="#webaclruleoverrideaction">Web<wbr>Acl<wbr>Rule<wbr>Override<wbr>Action<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}Configuration block of the override the action that a group requests CloudFront or AWS WAF takes when a web request matches the conditions in the rule.  Only used if `type` is `GROUP`. Detailed below.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Priority<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}Specifies the order in which the rules in a WebACL are evaluated.
Rules with a lower value are evaluated before rules with a higher value.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Rule<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}ID of the associated WAF (Regional) rule (e.g. [`aws.wafregional.Rule`](https://www.terraform.io/docs/providers/aws/r/wafregional_rule.html)). WAF (Global) rules cannot be used.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Specifies how you want AWS WAF Regional to respond to requests that match the settings in a rule. e.g. `ALLOW`, `BLOCK` or `COUNT`
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Action<span class="property-indicator"></span>
        <span class="property-type"><a href="#webaclruleaction">*Web<wbr>Acl<wbr>Rule<wbr>Action</a></span>
    </dt>
    <dd>{{% md %}}Configuration block of the action that CloudFront or AWS WAF takes when a web request matches the conditions in the rule.  Not used if `type` is `GROUP`. Detailed below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Override<wbr>Action<span class="property-indicator"></span>
        <span class="property-type"><a href="#webaclruleoverrideaction">*Web<wbr>Acl<wbr>Rule<wbr>Override<wbr>Action</a></span>
    </dt>
    <dd>{{% md %}}Configuration block of the override the action that a group requests CloudFront or AWS WAF takes when a web request matches the conditions in the rule.  Only used if `type` is `GROUP`. Detailed below.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Priority<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}Specifies the order in which the rules in a WebACL are evaluated.
Rules with a lower value are evaluated before rules with a higher value.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Rule<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}ID of the associated WAF (Regional) rule (e.g. [`aws.wafregional.Rule`](https://www.terraform.io/docs/providers/aws/r/wafregional_rule.html)). WAF (Global) rules cannot be used.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Type<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Specifies how you want AWS WAF Regional to respond to requests that match the settings in a rule. e.g. `ALLOW`, `BLOCK` or `COUNT`
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">action<span class="property-indicator"></span>
        <span class="property-type"><a href="#webaclruleaction">Web<wbr>Acl<wbr>Rule<wbr>Action?</a></span>
    </dt>
    <dd>{{% md %}}Configuration block of the action that CloudFront or AWS WAF takes when a web request matches the conditions in the rule.  Not used if `type` is `GROUP`. Detailed below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">override<wbr>Action<span class="property-indicator"></span>
        <span class="property-type"><a href="#webaclruleoverrideaction">Web<wbr>Acl<wbr>Rule<wbr>Override<wbr>Action?</a></span>
    </dt>
    <dd>{{% md %}}Configuration block of the override the action that a group requests CloudFront or AWS WAF takes when a web request matches the conditions in the rule.  Only used if `type` is `GROUP`. Detailed below.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">priority<span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}Specifies the order in which the rules in a WebACL are evaluated.
Rules with a lower value are evaluated before rules with a higher value.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">rule<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}ID of the associated WAF (Regional) rule (e.g. [`aws.wafregional.Rule`](https://www.terraform.io/docs/providers/aws/r/wafregional_rule.html)). WAF (Global) rules cannot be used.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Specifies how you want AWS WAF Regional to respond to requests that match the settings in a rule. e.g. `ALLOW`, `BLOCK` or `COUNT`
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">action<span class="property-indicator"></span>
        <span class="property-type"><a href="#webaclruleaction">Dict[Web<wbr>Acl<wbr>Rule<wbr>Action]</a></span>
    </dt>
    <dd>{{% md %}}Configuration block of the action that CloudFront or AWS WAF takes when a web request matches the conditions in the rule.  Not used if `type` is `GROUP`. Detailed below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">override<wbr>Action<span class="property-indicator"></span>
        <span class="property-type"><a href="#webaclruleoverrideaction">Dict[Web<wbr>Acl<wbr>Rule<wbr>Override<wbr>Action]</a></span>
    </dt>
    <dd>{{% md %}}Configuration block of the override the action that a group requests CloudFront or AWS WAF takes when a web request matches the conditions in the rule.  Only used if `type` is `GROUP`. Detailed below.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">priority<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}Specifies the order in which the rules in a WebACL are evaluated.
Rules with a lower value are evaluated before rules with a higher value.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">rule_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}ID of the associated WAF (Regional) rule (e.g. [`aws.wafregional.Rule`](https://www.terraform.io/docs/providers/aws/r/wafregional_rule.html)). WAF (Global) rules cannot be used.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Specifies how you want AWS WAF Regional to respond to requests that match the settings in a rule. e.g. `ALLOW`, `BLOCK` or `COUNT`
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### WebAclRuleAction
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#WebAclRuleAction">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#WebAclRuleAction">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/wafregional?tab=doc#WebAclRuleActionArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/wafregional?tab=doc#WebAclRuleActionOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Wafregional.WebAclRuleActionArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Wafregional.WebAclRuleAction.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Specifies how you want AWS WAF Regional to respond to requests that match the settings in a rule. e.g. `ALLOW`, `BLOCK` or `COUNT`
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Specifies how you want AWS WAF Regional to respond to requests that match the settings in a rule. e.g. `ALLOW`, `BLOCK` or `COUNT`
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Specifies how you want AWS WAF Regional to respond to requests that match the settings in a rule. e.g. `ALLOW`, `BLOCK` or `COUNT`
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Specifies how you want AWS WAF Regional to respond to requests that match the settings in a rule. e.g. `ALLOW`, `BLOCK` or `COUNT`
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### WebAclRuleOverrideAction
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#WebAclRuleOverrideAction">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#WebAclRuleOverrideAction">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/wafregional?tab=doc#WebAclRuleOverrideActionArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/wafregional?tab=doc#WebAclRuleOverrideActionOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Wafregional.WebAclRuleOverrideActionArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Wafregional.WebAclRuleOverrideAction.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Specifies how you want AWS WAF Regional to respond to requests that match the settings in a rule. e.g. `ALLOW`, `BLOCK` or `COUNT`
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Specifies how you want AWS WAF Regional to respond to requests that match the settings in a rule. e.g. `ALLOW`, `BLOCK` or `COUNT`
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Specifies how you want AWS WAF Regional to respond to requests that match the settings in a rule. e.g. `ALLOW`, `BLOCK` or `COUNT`
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Specifies how you want AWS WAF Regional to respond to requests that match the settings in a rule. e.g. `ALLOW`, `BLOCK` or `COUNT`
{{% /md %}}</dd>

</dl>
{{% /choosable %}}








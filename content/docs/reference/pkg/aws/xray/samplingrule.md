
---
title: "SamplingRule"
block_external_search_index: true
---

Creates and manages an AWS XRay Sampling Rule.

## Example Usage

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const example = new aws.xray.SamplingRule("example", {
    attributes: {
        Hello: "Tris",
    },
    fixedRate: 0.05,
    host: "*",
    httpMethod: "*",
    priority: 10000,
    reservoirSize: 1,
    resourceArn: "*",
    ruleName: "example",
    serviceName: "*",
    serviceType: "*",
    urlPath: "*",
    version: 1,
});
```

> This content is derived from https://github.com/terraform-providers/terraform-provider-aws/blob/master/website/docs/r/xray_sampling_rule.html.markdown.



## Create a SamplingRule Resource

{{< chooser language "javascript,typescript,python,go,csharp" / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/xray/#SamplingRule">SamplingRule</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/xray/#SamplingRuleArgs">SamplingRuleArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">SamplingRule</span><span class="p">(resource_name, opts=None, </span>attributes=None<span class="p">, </span>fixed_rate=None<span class="p">, </span>host=None<span class="p">, </span>http_method=None<span class="p">, </span>priority=None<span class="p">, </span>reservoir_size=None<span class="p">, </span>resource_arn=None<span class="p">, </span>rule_name=None<span class="p">, </span>service_name=None<span class="p">, </span>service_type=None<span class="p">, </span>url_path=None<span class="p">, </span>version=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewSamplingRule<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/xray?tab=doc#SamplingRuleArgs">SamplingRuleArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/xray?tab=doc#SamplingRule">SamplingRule</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Xray.SamplingRule.html">SamplingRule</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Xray.SamplingRuleArgs.html">SamplingRuleArgs</a></span> <span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
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
            title="Optional">Attributes<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, string>?</span>
    </dt>
    <dd>{{% md %}}Matches attributes derived from the request.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Fixed<wbr>Rate<span class="property-indicator"></span>
        <span class="property-type">double</span>
    </dt>
    <dd>{{% md %}}The percentage of matching requests to instrument, after the reservoir is exhausted.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Host<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Matches the hostname from a request URL.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Http<wbr>Method<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Matches the HTTP method of a request.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Priority<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The priority of the sampling rule.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Reservoir<wbr>Size<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}A fixed number of matching requests to instrument per second, prior to applying the fixed rate. The reservoir is not used directly by services, but applies to all services using the rule collectively.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Resource<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Matches the ARN of the AWS resource on which the service runs.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Rule<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the sampling rule.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Service<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Matches the `name` that the service uses to identify itself in segments.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Service<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Matches the `origin` that the service uses to identify its type in segments.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Url<wbr>Path<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Matches the path from a request URL.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Version<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The version of the sampling rule format (`1` )
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Attributes<span class="property-indicator"></span>
        <span class="property-type">map[string]string</span>
    </dt>
    <dd>{{% md %}}Matches attributes derived from the request.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Fixed<wbr>Rate<span class="property-indicator"></span>
        <span class="property-type">float64</span>
    </dt>
    <dd>{{% md %}}The percentage of matching requests to instrument, after the reservoir is exhausted.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Host<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Matches the hostname from a request URL.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Http<wbr>Method<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Matches the HTTP method of a request.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Priority<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The priority of the sampling rule.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Reservoir<wbr>Size<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}A fixed number of matching requests to instrument per second, prior to applying the fixed rate. The reservoir is not used directly by services, but applies to all services using the rule collectively.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Resource<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Matches the ARN of the AWS resource on which the service runs.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Rule<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name of the sampling rule.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Service<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Matches the `name` that the service uses to identify itself in segments.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Service<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Matches the `origin` that the service uses to identify its type in segments.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Url<wbr>Path<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Matches the path from a request URL.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Version<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The version of the sampling rule format (`1` )
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">attributes<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: string}?</span>
    </dt>
    <dd>{{% md %}}Matches attributes derived from the request.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">fixed<wbr>Rate<span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}The percentage of matching requests to instrument, after the reservoir is exhausted.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">host<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Matches the hostname from a request URL.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">http<wbr>Method<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Matches the HTTP method of a request.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">priority<span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}The priority of the sampling rule.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">reservoir<wbr>Size<span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}A fixed number of matching requests to instrument per second, prior to applying the fixed rate. The reservoir is not used directly by services, but applies to all services using the rule collectively.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">resource<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Matches the ARN of the AWS resource on which the service runs.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">rule<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the sampling rule.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">service<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Matches the `name` that the service uses to identify itself in segments.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">service<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Matches the `origin` that the service uses to identify its type in segments.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">url<wbr>Path<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Matches the path from a request URL.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">version<span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}The version of the sampling rule format (`1` )
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">attributes<span class="property-indicator"></span>
        <span class="property-type">Dict[str, str]</span>
    </dt>
    <dd>{{% md %}}Matches attributes derived from the request.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">fixed_<wbr>rate<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The percentage of matching requests to instrument, after the reservoir is exhausted.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">host<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Matches the hostname from a request URL.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">http_<wbr>method<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Matches the HTTP method of a request.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">priority<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The priority of the sampling rule.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">reservoir_<wbr>size<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}A fixed number of matching requests to instrument per second, prior to applying the fixed rate. The reservoir is not used directly by services, but applies to all services using the rule collectively.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">resource_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Matches the ARN of the AWS resource on which the service runs.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">rule_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the sampling rule.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">service_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Matches the `name` that the service uses to identify itself in segments.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">service_<wbr>type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Matches the `origin` that the service uses to identify its type in segments.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">url_<wbr>path<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Matches the path from a request URL.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">version<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The version of the sampling rule format (`1` )
{{% /md %}}</dd>

</dl>
{{% /choosable %}}




## SamplingRule Output Properties

The following output properties are available:




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of the sampling rule.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Attributes<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, string>?</span>
    </dt>
    <dd>{{% md %}}Matches attributes derived from the request.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Fixed<wbr>Rate<span class="property-indicator"></span>
        <span class="property-type">double</span>
    </dt>
    <dd>{{% md %}}The percentage of matching requests to instrument, after the reservoir is exhausted.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Host<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Matches the hostname from a request URL.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Http<wbr>Method<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Matches the HTTP method of a request.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Priority<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The priority of the sampling rule.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Reservoir<wbr>Size<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}A fixed number of matching requests to instrument per second, prior to applying the fixed rate. The reservoir is not used directly by services, but applies to all services using the rule collectively.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Resource<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Matches the ARN of the AWS resource on which the service runs.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Rule<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the sampling rule.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Service<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Matches the `name` that the service uses to identify itself in segments.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Service<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Matches the `origin` that the service uses to identify its type in segments.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Url<wbr>Path<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Matches the path from a request URL.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Version<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The version of the sampling rule format (`1` )
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of the sampling rule.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Attributes<span class="property-indicator"></span>
        <span class="property-type">map[string]string</span>
    </dt>
    <dd>{{% md %}}Matches attributes derived from the request.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Fixed<wbr>Rate<span class="property-indicator"></span>
        <span class="property-type">float64</span>
    </dt>
    <dd>{{% md %}}The percentage of matching requests to instrument, after the reservoir is exhausted.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Host<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Matches the hostname from a request URL.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Http<wbr>Method<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Matches the HTTP method of a request.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Priority<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The priority of the sampling rule.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Reservoir<wbr>Size<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}A fixed number of matching requests to instrument per second, prior to applying the fixed rate. The reservoir is not used directly by services, but applies to all services using the rule collectively.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Resource<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Matches the ARN of the AWS resource on which the service runs.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Rule<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name of the sampling rule.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Service<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Matches the `name` that the service uses to identify itself in segments.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Service<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Matches the `origin` that the service uses to identify its type in segments.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Url<wbr>Path<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Matches the path from a request URL.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Version<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The version of the sampling rule format (`1` )
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of the sampling rule.
{{% /md %}}</dd>

    <dt class="property-"
            title="">attributes<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: string}?</span>
    </dt>
    <dd>{{% md %}}Matches attributes derived from the request.
{{% /md %}}</dd>

    <dt class="property-"
            title="">fixed<wbr>Rate<span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}The percentage of matching requests to instrument, after the reservoir is exhausted.
{{% /md %}}</dd>

    <dt class="property-"
            title="">host<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Matches the hostname from a request URL.
{{% /md %}}</dd>

    <dt class="property-"
            title="">http<wbr>Method<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Matches the HTTP method of a request.
{{% /md %}}</dd>

    <dt class="property-"
            title="">priority<span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}The priority of the sampling rule.
{{% /md %}}</dd>

    <dt class="property-"
            title="">reservoir<wbr>Size<span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}A fixed number of matching requests to instrument per second, prior to applying the fixed rate. The reservoir is not used directly by services, but applies to all services using the rule collectively.
{{% /md %}}</dd>

    <dt class="property-"
            title="">resource<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Matches the ARN of the AWS resource on which the service runs.
{{% /md %}}</dd>

    <dt class="property-"
            title="">rule<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the sampling rule.
{{% /md %}}</dd>

    <dt class="property-"
            title="">service<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Matches the `name` that the service uses to identify itself in segments.
{{% /md %}}</dd>

    <dt class="property-"
            title="">service<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Matches the `origin` that the service uses to identify its type in segments.
{{% /md %}}</dd>

    <dt class="property-"
            title="">url<wbr>Path<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Matches the path from a request URL.
{{% /md %}}</dd>

    <dt class="property-"
            title="">version<span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}The version of the sampling rule format (`1` )
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ARN of the sampling rule.
{{% /md %}}</dd>

    <dt class="property-"
            title="">attributes<span class="property-indicator"></span>
        <span class="property-type">Dict[str, str]</span>
    </dt>
    <dd>{{% md %}}Matches attributes derived from the request.
{{% /md %}}</dd>

    <dt class="property-"
            title="">fixed_<wbr>rate<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The percentage of matching requests to instrument, after the reservoir is exhausted.
{{% /md %}}</dd>

    <dt class="property-"
            title="">host<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Matches the hostname from a request URL.
{{% /md %}}</dd>

    <dt class="property-"
            title="">http_<wbr>method<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Matches the HTTP method of a request.
{{% /md %}}</dd>

    <dt class="property-"
            title="">priority<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The priority of the sampling rule.
{{% /md %}}</dd>

    <dt class="property-"
            title="">reservoir_<wbr>size<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}A fixed number of matching requests to instrument per second, prior to applying the fixed rate. The reservoir is not used directly by services, but applies to all services using the rule collectively.
{{% /md %}}</dd>

    <dt class="property-"
            title="">resource_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Matches the ARN of the AWS resource on which the service runs.
{{% /md %}}</dd>

    <dt class="property-"
            title="">rule_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the sampling rule.
{{% /md %}}</dd>

    <dt class="property-"
            title="">service_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Matches the `name` that the service uses to identify itself in segments.
{{% /md %}}</dd>

    <dt class="property-"
            title="">service_<wbr>type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Matches the `origin` that the service uses to identify its type in segments.
{{% /md %}}</dd>

    <dt class="property-"
            title="">url_<wbr>path<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Matches the path from a request URL.
{{% /md %}}</dd>

    <dt class="property-"
            title="">version<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The version of the sampling rule format (`1` )
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





## Look up an Existing SamplingRule Resource

{{< chooser language "javascript,typescript,python,go,csharp  " / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">pulumi.Input&lt;pulumi.ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/xray/#SamplingRuleState">SamplingRuleState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/xray/#SamplingRule">SamplingRule</a></span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>arn=None<span class="p">, </span>attributes=None<span class="p">, </span>fixed_rate=None<span class="p">, </span>host=None<span class="p">, </span>http_method=None<span class="p">, </span>priority=None<span class="p">, </span>reservoir_size=None<span class="p">, </span>resource_arn=None<span class="p">, </span>rule_name=None<span class="p">, </span>service_name=None<span class="p">, </span>service_type=None<span class="p">, </span>url_path=None<span class="p">, </span>version=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetSamplingRule<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">pulumi.IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/xray?tab=doc#SamplingRuleState">SamplingRuleState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/xray?tab=doc#SamplingRule">SamplingRule</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Xray.SamplingRule.html">SamplingRule</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Pulumi.Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Xray.SamplingRuleState.html">SamplingRuleState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
{{% /choosable %}}

Get an existing SamplingRule resource's state with the given name, ID, and optional extra properties used to qualify the lookup.

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
    <dd>{{% md %}}The ARN of the sampling rule.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Attributes<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, string>?</span>
    </dt>
    <dd>{{% md %}}Matches attributes derived from the request.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Fixed<wbr>Rate<span class="property-indicator"></span>
        <span class="property-type">double?</span>
    </dt>
    <dd>{{% md %}}The percentage of matching requests to instrument, after the reservoir is exhausted.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Host<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Matches the hostname from a request URL.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Http<wbr>Method<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Matches the HTTP method of a request.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Priority<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The priority of the sampling rule.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Reservoir<wbr>Size<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}A fixed number of matching requests to instrument per second, prior to applying the fixed rate. The reservoir is not used directly by services, but applies to all services using the rule collectively.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Resource<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Matches the ARN of the AWS resource on which the service runs.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Rule<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the sampling rule.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Service<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Matches the `name` that the service uses to identify itself in segments.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Service<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Matches the `origin` that the service uses to identify its type in segments.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Url<wbr>Path<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Matches the path from a request URL.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Version<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The version of the sampling rule format (`1` )
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The ARN of the sampling rule.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Attributes<span class="property-indicator"></span>
        <span class="property-type">map[string]string</span>
    </dt>
    <dd>{{% md %}}Matches attributes derived from the request.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Fixed<wbr>Rate<span class="property-indicator"></span>
        <span class="property-type">*float64</span>
    </dt>
    <dd>{{% md %}}The percentage of matching requests to instrument, after the reservoir is exhausted.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Host<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Matches the hostname from a request URL.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Http<wbr>Method<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Matches the HTTP method of a request.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Priority<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The priority of the sampling rule.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Reservoir<wbr>Size<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}A fixed number of matching requests to instrument per second, prior to applying the fixed rate. The reservoir is not used directly by services, but applies to all services using the rule collectively.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Resource<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Matches the ARN of the AWS resource on which the service runs.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Rule<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name of the sampling rule.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Service<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Matches the `name` that the service uses to identify itself in segments.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Service<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Matches the `origin` that the service uses to identify its type in segments.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Url<wbr>Path<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Matches the path from a request URL.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Version<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The version of the sampling rule format (`1` )
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ARN of the sampling rule.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">attributes<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: string}?</span>
    </dt>
    <dd>{{% md %}}Matches attributes derived from the request.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">fixed<wbr>Rate<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The percentage of matching requests to instrument, after the reservoir is exhausted.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">host<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Matches the hostname from a request URL.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">http<wbr>Method<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Matches the HTTP method of a request.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">priority<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The priority of the sampling rule.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">reservoir<wbr>Size<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}A fixed number of matching requests to instrument per second, prior to applying the fixed rate. The reservoir is not used directly by services, but applies to all services using the rule collectively.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">resource<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Matches the ARN of the AWS resource on which the service runs.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">rule<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the sampling rule.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">service<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Matches the `name` that the service uses to identify itself in segments.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">service<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Matches the `origin` that the service uses to identify its type in segments.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">url<wbr>Path<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Matches the path from a request URL.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">version<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The version of the sampling rule format (`1` )
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ARN of the sampling rule.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">attributes<span class="property-indicator"></span>
        <span class="property-type">Dict[str, str]</span>
    </dt>
    <dd>{{% md %}}Matches attributes derived from the request.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">fixed_<wbr>rate<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The percentage of matching requests to instrument, after the reservoir is exhausted.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">host<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Matches the hostname from a request URL.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">http_<wbr>method<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Matches the HTTP method of a request.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">priority<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The priority of the sampling rule.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">reservoir_<wbr>size<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}A fixed number of matching requests to instrument per second, prior to applying the fixed rate. The reservoir is not used directly by services, but applies to all services using the rule collectively.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">resource_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Matches the ARN of the AWS resource on which the service runs.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">rule_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the sampling rule.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">service_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Matches the `name` that the service uses to identify itself in segments.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">service_<wbr>type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Matches the `origin` that the service uses to identify its type in segments.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">url_<wbr>path<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Matches the path from a request URL.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">version<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The version of the sampling rule format (`1` )
{{% /md %}}</dd>

</dl>
{{% /choosable %}}







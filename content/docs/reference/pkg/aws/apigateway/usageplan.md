
---
title: "UsagePlan"
block_external_search_index: true
---

Provides an API Gateway Usage Plan.

## Example Usage

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const myapi = new aws.apigateway.RestApi("myapi", {});
const dev = new aws.apigateway.Deployment("dev", {
    restApi: myapi.id,
    stageName: "dev",
});
const prod = new aws.apigateway.Deployment("prod", {
    restApi: myapi.id,
    stageName: "prod",
});
const myUsagePlan = new aws.apigateway.UsagePlan("MyUsagePlan", {
    apiStages: [
        {
            apiId: myapi.id,
            stage: dev.stageName,
        },
        {
            apiId: myapi.id,
            stage: prod.stageName,
        },
    ],
    description: "my description",
    productCode: "MYCODE",
    quotaSettings: {
        limit: 20,
        offset: 2,
        period: "WEEK",
    },
    throttleSettings: {
        burstLimit: 5,
        rateLimit: 10,
    },
});
```

> This content is derived from https://github.com/terraform-providers/terraform-provider-aws/blob/master/website/docs/r/api_gateway_usage_plan.html.markdown.



## Create a UsagePlan Resource

{{< chooser language "javascript,typescript,python,go,csharp" / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/apigateway/#UsagePlan">UsagePlan</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/apigateway/#UsagePlanArgs">UsagePlanArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">UsagePlan</span><span class="p">(resource_name, opts=None, </span>api_stages=None<span class="p">, </span>description=None<span class="p">, </span>name=None<span class="p">, </span>product_code=None<span class="p">, </span>quota_settings=None<span class="p">, </span>tags=None<span class="p">, </span>throttle_settings=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewUsagePlan<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/apigateway?tab=doc#UsagePlanArgs">UsagePlanArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/apigateway?tab=doc#UsagePlan">UsagePlan</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Apigateway.UsagePlan.html">UsagePlan</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Apigateway.UsagePlanArgs.html">UsagePlanArgs</a></span>? <span class="nx">args = null<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
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
            title="Optional">Api<wbr>Stages<span class="property-indicator"></span>
        <span class="property-type"><a href="#usageplanapistage">List&lt;Usage<wbr>Plan<wbr>Api<wbr>Stage<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}The associated API stages of the usage plan.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Description<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The description of a usage plan.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the usage plan.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Product<wbr>Code<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The AWS Markeplace product identifier to associate with the usage plan as a SaaS product on AWS Marketplace.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Quota<wbr>Settings<span class="property-indicator"></span>
        <span class="property-type"><a href="#usageplanquotasettings">Usage<wbr>Plan<wbr>Quota<wbr>Settings<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}The quota settings of the usage plan.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}Key-value mapping of resource tags
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Throttle<wbr>Settings<span class="property-indicator"></span>
        <span class="property-type"><a href="#usageplanthrottlesettings">Usage<wbr>Plan<wbr>Throttle<wbr>Settings<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}The throttling limits of the usage plan.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Api<wbr>Stages<span class="property-indicator"></span>
        <span class="property-type"><a href="#usageplanapistage">[]Usage<wbr>Plan<wbr>Api<wbr>Stage</a></span>
    </dt>
    <dd>{{% md %}}The associated API stages of the usage plan.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Description<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The description of a usage plan.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name of the usage plan.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Product<wbr>Code<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The AWS Markeplace product identifier to associate with the usage plan as a SaaS product on AWS Marketplace.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Quota<wbr>Settings<span class="property-indicator"></span>
        <span class="property-type"><a href="#usageplanquotasettings">*Usage<wbr>Plan<wbr>Quota<wbr>Settings</a></span>
    </dt>
    <dd>{{% md %}}The quota settings of the usage plan.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}Key-value mapping of resource tags
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Throttle<wbr>Settings<span class="property-indicator"></span>
        <span class="property-type"><a href="#usageplanthrottlesettings">*Usage<wbr>Plan<wbr>Throttle<wbr>Settings</a></span>
    </dt>
    <dd>{{% md %}}The throttling limits of the usage plan.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">api<wbr>Stages<span class="property-indicator"></span>
        <span class="property-type"><a href="#usageplanapistage">Usage<wbr>Plan<wbr>Api<wbr>Stage[]?</a></span>
    </dt>
    <dd>{{% md %}}The associated API stages of the usage plan.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">description<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The description of a usage plan.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the usage plan.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">product<wbr>Code<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The AWS Markeplace product identifier to associate with the usage plan as a SaaS product on AWS Marketplace.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">quota<wbr>Settings<span class="property-indicator"></span>
        <span class="property-type"><a href="#usageplanquotasettings">Usage<wbr>Plan<wbr>Quota<wbr>Settings?</a></span>
    </dt>
    <dd>{{% md %}}The quota settings of the usage plan.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}Key-value mapping of resource tags
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">throttle<wbr>Settings<span class="property-indicator"></span>
        <span class="property-type"><a href="#usageplanthrottlesettings">Usage<wbr>Plan<wbr>Throttle<wbr>Settings?</a></span>
    </dt>
    <dd>{{% md %}}The throttling limits of the usage plan.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">api_<wbr>stages<span class="property-indicator"></span>
        <span class="property-type"><a href="#usageplanapistage">List[Usage<wbr>Plan<wbr>Api<wbr>Stage]</a></span>
    </dt>
    <dd>{{% md %}}The associated API stages of the usage plan.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">description<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The description of a usage plan.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the usage plan.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">product_<wbr>code<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The AWS Markeplace product identifier to associate with the usage plan as a SaaS product on AWS Marketplace.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">quota_<wbr>settings<span class="property-indicator"></span>
        <span class="property-type"><a href="#usageplanquotasettings">Dict[Usage<wbr>Plan<wbr>Quota<wbr>Settings]</a></span>
    </dt>
    <dd>{{% md %}}The quota settings of the usage plan.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}Key-value mapping of resource tags
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">throttle_<wbr>settings<span class="property-indicator"></span>
        <span class="property-type"><a href="#usageplanthrottlesettings">Dict[Usage<wbr>Plan<wbr>Throttle<wbr>Settings]</a></span>
    </dt>
    <dd>{{% md %}}The throttling limits of the usage plan.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}




## UsagePlan Output Properties

The following output properties are available:




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Api<wbr>Stages<span class="property-indicator"></span>
        <span class="property-type"><a href="#usageplanapistage">List&lt;Usage<wbr>Plan<wbr>Api<wbr>Stage&gt;?</a></span>
    </dt>
    <dd>{{% md %}}The associated API stages of the usage plan.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN)
{{% /md %}}</dd>

    <dt class="property-"
            title="">Description<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The description of a usage plan.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the usage plan.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Product<wbr>Code<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The AWS Markeplace product identifier to associate with the usage plan as a SaaS product on AWS Marketplace.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Quota<wbr>Settings<span class="property-indicator"></span>
        <span class="property-type"><a href="#usageplanquotasettings">Usage<wbr>Plan<wbr>Quota<wbr>Settings?</a></span>
    </dt>
    <dd>{{% md %}}The quota settings of the usage plan.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}Key-value mapping of resource tags
{{% /md %}}</dd>

    <dt class="property-"
            title="">Throttle<wbr>Settings<span class="property-indicator"></span>
        <span class="property-type"><a href="#usageplanthrottlesettings">Usage<wbr>Plan<wbr>Throttle<wbr>Settings?</a></span>
    </dt>
    <dd>{{% md %}}The throttling limits of the usage plan.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Api<wbr>Stages<span class="property-indicator"></span>
        <span class="property-type"><a href="#usageplanapistage">[]Usage<wbr>Plan<wbr>Api<wbr>Stage</a></span>
    </dt>
    <dd>{{% md %}}The associated API stages of the usage plan.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN)
{{% /md %}}</dd>

    <dt class="property-"
            title="">Description<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The description of a usage plan.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the usage plan.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Product<wbr>Code<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The AWS Markeplace product identifier to associate with the usage plan as a SaaS product on AWS Marketplace.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Quota<wbr>Settings<span class="property-indicator"></span>
        <span class="property-type"><a href="#usageplanquotasettings">*Usage<wbr>Plan<wbr>Quota<wbr>Settings</a></span>
    </dt>
    <dd>{{% md %}}The quota settings of the usage plan.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}Key-value mapping of resource tags
{{% /md %}}</dd>

    <dt class="property-"
            title="">Throttle<wbr>Settings<span class="property-indicator"></span>
        <span class="property-type"><a href="#usageplanthrottlesettings">*Usage<wbr>Plan<wbr>Throttle<wbr>Settings</a></span>
    </dt>
    <dd>{{% md %}}The throttling limits of the usage plan.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">api<wbr>Stages<span class="property-indicator"></span>
        <span class="property-type"><a href="#usageplanapistage">Usage<wbr>Plan<wbr>Api<wbr>Stage[]?</a></span>
    </dt>
    <dd>{{% md %}}The associated API stages of the usage plan.
{{% /md %}}</dd>

    <dt class="property-"
            title="">arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN)
{{% /md %}}</dd>

    <dt class="property-"
            title="">description<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The description of a usage plan.
{{% /md %}}</dd>

    <dt class="property-"
            title="">name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the usage plan.
{{% /md %}}</dd>

    <dt class="property-"
            title="">product<wbr>Code<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The AWS Markeplace product identifier to associate with the usage plan as a SaaS product on AWS Marketplace.
{{% /md %}}</dd>

    <dt class="property-"
            title="">quota<wbr>Settings<span class="property-indicator"></span>
        <span class="property-type"><a href="#usageplanquotasettings">Usage<wbr>Plan<wbr>Quota<wbr>Settings?</a></span>
    </dt>
    <dd>{{% md %}}The quota settings of the usage plan.
{{% /md %}}</dd>

    <dt class="property-"
            title="">tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}Key-value mapping of resource tags
{{% /md %}}</dd>

    <dt class="property-"
            title="">throttle<wbr>Settings<span class="property-indicator"></span>
        <span class="property-type"><a href="#usageplanthrottlesettings">Usage<wbr>Plan<wbr>Throttle<wbr>Settings?</a></span>
    </dt>
    <dd>{{% md %}}The throttling limits of the usage plan.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">api_<wbr>stages<span class="property-indicator"></span>
        <span class="property-type"><a href="#usageplanapistage">List[Usage<wbr>Plan<wbr>Api<wbr>Stage]</a></span>
    </dt>
    <dd>{{% md %}}The associated API stages of the usage plan.
{{% /md %}}</dd>

    <dt class="property-"
            title="">arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN)
{{% /md %}}</dd>

    <dt class="property-"
            title="">description<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The description of a usage plan.
{{% /md %}}</dd>

    <dt class="property-"
            title="">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the usage plan.
{{% /md %}}</dd>

    <dt class="property-"
            title="">product_<wbr>code<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The AWS Markeplace product identifier to associate with the usage plan as a SaaS product on AWS Marketplace.
{{% /md %}}</dd>

    <dt class="property-"
            title="">quota_<wbr>settings<span class="property-indicator"></span>
        <span class="property-type"><a href="#usageplanquotasettings">Dict[Usage<wbr>Plan<wbr>Quota<wbr>Settings]</a></span>
    </dt>
    <dd>{{% md %}}The quota settings of the usage plan.
{{% /md %}}</dd>

    <dt class="property-"
            title="">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}Key-value mapping of resource tags
{{% /md %}}</dd>

    <dt class="property-"
            title="">throttle_<wbr>settings<span class="property-indicator"></span>
        <span class="property-type"><a href="#usageplanthrottlesettings">Dict[Usage<wbr>Plan<wbr>Throttle<wbr>Settings]</a></span>
    </dt>
    <dd>{{% md %}}The throttling limits of the usage plan.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





## Look up an Existing UsagePlan Resource

{{< chooser language "javascript,typescript,python,go,csharp  " / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">pulumi.Input&lt;pulumi.ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/apigateway/#UsagePlanState">UsagePlanState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/apigateway/#UsagePlan">UsagePlan</a></span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>api_stages=None<span class="p">, </span>arn=None<span class="p">, </span>description=None<span class="p">, </span>name=None<span class="p">, </span>product_code=None<span class="p">, </span>quota_settings=None<span class="p">, </span>tags=None<span class="p">, </span>throttle_settings=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetUsagePlan<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">pulumi.IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/apigateway?tab=doc#UsagePlanState">UsagePlanState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/apigateway?tab=doc#UsagePlan">UsagePlan</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Apigateway.UsagePlan.html">UsagePlan</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Pulumi.Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Apigateway.UsagePlanState.html">UsagePlanState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
{{% /choosable %}}

Get an existing UsagePlan resource's state with the given name, ID, and optional extra properties used to qualify the lookup.

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
            title="Optional">Api<wbr>Stages<span class="property-indicator"></span>
        <span class="property-type"><a href="#usageplanapistage">List&lt;Usage<wbr>Plan<wbr>Api<wbr>Stage<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}The associated API stages of the usage plan.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Description<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The description of a usage plan.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the usage plan.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Product<wbr>Code<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The AWS Markeplace product identifier to associate with the usage plan as a SaaS product on AWS Marketplace.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Quota<wbr>Settings<span class="property-indicator"></span>
        <span class="property-type"><a href="#usageplanquotasettings">Usage<wbr>Plan<wbr>Quota<wbr>Settings<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}The quota settings of the usage plan.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}Key-value mapping of resource tags
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Throttle<wbr>Settings<span class="property-indicator"></span>
        <span class="property-type"><a href="#usageplanthrottlesettings">Usage<wbr>Plan<wbr>Throttle<wbr>Settings<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}The throttling limits of the usage plan.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Api<wbr>Stages<span class="property-indicator"></span>
        <span class="property-type"><a href="#usageplanapistage">[]Usage<wbr>Plan<wbr>Api<wbr>Stage</a></span>
    </dt>
    <dd>{{% md %}}The associated API stages of the usage plan.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Description<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The description of a usage plan.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name of the usage plan.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Product<wbr>Code<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The AWS Markeplace product identifier to associate with the usage plan as a SaaS product on AWS Marketplace.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Quota<wbr>Settings<span class="property-indicator"></span>
        <span class="property-type"><a href="#usageplanquotasettings">*Usage<wbr>Plan<wbr>Quota<wbr>Settings</a></span>
    </dt>
    <dd>{{% md %}}The quota settings of the usage plan.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}Key-value mapping of resource tags
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Throttle<wbr>Settings<span class="property-indicator"></span>
        <span class="property-type"><a href="#usageplanthrottlesettings">*Usage<wbr>Plan<wbr>Throttle<wbr>Settings</a></span>
    </dt>
    <dd>{{% md %}}The throttling limits of the usage plan.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">api<wbr>Stages<span class="property-indicator"></span>
        <span class="property-type"><a href="#usageplanapistage">Usage<wbr>Plan<wbr>Api<wbr>Stage[]?</a></span>
    </dt>
    <dd>{{% md %}}The associated API stages of the usage plan.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">description<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The description of a usage plan.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the usage plan.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">product<wbr>Code<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The AWS Markeplace product identifier to associate with the usage plan as a SaaS product on AWS Marketplace.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">quota<wbr>Settings<span class="property-indicator"></span>
        <span class="property-type"><a href="#usageplanquotasettings">Usage<wbr>Plan<wbr>Quota<wbr>Settings?</a></span>
    </dt>
    <dd>{{% md %}}The quota settings of the usage plan.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}Key-value mapping of resource tags
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">throttle<wbr>Settings<span class="property-indicator"></span>
        <span class="property-type"><a href="#usageplanthrottlesettings">Usage<wbr>Plan<wbr>Throttle<wbr>Settings?</a></span>
    </dt>
    <dd>{{% md %}}The throttling limits of the usage plan.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">api_<wbr>stages<span class="property-indicator"></span>
        <span class="property-type"><a href="#usageplanapistage">List[Usage<wbr>Plan<wbr>Api<wbr>Stage]</a></span>
    </dt>
    <dd>{{% md %}}The associated API stages of the usage plan.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">description<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The description of a usage plan.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the usage plan.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">product_<wbr>code<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The AWS Markeplace product identifier to associate with the usage plan as a SaaS product on AWS Marketplace.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">quota_<wbr>settings<span class="property-indicator"></span>
        <span class="property-type"><a href="#usageplanquotasettings">Dict[Usage<wbr>Plan<wbr>Quota<wbr>Settings]</a></span>
    </dt>
    <dd>{{% md %}}The quota settings of the usage plan.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}Key-value mapping of resource tags
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">throttle_<wbr>settings<span class="property-indicator"></span>
        <span class="property-type"><a href="#usageplanthrottlesettings">Dict[Usage<wbr>Plan<wbr>Throttle<wbr>Settings]</a></span>
    </dt>
    <dd>{{% md %}}The throttling limits of the usage plan.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}







## Supporting Types

#### UsagePlanApiStage
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#UsagePlanApiStage">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#UsagePlanApiStage">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/apigateway?tab=doc#UsagePlanApiStageArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/apigateway?tab=doc#UsagePlanApiStageOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Apigateway.UsagePlanApiStageArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Apigateway.UsagePlanApiStage.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Api<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}API Id of the associated API stage in a usage plan.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Stage<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}API stage name of the associated API stage in a usage plan.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Api<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}API Id of the associated API stage in a usage plan.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Stage<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}API stage name of the associated API stage in a usage plan.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">api<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}API Id of the associated API stage in a usage plan.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">stage<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}API stage name of the associated API stage in a usage plan.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">api_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}API Id of the associated API stage in a usage plan.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">stage<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}API stage name of the associated API stage in a usage plan.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### UsagePlanQuotaSettings
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#UsagePlanQuotaSettings">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#UsagePlanQuotaSettings">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/apigateway?tab=doc#UsagePlanQuotaSettingsArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/apigateway?tab=doc#UsagePlanQuotaSettingsOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Apigateway.UsagePlanQuotaSettingsArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Apigateway.UsagePlanQuotaSettings.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Limit<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The maximum number of requests that can be made in a given time period.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Offset<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The number of requests subtracted from the given limit in the initial time period.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Period<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The time period in which the limit applies. Valid values are &#34;DAY&#34;, &#34;WEEK&#34; or &#34;MONTH&#34;.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Limit<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The maximum number of requests that can be made in a given time period.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Offset<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The number of requests subtracted from the given limit in the initial time period.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Period<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The time period in which the limit applies. Valid values are &#34;DAY&#34;, &#34;WEEK&#34; or &#34;MONTH&#34;.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">limit<span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}The maximum number of requests that can be made in a given time period.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">offset<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The number of requests subtracted from the given limit in the initial time period.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">period<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The time period in which the limit applies. Valid values are &#34;DAY&#34;, &#34;WEEK&#34; or &#34;MONTH&#34;.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">limit<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The maximum number of requests that can be made in a given time period.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">offset<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The number of requests subtracted from the given limit in the initial time period.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">period<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The time period in which the limit applies. Valid values are &#34;DAY&#34;, &#34;WEEK&#34; or &#34;MONTH&#34;.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### UsagePlanThrottleSettings
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#UsagePlanThrottleSettings">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#UsagePlanThrottleSettings">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/apigateway?tab=doc#UsagePlanThrottleSettingsArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/apigateway?tab=doc#UsagePlanThrottleSettingsOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Apigateway.UsagePlanThrottleSettingsArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Apigateway.UsagePlanThrottleSettings.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Burst<wbr>Limit<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The API request burst limit, the maximum rate limit over a time ranging from one to a few seconds, depending upon whether the underlying token bucket is at its full capacity.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Rate<wbr>Limit<span class="property-indicator"></span>
        <span class="property-type">double?</span>
    </dt>
    <dd>{{% md %}}The API request steady-state rate limit.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Burst<wbr>Limit<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The API request burst limit, the maximum rate limit over a time ranging from one to a few seconds, depending upon whether the underlying token bucket is at its full capacity.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Rate<wbr>Limit<span class="property-indicator"></span>
        <span class="property-type">*float64</span>
    </dt>
    <dd>{{% md %}}The API request steady-state rate limit.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">burst<wbr>Limit<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The API request burst limit, the maximum rate limit over a time ranging from one to a few seconds, depending upon whether the underlying token bucket is at its full capacity.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">rate<wbr>Limit<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The API request steady-state rate limit.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">burst<wbr>Limit<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The API request burst limit, the maximum rate limit over a time ranging from one to a few seconds, depending upon whether the underlying token bucket is at its full capacity.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">rate_<wbr>limit<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The API request steady-state rate limit.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}









---
title: "App"
block_external_search_index: true
---

Provides a Pinpoint App resource.

## Example Usage

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const example = new aws.pinpoint.App("example", {
    limits: {
        maximumDuration: 600,
    },
    quietTime: {
        end: "06:00",
        start: "00:00",
    },
});
```

> This content is derived from https://github.com/terraform-providers/terraform-provider-aws/blob/master/website/docs/r/pinpoint_app.markdown.



## Create a App Resource

{{< chooser language "javascript,typescript,python,go,csharp" / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/pinpoint/#App">App</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/pinpoint/#AppArgs">AppArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">App</span><span class="p">(resource_name, opts=None, </span>campaign_hook=None<span class="p">, </span>limits=None<span class="p">, </span>name=None<span class="p">, </span>name_prefix=None<span class="p">, </span>quiet_time=None<span class="p">, </span>tags=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewApp<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/pinpoint?tab=doc#AppArgs">AppArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/pinpoint?tab=doc#App">App</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Pinpoint.App.html">App</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Pinpoint.AppArgs.html">AppArgs</a></span>? <span class="nx">args = null<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
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
            title="Optional">Campaign<wbr>Hook<span class="property-indicator"></span>
        <span class="property-type"><a href="#appcampaignhook">App<wbr>Campaign<wbr>Hook<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}The default campaign limits for the app. These limits apply to each campaign for the app, unless the campaign overrides the default with limits of its own
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Limits<span class="property-indicator"></span>
        <span class="property-type"><a href="#applimits">App<wbr>Limits<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}The default campaign limits for the app. These limits apply to each campaign for the app, unless the campaign overrides the default with limits of its own
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The application name. By default generated by this provider
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<wbr>Prefix<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the Pinpoint application. Conflicts with `name`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Quiet<wbr>Time<span class="property-indicator"></span>
        <span class="property-type"><a href="#appquiettime">App<wbr>Quiet<wbr>Time<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}The default quiet time for the app. Each campaign for this app sends no messages during this time unless the campaign overrides the default with a quiet time of its own
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
            title="Optional">Campaign<wbr>Hook<span class="property-indicator"></span>
        <span class="property-type"><a href="#appcampaignhook">*App<wbr>Campaign<wbr>Hook</a></span>
    </dt>
    <dd>{{% md %}}The default campaign limits for the app. These limits apply to each campaign for the app, unless the campaign overrides the default with limits of its own
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Limits<span class="property-indicator"></span>
        <span class="property-type"><a href="#applimits">*App<wbr>Limits</a></span>
    </dt>
    <dd>{{% md %}}The default campaign limits for the app. These limits apply to each campaign for the app, unless the campaign overrides the default with limits of its own
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The application name. By default generated by this provider
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<wbr>Prefix<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name of the Pinpoint application. Conflicts with `name`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Quiet<wbr>Time<span class="property-indicator"></span>
        <span class="property-type"><a href="#appquiettime">*App<wbr>Quiet<wbr>Time</a></span>
    </dt>
    <dd>{{% md %}}The default quiet time for the app. Each campaign for this app sends no messages during this time unless the campaign overrides the default with a quiet time of its own
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
            title="Optional">campaign<wbr>Hook<span class="property-indicator"></span>
        <span class="property-type"><a href="#appcampaignhook">App<wbr>Campaign<wbr>Hook?</a></span>
    </dt>
    <dd>{{% md %}}The default campaign limits for the app. These limits apply to each campaign for the app, unless the campaign overrides the default with limits of its own
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">limits<span class="property-indicator"></span>
        <span class="property-type"><a href="#applimits">App<wbr>Limits?</a></span>
    </dt>
    <dd>{{% md %}}The default campaign limits for the app. These limits apply to each campaign for the app, unless the campaign overrides the default with limits of its own
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The application name. By default generated by this provider
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<wbr>Prefix<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the Pinpoint application. Conflicts with `name`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">quiet<wbr>Time<span class="property-indicator"></span>
        <span class="property-type"><a href="#appquiettime">App<wbr>Quiet<wbr>Time?</a></span>
    </dt>
    <dd>{{% md %}}The default quiet time for the app. Each campaign for this app sends no messages during this time unless the campaign overrides the default with a quiet time of its own
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
            title="Optional">campaign_<wbr>hook<span class="property-indicator"></span>
        <span class="property-type"><a href="#appcampaignhook">Dict[App<wbr>Campaign<wbr>Hook]</a></span>
    </dt>
    <dd>{{% md %}}The default campaign limits for the app. These limits apply to each campaign for the app, unless the campaign overrides the default with limits of its own
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">limits<span class="property-indicator"></span>
        <span class="property-type"><a href="#applimits">Dict[App<wbr>Limits]</a></span>
    </dt>
    <dd>{{% md %}}The default campaign limits for the app. These limits apply to each campaign for the app, unless the campaign overrides the default with limits of its own
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The application name. By default generated by this provider
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name_<wbr>prefix<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the Pinpoint application. Conflicts with `name`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">quiet_<wbr>time<span class="property-indicator"></span>
        <span class="property-type"><a href="#appquiettime">Dict[App<wbr>Quiet<wbr>Time]</a></span>
    </dt>
    <dd>{{% md %}}The default quiet time for the app. Each campaign for this app sends no messages during this time unless the campaign overrides the default with a quiet time of its own
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}Key-value mapping of resource tags
{{% /md %}}</dd>

</dl>
{{% /choosable %}}




## App Output Properties

The following output properties are available:




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Application<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Application ID of the Pinpoint App.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of the PinPoint Application
{{% /md %}}</dd>

    <dt class="property-"
            title="">Campaign<wbr>Hook<span class="property-indicator"></span>
        <span class="property-type"><a href="#appcampaignhook">App<wbr>Campaign<wbr>Hook?</a></span>
    </dt>
    <dd>{{% md %}}The default campaign limits for the app. These limits apply to each campaign for the app, unless the campaign overrides the default with limits of its own
{{% /md %}}</dd>

    <dt class="property-"
            title="">Limits<span class="property-indicator"></span>
        <span class="property-type"><a href="#applimits">App<wbr>Limits?</a></span>
    </dt>
    <dd>{{% md %}}The default campaign limits for the app. These limits apply to each campaign for the app, unless the campaign overrides the default with limits of its own
{{% /md %}}</dd>

    <dt class="property-"
            title="">Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The application name. By default generated by this provider
{{% /md %}}</dd>

    <dt class="property-"
            title="">Name<wbr>Prefix<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the Pinpoint application. Conflicts with `name`
{{% /md %}}</dd>

    <dt class="property-"
            title="">Quiet<wbr>Time<span class="property-indicator"></span>
        <span class="property-type"><a href="#appquiettime">App<wbr>Quiet<wbr>Time?</a></span>
    </dt>
    <dd>{{% md %}}The default quiet time for the app. Each campaign for this app sends no messages during this time unless the campaign overrides the default with a quiet time of its own
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
            title="">Application<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Application ID of the Pinpoint App.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of the PinPoint Application
{{% /md %}}</dd>

    <dt class="property-"
            title="">Campaign<wbr>Hook<span class="property-indicator"></span>
        <span class="property-type"><a href="#appcampaignhook">*App<wbr>Campaign<wbr>Hook</a></span>
    </dt>
    <dd>{{% md %}}The default campaign limits for the app. These limits apply to each campaign for the app, unless the campaign overrides the default with limits of its own
{{% /md %}}</dd>

    <dt class="property-"
            title="">Limits<span class="property-indicator"></span>
        <span class="property-type"><a href="#applimits">*App<wbr>Limits</a></span>
    </dt>
    <dd>{{% md %}}The default campaign limits for the app. These limits apply to each campaign for the app, unless the campaign overrides the default with limits of its own
{{% /md %}}</dd>

    <dt class="property-"
            title="">Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The application name. By default generated by this provider
{{% /md %}}</dd>

    <dt class="property-"
            title="">Name<wbr>Prefix<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name of the Pinpoint application. Conflicts with `name`
{{% /md %}}</dd>

    <dt class="property-"
            title="">Quiet<wbr>Time<span class="property-indicator"></span>
        <span class="property-type"><a href="#appquiettime">*App<wbr>Quiet<wbr>Time</a></span>
    </dt>
    <dd>{{% md %}}The default quiet time for the app. Each campaign for this app sends no messages during this time unless the campaign overrides the default with a quiet time of its own
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
            title="">application<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Application ID of the Pinpoint App.
{{% /md %}}</dd>

    <dt class="property-"
            title="">arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of the PinPoint Application
{{% /md %}}</dd>

    <dt class="property-"
            title="">campaign<wbr>Hook<span class="property-indicator"></span>
        <span class="property-type"><a href="#appcampaignhook">App<wbr>Campaign<wbr>Hook?</a></span>
    </dt>
    <dd>{{% md %}}The default campaign limits for the app. These limits apply to each campaign for the app, unless the campaign overrides the default with limits of its own
{{% /md %}}</dd>

    <dt class="property-"
            title="">limits<span class="property-indicator"></span>
        <span class="property-type"><a href="#applimits">App<wbr>Limits?</a></span>
    </dt>
    <dd>{{% md %}}The default campaign limits for the app. These limits apply to each campaign for the app, unless the campaign overrides the default with limits of its own
{{% /md %}}</dd>

    <dt class="property-"
            title="">name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The application name. By default generated by this provider
{{% /md %}}</dd>

    <dt class="property-"
            title="">name<wbr>Prefix<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the Pinpoint application. Conflicts with `name`
{{% /md %}}</dd>

    <dt class="property-"
            title="">quiet<wbr>Time<span class="property-indicator"></span>
        <span class="property-type"><a href="#appquiettime">App<wbr>Quiet<wbr>Time?</a></span>
    </dt>
    <dd>{{% md %}}The default quiet time for the app. Each campaign for this app sends no messages during this time unless the campaign overrides the default with a quiet time of its own
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
            title="">application_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The Application ID of the Pinpoint App.
{{% /md %}}</dd>

    <dt class="property-"
            title="">arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of the PinPoint Application
{{% /md %}}</dd>

    <dt class="property-"
            title="">campaign_<wbr>hook<span class="property-indicator"></span>
        <span class="property-type"><a href="#appcampaignhook">Dict[App<wbr>Campaign<wbr>Hook]</a></span>
    </dt>
    <dd>{{% md %}}The default campaign limits for the app. These limits apply to each campaign for the app, unless the campaign overrides the default with limits of its own
{{% /md %}}</dd>

    <dt class="property-"
            title="">limits<span class="property-indicator"></span>
        <span class="property-type"><a href="#applimits">Dict[App<wbr>Limits]</a></span>
    </dt>
    <dd>{{% md %}}The default campaign limits for the app. These limits apply to each campaign for the app, unless the campaign overrides the default with limits of its own
{{% /md %}}</dd>

    <dt class="property-"
            title="">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The application name. By default generated by this provider
{{% /md %}}</dd>

    <dt class="property-"
            title="">name_<wbr>prefix<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the Pinpoint application. Conflicts with `name`
{{% /md %}}</dd>

    <dt class="property-"
            title="">quiet_<wbr>time<span class="property-indicator"></span>
        <span class="property-type"><a href="#appquiettime">Dict[App<wbr>Quiet<wbr>Time]</a></span>
    </dt>
    <dd>{{% md %}}The default quiet time for the app. Each campaign for this app sends no messages during this time unless the campaign overrides the default with a quiet time of its own
{{% /md %}}</dd>

    <dt class="property-"
            title="">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}Key-value mapping of resource tags
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





## Look up an Existing App Resource

{{< chooser language "javascript,typescript,python,go,csharp  " / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">pulumi.Input&lt;pulumi.ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/pinpoint/#AppState">AppState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/pinpoint/#App">App</a></span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>application_id=None<span class="p">, </span>arn=None<span class="p">, </span>campaign_hook=None<span class="p">, </span>limits=None<span class="p">, </span>name=None<span class="p">, </span>name_prefix=None<span class="p">, </span>quiet_time=None<span class="p">, </span>tags=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetApp<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">pulumi.IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/pinpoint?tab=doc#AppState">AppState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/pinpoint?tab=doc#App">App</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Pinpoint.App.html">App</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Pulumi.Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Pinpoint.AppState.html">AppState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
{{% /choosable %}}

Get an existing App resource's state with the given name, ID, and optional extra properties used to qualify the lookup.

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
            title="Optional">Application<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The Application ID of the Pinpoint App.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of the PinPoint Application
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Campaign<wbr>Hook<span class="property-indicator"></span>
        <span class="property-type"><a href="#appcampaignhook">App<wbr>Campaign<wbr>Hook<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}The default campaign limits for the app. These limits apply to each campaign for the app, unless the campaign overrides the default with limits of its own
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Limits<span class="property-indicator"></span>
        <span class="property-type"><a href="#applimits">App<wbr>Limits<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}The default campaign limits for the app. These limits apply to each campaign for the app, unless the campaign overrides the default with limits of its own
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The application name. By default generated by this provider
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<wbr>Prefix<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the Pinpoint application. Conflicts with `name`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Quiet<wbr>Time<span class="property-indicator"></span>
        <span class="property-type"><a href="#appquiettime">App<wbr>Quiet<wbr>Time<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}The default quiet time for the app. Each campaign for this app sends no messages during this time unless the campaign overrides the default with a quiet time of its own
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
            title="Optional">Application<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The Application ID of the Pinpoint App.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of the PinPoint Application
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Campaign<wbr>Hook<span class="property-indicator"></span>
        <span class="property-type"><a href="#appcampaignhook">*App<wbr>Campaign<wbr>Hook</a></span>
    </dt>
    <dd>{{% md %}}The default campaign limits for the app. These limits apply to each campaign for the app, unless the campaign overrides the default with limits of its own
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Limits<span class="property-indicator"></span>
        <span class="property-type"><a href="#applimits">*App<wbr>Limits</a></span>
    </dt>
    <dd>{{% md %}}The default campaign limits for the app. These limits apply to each campaign for the app, unless the campaign overrides the default with limits of its own
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The application name. By default generated by this provider
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<wbr>Prefix<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name of the Pinpoint application. Conflicts with `name`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Quiet<wbr>Time<span class="property-indicator"></span>
        <span class="property-type"><a href="#appquiettime">*App<wbr>Quiet<wbr>Time</a></span>
    </dt>
    <dd>{{% md %}}The default quiet time for the app. Each campaign for this app sends no messages during this time unless the campaign overrides the default with a quiet time of its own
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
            title="Optional">application<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The Application ID of the Pinpoint App.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of the PinPoint Application
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">campaign<wbr>Hook<span class="property-indicator"></span>
        <span class="property-type"><a href="#appcampaignhook">App<wbr>Campaign<wbr>Hook?</a></span>
    </dt>
    <dd>{{% md %}}The default campaign limits for the app. These limits apply to each campaign for the app, unless the campaign overrides the default with limits of its own
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">limits<span class="property-indicator"></span>
        <span class="property-type"><a href="#applimits">App<wbr>Limits?</a></span>
    </dt>
    <dd>{{% md %}}The default campaign limits for the app. These limits apply to each campaign for the app, unless the campaign overrides the default with limits of its own
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The application name. By default generated by this provider
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<wbr>Prefix<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the Pinpoint application. Conflicts with `name`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">quiet<wbr>Time<span class="property-indicator"></span>
        <span class="property-type"><a href="#appquiettime">App<wbr>Quiet<wbr>Time?</a></span>
    </dt>
    <dd>{{% md %}}The default quiet time for the app. Each campaign for this app sends no messages during this time unless the campaign overrides the default with a quiet time of its own
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
            title="Optional">application_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The Application ID of the Pinpoint App.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of the PinPoint Application
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">campaign_<wbr>hook<span class="property-indicator"></span>
        <span class="property-type"><a href="#appcampaignhook">Dict[App<wbr>Campaign<wbr>Hook]</a></span>
    </dt>
    <dd>{{% md %}}The default campaign limits for the app. These limits apply to each campaign for the app, unless the campaign overrides the default with limits of its own
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">limits<span class="property-indicator"></span>
        <span class="property-type"><a href="#applimits">Dict[App<wbr>Limits]</a></span>
    </dt>
    <dd>{{% md %}}The default campaign limits for the app. These limits apply to each campaign for the app, unless the campaign overrides the default with limits of its own
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The application name. By default generated by this provider
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name_<wbr>prefix<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the Pinpoint application. Conflicts with `name`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">quiet_<wbr>time<span class="property-indicator"></span>
        <span class="property-type"><a href="#appquiettime">Dict[App<wbr>Quiet<wbr>Time]</a></span>
    </dt>
    <dd>{{% md %}}The default quiet time for the app. Each campaign for this app sends no messages during this time unless the campaign overrides the default with a quiet time of its own
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

#### AppCampaignHook
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#AppCampaignHook">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#AppCampaignHook">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/pinpoint?tab=doc#AppCampaignHookArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/pinpoint?tab=doc#AppCampaignHookOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Pinpoint.AppCampaignHookArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Pinpoint.AppCampaignHook.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Lambda<wbr>Function<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Lambda function name or ARN to be called for delivery. Conflicts with `web_url`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Mode<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}What mode Lambda should be invoked in. Valid values for this parameter are `DELIVERY`, `FILTER`.  
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Web<wbr>Url<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Web URL to call for hook. If the URL has authentication specified it will be added as authentication to the request. Conflicts with `lambda_function_name`
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Lambda<wbr>Function<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Lambda function name or ARN to be called for delivery. Conflicts with `web_url`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Mode<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}What mode Lambda should be invoked in. Valid values for this parameter are `DELIVERY`, `FILTER`.  
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Web<wbr>Url<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Web URL to call for hook. If the URL has authentication specified it will be added as authentication to the request. Conflicts with `lambda_function_name`
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">lambda<wbr>Function<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Lambda function name or ARN to be called for delivery. Conflicts with `web_url`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">mode<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}What mode Lambda should be invoked in. Valid values for this parameter are `DELIVERY`, `FILTER`.  
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">web<wbr>Url<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Web URL to call for hook. If the URL has authentication specified it will be added as authentication to the request. Conflicts with `lambda_function_name`
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">lambda<wbr>Function<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Lambda function name or ARN to be called for delivery. Conflicts with `web_url`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">mode<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}What mode Lambda should be invoked in. Valid values for this parameter are `DELIVERY`, `FILTER`.  
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">web<wbr>Url<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Web URL to call for hook. If the URL has authentication specified it will be added as authentication to the request. Conflicts with `lambda_function_name`
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### AppLimits
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#AppLimits">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#AppLimits">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/pinpoint?tab=doc#AppLimitsArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/pinpoint?tab=doc#AppLimitsOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Pinpoint.AppLimitsArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Pinpoint.AppLimits.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Daily<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The maximum number of messages that the campaign can send daily. 
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Maximum<wbr>Duration<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The length of time (in seconds) that the campaign can run before it ends and message deliveries stop. This duration begins at the scheduled start time for the campaign. The minimum value is 60.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Messages<wbr>Per<wbr>Second<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The number of messages that the campaign can send per second. The minimum value is 50, and the maximum is 20000.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Total<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The maximum total number of messages that the campaign can send.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Daily<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The maximum number of messages that the campaign can send daily. 
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Maximum<wbr>Duration<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The length of time (in seconds) that the campaign can run before it ends and message deliveries stop. This duration begins at the scheduled start time for the campaign. The minimum value is 60.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Messages<wbr>Per<wbr>Second<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The number of messages that the campaign can send per second. The minimum value is 50, and the maximum is 20000.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Total<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The maximum total number of messages that the campaign can send.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">daily<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The maximum number of messages that the campaign can send daily. 
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">maximum<wbr>Duration<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The length of time (in seconds) that the campaign can run before it ends and message deliveries stop. This duration begins at the scheduled start time for the campaign. The minimum value is 60.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">messages<wbr>Per<wbr>Second<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The number of messages that the campaign can send per second. The minimum value is 50, and the maximum is 20000.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">total<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The maximum total number of messages that the campaign can send.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">daily<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The maximum number of messages that the campaign can send daily. 
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">maximum<wbr>Duration<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The length of time (in seconds) that the campaign can run before it ends and message deliveries stop. This duration begins at the scheduled start time for the campaign. The minimum value is 60.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">messages_<wbr>per_<wbr>second<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The number of messages that the campaign can send per second. The minimum value is 50, and the maximum is 20000.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">total<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The maximum total number of messages that the campaign can send.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### AppQuietTime
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#AppQuietTime">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#AppQuietTime">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/pinpoint?tab=doc#AppQuietTimeArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/pinpoint?tab=doc#AppQuietTimeOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Pinpoint.AppQuietTimeArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Pinpoint.AppQuietTime.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">End<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The default end time for quiet time in ISO 8601 format. Required if `start` is set
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Start<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The default start time for quiet time in ISO 8601 format. Required if `end` is set
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">End<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The default end time for quiet time in ISO 8601 format. Required if `start` is set
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Start<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The default start time for quiet time in ISO 8601 format. Required if `end` is set
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">end<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The default end time for quiet time in ISO 8601 format. Required if `start` is set
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">start<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The default start time for quiet time in ISO 8601 format. Required if `end` is set
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">end<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The default end time for quiet time in ISO 8601 format. Required if `start` is set
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">start<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The default start time for quiet time in ISO 8601 format. Required if `end` is set
{{% /md %}}</dd>

</dl>
{{% /choosable %}}








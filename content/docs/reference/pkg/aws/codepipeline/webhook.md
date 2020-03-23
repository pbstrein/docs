
---
title: "Webhook"
block_external_search_index: true
---

Provides a CodePipeline Webhook.

> This content is derived from https://github.com/terraform-providers/terraform-provider-aws/blob/master/website/docs/r/codepipeline_webhook.markdown.



## Create a Webhook Resource

{{< chooser language "javascript,typescript,python,go,csharp" / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/codepipeline/#Webhook">Webhook</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/codepipeline/#WebhookArgs">WebhookArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">Webhook</span><span class="p">(resource_name, opts=None, </span>authentication=None<span class="p">, </span>authentication_configuration=None<span class="p">, </span>filters=None<span class="p">, </span>name=None<span class="p">, </span>tags=None<span class="p">, </span>target_action=None<span class="p">, </span>target_pipeline=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewWebhook<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/codepipeline?tab=doc#WebhookArgs">WebhookArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/codepipeline?tab=doc#Webhook">Webhook</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Codepipeline.Webhook.html">Webhook</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Codepipeline.WebhookArgs.html">WebhookArgs</a></span> <span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
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
            title="Required">Authentication<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type of authentication  to use. One of `IP`, `GITHUB_HMAC`, or `UNAUTHENTICATED`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Authentication<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#webhookauthenticationconfiguration">Webhook<wbr>Authentication<wbr>Configuration<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}An `auth` block. Required for `IP` and `GITHUB_HMAC`. Auth blocks are documented below.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Filters<span class="property-indicator"></span>
        <span class="property-type"><a href="#webhookfilter">List&lt;Webhook<wbr>Filter<wbr>Args&gt;</a></span>
    </dt>
    <dd>{{% md %}}One or more `filter` blocks. Filter blocks are documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the webhook.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Target<wbr>Action<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the action in a pipeline you want to connect to the webhook. The action must be from the source (first) stage of the pipeline.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Target<wbr>Pipeline<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the pipeline.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Authentication<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type of authentication  to use. One of `IP`, `GITHUB_HMAC`, or `UNAUTHENTICATED`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Authentication<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#webhookauthenticationconfiguration">*Webhook<wbr>Authentication<wbr>Configuration</a></span>
    </dt>
    <dd>{{% md %}}An `auth` block. Required for `IP` and `GITHUB_HMAC`. Auth blocks are documented below.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Filters<span class="property-indicator"></span>
        <span class="property-type"><a href="#webhookfilter">[]Webhook<wbr>Filter</a></span>
    </dt>
    <dd>{{% md %}}One or more `filter` blocks. Filter blocks are documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name of the webhook.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Target<wbr>Action<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the action in a pipeline you want to connect to the webhook. The action must be from the source (first) stage of the pipeline.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Target<wbr>Pipeline<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the pipeline.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">authentication<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type of authentication  to use. One of `IP`, `GITHUB_HMAC`, or `UNAUTHENTICATED`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">authentication<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#webhookauthenticationconfiguration">Webhook<wbr>Authentication<wbr>Configuration?</a></span>
    </dt>
    <dd>{{% md %}}An `auth` block. Required for `IP` and `GITHUB_HMAC`. Auth blocks are documented below.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">filters<span class="property-indicator"></span>
        <span class="property-type"><a href="#webhookfilter">Webhook<wbr>Filter[]</a></span>
    </dt>
    <dd>{{% md %}}One or more `filter` blocks. Filter blocks are documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the webhook.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">target<wbr>Action<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the action in a pipeline you want to connect to the webhook. The action must be from the source (first) stage of the pipeline.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">target<wbr>Pipeline<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the pipeline.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">authentication<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The type of authentication  to use. One of `IP`, `GITHUB_HMAC`, or `UNAUTHENTICATED`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">authentication_<wbr>configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#webhookauthenticationconfiguration">Dict[Webhook<wbr>Authentication<wbr>Configuration]</a></span>
    </dt>
    <dd>{{% md %}}An `auth` block. Required for `IP` and `GITHUB_HMAC`. Auth blocks are documented below.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">filters<span class="property-indicator"></span>
        <span class="property-type"><a href="#webhookfilter">List[Webhook<wbr>Filter]</a></span>
    </dt>
    <dd>{{% md %}}One or more `filter` blocks. Filter blocks are documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the webhook.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">target_<wbr>action<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the action in a pipeline you want to connect to the webhook. The action must be from the source (first) stage of the pipeline.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">target_<wbr>pipeline<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the pipeline.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}




## Webhook Output Properties

The following output properties are available:




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Authentication<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type of authentication  to use. One of `IP`, `GITHUB_HMAC`, or `UNAUTHENTICATED`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Authentication<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#webhookauthenticationconfiguration">Webhook<wbr>Authentication<wbr>Configuration?</a></span>
    </dt>
    <dd>{{% md %}}An `auth` block. Required for `IP` and `GITHUB_HMAC`. Auth blocks are documented below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Filters<span class="property-indicator"></span>
        <span class="property-type"><a href="#webhookfilter">List&lt;Webhook<wbr>Filter&gt;</a></span>
    </dt>
    <dd>{{% md %}}One or more `filter` blocks. Filter blocks are documented below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the webhook.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Target<wbr>Action<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the action in a pipeline you want to connect to the webhook. The action must be from the source (first) stage of the pipeline.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Target<wbr>Pipeline<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the pipeline.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Url<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The CodePipeline webhook&#39;s URL. POST events to this endpoint to trigger the target.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Authentication<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type of authentication  to use. One of `IP`, `GITHUB_HMAC`, or `UNAUTHENTICATED`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Authentication<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#webhookauthenticationconfiguration">*Webhook<wbr>Authentication<wbr>Configuration</a></span>
    </dt>
    <dd>{{% md %}}An `auth` block. Required for `IP` and `GITHUB_HMAC`. Auth blocks are documented below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Filters<span class="property-indicator"></span>
        <span class="property-type"><a href="#webhookfilter">[]Webhook<wbr>Filter</a></span>
    </dt>
    <dd>{{% md %}}One or more `filter` blocks. Filter blocks are documented below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the webhook.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Target<wbr>Action<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the action in a pipeline you want to connect to the webhook. The action must be from the source (first) stage of the pipeline.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Target<wbr>Pipeline<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the pipeline.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Url<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The CodePipeline webhook&#39;s URL. POST events to this endpoint to trigger the target.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">authentication<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type of authentication  to use. One of `IP`, `GITHUB_HMAC`, or `UNAUTHENTICATED`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">authentication<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#webhookauthenticationconfiguration">Webhook<wbr>Authentication<wbr>Configuration?</a></span>
    </dt>
    <dd>{{% md %}}An `auth` block. Required for `IP` and `GITHUB_HMAC`. Auth blocks are documented below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">filters<span class="property-indicator"></span>
        <span class="property-type"><a href="#webhookfilter">Webhook<wbr>Filter[]</a></span>
    </dt>
    <dd>{{% md %}}One or more `filter` blocks. Filter blocks are documented below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the webhook.
{{% /md %}}</dd>

    <dt class="property-"
            title="">tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-"
            title="">target<wbr>Action<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the action in a pipeline you want to connect to the webhook. The action must be from the source (first) stage of the pipeline.
{{% /md %}}</dd>

    <dt class="property-"
            title="">target<wbr>Pipeline<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the pipeline.
{{% /md %}}</dd>

    <dt class="property-"
            title="">url<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The CodePipeline webhook&#39;s URL. POST events to this endpoint to trigger the target.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">authentication<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The type of authentication  to use. One of `IP`, `GITHUB_HMAC`, or `UNAUTHENTICATED`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">authentication_<wbr>configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#webhookauthenticationconfiguration">Dict[Webhook<wbr>Authentication<wbr>Configuration]</a></span>
    </dt>
    <dd>{{% md %}}An `auth` block. Required for `IP` and `GITHUB_HMAC`. Auth blocks are documented below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">filters<span class="property-indicator"></span>
        <span class="property-type"><a href="#webhookfilter">List[Webhook<wbr>Filter]</a></span>
    </dt>
    <dd>{{% md %}}One or more `filter` blocks. Filter blocks are documented below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the webhook.
{{% /md %}}</dd>

    <dt class="property-"
            title="">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-"
            title="">target_<wbr>action<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the action in a pipeline you want to connect to the webhook. The action must be from the source (first) stage of the pipeline.
{{% /md %}}</dd>

    <dt class="property-"
            title="">target_<wbr>pipeline<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the pipeline.
{{% /md %}}</dd>

    <dt class="property-"
            title="">url<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The CodePipeline webhook&#39;s URL. POST events to this endpoint to trigger the target.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





## Look up an Existing Webhook Resource

{{< chooser language "javascript,typescript,python,go,csharp  " / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">pulumi.Input&lt;pulumi.ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/codepipeline/#WebhookState">WebhookState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/codepipeline/#Webhook">Webhook</a></span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>authentication=None<span class="p">, </span>authentication_configuration=None<span class="p">, </span>filters=None<span class="p">, </span>name=None<span class="p">, </span>tags=None<span class="p">, </span>target_action=None<span class="p">, </span>target_pipeline=None<span class="p">, </span>url=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetWebhook<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">pulumi.IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/codepipeline?tab=doc#WebhookState">WebhookState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/codepipeline?tab=doc#Webhook">Webhook</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Codepipeline.Webhook.html">Webhook</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Pulumi.Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Codepipeline.WebhookState.html">WebhookState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
{{% /choosable %}}

Get an existing Webhook resource's state with the given name, ID, and optional extra properties used to qualify the lookup.

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
            title="Optional">Authentication<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The type of authentication  to use. One of `IP`, `GITHUB_HMAC`, or `UNAUTHENTICATED`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Authentication<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#webhookauthenticationconfiguration">Webhook<wbr>Authentication<wbr>Configuration<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}An `auth` block. Required for `IP` and `GITHUB_HMAC`. Auth blocks are documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Filters<span class="property-indicator"></span>
        <span class="property-type"><a href="#webhookfilter">List&lt;Webhook<wbr>Filter<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}One or more `filter` blocks. Filter blocks are documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the webhook.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Target<wbr>Action<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the action in a pipeline you want to connect to the webhook. The action must be from the source (first) stage of the pipeline.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Target<wbr>Pipeline<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the pipeline.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Url<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The CodePipeline webhook&#39;s URL. POST events to this endpoint to trigger the target.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Authentication<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The type of authentication  to use. One of `IP`, `GITHUB_HMAC`, or `UNAUTHENTICATED`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Authentication<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#webhookauthenticationconfiguration">*Webhook<wbr>Authentication<wbr>Configuration</a></span>
    </dt>
    <dd>{{% md %}}An `auth` block. Required for `IP` and `GITHUB_HMAC`. Auth blocks are documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Filters<span class="property-indicator"></span>
        <span class="property-type"><a href="#webhookfilter">[]Webhook<wbr>Filter</a></span>
    </dt>
    <dd>{{% md %}}One or more `filter` blocks. Filter blocks are documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name of the webhook.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Target<wbr>Action<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name of the action in a pipeline you want to connect to the webhook. The action must be from the source (first) stage of the pipeline.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Target<wbr>Pipeline<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name of the pipeline.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Url<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The CodePipeline webhook&#39;s URL. POST events to this endpoint to trigger the target.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">authentication<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The type of authentication  to use. One of `IP`, `GITHUB_HMAC`, or `UNAUTHENTICATED`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">authentication<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#webhookauthenticationconfiguration">Webhook<wbr>Authentication<wbr>Configuration?</a></span>
    </dt>
    <dd>{{% md %}}An `auth` block. Required for `IP` and `GITHUB_HMAC`. Auth blocks are documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">filters<span class="property-indicator"></span>
        <span class="property-type"><a href="#webhookfilter">Webhook<wbr>Filter[]?</a></span>
    </dt>
    <dd>{{% md %}}One or more `filter` blocks. Filter blocks are documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the webhook.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">target<wbr>Action<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the action in a pipeline you want to connect to the webhook. The action must be from the source (first) stage of the pipeline.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">target<wbr>Pipeline<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the pipeline.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">url<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The CodePipeline webhook&#39;s URL. POST events to this endpoint to trigger the target.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">authentication<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The type of authentication  to use. One of `IP`, `GITHUB_HMAC`, or `UNAUTHENTICATED`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">authentication_<wbr>configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#webhookauthenticationconfiguration">Dict[Webhook<wbr>Authentication<wbr>Configuration]</a></span>
    </dt>
    <dd>{{% md %}}An `auth` block. Required for `IP` and `GITHUB_HMAC`. Auth blocks are documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">filters<span class="property-indicator"></span>
        <span class="property-type"><a href="#webhookfilter">List[Webhook<wbr>Filter]</a></span>
    </dt>
    <dd>{{% md %}}One or more `filter` blocks. Filter blocks are documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the webhook.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">target_<wbr>action<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the action in a pipeline you want to connect to the webhook. The action must be from the source (first) stage of the pipeline.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">target_<wbr>pipeline<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the pipeline.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">url<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The CodePipeline webhook&#39;s URL. POST events to this endpoint to trigger the target.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}







## Supporting Types

#### WebhookAuthenticationConfiguration
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#WebhookAuthenticationConfiguration">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#WebhookAuthenticationConfiguration">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/codepipeline?tab=doc#WebhookAuthenticationConfigurationArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/codepipeline?tab=doc#WebhookAuthenticationConfigurationOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Codepipeline.WebhookAuthenticationConfigurationArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Codepipeline.WebhookAuthenticationConfiguration.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Allowed<wbr>Ip<wbr>Range<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Secret<wbr>Token<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Allowed<wbr>Ip<wbr>Range<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Secret<wbr>Token<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">allowed<wbr>Ip<wbr>Range<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">secret<wbr>Token<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">allowed<wbr>Ip<wbr>Range<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">secret<wbr>Token<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### WebhookFilter
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#WebhookFilter">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#WebhookFilter">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/codepipeline?tab=doc#WebhookFilterArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/codepipeline?tab=doc#WebhookFilterOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Codepipeline.WebhookFilterArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Codepipeline.WebhookFilter.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Json<wbr>Path<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Match<wbr>Equals<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Json<wbr>Path<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Match<wbr>Equals<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">json<wbr>Path<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">match<wbr>Equals<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">json<wbr>Path<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">match<wbr>Equals<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}








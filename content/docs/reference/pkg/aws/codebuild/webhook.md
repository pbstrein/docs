
---
title: "Webhook"
block_external_search_index: true
---

Manages a CodeBuild webhook, which is an endpoint accepted by the CodeBuild service to trigger builds from source code repositories. Depending on the source type of the CodeBuild project, the CodeBuild service may also automatically create and delete the actual repository webhook as well.

## Example Usage

### Bitbucket and GitHub

When working with [Bitbucket](https://bitbucket.org) and [GitHub](https://github.com) source CodeBuild webhooks, the CodeBuild service will automatically create (on `aws.codebuild.Webhook` resource creation) and delete (on `aws.codebuild.Webhook` resource deletion) the Bitbucket/GitHub repository webhook using its granted OAuth permissions. This behavior cannot be controlled by this provider.

> **Note:** The AWS account that this provider uses to create this resource *must* have authorized CodeBuild to access Bitbucket/GitHub's OAuth API in each applicable region. This is a manual step that must be done *before* creating webhooks with this resource. If OAuth is not configured, AWS will return an error similar to `ResourceNotFoundException: Could not find access token for server type github`. More information can be found in the CodeBuild User Guide for [Bitbucket](https://docs.aws.amazon.com/codebuild/latest/userguide/sample-bitbucket-pull-request.html) and [GitHub](https://docs.aws.amazon.com/codebuild/latest/userguide/sample-github-pull-request.html).

> **Note:** Further managing the automatically created Bitbucket/GitHub webhook with the `bitbucket_hook`/`github_repository_webhook` resource is only possible with importing that resource after creation of the `aws.codebuild.Webhook` resource. The CodeBuild API does not ever provide the `secret` attribute for the `aws.codebuild.Webhook` resource in this scenario.

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const example = new aws.codebuild.Webhook("example", {
    filterGroups: [{
        filters: [
            {
                pattern: "PUSH",
                type: "EVENT",
            },
            {
                pattern: "master",
                type: "HEAD_REF",
            },
        ],
    }],
    projectName: aws_codebuild_project_example.name,
});
```

> This content is derived from https://github.com/terraform-providers/terraform-provider-aws/blob/master/website/docs/r/codebuild_webhook.html.markdown.



## Create a Webhook Resource

{{< chooser language "javascript,typescript,python,go,csharp" / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/codebuild/#Webhook">Webhook</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/codebuild/#WebhookArgs">WebhookArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">Webhook</span><span class="p">(resource_name, opts=None, </span>branch_filter=None<span class="p">, </span>filter_groups=None<span class="p">, </span>project_name=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewWebhook<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/codebuild?tab=doc#WebhookArgs">WebhookArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/codebuild?tab=doc#Webhook">Webhook</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Codebuild.Webhook.html">Webhook</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Codebuild.WebhookArgs.html">WebhookArgs</a></span> <span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
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
            title="Optional">Branch<wbr>Filter<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A regular expression used to determine which branches get built. Default is all branches are built. It is recommended to use `filter_group` over `branch_filter`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Filter<wbr>Groups<span class="property-indicator"></span>
        <span class="property-type"><a href="#webhookfiltergroup">List&lt;Webhook<wbr>Filter<wbr>Group<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}Information about the webhook&#39;s trigger. Filter group blocks are documented below.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Project<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the build project.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Branch<wbr>Filter<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}A regular expression used to determine which branches get built. Default is all branches are built. It is recommended to use `filter_group` over `branch_filter`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Filter<wbr>Groups<span class="property-indicator"></span>
        <span class="property-type"><a href="#webhookfiltergroup">[]Webhook<wbr>Filter<wbr>Group</a></span>
    </dt>
    <dd>{{% md %}}Information about the webhook&#39;s trigger. Filter group blocks are documented below.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Project<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the build project.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">branch<wbr>Filter<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A regular expression used to determine which branches get built. Default is all branches are built. It is recommended to use `filter_group` over `branch_filter`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">filter<wbr>Groups<span class="property-indicator"></span>
        <span class="property-type"><a href="#webhookfiltergroup">Webhook<wbr>Filter<wbr>Group[]?</a></span>
    </dt>
    <dd>{{% md %}}Information about the webhook&#39;s trigger. Filter group blocks are documented below.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">project<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the build project.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">branch_<wbr>filter<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A regular expression used to determine which branches get built. Default is all branches are built. It is recommended to use `filter_group` over `branch_filter`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">filter_<wbr>groups<span class="property-indicator"></span>
        <span class="property-type"><a href="#webhookfiltergroup">List[Webhook<wbr>Filter<wbr>Group]</a></span>
    </dt>
    <dd>{{% md %}}Information about the webhook&#39;s trigger. Filter group blocks are documented below.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">project_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the build project.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}




## Webhook Output Properties

The following output properties are available:




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Branch<wbr>Filter<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A regular expression used to determine which branches get built. Default is all branches are built. It is recommended to use `filter_group` over `branch_filter`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Filter<wbr>Groups<span class="property-indicator"></span>
        <span class="property-type"><a href="#webhookfiltergroup">List&lt;Webhook<wbr>Filter<wbr>Group&gt;?</a></span>
    </dt>
    <dd>{{% md %}}Information about the webhook&#39;s trigger. Filter group blocks are documented below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Payload<wbr>Url<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The CodeBuild endpoint where webhook events are sent.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Project<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the build project.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Secret<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The secret token of the associated repository. Not returned by the CodeBuild API for all source types.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Url<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The URL to the webhook.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Branch<wbr>Filter<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}A regular expression used to determine which branches get built. Default is all branches are built. It is recommended to use `filter_group` over `branch_filter`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Filter<wbr>Groups<span class="property-indicator"></span>
        <span class="property-type"><a href="#webhookfiltergroup">[]Webhook<wbr>Filter<wbr>Group</a></span>
    </dt>
    <dd>{{% md %}}Information about the webhook&#39;s trigger. Filter group blocks are documented below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Payload<wbr>Url<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The CodeBuild endpoint where webhook events are sent.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Project<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the build project.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Secret<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The secret token of the associated repository. Not returned by the CodeBuild API for all source types.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Url<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The URL to the webhook.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">branch<wbr>Filter<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A regular expression used to determine which branches get built. Default is all branches are built. It is recommended to use `filter_group` over `branch_filter`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">filter<wbr>Groups<span class="property-indicator"></span>
        <span class="property-type"><a href="#webhookfiltergroup">Webhook<wbr>Filter<wbr>Group[]?</a></span>
    </dt>
    <dd>{{% md %}}Information about the webhook&#39;s trigger. Filter group blocks are documented below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">payload<wbr>Url<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The CodeBuild endpoint where webhook events are sent.
{{% /md %}}</dd>

    <dt class="property-"
            title="">project<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the build project.
{{% /md %}}</dd>

    <dt class="property-"
            title="">secret<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The secret token of the associated repository. Not returned by the CodeBuild API for all source types.
{{% /md %}}</dd>

    <dt class="property-"
            title="">url<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The URL to the webhook.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">branch_<wbr>filter<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A regular expression used to determine which branches get built. Default is all branches are built. It is recommended to use `filter_group` over `branch_filter`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">filter_<wbr>groups<span class="property-indicator"></span>
        <span class="property-type"><a href="#webhookfiltergroup">List[Webhook<wbr>Filter<wbr>Group]</a></span>
    </dt>
    <dd>{{% md %}}Information about the webhook&#39;s trigger. Filter group blocks are documented below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">payload_<wbr>url<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The CodeBuild endpoint where webhook events are sent.
{{% /md %}}</dd>

    <dt class="property-"
            title="">project_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the build project.
{{% /md %}}</dd>

    <dt class="property-"
            title="">secret<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The secret token of the associated repository. Not returned by the CodeBuild API for all source types.
{{% /md %}}</dd>

    <dt class="property-"
            title="">url<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The URL to the webhook.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





## Look up an Existing Webhook Resource

{{< chooser language "javascript,typescript,python,go,csharp  " / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">pulumi.Input&lt;pulumi.ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/codebuild/#WebhookState">WebhookState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/codebuild/#Webhook">Webhook</a></span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>branch_filter=None<span class="p">, </span>filter_groups=None<span class="p">, </span>payload_url=None<span class="p">, </span>project_name=None<span class="p">, </span>secret=None<span class="p">, </span>url=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetWebhook<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">pulumi.IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/codebuild?tab=doc#WebhookState">WebhookState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/codebuild?tab=doc#Webhook">Webhook</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Codebuild.Webhook.html">Webhook</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Pulumi.Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Codebuild.WebhookState.html">WebhookState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
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
            title="Optional">Branch<wbr>Filter<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A regular expression used to determine which branches get built. Default is all branches are built. It is recommended to use `filter_group` over `branch_filter`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Filter<wbr>Groups<span class="property-indicator"></span>
        <span class="property-type"><a href="#webhookfiltergroup">List&lt;Webhook<wbr>Filter<wbr>Group<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}Information about the webhook&#39;s trigger. Filter group blocks are documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Payload<wbr>Url<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The CodeBuild endpoint where webhook events are sent.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Project<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the build project.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Secret<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The secret token of the associated repository. Not returned by the CodeBuild API for all source types.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Url<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The URL to the webhook.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Branch<wbr>Filter<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}A regular expression used to determine which branches get built. Default is all branches are built. It is recommended to use `filter_group` over `branch_filter`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Filter<wbr>Groups<span class="property-indicator"></span>
        <span class="property-type"><a href="#webhookfiltergroup">[]Webhook<wbr>Filter<wbr>Group</a></span>
    </dt>
    <dd>{{% md %}}Information about the webhook&#39;s trigger. Filter group blocks are documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Payload<wbr>Url<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The CodeBuild endpoint where webhook events are sent.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Project<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name of the build project.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Secret<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The secret token of the associated repository. Not returned by the CodeBuild API for all source types.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Url<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The URL to the webhook.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">branch<wbr>Filter<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A regular expression used to determine which branches get built. Default is all branches are built. It is recommended to use `filter_group` over `branch_filter`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">filter<wbr>Groups<span class="property-indicator"></span>
        <span class="property-type"><a href="#webhookfiltergroup">Webhook<wbr>Filter<wbr>Group[]?</a></span>
    </dt>
    <dd>{{% md %}}Information about the webhook&#39;s trigger. Filter group blocks are documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">payload<wbr>Url<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The CodeBuild endpoint where webhook events are sent.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">project<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the build project.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">secret<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The secret token of the associated repository. Not returned by the CodeBuild API for all source types.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">url<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The URL to the webhook.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">branch_<wbr>filter<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A regular expression used to determine which branches get built. Default is all branches are built. It is recommended to use `filter_group` over `branch_filter`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">filter_<wbr>groups<span class="property-indicator"></span>
        <span class="property-type"><a href="#webhookfiltergroup">List[Webhook<wbr>Filter<wbr>Group]</a></span>
    </dt>
    <dd>{{% md %}}Information about the webhook&#39;s trigger. Filter group blocks are documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">payload_<wbr>url<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The CodeBuild endpoint where webhook events are sent.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">project_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the build project.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">secret<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The secret token of the associated repository. Not returned by the CodeBuild API for all source types.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">url<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The URL to the webhook.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}







## Supporting Types

#### WebhookFilterGroup
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#WebhookFilterGroup">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#WebhookFilterGroup">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/codebuild?tab=doc#WebhookFilterGroupArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/codebuild?tab=doc#WebhookFilterGroupOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Codebuild.WebhookFilterGroupArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Codebuild.WebhookFilterGroup.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Filters<span class="property-indicator"></span>
        <span class="property-type"><a href="#webhookfiltergroupfilter">List&lt;Webhook<wbr>Filter<wbr>Group<wbr>Filter<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}A webhook filter for the group. Filter blocks are documented below.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Filters<span class="property-indicator"></span>
        <span class="property-type"><a href="#webhookfiltergroupfilter">[]Webhook<wbr>Filter<wbr>Group<wbr>Filter</a></span>
    </dt>
    <dd>{{% md %}}A webhook filter for the group. Filter blocks are documented below.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">filters<span class="property-indicator"></span>
        <span class="property-type"><a href="#webhookfiltergroupfilter">Webhook<wbr>Filter<wbr>Group<wbr>Filter[]?</a></span>
    </dt>
    <dd>{{% md %}}A webhook filter for the group. Filter blocks are documented below.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">filters<span class="property-indicator"></span>
        <span class="property-type"><a href="#webhookfiltergroupfilter">List[Webhook<wbr>Filter<wbr>Group<wbr>Filter]</a></span>
    </dt>
    <dd>{{% md %}}A webhook filter for the group. Filter blocks are documented below.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### WebhookFilterGroupFilter
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#WebhookFilterGroupFilter">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#WebhookFilterGroupFilter">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/codebuild?tab=doc#WebhookFilterGroupFilterArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/codebuild?tab=doc#WebhookFilterGroupFilterOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Codebuild.WebhookFilterGroupFilterArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Codebuild.WebhookFilterGroupFilter.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Exclude<wbr>Matched<wbr>Pattern<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}If set to `true`, the specified filter does *not* trigger a build. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Pattern<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}For a filter that uses `EVENT` type, a comma-separated string that specifies one event: `PUSH`, `PULL_REQUEST_CREATED`, `PULL_REQUEST_UPDATED`, `PULL_REQUEST_REOPENED`. `PULL_REQUEST_MERGED` works with GitHub &amp; GitHub Enterprise only. For a filter that uses any of the other filter types, a regular expression.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The webhook filter group&#39;s type. Valid values for this parameter are: `EVENT`, `BASE_REF`, `HEAD_REF`, `ACTOR_ACCOUNT_ID`, `FILE_PATH`. At least one filter group must specify `EVENT` as its type.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Exclude<wbr>Matched<wbr>Pattern<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}If set to `true`, the specified filter does *not* trigger a build. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Pattern<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}For a filter that uses `EVENT` type, a comma-separated string that specifies one event: `PUSH`, `PULL_REQUEST_CREATED`, `PULL_REQUEST_UPDATED`, `PULL_REQUEST_REOPENED`. `PULL_REQUEST_MERGED` works with GitHub &amp; GitHub Enterprise only. For a filter that uses any of the other filter types, a regular expression.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The webhook filter group&#39;s type. Valid values for this parameter are: `EVENT`, `BASE_REF`, `HEAD_REF`, `ACTOR_ACCOUNT_ID`, `FILE_PATH`. At least one filter group must specify `EVENT` as its type.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">exclude<wbr>Matched<wbr>Pattern<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}If set to `true`, the specified filter does *not* trigger a build. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">pattern<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}For a filter that uses `EVENT` type, a comma-separated string that specifies one event: `PUSH`, `PULL_REQUEST_CREATED`, `PULL_REQUEST_UPDATED`, `PULL_REQUEST_REOPENED`. `PULL_REQUEST_MERGED` works with GitHub &amp; GitHub Enterprise only. For a filter that uses any of the other filter types, a regular expression.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The webhook filter group&#39;s type. Valid values for this parameter are: `EVENT`, `BASE_REF`, `HEAD_REF`, `ACTOR_ACCOUNT_ID`, `FILE_PATH`. At least one filter group must specify `EVENT` as its type.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">exclude<wbr>Matched<wbr>Pattern<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}If set to `true`, the specified filter does *not* trigger a build. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">pattern<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}For a filter that uses `EVENT` type, a comma-separated string that specifies one event: `PUSH`, `PULL_REQUEST_CREATED`, `PULL_REQUEST_UPDATED`, `PULL_REQUEST_REOPENED`. `PULL_REQUEST_MERGED` works with GitHub &amp; GitHub Enterprise only. For a filter that uses any of the other filter types, a regular expression.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The webhook filter group&#39;s type. Valid values for this parameter are: `EVENT`, `BASE_REF`, `HEAD_REF`, `ACTOR_ACCOUNT_ID`, `FILE_PATH`. At least one filter group must specify `EVENT` as its type.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}








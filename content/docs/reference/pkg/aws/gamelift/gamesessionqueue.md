
---
title: "GameSessionQueue"
block_external_search_index: true
---

Provides an Gamelift Game Session Queue resource.

## Example Usage

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const test = new aws.gamelift.GameSessionQueue("test", {
    destinations: [
        aws_gamelift_fleet_us_west_2_fleet.arn,
        aws_gamelift_fleet_eu_central_1_fleet.arn,
    ],
    playerLatencyPolicies: [
        {
            maximumIndividualPlayerLatencyMilliseconds: 100,
            policyDurationSeconds: 5,
        },
        {
            maximumIndividualPlayerLatencyMilliseconds: 200,
        },
    ],
    timeoutInSeconds: 60,
});
```

> This content is derived from https://github.com/terraform-providers/terraform-provider-aws/blob/master/website/docs/r/gamelift_game_session_queue.html.markdown.



## Create a GameSessionQueue Resource

{{< chooser language "javascript,typescript,python,go,csharp" / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/gamelift/#GameSessionQueue">GameSessionQueue</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/gamelift/#GameSessionQueueArgs">GameSessionQueueArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">GameSessionQueue</span><span class="p">(resource_name, opts=None, </span>destinations=None<span class="p">, </span>name=None<span class="p">, </span>player_latency_policies=None<span class="p">, </span>tags=None<span class="p">, </span>timeout_in_seconds=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewGameSessionQueue<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/gamelift?tab=doc#GameSessionQueueArgs">GameSessionQueueArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/gamelift?tab=doc#GameSessionQueue">GameSessionQueue</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Gamelift.GameSessionQueue.html">GameSessionQueue</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Gamelift.GameSessionQueueArgs.html">GameSessionQueueArgs</a></span>? <span class="nx">args = null<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
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
            title="Optional">Destinations<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}List of fleet/alias ARNs used by session queue for placing game sessions.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Name of the session queue.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Player<wbr>Latency<wbr>Policies<span class="property-indicator"></span>
        <span class="property-type"><a href="#gamesessionqueueplayerlatencypolicy">List&lt;Game<wbr>Session<wbr>Queue<wbr>Player<wbr>Latency<wbr>Policy<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}One or more policies used to choose fleet based on player latency. See below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}Key-value mapping of resource tags
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Timeout<wbr>In<wbr>Seconds<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}Maximum time a game session request can remain in the queue.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Destinations<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}List of fleet/alias ARNs used by session queue for placing game sessions.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Name of the session queue.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Player<wbr>Latency<wbr>Policies<span class="property-indicator"></span>
        <span class="property-type"><a href="#gamesessionqueueplayerlatencypolicy">[]Game<wbr>Session<wbr>Queue<wbr>Player<wbr>Latency<wbr>Policy</a></span>
    </dt>
    <dd>{{% md %}}One or more policies used to choose fleet based on player latency. See below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}Key-value mapping of resource tags
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Timeout<wbr>In<wbr>Seconds<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}Maximum time a game session request can remain in the queue.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">destinations<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}List of fleet/alias ARNs used by session queue for placing game sessions.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Name of the session queue.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">player<wbr>Latency<wbr>Policies<span class="property-indicator"></span>
        <span class="property-type"><a href="#gamesessionqueueplayerlatencypolicy">Game<wbr>Session<wbr>Queue<wbr>Player<wbr>Latency<wbr>Policy[]?</a></span>
    </dt>
    <dd>{{% md %}}One or more policies used to choose fleet based on player latency. See below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}Key-value mapping of resource tags
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">timeout<wbr>In<wbr>Seconds<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}Maximum time a game session request can remain in the queue.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">destinations<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}List of fleet/alias ARNs used by session queue for placing game sessions.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Name of the session queue.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">player_<wbr>latency_<wbr>policies<span class="property-indicator"></span>
        <span class="property-type"><a href="#gamesessionqueueplayerlatencypolicy">List[Game<wbr>Session<wbr>Queue<wbr>Player<wbr>Latency<wbr>Policy]</a></span>
    </dt>
    <dd>{{% md %}}One or more policies used to choose fleet based on player latency. See below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}Key-value mapping of resource tags
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">timeout_<wbr>in_<wbr>seconds<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}Maximum time a game session request can remain in the queue.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}




## GameSessionQueue Output Properties

The following output properties are available:




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Game Session Queue ARN.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Destinations<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}List of fleet/alias ARNs used by session queue for placing game sessions.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Name of the session queue.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Player<wbr>Latency<wbr>Policies<span class="property-indicator"></span>
        <span class="property-type"><a href="#gamesessionqueueplayerlatencypolicy">List&lt;Game<wbr>Session<wbr>Queue<wbr>Player<wbr>Latency<wbr>Policy&gt;?</a></span>
    </dt>
    <dd>{{% md %}}One or more policies used to choose fleet based on player latency. See below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}Key-value mapping of resource tags
{{% /md %}}</dd>

    <dt class="property-"
            title="">Timeout<wbr>In<wbr>Seconds<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}Maximum time a game session request can remain in the queue.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Game Session Queue ARN.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Destinations<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}List of fleet/alias ARNs used by session queue for placing game sessions.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Name of the session queue.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Player<wbr>Latency<wbr>Policies<span class="property-indicator"></span>
        <span class="property-type"><a href="#gamesessionqueueplayerlatencypolicy">[]Game<wbr>Session<wbr>Queue<wbr>Player<wbr>Latency<wbr>Policy</a></span>
    </dt>
    <dd>{{% md %}}One or more policies used to choose fleet based on player latency. See below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}Key-value mapping of resource tags
{{% /md %}}</dd>

    <dt class="property-"
            title="">Timeout<wbr>In<wbr>Seconds<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}Maximum time a game session request can remain in the queue.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Game Session Queue ARN.
{{% /md %}}</dd>

    <dt class="property-"
            title="">destinations<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}List of fleet/alias ARNs used by session queue for placing game sessions.
{{% /md %}}</dd>

    <dt class="property-"
            title="">name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Name of the session queue.
{{% /md %}}</dd>

    <dt class="property-"
            title="">player<wbr>Latency<wbr>Policies<span class="property-indicator"></span>
        <span class="property-type"><a href="#gamesessionqueueplayerlatencypolicy">Game<wbr>Session<wbr>Queue<wbr>Player<wbr>Latency<wbr>Policy[]?</a></span>
    </dt>
    <dd>{{% md %}}One or more policies used to choose fleet based on player latency. See below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}Key-value mapping of resource tags
{{% /md %}}</dd>

    <dt class="property-"
            title="">timeout<wbr>In<wbr>Seconds<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}Maximum time a game session request can remain in the queue.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Game Session Queue ARN.
{{% /md %}}</dd>

    <dt class="property-"
            title="">destinations<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}List of fleet/alias ARNs used by session queue for placing game sessions.
{{% /md %}}</dd>

    <dt class="property-"
            title="">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Name of the session queue.
{{% /md %}}</dd>

    <dt class="property-"
            title="">player_<wbr>latency_<wbr>policies<span class="property-indicator"></span>
        <span class="property-type"><a href="#gamesessionqueueplayerlatencypolicy">List[Game<wbr>Session<wbr>Queue<wbr>Player<wbr>Latency<wbr>Policy]</a></span>
    </dt>
    <dd>{{% md %}}One or more policies used to choose fleet based on player latency. See below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}Key-value mapping of resource tags
{{% /md %}}</dd>

    <dt class="property-"
            title="">timeout_<wbr>in_<wbr>seconds<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}Maximum time a game session request can remain in the queue.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





## Look up an Existing GameSessionQueue Resource

{{< chooser language "javascript,typescript,python,go,csharp  " / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">pulumi.Input&lt;pulumi.ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/gamelift/#GameSessionQueueState">GameSessionQueueState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/gamelift/#GameSessionQueue">GameSessionQueue</a></span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>arn=None<span class="p">, </span>destinations=None<span class="p">, </span>name=None<span class="p">, </span>player_latency_policies=None<span class="p">, </span>tags=None<span class="p">, </span>timeout_in_seconds=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetGameSessionQueue<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">pulumi.IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/gamelift?tab=doc#GameSessionQueueState">GameSessionQueueState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/gamelift?tab=doc#GameSessionQueue">GameSessionQueue</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Gamelift.GameSessionQueue.html">GameSessionQueue</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Pulumi.Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Gamelift.GameSessionQueueState.html">GameSessionQueueState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
{{% /choosable %}}

Get an existing GameSessionQueue resource's state with the given name, ID, and optional extra properties used to qualify the lookup.

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
    <dd>{{% md %}}Game Session Queue ARN.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Destinations<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}List of fleet/alias ARNs used by session queue for placing game sessions.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Name of the session queue.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Player<wbr>Latency<wbr>Policies<span class="property-indicator"></span>
        <span class="property-type"><a href="#gamesessionqueueplayerlatencypolicy">List&lt;Game<wbr>Session<wbr>Queue<wbr>Player<wbr>Latency<wbr>Policy<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}One or more policies used to choose fleet based on player latency. See below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}Key-value mapping of resource tags
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Timeout<wbr>In<wbr>Seconds<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}Maximum time a game session request can remain in the queue.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Game Session Queue ARN.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Destinations<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}List of fleet/alias ARNs used by session queue for placing game sessions.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Name of the session queue.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Player<wbr>Latency<wbr>Policies<span class="property-indicator"></span>
        <span class="property-type"><a href="#gamesessionqueueplayerlatencypolicy">[]Game<wbr>Session<wbr>Queue<wbr>Player<wbr>Latency<wbr>Policy</a></span>
    </dt>
    <dd>{{% md %}}One or more policies used to choose fleet based on player latency. See below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}Key-value mapping of resource tags
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Timeout<wbr>In<wbr>Seconds<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}Maximum time a game session request can remain in the queue.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Game Session Queue ARN.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">destinations<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}List of fleet/alias ARNs used by session queue for placing game sessions.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Name of the session queue.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">player<wbr>Latency<wbr>Policies<span class="property-indicator"></span>
        <span class="property-type"><a href="#gamesessionqueueplayerlatencypolicy">Game<wbr>Session<wbr>Queue<wbr>Player<wbr>Latency<wbr>Policy[]?</a></span>
    </dt>
    <dd>{{% md %}}One or more policies used to choose fleet based on player latency. See below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}Key-value mapping of resource tags
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">timeout<wbr>In<wbr>Seconds<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}Maximum time a game session request can remain in the queue.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Game Session Queue ARN.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">destinations<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}List of fleet/alias ARNs used by session queue for placing game sessions.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Name of the session queue.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">player_<wbr>latency_<wbr>policies<span class="property-indicator"></span>
        <span class="property-type"><a href="#gamesessionqueueplayerlatencypolicy">List[Game<wbr>Session<wbr>Queue<wbr>Player<wbr>Latency<wbr>Policy]</a></span>
    </dt>
    <dd>{{% md %}}One or more policies used to choose fleet based on player latency. See below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}Key-value mapping of resource tags
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">timeout_<wbr>in_<wbr>seconds<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}Maximum time a game session request can remain in the queue.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}







## Supporting Types

#### GameSessionQueuePlayerLatencyPolicy
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#GameSessionQueuePlayerLatencyPolicy">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#GameSessionQueuePlayerLatencyPolicy">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/gamelift?tab=doc#GameSessionQueuePlayerLatencyPolicyArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/gamelift?tab=doc#GameSessionQueuePlayerLatencyPolicyOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Gamelift.GameSessionQueuePlayerLatencyPolicyArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Gamelift.GameSessionQueuePlayerLatencyPolicy.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Maximum<wbr>Individual<wbr>Player<wbr>Latency<wbr>Milliseconds<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}Maximum latency value that is allowed for any player.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Policy<wbr>Duration<wbr>Seconds<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}Length of time that the policy is enforced while placing a new game session. Absence of value for this attribute means that the policy is enforced until the queue times out.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Maximum<wbr>Individual<wbr>Player<wbr>Latency<wbr>Milliseconds<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}Maximum latency value that is allowed for any player.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Policy<wbr>Duration<wbr>Seconds<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}Length of time that the policy is enforced while placing a new game session. Absence of value for this attribute means that the policy is enforced until the queue times out.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">maximum<wbr>Individual<wbr>Player<wbr>Latency<wbr>Milliseconds<span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}Maximum latency value that is allowed for any player.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">policy<wbr>Duration<wbr>Seconds<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}Length of time that the policy is enforced while placing a new game session. Absence of value for this attribute means that the policy is enforced until the queue times out.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">maximum<wbr>Individual<wbr>Player<wbr>Latency<wbr>Milliseconds<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}Maximum latency value that is allowed for any player.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">policy<wbr>Duration<wbr>Seconds<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}Length of time that the policy is enforced while placing a new game session. Absence of value for this attribute means that the policy is enforced until the queue times out.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}








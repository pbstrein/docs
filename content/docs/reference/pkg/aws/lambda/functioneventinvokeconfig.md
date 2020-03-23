
---
title: "FunctionEventInvokeConfig"
block_external_search_index: true
---

Manages an asynchronous invocation configuration for a Lambda Function or Alias. More information about asynchronous invocations and the configurable values can be found in the [Lambda Developer Guide](https://docs.aws.amazon.com/lambda/latest/dg/invocation-async.html).

> This content is derived from https://github.com/terraform-providers/terraform-provider-aws/blob/master/website/docs/r/lambda_function_event_invoke_config.html.markdown.



## Create a FunctionEventInvokeConfig Resource

{{< chooser language "javascript,typescript,python,go,csharp" / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/lambda/#FunctionEventInvokeConfig">FunctionEventInvokeConfig</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/lambda/#FunctionEventInvokeConfigArgs">FunctionEventInvokeConfigArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">FunctionEventInvokeConfig</span><span class="p">(resource_name, opts=None, </span>destination_config=None<span class="p">, </span>function_name=None<span class="p">, </span>maximum_event_age_in_seconds=None<span class="p">, </span>maximum_retry_attempts=None<span class="p">, </span>qualifier=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewFunctionEventInvokeConfig<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/lambda?tab=doc#FunctionEventInvokeConfigArgs">FunctionEventInvokeConfigArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/lambda?tab=doc#FunctionEventInvokeConfig">FunctionEventInvokeConfig</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Lambda.FunctionEventInvokeConfig.html">FunctionEventInvokeConfig</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Lambda.FunctionEventInvokeConfigArgs.html">FunctionEventInvokeConfigArgs</a></span> <span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
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
            title="Optional">Destination<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#functioneventinvokeconfigdestinationconfig">Function<wbr>Event<wbr>Invoke<wbr>Config<wbr>Destination<wbr>Config<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}Configuration block with destination configuration. See below for details.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Function<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Name or Amazon Resource Name (ARN) of the Lambda Function, omitting any version or alias qualifier.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Maximum<wbr>Event<wbr>Age<wbr>In<wbr>Seconds<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}Maximum age of a request that Lambda sends to a function for processing in seconds. Valid values between 60 and 21600.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Maximum<wbr>Retry<wbr>Attempts<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}Maximum number of times to retry when the function returns an error. Valid values between 0 and 2. Defaults to 2.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Qualifier<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Lambda Function published version, `$LATEST`, or Lambda Alias name.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Destination<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#functioneventinvokeconfigdestinationconfig">*Function<wbr>Event<wbr>Invoke<wbr>Config<wbr>Destination<wbr>Config</a></span>
    </dt>
    <dd>{{% md %}}Configuration block with destination configuration. See below for details.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Function<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Name or Amazon Resource Name (ARN) of the Lambda Function, omitting any version or alias qualifier.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Maximum<wbr>Event<wbr>Age<wbr>In<wbr>Seconds<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}Maximum age of a request that Lambda sends to a function for processing in seconds. Valid values between 60 and 21600.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Maximum<wbr>Retry<wbr>Attempts<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}Maximum number of times to retry when the function returns an error. Valid values between 0 and 2. Defaults to 2.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Qualifier<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Lambda Function published version, `$LATEST`, or Lambda Alias name.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">destination<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#functioneventinvokeconfigdestinationconfig">Function<wbr>Event<wbr>Invoke<wbr>Config<wbr>Destination<wbr>Config?</a></span>
    </dt>
    <dd>{{% md %}}Configuration block with destination configuration. See below for details.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">function<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Name or Amazon Resource Name (ARN) of the Lambda Function, omitting any version or alias qualifier.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">maximum<wbr>Event<wbr>Age<wbr>In<wbr>Seconds<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}Maximum age of a request that Lambda sends to a function for processing in seconds. Valid values between 60 and 21600.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">maximum<wbr>Retry<wbr>Attempts<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}Maximum number of times to retry when the function returns an error. Valid values between 0 and 2. Defaults to 2.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">qualifier<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Lambda Function published version, `$LATEST`, or Lambda Alias name.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">destination_<wbr>config<span class="property-indicator"></span>
        <span class="property-type"><a href="#functioneventinvokeconfigdestinationconfig">Dict[Function<wbr>Event<wbr>Invoke<wbr>Config<wbr>Destination<wbr>Config]</a></span>
    </dt>
    <dd>{{% md %}}Configuration block with destination configuration. See below for details.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">function_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Name or Amazon Resource Name (ARN) of the Lambda Function, omitting any version or alias qualifier.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">maximum_<wbr>event_<wbr>age_<wbr>in_<wbr>seconds<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}Maximum age of a request that Lambda sends to a function for processing in seconds. Valid values between 60 and 21600.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">maximum_<wbr>retry_<wbr>attempts<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}Maximum number of times to retry when the function returns an error. Valid values between 0 and 2. Defaults to 2.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">qualifier<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Lambda Function published version, `$LATEST`, or Lambda Alias name.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}




## FunctionEventInvokeConfig Output Properties

The following output properties are available:




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Destination<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#functioneventinvokeconfigdestinationconfig">Function<wbr>Event<wbr>Invoke<wbr>Config<wbr>Destination<wbr>Config?</a></span>
    </dt>
    <dd>{{% md %}}Configuration block with destination configuration. See below for details.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Function<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Name or Amazon Resource Name (ARN) of the Lambda Function, omitting any version or alias qualifier.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Maximum<wbr>Event<wbr>Age<wbr>In<wbr>Seconds<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}Maximum age of a request that Lambda sends to a function for processing in seconds. Valid values between 60 and 21600.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Maximum<wbr>Retry<wbr>Attempts<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}Maximum number of times to retry when the function returns an error. Valid values between 0 and 2. Defaults to 2.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Qualifier<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Lambda Function published version, `$LATEST`, or Lambda Alias name.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Destination<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#functioneventinvokeconfigdestinationconfig">*Function<wbr>Event<wbr>Invoke<wbr>Config<wbr>Destination<wbr>Config</a></span>
    </dt>
    <dd>{{% md %}}Configuration block with destination configuration. See below for details.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Function<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Name or Amazon Resource Name (ARN) of the Lambda Function, omitting any version or alias qualifier.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Maximum<wbr>Event<wbr>Age<wbr>In<wbr>Seconds<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}Maximum age of a request that Lambda sends to a function for processing in seconds. Valid values between 60 and 21600.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Maximum<wbr>Retry<wbr>Attempts<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}Maximum number of times to retry when the function returns an error. Valid values between 0 and 2. Defaults to 2.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Qualifier<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Lambda Function published version, `$LATEST`, or Lambda Alias name.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">destination<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#functioneventinvokeconfigdestinationconfig">Function<wbr>Event<wbr>Invoke<wbr>Config<wbr>Destination<wbr>Config?</a></span>
    </dt>
    <dd>{{% md %}}Configuration block with destination configuration. See below for details.
{{% /md %}}</dd>

    <dt class="property-"
            title="">function<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Name or Amazon Resource Name (ARN) of the Lambda Function, omitting any version or alias qualifier.
{{% /md %}}</dd>

    <dt class="property-"
            title="">maximum<wbr>Event<wbr>Age<wbr>In<wbr>Seconds<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}Maximum age of a request that Lambda sends to a function for processing in seconds. Valid values between 60 and 21600.
{{% /md %}}</dd>

    <dt class="property-"
            title="">maximum<wbr>Retry<wbr>Attempts<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}Maximum number of times to retry when the function returns an error. Valid values between 0 and 2. Defaults to 2.
{{% /md %}}</dd>

    <dt class="property-"
            title="">qualifier<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Lambda Function published version, `$LATEST`, or Lambda Alias name.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">destination_<wbr>config<span class="property-indicator"></span>
        <span class="property-type"><a href="#functioneventinvokeconfigdestinationconfig">Dict[Function<wbr>Event<wbr>Invoke<wbr>Config<wbr>Destination<wbr>Config]</a></span>
    </dt>
    <dd>{{% md %}}Configuration block with destination configuration. See below for details.
{{% /md %}}</dd>

    <dt class="property-"
            title="">function_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Name or Amazon Resource Name (ARN) of the Lambda Function, omitting any version or alias qualifier.
{{% /md %}}</dd>

    <dt class="property-"
            title="">maximum_<wbr>event_<wbr>age_<wbr>in_<wbr>seconds<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}Maximum age of a request that Lambda sends to a function for processing in seconds. Valid values between 60 and 21600.
{{% /md %}}</dd>

    <dt class="property-"
            title="">maximum_<wbr>retry_<wbr>attempts<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}Maximum number of times to retry when the function returns an error. Valid values between 0 and 2. Defaults to 2.
{{% /md %}}</dd>

    <dt class="property-"
            title="">qualifier<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Lambda Function published version, `$LATEST`, or Lambda Alias name.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





## Look up an Existing FunctionEventInvokeConfig Resource

{{< chooser language "javascript,typescript,python,go,csharp  " / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">pulumi.Input&lt;pulumi.ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/lambda/#FunctionEventInvokeConfigState">FunctionEventInvokeConfigState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/lambda/#FunctionEventInvokeConfig">FunctionEventInvokeConfig</a></span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>destination_config=None<span class="p">, </span>function_name=None<span class="p">, </span>maximum_event_age_in_seconds=None<span class="p">, </span>maximum_retry_attempts=None<span class="p">, </span>qualifier=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetFunctionEventInvokeConfig<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">pulumi.IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/lambda?tab=doc#FunctionEventInvokeConfigState">FunctionEventInvokeConfigState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/lambda?tab=doc#FunctionEventInvokeConfig">FunctionEventInvokeConfig</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Lambda.FunctionEventInvokeConfig.html">FunctionEventInvokeConfig</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Pulumi.Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Lambda.FunctionEventInvokeConfigState.html">FunctionEventInvokeConfigState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
{{% /choosable %}}

Get an existing FunctionEventInvokeConfig resource's state with the given name, ID, and optional extra properties used to qualify the lookup.

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
            title="Optional">Destination<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#functioneventinvokeconfigdestinationconfig">Function<wbr>Event<wbr>Invoke<wbr>Config<wbr>Destination<wbr>Config<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}Configuration block with destination configuration. See below for details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Function<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Name or Amazon Resource Name (ARN) of the Lambda Function, omitting any version or alias qualifier.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Maximum<wbr>Event<wbr>Age<wbr>In<wbr>Seconds<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}Maximum age of a request that Lambda sends to a function for processing in seconds. Valid values between 60 and 21600.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Maximum<wbr>Retry<wbr>Attempts<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}Maximum number of times to retry when the function returns an error. Valid values between 0 and 2. Defaults to 2.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Qualifier<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Lambda Function published version, `$LATEST`, or Lambda Alias name.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Destination<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#functioneventinvokeconfigdestinationconfig">*Function<wbr>Event<wbr>Invoke<wbr>Config<wbr>Destination<wbr>Config</a></span>
    </dt>
    <dd>{{% md %}}Configuration block with destination configuration. See below for details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Function<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Name or Amazon Resource Name (ARN) of the Lambda Function, omitting any version or alias qualifier.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Maximum<wbr>Event<wbr>Age<wbr>In<wbr>Seconds<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}Maximum age of a request that Lambda sends to a function for processing in seconds. Valid values between 60 and 21600.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Maximum<wbr>Retry<wbr>Attempts<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}Maximum number of times to retry when the function returns an error. Valid values between 0 and 2. Defaults to 2.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Qualifier<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Lambda Function published version, `$LATEST`, or Lambda Alias name.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">destination<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#functioneventinvokeconfigdestinationconfig">Function<wbr>Event<wbr>Invoke<wbr>Config<wbr>Destination<wbr>Config?</a></span>
    </dt>
    <dd>{{% md %}}Configuration block with destination configuration. See below for details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">function<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Name or Amazon Resource Name (ARN) of the Lambda Function, omitting any version or alias qualifier.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">maximum<wbr>Event<wbr>Age<wbr>In<wbr>Seconds<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}Maximum age of a request that Lambda sends to a function for processing in seconds. Valid values between 60 and 21600.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">maximum<wbr>Retry<wbr>Attempts<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}Maximum number of times to retry when the function returns an error. Valid values between 0 and 2. Defaults to 2.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">qualifier<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Lambda Function published version, `$LATEST`, or Lambda Alias name.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">destination_<wbr>config<span class="property-indicator"></span>
        <span class="property-type"><a href="#functioneventinvokeconfigdestinationconfig">Dict[Function<wbr>Event<wbr>Invoke<wbr>Config<wbr>Destination<wbr>Config]</a></span>
    </dt>
    <dd>{{% md %}}Configuration block with destination configuration. See below for details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">function_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Name or Amazon Resource Name (ARN) of the Lambda Function, omitting any version or alias qualifier.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">maximum_<wbr>event_<wbr>age_<wbr>in_<wbr>seconds<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}Maximum age of a request that Lambda sends to a function for processing in seconds. Valid values between 60 and 21600.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">maximum_<wbr>retry_<wbr>attempts<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}Maximum number of times to retry when the function returns an error. Valid values between 0 and 2. Defaults to 2.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">qualifier<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Lambda Function published version, `$LATEST`, or Lambda Alias name.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}







## Supporting Types

#### FunctionEventInvokeConfigDestinationConfig
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#FunctionEventInvokeConfigDestinationConfig">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#FunctionEventInvokeConfigDestinationConfig">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/lambda?tab=doc#FunctionEventInvokeConfigDestinationConfigArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/lambda?tab=doc#FunctionEventInvokeConfigDestinationConfigOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Lambda.FunctionEventInvokeConfigDestinationConfigArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Lambda.FunctionEventInvokeConfigDestinationConfig.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">On<wbr>Failure<span class="property-indicator"></span>
        <span class="property-type"><a href="#functioneventinvokeconfigdestinationconfigonfailure">Function<wbr>Event<wbr>Invoke<wbr>Config<wbr>Destination<wbr>Config<wbr>On<wbr>Failure<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}Configuration block with destination configuration for failed asynchronous invocations. See below for details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">On<wbr>Success<span class="property-indicator"></span>
        <span class="property-type"><a href="#functioneventinvokeconfigdestinationconfigonsuccess">Function<wbr>Event<wbr>Invoke<wbr>Config<wbr>Destination<wbr>Config<wbr>On<wbr>Success<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}Configuration block with destination configuration for successful asynchronous invocations. See below for details.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">On<wbr>Failure<span class="property-indicator"></span>
        <span class="property-type"><a href="#functioneventinvokeconfigdestinationconfigonfailure">*Function<wbr>Event<wbr>Invoke<wbr>Config<wbr>Destination<wbr>Config<wbr>On<wbr>Failure</a></span>
    </dt>
    <dd>{{% md %}}Configuration block with destination configuration for failed asynchronous invocations. See below for details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">On<wbr>Success<span class="property-indicator"></span>
        <span class="property-type"><a href="#functioneventinvokeconfigdestinationconfigonsuccess">*Function<wbr>Event<wbr>Invoke<wbr>Config<wbr>Destination<wbr>Config<wbr>On<wbr>Success</a></span>
    </dt>
    <dd>{{% md %}}Configuration block with destination configuration for successful asynchronous invocations. See below for details.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">on<wbr>Failure<span class="property-indicator"></span>
        <span class="property-type"><a href="#functioneventinvokeconfigdestinationconfigonfailure">Function<wbr>Event<wbr>Invoke<wbr>Config<wbr>Destination<wbr>Config<wbr>On<wbr>Failure?</a></span>
    </dt>
    <dd>{{% md %}}Configuration block with destination configuration for failed asynchronous invocations. See below for details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">on<wbr>Success<span class="property-indicator"></span>
        <span class="property-type"><a href="#functioneventinvokeconfigdestinationconfigonsuccess">Function<wbr>Event<wbr>Invoke<wbr>Config<wbr>Destination<wbr>Config<wbr>On<wbr>Success?</a></span>
    </dt>
    <dd>{{% md %}}Configuration block with destination configuration for successful asynchronous invocations. See below for details.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">on_<wbr>failure<span class="property-indicator"></span>
        <span class="property-type"><a href="#functioneventinvokeconfigdestinationconfigonfailure">Dict[Function<wbr>Event<wbr>Invoke<wbr>Config<wbr>Destination<wbr>Config<wbr>On<wbr>Failure]</a></span>
    </dt>
    <dd>{{% md %}}Configuration block with destination configuration for failed asynchronous invocations. See below for details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">on<wbr>Success<span class="property-indicator"></span>
        <span class="property-type"><a href="#functioneventinvokeconfigdestinationconfigonsuccess">Dict[Function<wbr>Event<wbr>Invoke<wbr>Config<wbr>Destination<wbr>Config<wbr>On<wbr>Success]</a></span>
    </dt>
    <dd>{{% md %}}Configuration block with destination configuration for successful asynchronous invocations. See below for details.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### FunctionEventInvokeConfigDestinationConfigOnFailure
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#FunctionEventInvokeConfigDestinationConfigOnFailure">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#FunctionEventInvokeConfigDestinationConfigOnFailure">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/lambda?tab=doc#FunctionEventInvokeConfigDestinationConfigOnFailureArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/lambda?tab=doc#FunctionEventInvokeConfigDestinationConfigOnFailureOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Lambda.FunctionEventInvokeConfigDestinationConfigOnFailureArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Lambda.FunctionEventInvokeConfigDestinationConfigOnFailure.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Destination<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of the destination resource. See the [Lambda Developer Guide](https://docs.aws.amazon.com/lambda/latest/dg/invocation-async.html#invocation-async-destinations) for acceptable resource types and associated IAM permissions.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Destination<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of the destination resource. See the [Lambda Developer Guide](https://docs.aws.amazon.com/lambda/latest/dg/invocation-async.html#invocation-async-destinations) for acceptable resource types and associated IAM permissions.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">destination<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of the destination resource. See the [Lambda Developer Guide](https://docs.aws.amazon.com/lambda/latest/dg/invocation-async.html#invocation-async-destinations) for acceptable resource types and associated IAM permissions.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">destination<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of the destination resource. See the [Lambda Developer Guide](https://docs.aws.amazon.com/lambda/latest/dg/invocation-async.html#invocation-async-destinations) for acceptable resource types and associated IAM permissions.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### FunctionEventInvokeConfigDestinationConfigOnSuccess
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#FunctionEventInvokeConfigDestinationConfigOnSuccess">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#FunctionEventInvokeConfigDestinationConfigOnSuccess">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/lambda?tab=doc#FunctionEventInvokeConfigDestinationConfigOnSuccessArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/lambda?tab=doc#FunctionEventInvokeConfigDestinationConfigOnSuccessOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Lambda.FunctionEventInvokeConfigDestinationConfigOnSuccessArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Lambda.FunctionEventInvokeConfigDestinationConfigOnSuccess.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Destination<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of the destination resource. See the [Lambda Developer Guide](https://docs.aws.amazon.com/lambda/latest/dg/invocation-async.html#invocation-async-destinations) for acceptable resource types and associated IAM permissions.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Destination<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of the destination resource. See the [Lambda Developer Guide](https://docs.aws.amazon.com/lambda/latest/dg/invocation-async.html#invocation-async-destinations) for acceptable resource types and associated IAM permissions.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">destination<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of the destination resource. See the [Lambda Developer Guide](https://docs.aws.amazon.com/lambda/latest/dg/invocation-async.html#invocation-async-destinations) for acceptable resource types and associated IAM permissions.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">destination<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of the destination resource. See the [Lambda Developer Guide](https://docs.aws.amazon.com/lambda/latest/dg/invocation-async.html#invocation-async-destinations) for acceptable resource types and associated IAM permissions.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}








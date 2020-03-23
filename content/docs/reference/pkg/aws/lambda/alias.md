
---
title: "Alias"
block_external_search_index: true
---

Creates a Lambda function alias. Creates an alias that points to the specified Lambda function version.

For information about Lambda and how to use it, see [What is AWS Lambda?][1]
For information about function aliases, see [CreateAlias][2] and [AliasRoutingConfiguration][3] in the API docs.

## Example Usage

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const testAlias = new aws.lambda.Alias("test_alias", {
    description: "a sample description",
    functionName: aws_lambda_function_lambda_function_test.arn,
    functionVersion: "1",
    routingConfig: {
        additionalVersionWeights: {
            "2": 0.5,
        },
    },
});
```

> This content is derived from https://github.com/terraform-providers/terraform-provider-aws/blob/master/website/docs/r/lambda_alias.html.markdown.



## Create a Alias Resource

{{< chooser language "javascript,typescript,python,go,csharp" / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/lambda/#Alias">Alias</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/lambda/#AliasArgs">AliasArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">Alias</span><span class="p">(resource_name, opts=None, </span>description=None<span class="p">, </span>function_name=None<span class="p">, </span>function_version=None<span class="p">, </span>name=None<span class="p">, </span>routing_config=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewAlias<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/lambda?tab=doc#AliasArgs">AliasArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/lambda?tab=doc#Alias">Alias</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Lambda.Alias.html">Alias</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Lambda.AliasArgs.html">AliasArgs</a></span> <span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
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
    <dd>{{% md %}}Description of the alias.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Function<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The function ARN of the Lambda function for which you want to create an alias.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Function<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Lambda function version for which you are creating the alias. Pattern: `(\$LATEST|[0-9]&#43;)`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Name for the alias you are creating. Pattern: `(?!^[0-9]&#43;$)([a-zA-Z0-9-_]&#43;)`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Routing<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#aliasroutingconfig">Alias<wbr>Routing<wbr>Config<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}The Lambda alias&#39; route configuration settings. Fields documented below
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Description<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Description of the alias.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Function<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The function ARN of the Lambda function for which you want to create an alias.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Function<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Lambda function version for which you are creating the alias. Pattern: `(\$LATEST|[0-9]&#43;)`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Name for the alias you are creating. Pattern: `(?!^[0-9]&#43;$)([a-zA-Z0-9-_]&#43;)`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Routing<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#aliasroutingconfig">*Alias<wbr>Routing<wbr>Config</a></span>
    </dt>
    <dd>{{% md %}}The Lambda alias&#39; route configuration settings. Fields documented below
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">description<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Description of the alias.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">function<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The function ARN of the Lambda function for which you want to create an alias.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">function<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Lambda function version for which you are creating the alias. Pattern: `(\$LATEST|[0-9]&#43;)`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Name for the alias you are creating. Pattern: `(?!^[0-9]&#43;$)([a-zA-Z0-9-_]&#43;)`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">routing<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#aliasroutingconfig">Alias<wbr>Routing<wbr>Config?</a></span>
    </dt>
    <dd>{{% md %}}The Lambda alias&#39; route configuration settings. Fields documented below
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">description<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Description of the alias.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">function_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The function ARN of the Lambda function for which you want to create an alias.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">function_<wbr>version<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Lambda function version for which you are creating the alias. Pattern: `(\$LATEST|[0-9]&#43;)`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Name for the alias you are creating. Pattern: `(?!^[0-9]&#43;$)([a-zA-Z0-9-_]&#43;)`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">routing_<wbr>config<span class="property-indicator"></span>
        <span class="property-type"><a href="#aliasroutingconfig">Dict[Alias<wbr>Routing<wbr>Config]</a></span>
    </dt>
    <dd>{{% md %}}The Lambda alias&#39; route configuration settings. Fields documented below
{{% /md %}}</dd>

</dl>
{{% /choosable %}}




## Alias Output Properties

The following output properties are available:




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Amazon Resource Name (ARN) identifying your Lambda function alias.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Description<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Description of the alias.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Function<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The function ARN of the Lambda function for which you want to create an alias.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Function<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Lambda function version for which you are creating the alias. Pattern: `(\$LATEST|[0-9]&#43;)`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Invoke<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN to be used for invoking Lambda Function from API Gateway - to be used in [`aws.apigateway.Integration`](https://www.terraform.io/docs/providers/aws/r/api_gateway_integration.html)&#39;s `uri`
{{% /md %}}</dd>

    <dt class="property-"
            title="">Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Name for the alias you are creating. Pattern: `(?!^[0-9]&#43;$)([a-zA-Z0-9-_]&#43;)`
{{% /md %}}</dd>

    <dt class="property-"
            title="">Routing<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#aliasroutingconfig">Alias<wbr>Routing<wbr>Config?</a></span>
    </dt>
    <dd>{{% md %}}The Lambda alias&#39; route configuration settings. Fields documented below
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Amazon Resource Name (ARN) identifying your Lambda function alias.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Description<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Description of the alias.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Function<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The function ARN of the Lambda function for which you want to create an alias.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Function<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Lambda function version for which you are creating the alias. Pattern: `(\$LATEST|[0-9]&#43;)`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Invoke<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN to be used for invoking Lambda Function from API Gateway - to be used in [`aws.apigateway.Integration`](https://www.terraform.io/docs/providers/aws/r/api_gateway_integration.html)&#39;s `uri`
{{% /md %}}</dd>

    <dt class="property-"
            title="">Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Name for the alias you are creating. Pattern: `(?!^[0-9]&#43;$)([a-zA-Z0-9-_]&#43;)`
{{% /md %}}</dd>

    <dt class="property-"
            title="">Routing<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#aliasroutingconfig">*Alias<wbr>Routing<wbr>Config</a></span>
    </dt>
    <dd>{{% md %}}The Lambda alias&#39; route configuration settings. Fields documented below
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Amazon Resource Name (ARN) identifying your Lambda function alias.
{{% /md %}}</dd>

    <dt class="property-"
            title="">description<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Description of the alias.
{{% /md %}}</dd>

    <dt class="property-"
            title="">function<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The function ARN of the Lambda function for which you want to create an alias.
{{% /md %}}</dd>

    <dt class="property-"
            title="">function<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Lambda function version for which you are creating the alias. Pattern: `(\$LATEST|[0-9]&#43;)`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">invoke<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN to be used for invoking Lambda Function from API Gateway - to be used in [`aws.apigateway.Integration`](https://www.terraform.io/docs/providers/aws/r/api_gateway_integration.html)&#39;s `uri`
{{% /md %}}</dd>

    <dt class="property-"
            title="">name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Name for the alias you are creating. Pattern: `(?!^[0-9]&#43;$)([a-zA-Z0-9-_]&#43;)`
{{% /md %}}</dd>

    <dt class="property-"
            title="">routing<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#aliasroutingconfig">Alias<wbr>Routing<wbr>Config?</a></span>
    </dt>
    <dd>{{% md %}}The Lambda alias&#39; route configuration settings. Fields documented below
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The Amazon Resource Name (ARN) identifying your Lambda function alias.
{{% /md %}}</dd>

    <dt class="property-"
            title="">description<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Description of the alias.
{{% /md %}}</dd>

    <dt class="property-"
            title="">function_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The function ARN of the Lambda function for which you want to create an alias.
{{% /md %}}</dd>

    <dt class="property-"
            title="">function_<wbr>version<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Lambda function version for which you are creating the alias. Pattern: `(\$LATEST|[0-9]&#43;)`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">invoke_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ARN to be used for invoking Lambda Function from API Gateway - to be used in [`aws.apigateway.Integration`](https://www.terraform.io/docs/providers/aws/r/api_gateway_integration.html)&#39;s `uri`
{{% /md %}}</dd>

    <dt class="property-"
            title="">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Name for the alias you are creating. Pattern: `(?!^[0-9]&#43;$)([a-zA-Z0-9-_]&#43;)`
{{% /md %}}</dd>

    <dt class="property-"
            title="">routing_<wbr>config<span class="property-indicator"></span>
        <span class="property-type"><a href="#aliasroutingconfig">Dict[Alias<wbr>Routing<wbr>Config]</a></span>
    </dt>
    <dd>{{% md %}}The Lambda alias&#39; route configuration settings. Fields documented below
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





## Look up an Existing Alias Resource

{{< chooser language "javascript,typescript,python,go,csharp  " / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">pulumi.Input&lt;pulumi.ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/lambda/#AliasState">AliasState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/lambda/#Alias">Alias</a></span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>arn=None<span class="p">, </span>description=None<span class="p">, </span>function_name=None<span class="p">, </span>function_version=None<span class="p">, </span>invoke_arn=None<span class="p">, </span>name=None<span class="p">, </span>routing_config=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetAlias<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">pulumi.IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/lambda?tab=doc#AliasState">AliasState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/lambda?tab=doc#Alias">Alias</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Lambda.Alias.html">Alias</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Pulumi.Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Lambda.AliasState.html">AliasState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
{{% /choosable %}}

Get an existing Alias resource's state with the given name, ID, and optional extra properties used to qualify the lookup.

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
    <dd>{{% md %}}The Amazon Resource Name (ARN) identifying your Lambda function alias.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Description<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Description of the alias.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Function<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The function ARN of the Lambda function for which you want to create an alias.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Function<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Lambda function version for which you are creating the alias. Pattern: `(\$LATEST|[0-9]&#43;)`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Invoke<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ARN to be used for invoking Lambda Function from API Gateway - to be used in [`aws.apigateway.Integration`](https://www.terraform.io/docs/providers/aws/r/api_gateway_integration.html)&#39;s `uri`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Name for the alias you are creating. Pattern: `(?!^[0-9]&#43;$)([a-zA-Z0-9-_]&#43;)`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Routing<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#aliasroutingconfig">Alias<wbr>Routing<wbr>Config<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}The Lambda alias&#39; route configuration settings. Fields documented below
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The Amazon Resource Name (ARN) identifying your Lambda function alias.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Description<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Description of the alias.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Function<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The function ARN of the Lambda function for which you want to create an alias.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Function<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Lambda function version for which you are creating the alias. Pattern: `(\$LATEST|[0-9]&#43;)`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Invoke<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The ARN to be used for invoking Lambda Function from API Gateway - to be used in [`aws.apigateway.Integration`](https://www.terraform.io/docs/providers/aws/r/api_gateway_integration.html)&#39;s `uri`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Name for the alias you are creating. Pattern: `(?!^[0-9]&#43;$)([a-zA-Z0-9-_]&#43;)`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Routing<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#aliasroutingconfig">*Alias<wbr>Routing<wbr>Config</a></span>
    </dt>
    <dd>{{% md %}}The Lambda alias&#39; route configuration settings. Fields documented below
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The Amazon Resource Name (ARN) identifying your Lambda function alias.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">description<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Description of the alias.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">function<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The function ARN of the Lambda function for which you want to create an alias.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">function<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Lambda function version for which you are creating the alias. Pattern: `(\$LATEST|[0-9]&#43;)`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">invoke<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ARN to be used for invoking Lambda Function from API Gateway - to be used in [`aws.apigateway.Integration`](https://www.terraform.io/docs/providers/aws/r/api_gateway_integration.html)&#39;s `uri`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Name for the alias you are creating. Pattern: `(?!^[0-9]&#43;$)([a-zA-Z0-9-_]&#43;)`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">routing<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#aliasroutingconfig">Alias<wbr>Routing<wbr>Config?</a></span>
    </dt>
    <dd>{{% md %}}The Lambda alias&#39; route configuration settings. Fields documented below
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The Amazon Resource Name (ARN) identifying your Lambda function alias.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">description<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Description of the alias.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">function_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The function ARN of the Lambda function for which you want to create an alias.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">function_<wbr>version<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Lambda function version for which you are creating the alias. Pattern: `(\$LATEST|[0-9]&#43;)`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">invoke_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ARN to be used for invoking Lambda Function from API Gateway - to be used in [`aws.apigateway.Integration`](https://www.terraform.io/docs/providers/aws/r/api_gateway_integration.html)&#39;s `uri`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Name for the alias you are creating. Pattern: `(?!^[0-9]&#43;$)([a-zA-Z0-9-_]&#43;)`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">routing_<wbr>config<span class="property-indicator"></span>
        <span class="property-type"><a href="#aliasroutingconfig">Dict[Alias<wbr>Routing<wbr>Config]</a></span>
    </dt>
    <dd>{{% md %}}The Lambda alias&#39; route configuration settings. Fields documented below
{{% /md %}}</dd>

</dl>
{{% /choosable %}}







## Supporting Types

#### AliasRoutingConfig
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#AliasRoutingConfig">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#AliasRoutingConfig">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/lambda?tab=doc#AliasRoutingConfigArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/lambda?tab=doc#AliasRoutingConfigOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Lambda.AliasRoutingConfigArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Lambda.AliasRoutingConfig.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Additional<wbr>Version<wbr>Weights<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, double>?</span>
    </dt>
    <dd>{{% md %}}A map that defines the proportion of events that should be sent to different versions of a lambda function.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Additional<wbr>Version<wbr>Weights<span class="property-indicator"></span>
        <span class="property-type">map[string]float64</span>
    </dt>
    <dd>{{% md %}}A map that defines the proportion of events that should be sent to different versions of a lambda function.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">additional<wbr>Version<wbr>Weights<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: number}?</span>
    </dt>
    <dd>{{% md %}}A map that defines the proportion of events that should be sent to different versions of a lambda function.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">additional<wbr>Version<wbr>Weights<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Number]</span>
    </dt>
    <dd>{{% md %}}A map that defines the proportion of events that should be sent to different versions of a lambda function.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}








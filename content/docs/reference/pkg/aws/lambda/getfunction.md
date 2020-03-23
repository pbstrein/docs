
---
title: "GetFunction"
block_external_search_index: true
---

Provides information about a Lambda Function.

## Example Usage

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const config = new pulumi.Config();
const functionName = config.require("functionName");

const existing = aws.lambda.getFunction({
    functionName: functionName,
});
```

> This content is derived from https://github.com/terraform-providers/terraform-provider-aws/blob/master/website/docs/d/lambda_function.html.markdown.





## Using GetFunction

{{< chooser language "typescript,python,go,csharp" >}}

{{% choosable language typescript %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">function </span>getFunction<span class="p">(</span><span class="nx">args</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/lambda/#GetFunctionArgs">GetFunctionArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#InvokeOptions">pulumi.InvokeOptions</a></span><span class="p">): Promise&lt;<span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/lambda/#GetFunctionResult">GetFunctionResult</a></span>></span></code></pre></div>
{{% /choosable %}}" }}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">function </span> get_function(</span>function_name=None<span class="p">, </span>qualifier=None<span class="p">, </span>tags=None<span class="p">, </span>opts=None<span class="p">)</span></code></pre></div>
{{% /choosable %}}" }}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>LookupFunction<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">args</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/lambda?tab=doc#LookupFunctionArgs">LookupFunctionArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#InvokeOption">pulumi.InvokeOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/lambda?tab=doc#LookupFunctionResult">LookupFunctionResult</a></span>, error)</span></code></pre></div>
{{% /choosable %}}" }}

{{% choosable language csharp %}}
<div class="highlight">
<pre class="chroma">
<code class="language-csharp" data-lang="csharp"><span class="k">public static class </span><span class="nx">GetFunction </span><span class="p">{</span>
    <span class="k">public static </span>Task&lt;<span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Lambda.GetFunctionResult.html">GetFunctionResult</a></span>> <span class="p">InvokeAsync(</span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Lambda.GetFunctionArgs.html">GetFunctionArgs</a></span> <span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/InvokeOptions.html">InvokeOptions</a></span>? <span class="nx">opts = null<span class="p">)</span>
<span class="p">}</span></code></pre>
</div>
{{% /choosable %}}" }}



The following arguments are supported:



{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Function<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Name of the lambda function.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Qualifier<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Alias name or version number of the lambda function. e.g. `$LATEST`, `my-alias`, or `1`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Function<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Name of the lambda function.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Qualifier<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Alias name or version number of the lambda function. e.g. `$LATEST`, `my-alias`, or `1`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">function<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Name of the lambda function.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">qualifier<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Alias name or version number of the lambda function. e.g. `$LATEST`, `my-alias`, or `1`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">function_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Name of the lambda function.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">qualifier<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Alias name or version number of the lambda function. e.g. `$LATEST`, `my-alias`, or `1`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}








## GetFunction Result

The following output properties are available:




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Unqualified (no `:QUALIFIER` or `:VERSION` suffix) Amazon Resource Name (ARN) identifying your Lambda Function. See also `qualified_arn`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Dead<wbr>Letter<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#getfunctiondeadletterconfig">Get<wbr>Function<wbr>Dead<wbr>Letter<wbr>Config</a></span>
    </dt>
    <dd>{{% md %}}Configure the function&#39;s *dead letter queue*.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Description<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Description of what your Lambda Function does.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Environment<span class="property-indicator"></span>
        <span class="property-type"><a href="#getfunctionenvironment">Get<wbr>Function<wbr>Environment</a></span>
    </dt>
    <dd>{{% md %}}The Lambda environment&#39;s configuration settings.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Function<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">Handler<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The function entrypoint in your code.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}id is the provider-assigned unique ID for this managed resource.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Invoke<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN to be used for invoking Lambda Function from API Gateway.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Kms<wbr>Key<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN for the KMS encryption key.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Last<wbr>Modified<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The date this resource was last modified.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Layers<span class="property-indicator"></span>
        <span class="property-type">List<string></span>
    </dt>
    <dd>{{% md %}}A list of Lambda Layer ARNs attached to your Lambda Function.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Memory<wbr>Size<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}Amount of memory in MB your Lambda Function can use at runtime.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Qualified<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Qualified (`:QUALIFIER` or `:VERSION` suffix) Amazon Resource Name (ARN) identifying your Lambda Function. See also `arn`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Qualifier<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">Reserved<wbr>Concurrent<wbr>Executions<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The amount of reserved concurrent executions for this lambda function or `-1` if unreserved.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Role<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}IAM role attached to the Lambda Function.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Runtime<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The runtime environment for the Lambda function..
{{% /md %}}</dd>

    <dt class="property-"
            title="">Source<wbr>Code<wbr>Hash<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Base64-encoded representation of raw SHA-256 sum of the zip file.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Source<wbr>Code<wbr>Size<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The size in bytes of the function .zip file.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">Timeout<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The function execution time at which Lambda should terminate the function.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Tracing<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#getfunctiontracingconfig">Get<wbr>Function<wbr>Tracing<wbr>Config</a></span>
    </dt>
    <dd>{{% md %}}Tracing settings of the function.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Version<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The version of the Lambda function.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Vpc<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#getfunctionvpcconfig">Get<wbr>Function<wbr>Vpc<wbr>Config</a></span>
    </dt>
    <dd>{{% md %}}VPC configuration associated with your Lambda function.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Unqualified (no `:QUALIFIER` or `:VERSION` suffix) Amazon Resource Name (ARN) identifying your Lambda Function. See also `qualified_arn`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Dead<wbr>Letter<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#getfunctiondeadletterconfig">Get<wbr>Function<wbr>Dead<wbr>Letter<wbr>Config</a></span>
    </dt>
    <dd>{{% md %}}Configure the function&#39;s *dead letter queue*.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Description<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Description of what your Lambda Function does.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Environment<span class="property-indicator"></span>
        <span class="property-type"><a href="#getfunctionenvironment">Get<wbr>Function<wbr>Environment</a></span>
    </dt>
    <dd>{{% md %}}The Lambda environment&#39;s configuration settings.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Function<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">Handler<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The function entrypoint in your code.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}id is the provider-assigned unique ID for this managed resource.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Invoke<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN to be used for invoking Lambda Function from API Gateway.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Kms<wbr>Key<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN for the KMS encryption key.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Last<wbr>Modified<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The date this resource was last modified.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Layers<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}A list of Lambda Layer ARNs attached to your Lambda Function.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Memory<wbr>Size<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}Amount of memory in MB your Lambda Function can use at runtime.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Qualified<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Qualified (`:QUALIFIER` or `:VERSION` suffix) Amazon Resource Name (ARN) identifying your Lambda Function. See also `arn`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Qualifier<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">Reserved<wbr>Concurrent<wbr>Executions<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The amount of reserved concurrent executions for this lambda function or `-1` if unreserved.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Role<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}IAM role attached to the Lambda Function.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Runtime<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The runtime environment for the Lambda function..
{{% /md %}}</dd>

    <dt class="property-"
            title="">Source<wbr>Code<wbr>Hash<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Base64-encoded representation of raw SHA-256 sum of the zip file.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Source<wbr>Code<wbr>Size<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The size in bytes of the function .zip file.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">Timeout<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The function execution time at which Lambda should terminate the function.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Tracing<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#getfunctiontracingconfig">Get<wbr>Function<wbr>Tracing<wbr>Config</a></span>
    </dt>
    <dd>{{% md %}}Tracing settings of the function.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Version<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The version of the Lambda function.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Vpc<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#getfunctionvpcconfig">Get<wbr>Function<wbr>Vpc<wbr>Config</a></span>
    </dt>
    <dd>{{% md %}}VPC configuration associated with your Lambda function.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Unqualified (no `:QUALIFIER` or `:VERSION` suffix) Amazon Resource Name (ARN) identifying your Lambda Function. See also `qualified_arn`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">dead<wbr>Letter<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#getfunctiondeadletterconfig">Get<wbr>Function<wbr>Dead<wbr>Letter<wbr>Config</a></span>
    </dt>
    <dd>{{% md %}}Configure the function&#39;s *dead letter queue*.
{{% /md %}}</dd>

    <dt class="property-"
            title="">description<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Description of what your Lambda Function does.
{{% /md %}}</dd>

    <dt class="property-"
            title="">environment<span class="property-indicator"></span>
        <span class="property-type"><a href="#getfunctionenvironment">Get<wbr>Function<wbr>Environment</a></span>
    </dt>
    <dd>{{% md %}}The Lambda environment&#39;s configuration settings.
{{% /md %}}</dd>

    <dt class="property-"
            title="">function<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">handler<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The function entrypoint in your code.
{{% /md %}}</dd>

    <dt class="property-"
            title="">id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}id is the provider-assigned unique ID for this managed resource.
{{% /md %}}</dd>

    <dt class="property-"
            title="">invoke<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN to be used for invoking Lambda Function from API Gateway.
{{% /md %}}</dd>

    <dt class="property-"
            title="">kms<wbr>Key<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN for the KMS encryption key.
{{% /md %}}</dd>

    <dt class="property-"
            title="">last<wbr>Modified<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The date this resource was last modified.
{{% /md %}}</dd>

    <dt class="property-"
            title="">layers<span class="property-indicator"></span>
        <span class="property-type">string[]</span>
    </dt>
    <dd>{{% md %}}A list of Lambda Layer ARNs attached to your Lambda Function.
{{% /md %}}</dd>

    <dt class="property-"
            title="">memory<wbr>Size<span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}Amount of memory in MB your Lambda Function can use at runtime.
{{% /md %}}</dd>

    <dt class="property-"
            title="">qualified<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Qualified (`:QUALIFIER` or `:VERSION` suffix) Amazon Resource Name (ARN) identifying your Lambda Function. See also `arn`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">qualifier<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">reserved<wbr>Concurrent<wbr>Executions<span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}The amount of reserved concurrent executions for this lambda function or `-1` if unreserved.
{{% /md %}}</dd>

    <dt class="property-"
            title="">role<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}IAM role attached to the Lambda Function.
{{% /md %}}</dd>

    <dt class="property-"
            title="">runtime<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The runtime environment for the Lambda function..
{{% /md %}}</dd>

    <dt class="property-"
            title="">source<wbr>Code<wbr>Hash<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Base64-encoded representation of raw SHA-256 sum of the zip file.
{{% /md %}}</dd>

    <dt class="property-"
            title="">source<wbr>Code<wbr>Size<span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}The size in bytes of the function .zip file.
{{% /md %}}</dd>

    <dt class="property-"
            title="">tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">timeout<span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}The function execution time at which Lambda should terminate the function.
{{% /md %}}</dd>

    <dt class="property-"
            title="">tracing<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#getfunctiontracingconfig">Get<wbr>Function<wbr>Tracing<wbr>Config</a></span>
    </dt>
    <dd>{{% md %}}Tracing settings of the function.
{{% /md %}}</dd>

    <dt class="property-"
            title="">version<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The version of the Lambda function.
{{% /md %}}</dd>

    <dt class="property-"
            title="">vpc<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#getfunctionvpcconfig">Get<wbr>Function<wbr>Vpc<wbr>Config</a></span>
    </dt>
    <dd>{{% md %}}VPC configuration associated with your Lambda function.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Unqualified (no `:QUALIFIER` or `:VERSION` suffix) Amazon Resource Name (ARN) identifying your Lambda Function. See also `qualified_arn`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">dead_<wbr>letter_<wbr>config<span class="property-indicator"></span>
        <span class="property-type"><a href="#getfunctiondeadletterconfig">Dict[Get<wbr>Function<wbr>Dead<wbr>Letter<wbr>Config]</a></span>
    </dt>
    <dd>{{% md %}}Configure the function&#39;s *dead letter queue*.
{{% /md %}}</dd>

    <dt class="property-"
            title="">description<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Description of what your Lambda Function does.
{{% /md %}}</dd>

    <dt class="property-"
            title="">environment<span class="property-indicator"></span>
        <span class="property-type"><a href="#getfunctionenvironment">Dict[Get<wbr>Function<wbr>Environment]</a></span>
    </dt>
    <dd>{{% md %}}The Lambda environment&#39;s configuration settings.
{{% /md %}}</dd>

    <dt class="property-"
            title="">function_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">handler<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The function entrypoint in your code.
{{% /md %}}</dd>

    <dt class="property-"
            title="">id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}id is the provider-assigned unique ID for this managed resource.
{{% /md %}}</dd>

    <dt class="property-"
            title="">invoke_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ARN to be used for invoking Lambda Function from API Gateway.
{{% /md %}}</dd>

    <dt class="property-"
            title="">kms_<wbr>key_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ARN for the KMS encryption key.
{{% /md %}}</dd>

    <dt class="property-"
            title="">last_<wbr>modified<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The date this resource was last modified.
{{% /md %}}</dd>

    <dt class="property-"
            title="">layers<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}A list of Lambda Layer ARNs attached to your Lambda Function.
{{% /md %}}</dd>

    <dt class="property-"
            title="">memory_<wbr>size<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}Amount of memory in MB your Lambda Function can use at runtime.
{{% /md %}}</dd>

    <dt class="property-"
            title="">qualified_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Qualified (`:QUALIFIER` or `:VERSION` suffix) Amazon Resource Name (ARN) identifying your Lambda Function. See also `arn`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">qualifier<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">reserved_<wbr>concurrent_<wbr>executions<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The amount of reserved concurrent executions for this lambda function or `-1` if unreserved.
{{% /md %}}</dd>

    <dt class="property-"
            title="">role<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}IAM role attached to the Lambda Function.
{{% /md %}}</dd>

    <dt class="property-"
            title="">runtime<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The runtime environment for the Lambda function..
{{% /md %}}</dd>

    <dt class="property-"
            title="">source_<wbr>code_<wbr>hash<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Base64-encoded representation of raw SHA-256 sum of the zip file.
{{% /md %}}</dd>

    <dt class="property-"
            title="">source_<wbr>code_<wbr>size<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The size in bytes of the function .zip file.
{{% /md %}}</dd>

    <dt class="property-"
            title="">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">timeout<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The function execution time at which Lambda should terminate the function.
{{% /md %}}</dd>

    <dt class="property-"
            title="">tracing_<wbr>config<span class="property-indicator"></span>
        <span class="property-type"><a href="#getfunctiontracingconfig">Dict[Get<wbr>Function<wbr>Tracing<wbr>Config]</a></span>
    </dt>
    <dd>{{% md %}}Tracing settings of the function.
{{% /md %}}</dd>

    <dt class="property-"
            title="">version<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The version of the Lambda function.
{{% /md %}}</dd>

    <dt class="property-"
            title="">vpc_<wbr>config<span class="property-indicator"></span>
        <span class="property-type"><a href="#getfunctionvpcconfig">Dict[Get<wbr>Function<wbr>Vpc<wbr>Config]</a></span>
    </dt>
    <dd>{{% md %}}VPC configuration associated with your Lambda function.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}








## Supporting Types

#### GetFunctionDeadLetterConfig
{{% lang nodejs %}}
> See the   <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#GetFunctionDeadLetterConfig">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the   <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/lambda?tab=doc#GetFunctionDeadLetterConfig">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the   <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Lambda.GetFunctionDeadLetterConfig.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Target<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Target<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">target<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">target_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### GetFunctionEnvironment
{{% lang nodejs %}}
> See the   <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#GetFunctionEnvironment">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the   <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/lambda?tab=doc#GetFunctionEnvironment">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the   <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Lambda.GetFunctionEnvironment.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Variables<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, string></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Variables<span class="property-indicator"></span>
        <span class="property-type">map[string]string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">variables<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: string}</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">variables<span class="property-indicator"></span>
        <span class="property-type">Dict[str, str]</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### GetFunctionTracingConfig
{{% lang nodejs %}}
> See the   <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#GetFunctionTracingConfig">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the   <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/lambda?tab=doc#GetFunctionTracingConfig">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the   <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Lambda.GetFunctionTracingConfig.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Mode<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Mode<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">mode<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">mode<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### GetFunctionVpcConfig
{{% lang nodejs %}}
> See the   <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#GetFunctionVpcConfig">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the   <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/lambda?tab=doc#GetFunctionVpcConfig">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the   <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Lambda.GetFunctionVpcConfig.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Security<wbr>Group<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">List<string></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Subnet<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">List<string></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Vpc<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Security<wbr>Group<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Subnet<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Vpc<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">security<wbr>Group<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">string[]</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">subnet<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">string[]</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">vpc<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">security_<wbr>group_<wbr>ids<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">subnet_<wbr>ids<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">vpc_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}








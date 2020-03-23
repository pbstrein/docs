
---
title: "Function"
block_external_search_index: true
---




## Create a Function Resource

{{< chooser language "javascript,typescript,python,go,csharp" / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/lambda/#Function">Function</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/lambda/#FunctionArgs">FunctionArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">Function</span><span class="p">(resource_name, opts=None, </span>code=None<span class="p">, </span>dead_letter_config=None<span class="p">, </span>description=None<span class="p">, </span>environment=None<span class="p">, </span>handler=None<span class="p">, </span>kms_key_arn=None<span class="p">, </span>layers=None<span class="p">, </span>memory_size=None<span class="p">, </span>name=None<span class="p">, </span>publish=None<span class="p">, </span>reserved_concurrent_executions=None<span class="p">, </span>role=None<span class="p">, </span>runtime=None<span class="p">, </span>s3_bucket=None<span class="p">, </span>s3_key=None<span class="p">, </span>s3_object_version=None<span class="p">, </span>source_code_hash=None<span class="p">, </span>tags=None<span class="p">, </span>timeout=None<span class="p">, </span>tracing_config=None<span class="p">, </span>vpc_config=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewFunction<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/lambda?tab=doc#FunctionArgs">FunctionArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/lambda?tab=doc#Function">Function</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Lambda.Function.html">Function</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Lambda.FunctionArgs.html">FunctionArgs</a></span> <span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
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
            title="Optional">Code<span class="property-indicator"></span>
        <span class="property-type">Archive?</span>
    </dt>
    <dd>{{% md %}}The path to the function&#39;s deployment package within the local filesystem. If defined, The `s3_`-prefixed options cannot be used.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Dead<wbr>Letter<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#functiondeadletterconfig">Function<wbr>Dead<wbr>Letter<wbr>Config<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}Nested block to configure the function&#39;s *dead letter queue*. See details below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Description<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Description of what your Lambda Function does.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Environment<span class="property-indicator"></span>
        <span class="property-type"><a href="#functionenvironment">Function<wbr>Environment<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}The Lambda environment&#39;s configuration settings. Fields documented below.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Handler<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The function [entrypoint][3] in your code.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Kms<wbr>Key<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ARN for the KMS encryption key.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Layers<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}List of Lambda Layer Version ARNs (maximum of 5) to attach to your Lambda Function. See [Lambda Layers][10]
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Memory<wbr>Size<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}Amount of memory in MB your Lambda Function can use at runtime. Defaults to `128`. See [Limits][5]
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A unique name for your Lambda Function.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Publish<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Whether to publish creation/change as new Lambda Function Version. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Reserved<wbr>Concurrent<wbr>Executions<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The amount of reserved concurrent executions for this lambda function. A value of `0` disables lambda from being triggered and `-1` removes any concurrency limitations. Defaults to Unreserved Concurrency Limits `-1`. See [Managing Concurrency][9]
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Role<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}IAM role attached to the Lambda Function. This governs both who / what can invoke your Lambda Function, as well as what resources our Lambda Function has access to. See [Lambda Permission Model][4] for more details.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Runtime<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}See [Runtimes][6] for valid values.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">S3Bucket<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The S3 bucket location containing the function&#39;s deployment package. Conflicts with `filename`. This bucket must reside in the same AWS region where you are creating the Lambda function.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">S3Key<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The S3 key of an object containing the function&#39;s deployment package. Conflicts with `filename`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">S3Object<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The object version containing the function&#39;s deployment package. Conflicts with `filename`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Source<wbr>Code<wbr>Hash<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Used to trigger updates. Must be set to a base64-encoded SHA256 hash of the package file specified with either `filename` or `s3_key`. The usual way to set this is `filebase64sha256(&#34;file.zip&#34;)` (this provider 0.11.12 and later) or `base64sha256(file(&#34;file.zip&#34;))` (this provider 0.11.11 and earlier), where &#34;file.zip&#34; is the local filename of the lambda function source archive.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the object.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Timeout<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The amount of time your Lambda Function has to run in seconds. Defaults to `3`. See [Limits][5]
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tracing<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#functiontracingconfig">Function<wbr>Tracing<wbr>Config<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Vpc<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#functionvpcconfig">Function<wbr>Vpc<wbr>Config<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}Provide this to allow your function to access your VPC. Fields documented below. See [Lambda in VPC][7]
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Code<span class="property-indicator"></span>
        <span class="property-type">pulumi.Archive</span>
    </dt>
    <dd>{{% md %}}The path to the function&#39;s deployment package within the local filesystem. If defined, The `s3_`-prefixed options cannot be used.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Dead<wbr>Letter<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#functiondeadletterconfig">*Function<wbr>Dead<wbr>Letter<wbr>Config</a></span>
    </dt>
    <dd>{{% md %}}Nested block to configure the function&#39;s *dead letter queue*. See details below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Description<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Description of what your Lambda Function does.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Environment<span class="property-indicator"></span>
        <span class="property-type"><a href="#functionenvironment">*Function<wbr>Environment</a></span>
    </dt>
    <dd>{{% md %}}The Lambda environment&#39;s configuration settings. Fields documented below.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Handler<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The function [entrypoint][3] in your code.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Kms<wbr>Key<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The ARN for the KMS encryption key.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Layers<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}List of Lambda Layer Version ARNs (maximum of 5) to attach to your Lambda Function. See [Lambda Layers][10]
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Memory<wbr>Size<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}Amount of memory in MB your Lambda Function can use at runtime. Defaults to `128`. See [Limits][5]
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}A unique name for your Lambda Function.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Publish<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Whether to publish creation/change as new Lambda Function Version. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Reserved<wbr>Concurrent<wbr>Executions<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The amount of reserved concurrent executions for this lambda function. A value of `0` disables lambda from being triggered and `-1` removes any concurrency limitations. Defaults to Unreserved Concurrency Limits `-1`. See [Managing Concurrency][9]
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Role<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}IAM role attached to the Lambda Function. This governs both who / what can invoke your Lambda Function, as well as what resources our Lambda Function has access to. See [Lambda Permission Model][4] for more details.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Runtime<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}See [Runtimes][6] for valid values.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">S3Bucket<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The S3 bucket location containing the function&#39;s deployment package. Conflicts with `filename`. This bucket must reside in the same AWS region where you are creating the Lambda function.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">S3Key<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The S3 key of an object containing the function&#39;s deployment package. Conflicts with `filename`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">S3Object<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The object version containing the function&#39;s deployment package. Conflicts with `filename`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Source<wbr>Code<wbr>Hash<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Used to trigger updates. Must be set to a base64-encoded SHA256 hash of the package file specified with either `filename` or `s3_key`. The usual way to set this is `filebase64sha256(&#34;file.zip&#34;)` (this provider 0.11.12 and later) or `base64sha256(file(&#34;file.zip&#34;))` (this provider 0.11.11 and earlier), where &#34;file.zip&#34; is the local filename of the lambda function source archive.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the object.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Timeout<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The amount of time your Lambda Function has to run in seconds. Defaults to `3`. See [Limits][5]
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tracing<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#functiontracingconfig">*Function<wbr>Tracing<wbr>Config</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Vpc<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#functionvpcconfig">*Function<wbr>Vpc<wbr>Config</a></span>
    </dt>
    <dd>{{% md %}}Provide this to allow your function to access your VPC. Fields documented below. See [Lambda in VPC][7]
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">code<span class="property-indicator"></span>
        <span class="property-type">pulumi.asset.Archive?</span>
    </dt>
    <dd>{{% md %}}The path to the function&#39;s deployment package within the local filesystem. If defined, The `s3_`-prefixed options cannot be used.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">dead<wbr>Letter<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#functiondeadletterconfig">Function<wbr>Dead<wbr>Letter<wbr>Config?</a></span>
    </dt>
    <dd>{{% md %}}Nested block to configure the function&#39;s *dead letter queue*. See details below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">description<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Description of what your Lambda Function does.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">environment<span class="property-indicator"></span>
        <span class="property-type"><a href="#functionenvironment">Function<wbr>Environment?</a></span>
    </dt>
    <dd>{{% md %}}The Lambda environment&#39;s configuration settings. Fields documented below.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">handler<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The function [entrypoint][3] in your code.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">kms<wbr>Key<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ARN for the KMS encryption key.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">layers<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}List of Lambda Layer Version ARNs (maximum of 5) to attach to your Lambda Function. See [Lambda Layers][10]
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">memory<wbr>Size<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}Amount of memory in MB your Lambda Function can use at runtime. Defaults to `128`. See [Limits][5]
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A unique name for your Lambda Function.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">publish<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Whether to publish creation/change as new Lambda Function Version. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">reserved<wbr>Concurrent<wbr>Executions<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The amount of reserved concurrent executions for this lambda function. A value of `0` disables lambda from being triggered and `-1` removes any concurrency limitations. Defaults to Unreserved Concurrency Limits `-1`. See [Managing Concurrency][9]
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">role<span class="property-indicator"></span>
        <span class="property-type">ARN</span>
    </dt>
    <dd>{{% md %}}IAM role attached to the Lambda Function. This governs both who / what can invoke your Lambda Function, as well as what resources our Lambda Function has access to. See [Lambda Permission Model][4] for more details.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">runtime<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}See [Runtimes][6] for valid values.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">s3Bucket<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The S3 bucket location containing the function&#39;s deployment package. Conflicts with `filename`. This bucket must reside in the same AWS region where you are creating the Lambda function.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">s3Key<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The S3 key of an object containing the function&#39;s deployment package. Conflicts with `filename`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">s3Object<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The object version containing the function&#39;s deployment package. Conflicts with `filename`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">source<wbr>Code<wbr>Hash<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Used to trigger updates. Must be set to a base64-encoded SHA256 hash of the package file specified with either `filename` or `s3_key`. The usual way to set this is `filebase64sha256(&#34;file.zip&#34;)` (this provider 0.11.12 and later) or `base64sha256(file(&#34;file.zip&#34;))` (this provider 0.11.11 and earlier), where &#34;file.zip&#34; is the local filename of the lambda function source archive.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the object.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">timeout<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The amount of time your Lambda Function has to run in seconds. Defaults to `3`. See [Limits][5]
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tracing<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#functiontracingconfig">Function<wbr>Tracing<wbr>Config?</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">vpc<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#functionvpcconfig">Function<wbr>Vpc<wbr>Config?</a></span>
    </dt>
    <dd>{{% md %}}Provide this to allow your function to access your VPC. Fields documented below. See [Lambda in VPC][7]
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">code<span class="property-indicator"></span>
        <span class="property-type">pulumi.Archive</span>
    </dt>
    <dd>{{% md %}}The path to the function&#39;s deployment package within the local filesystem. If defined, The `s3_`-prefixed options cannot be used.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">dead_<wbr>letter_<wbr>config<span class="property-indicator"></span>
        <span class="property-type"><a href="#functiondeadletterconfig">Dict[Function<wbr>Dead<wbr>Letter<wbr>Config]</a></span>
    </dt>
    <dd>{{% md %}}Nested block to configure the function&#39;s *dead letter queue*. See details below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">description<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Description of what your Lambda Function does.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">environment<span class="property-indicator"></span>
        <span class="property-type"><a href="#functionenvironment">Dict[Function<wbr>Environment]</a></span>
    </dt>
    <dd>{{% md %}}The Lambda environment&#39;s configuration settings. Fields documented below.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">handler<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The function [entrypoint][3] in your code.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">kms_<wbr>key_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ARN for the KMS encryption key.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">layers<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}List of Lambda Layer Version ARNs (maximum of 5) to attach to your Lambda Function. See [Lambda Layers][10]
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">memory_<wbr>size<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}Amount of memory in MB your Lambda Function can use at runtime. Defaults to `128`. See [Limits][5]
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A unique name for your Lambda Function.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">publish<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Whether to publish creation/change as new Lambda Function Version. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">reserved_<wbr>concurrent_<wbr>executions<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The amount of reserved concurrent executions for this lambda function. A value of `0` disables lambda from being triggered and `-1` removes any concurrency limitations. Defaults to Unreserved Concurrency Limits `-1`. See [Managing Concurrency][9]
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">role<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}IAM role attached to the Lambda Function. This governs both who / what can invoke your Lambda Function, as well as what resources our Lambda Function has access to. See [Lambda Permission Model][4] for more details.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">runtime<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}See [Runtimes][6] for valid values.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">s3_<wbr>bucket<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The S3 bucket location containing the function&#39;s deployment package. Conflicts with `filename`. This bucket must reside in the same AWS region where you are creating the Lambda function.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">s3_<wbr>key<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The S3 key of an object containing the function&#39;s deployment package. Conflicts with `filename`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">s3_<wbr>object_<wbr>version<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The object version containing the function&#39;s deployment package. Conflicts with `filename`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">source_<wbr>code_<wbr>hash<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Used to trigger updates. Must be set to a base64-encoded SHA256 hash of the package file specified with either `filename` or `s3_key`. The usual way to set this is `filebase64sha256(&#34;file.zip&#34;)` (this provider 0.11.12 and later) or `base64sha256(file(&#34;file.zip&#34;))` (this provider 0.11.11 and earlier), where &#34;file.zip&#34; is the local filename of the lambda function source archive.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the object.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">timeout<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The amount of time your Lambda Function has to run in seconds. Defaults to `3`. See [Limits][5]
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tracing_<wbr>config<span class="property-indicator"></span>
        <span class="property-type"><a href="#functiontracingconfig">Dict[Function<wbr>Tracing<wbr>Config]</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">vpc_<wbr>config<span class="property-indicator"></span>
        <span class="property-type"><a href="#functionvpcconfig">Dict[Function<wbr>Vpc<wbr>Config]</a></span>
    </dt>
    <dd>{{% md %}}Provide this to allow your function to access your VPC. Fields documented below. See [Lambda in VPC][7]
{{% /md %}}</dd>

</dl>
{{% /choosable %}}




## Function Output Properties

The following output properties are available:




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Amazon Resource Name (ARN) identifying your Lambda Function.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Code<span class="property-indicator"></span>
        <span class="property-type">Archive?</span>
    </dt>
    <dd>{{% md %}}The path to the function&#39;s deployment package within the local filesystem. If defined, The `s3_`-prefixed options cannot be used.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Dead<wbr>Letter<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#functiondeadletterconfig">Function<wbr>Dead<wbr>Letter<wbr>Config?</a></span>
    </dt>
    <dd>{{% md %}}Nested block to configure the function&#39;s *dead letter queue*. See details below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Description<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Description of what your Lambda Function does.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Environment<span class="property-indicator"></span>
        <span class="property-type"><a href="#functionenvironment">Function<wbr>Environment?</a></span>
    </dt>
    <dd>{{% md %}}The Lambda environment&#39;s configuration settings. Fields documented below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Handler<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The function [entrypoint][3] in your code.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Invoke<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN to be used for invoking Lambda Function from API Gateway - to be used in [`aws.apigateway.Integration`](https://www.terraform.io/docs/providers/aws/r/api_gateway_integration.html)&#39;s `uri`
{{% /md %}}</dd>

    <dt class="property-"
            title="">Kms<wbr>Key<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
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
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}List of Lambda Layer Version ARNs (maximum of 5) to attach to your Lambda Function. See [Lambda Layers][10]
{{% /md %}}</dd>

    <dt class="property-"
            title="">Memory<wbr>Size<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}Amount of memory in MB your Lambda Function can use at runtime. Defaults to `128`. See [Limits][5]
{{% /md %}}</dd>

    <dt class="property-"
            title="">Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}A unique name for your Lambda Function.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Publish<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Whether to publish creation/change as new Lambda Function Version. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Qualified<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Amazon Resource Name (ARN) identifying your Lambda Function Version
(if versioning is enabled via `publish = true`).
{{% /md %}}</dd>

    <dt class="property-"
            title="">Reserved<wbr>Concurrent<wbr>Executions<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The amount of reserved concurrent executions for this lambda function. A value of `0` disables lambda from being triggered and `-1` removes any concurrency limitations. Defaults to Unreserved Concurrency Limits `-1`. See [Managing Concurrency][9]
{{% /md %}}</dd>

    <dt class="property-"
            title="">Role<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}IAM role attached to the Lambda Function. This governs both who / what can invoke your Lambda Function, as well as what resources our Lambda Function has access to. See [Lambda Permission Model][4] for more details.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Runtime<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}See [Runtimes][6] for valid values.
{{% /md %}}</dd>

    <dt class="property-"
            title="">S3Bucket<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The S3 bucket location containing the function&#39;s deployment package. Conflicts with `filename`. This bucket must reside in the same AWS region where you are creating the Lambda function.
{{% /md %}}</dd>

    <dt class="property-"
            title="">S3Key<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The S3 key of an object containing the function&#39;s deployment package. Conflicts with `filename`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">S3Object<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The object version containing the function&#39;s deployment package. Conflicts with `filename`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Source<wbr>Code<wbr>Hash<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Used to trigger updates. Must be set to a base64-encoded SHA256 hash of the package file specified with either `filename` or `s3_key`. The usual way to set this is `filebase64sha256(&#34;file.zip&#34;)` (this provider 0.11.12 and later) or `base64sha256(file(&#34;file.zip&#34;))` (this provider 0.11.11 and earlier), where &#34;file.zip&#34; is the local filename of the lambda function source archive.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Source<wbr>Code<wbr>Size<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The size in bytes of the function .zip file.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the object.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Timeout<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The amount of time your Lambda Function has to run in seconds. Defaults to `3`. See [Limits][5]
{{% /md %}}</dd>

    <dt class="property-"
            title="">Tracing<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#functiontracingconfig">Function<wbr>Tracing<wbr>Config</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">Version<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Latest published version of your Lambda Function.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Vpc<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#functionvpcconfig">Function<wbr>Vpc<wbr>Config?</a></span>
    </dt>
    <dd>{{% md %}}Provide this to allow your function to access your VPC. Fields documented below. See [Lambda in VPC][7]
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Amazon Resource Name (ARN) identifying your Lambda Function.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Code<span class="property-indicator"></span>
        <span class="property-type">pulumi.Archive</span>
    </dt>
    <dd>{{% md %}}The path to the function&#39;s deployment package within the local filesystem. If defined, The `s3_`-prefixed options cannot be used.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Dead<wbr>Letter<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#functiondeadletterconfig">*Function<wbr>Dead<wbr>Letter<wbr>Config</a></span>
    </dt>
    <dd>{{% md %}}Nested block to configure the function&#39;s *dead letter queue*. See details below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Description<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Description of what your Lambda Function does.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Environment<span class="property-indicator"></span>
        <span class="property-type"><a href="#functionenvironment">*Function<wbr>Environment</a></span>
    </dt>
    <dd>{{% md %}}The Lambda environment&#39;s configuration settings. Fields documented below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Handler<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The function [entrypoint][3] in your code.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Invoke<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN to be used for invoking Lambda Function from API Gateway - to be used in [`aws.apigateway.Integration`](https://www.terraform.io/docs/providers/aws/r/api_gateway_integration.html)&#39;s `uri`
{{% /md %}}</dd>

    <dt class="property-"
            title="">Kms<wbr>Key<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
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
    <dd>{{% md %}}List of Lambda Layer Version ARNs (maximum of 5) to attach to your Lambda Function. See [Lambda Layers][10]
{{% /md %}}</dd>

    <dt class="property-"
            title="">Memory<wbr>Size<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}Amount of memory in MB your Lambda Function can use at runtime. Defaults to `128`. See [Limits][5]
{{% /md %}}</dd>

    <dt class="property-"
            title="">Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}A unique name for your Lambda Function.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Publish<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Whether to publish creation/change as new Lambda Function Version. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Qualified<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Amazon Resource Name (ARN) identifying your Lambda Function Version
(if versioning is enabled via `publish = true`).
{{% /md %}}</dd>

    <dt class="property-"
            title="">Reserved<wbr>Concurrent<wbr>Executions<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The amount of reserved concurrent executions for this lambda function. A value of `0` disables lambda from being triggered and `-1` removes any concurrency limitations. Defaults to Unreserved Concurrency Limits `-1`. See [Managing Concurrency][9]
{{% /md %}}</dd>

    <dt class="property-"
            title="">Role<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}IAM role attached to the Lambda Function. This governs both who / what can invoke your Lambda Function, as well as what resources our Lambda Function has access to. See [Lambda Permission Model][4] for more details.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Runtime<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}See [Runtimes][6] for valid values.
{{% /md %}}</dd>

    <dt class="property-"
            title="">S3Bucket<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The S3 bucket location containing the function&#39;s deployment package. Conflicts with `filename`. This bucket must reside in the same AWS region where you are creating the Lambda function.
{{% /md %}}</dd>

    <dt class="property-"
            title="">S3Key<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The S3 key of an object containing the function&#39;s deployment package. Conflicts with `filename`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">S3Object<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The object version containing the function&#39;s deployment package. Conflicts with `filename`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Source<wbr>Code<wbr>Hash<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Used to trigger updates. Must be set to a base64-encoded SHA256 hash of the package file specified with either `filename` or `s3_key`. The usual way to set this is `filebase64sha256(&#34;file.zip&#34;)` (this provider 0.11.12 and later) or `base64sha256(file(&#34;file.zip&#34;))` (this provider 0.11.11 and earlier), where &#34;file.zip&#34; is the local filename of the lambda function source archive.
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
    <dd>{{% md %}}A mapping of tags to assign to the object.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Timeout<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The amount of time your Lambda Function has to run in seconds. Defaults to `3`. See [Limits][5]
{{% /md %}}</dd>

    <dt class="property-"
            title="">Tracing<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#functiontracingconfig">Function<wbr>Tracing<wbr>Config</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">Version<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Latest published version of your Lambda Function.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Vpc<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#functionvpcconfig">*Function<wbr>Vpc<wbr>Config</a></span>
    </dt>
    <dd>{{% md %}}Provide this to allow your function to access your VPC. Fields documented below. See [Lambda in VPC][7]
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Amazon Resource Name (ARN) identifying your Lambda Function.
{{% /md %}}</dd>

    <dt class="property-"
            title="">code<span class="property-indicator"></span>
        <span class="property-type">pulumi.asset.Archive?</span>
    </dt>
    <dd>{{% md %}}The path to the function&#39;s deployment package within the local filesystem. If defined, The `s3_`-prefixed options cannot be used.
{{% /md %}}</dd>

    <dt class="property-"
            title="">dead<wbr>Letter<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#functiondeadletterconfig">Function<wbr>Dead<wbr>Letter<wbr>Config?</a></span>
    </dt>
    <dd>{{% md %}}Nested block to configure the function&#39;s *dead letter queue*. See details below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">description<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Description of what your Lambda Function does.
{{% /md %}}</dd>

    <dt class="property-"
            title="">environment<span class="property-indicator"></span>
        <span class="property-type"><a href="#functionenvironment">Function<wbr>Environment?</a></span>
    </dt>
    <dd>{{% md %}}The Lambda environment&#39;s configuration settings. Fields documented below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">handler<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The function [entrypoint][3] in your code.
{{% /md %}}</dd>

    <dt class="property-"
            title="">invoke<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN to be used for invoking Lambda Function from API Gateway - to be used in [`aws.apigateway.Integration`](https://www.terraform.io/docs/providers/aws/r/api_gateway_integration.html)&#39;s `uri`
{{% /md %}}</dd>

    <dt class="property-"
            title="">kms<wbr>Key<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
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
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}List of Lambda Layer Version ARNs (maximum of 5) to attach to your Lambda Function. See [Lambda Layers][10]
{{% /md %}}</dd>

    <dt class="property-"
            title="">memory<wbr>Size<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}Amount of memory in MB your Lambda Function can use at runtime. Defaults to `128`. See [Limits][5]
{{% /md %}}</dd>

    <dt class="property-"
            title="">name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}A unique name for your Lambda Function.
{{% /md %}}</dd>

    <dt class="property-"
            title="">publish<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Whether to publish creation/change as new Lambda Function Version. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">qualified<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Amazon Resource Name (ARN) identifying your Lambda Function Version
(if versioning is enabled via `publish = true`).
{{% /md %}}</dd>

    <dt class="property-"
            title="">reserved<wbr>Concurrent<wbr>Executions<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The amount of reserved concurrent executions for this lambda function. A value of `0` disables lambda from being triggered and `-1` removes any concurrency limitations. Defaults to Unreserved Concurrency Limits `-1`. See [Managing Concurrency][9]
{{% /md %}}</dd>

    <dt class="property-"
            title="">role<span class="property-indicator"></span>
        <span class="property-type">ARN</span>
    </dt>
    <dd>{{% md %}}IAM role attached to the Lambda Function. This governs both who / what can invoke your Lambda Function, as well as what resources our Lambda Function has access to. See [Lambda Permission Model][4] for more details.
{{% /md %}}</dd>

    <dt class="property-"
            title="">runtime<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}See [Runtimes][6] for valid values.
{{% /md %}}</dd>

    <dt class="property-"
            title="">s3Bucket<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The S3 bucket location containing the function&#39;s deployment package. Conflicts with `filename`. This bucket must reside in the same AWS region where you are creating the Lambda function.
{{% /md %}}</dd>

    <dt class="property-"
            title="">s3Key<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The S3 key of an object containing the function&#39;s deployment package. Conflicts with `filename`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">s3Object<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The object version containing the function&#39;s deployment package. Conflicts with `filename`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">source<wbr>Code<wbr>Hash<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Used to trigger updates. Must be set to a base64-encoded SHA256 hash of the package file specified with either `filename` or `s3_key`. The usual way to set this is `filebase64sha256(&#34;file.zip&#34;)` (this provider 0.11.12 and later) or `base64sha256(file(&#34;file.zip&#34;))` (this provider 0.11.11 and earlier), where &#34;file.zip&#34; is the local filename of the lambda function source archive.
{{% /md %}}</dd>

    <dt class="property-"
            title="">source<wbr>Code<wbr>Size<span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}The size in bytes of the function .zip file.
{{% /md %}}</dd>

    <dt class="property-"
            title="">tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the object.
{{% /md %}}</dd>

    <dt class="property-"
            title="">timeout<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The amount of time your Lambda Function has to run in seconds. Defaults to `3`. See [Limits][5]
{{% /md %}}</dd>

    <dt class="property-"
            title="">tracing<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#functiontracingconfig">Function<wbr>Tracing<wbr>Config</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">version<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Latest published version of your Lambda Function.
{{% /md %}}</dd>

    <dt class="property-"
            title="">vpc<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#functionvpcconfig">Function<wbr>Vpc<wbr>Config?</a></span>
    </dt>
    <dd>{{% md %}}Provide this to allow your function to access your VPC. Fields documented below. See [Lambda in VPC][7]
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The Amazon Resource Name (ARN) identifying your Lambda Function.
{{% /md %}}</dd>

    <dt class="property-"
            title="">code<span class="property-indicator"></span>
        <span class="property-type">pulumi.Archive</span>
    </dt>
    <dd>{{% md %}}The path to the function&#39;s deployment package within the local filesystem. If defined, The `s3_`-prefixed options cannot be used.
{{% /md %}}</dd>

    <dt class="property-"
            title="">dead_<wbr>letter_<wbr>config<span class="property-indicator"></span>
        <span class="property-type"><a href="#functiondeadletterconfig">Dict[Function<wbr>Dead<wbr>Letter<wbr>Config]</a></span>
    </dt>
    <dd>{{% md %}}Nested block to configure the function&#39;s *dead letter queue*. See details below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">description<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Description of what your Lambda Function does.
{{% /md %}}</dd>

    <dt class="property-"
            title="">environment<span class="property-indicator"></span>
        <span class="property-type"><a href="#functionenvironment">Dict[Function<wbr>Environment]</a></span>
    </dt>
    <dd>{{% md %}}The Lambda environment&#39;s configuration settings. Fields documented below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">handler<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The function [entrypoint][3] in your code.
{{% /md %}}</dd>

    <dt class="property-"
            title="">invoke_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ARN to be used for invoking Lambda Function from API Gateway - to be used in [`aws.apigateway.Integration`](https://www.terraform.io/docs/providers/aws/r/api_gateway_integration.html)&#39;s `uri`
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
    <dd>{{% md %}}List of Lambda Layer Version ARNs (maximum of 5) to attach to your Lambda Function. See [Lambda Layers][10]
{{% /md %}}</dd>

    <dt class="property-"
            title="">memory_<wbr>size<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}Amount of memory in MB your Lambda Function can use at runtime. Defaults to `128`. See [Limits][5]
{{% /md %}}</dd>

    <dt class="property-"
            title="">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A unique name for your Lambda Function.
{{% /md %}}</dd>

    <dt class="property-"
            title="">publish<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Whether to publish creation/change as new Lambda Function Version. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">qualified_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The Amazon Resource Name (ARN) identifying your Lambda Function Version
(if versioning is enabled via `publish = true`).
{{% /md %}}</dd>

    <dt class="property-"
            title="">reserved_<wbr>concurrent_<wbr>executions<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The amount of reserved concurrent executions for this lambda function. A value of `0` disables lambda from being triggered and `-1` removes any concurrency limitations. Defaults to Unreserved Concurrency Limits `-1`. See [Managing Concurrency][9]
{{% /md %}}</dd>

    <dt class="property-"
            title="">role<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}IAM role attached to the Lambda Function. This governs both who / what can invoke your Lambda Function, as well as what resources our Lambda Function has access to. See [Lambda Permission Model][4] for more details.
{{% /md %}}</dd>

    <dt class="property-"
            title="">runtime<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}See [Runtimes][6] for valid values.
{{% /md %}}</dd>

    <dt class="property-"
            title="">s3_<wbr>bucket<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The S3 bucket location containing the function&#39;s deployment package. Conflicts with `filename`. This bucket must reside in the same AWS region where you are creating the Lambda function.
{{% /md %}}</dd>

    <dt class="property-"
            title="">s3_<wbr>key<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The S3 key of an object containing the function&#39;s deployment package. Conflicts with `filename`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">s3_<wbr>object_<wbr>version<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The object version containing the function&#39;s deployment package. Conflicts with `filename`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">source_<wbr>code_<wbr>hash<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Used to trigger updates. Must be set to a base64-encoded SHA256 hash of the package file specified with either `filename` or `s3_key`. The usual way to set this is `filebase64sha256(&#34;file.zip&#34;)` (this provider 0.11.12 and later) or `base64sha256(file(&#34;file.zip&#34;))` (this provider 0.11.11 and earlier), where &#34;file.zip&#34; is the local filename of the lambda function source archive.
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
    <dd>{{% md %}}A mapping of tags to assign to the object.
{{% /md %}}</dd>

    <dt class="property-"
            title="">timeout<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The amount of time your Lambda Function has to run in seconds. Defaults to `3`. See [Limits][5]
{{% /md %}}</dd>

    <dt class="property-"
            title="">tracing_<wbr>config<span class="property-indicator"></span>
        <span class="property-type"><a href="#functiontracingconfig">Dict[Function<wbr>Tracing<wbr>Config]</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">version<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Latest published version of your Lambda Function.
{{% /md %}}</dd>

    <dt class="property-"
            title="">vpc_<wbr>config<span class="property-indicator"></span>
        <span class="property-type"><a href="#functionvpcconfig">Dict[Function<wbr>Vpc<wbr>Config]</a></span>
    </dt>
    <dd>{{% md %}}Provide this to allow your function to access your VPC. Fields documented below. See [Lambda in VPC][7]
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





## Look up an Existing Function Resource

{{< chooser language "javascript,typescript,python,go,csharp  " / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">pulumi.Input&lt;pulumi.ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/lambda/#FunctionState">FunctionState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/lambda/#Function">Function</a></span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>arn=None<span class="p">, </span>code=None<span class="p">, </span>dead_letter_config=None<span class="p">, </span>description=None<span class="p">, </span>environment=None<span class="p">, </span>handler=None<span class="p">, </span>invoke_arn=None<span class="p">, </span>kms_key_arn=None<span class="p">, </span>last_modified=None<span class="p">, </span>layers=None<span class="p">, </span>memory_size=None<span class="p">, </span>name=None<span class="p">, </span>publish=None<span class="p">, </span>qualified_arn=None<span class="p">, </span>reserved_concurrent_executions=None<span class="p">, </span>role=None<span class="p">, </span>runtime=None<span class="p">, </span>s3_bucket=None<span class="p">, </span>s3_key=None<span class="p">, </span>s3_object_version=None<span class="p">, </span>source_code_hash=None<span class="p">, </span>source_code_size=None<span class="p">, </span>tags=None<span class="p">, </span>timeout=None<span class="p">, </span>tracing_config=None<span class="p">, </span>version=None<span class="p">, </span>vpc_config=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetFunction<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">pulumi.IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/lambda?tab=doc#FunctionState">FunctionState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/lambda?tab=doc#Function">Function</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Lambda.Function.html">Function</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Pulumi.Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Lambda.FunctionState.html">FunctionState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
{{% /choosable %}}

Get an existing Function resource's state with the given name, ID, and optional extra properties used to qualify the lookup.

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
    <dd>{{% md %}}The Amazon Resource Name (ARN) identifying your Lambda Function.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Code<span class="property-indicator"></span>
        <span class="property-type">Archive?</span>
    </dt>
    <dd>{{% md %}}The path to the function&#39;s deployment package within the local filesystem. If defined, The `s3_`-prefixed options cannot be used.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Dead<wbr>Letter<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#functiondeadletterconfig">Function<wbr>Dead<wbr>Letter<wbr>Config<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}Nested block to configure the function&#39;s *dead letter queue*. See details below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Description<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Description of what your Lambda Function does.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Environment<span class="property-indicator"></span>
        <span class="property-type"><a href="#functionenvironment">Function<wbr>Environment<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}The Lambda environment&#39;s configuration settings. Fields documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Handler<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The function [entrypoint][3] in your code.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Invoke<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ARN to be used for invoking Lambda Function from API Gateway - to be used in [`aws.apigateway.Integration`](https://www.terraform.io/docs/providers/aws/r/api_gateway_integration.html)&#39;s `uri`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Kms<wbr>Key<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ARN for the KMS encryption key.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Last<wbr>Modified<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The date this resource was last modified.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Layers<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}List of Lambda Layer Version ARNs (maximum of 5) to attach to your Lambda Function. See [Lambda Layers][10]
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Memory<wbr>Size<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}Amount of memory in MB your Lambda Function can use at runtime. Defaults to `128`. See [Limits][5]
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A unique name for your Lambda Function.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Publish<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Whether to publish creation/change as new Lambda Function Version. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Qualified<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The Amazon Resource Name (ARN) identifying your Lambda Function Version
(if versioning is enabled via `publish = true`).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Reserved<wbr>Concurrent<wbr>Executions<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The amount of reserved concurrent executions for this lambda function. A value of `0` disables lambda from being triggered and `-1` removes any concurrency limitations. Defaults to Unreserved Concurrency Limits `-1`. See [Managing Concurrency][9]
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Role<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}IAM role attached to the Lambda Function. This governs both who / what can invoke your Lambda Function, as well as what resources our Lambda Function has access to. See [Lambda Permission Model][4] for more details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Runtime<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}See [Runtimes][6] for valid values.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">S3Bucket<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The S3 bucket location containing the function&#39;s deployment package. Conflicts with `filename`. This bucket must reside in the same AWS region where you are creating the Lambda function.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">S3Key<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The S3 key of an object containing the function&#39;s deployment package. Conflicts with `filename`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">S3Object<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The object version containing the function&#39;s deployment package. Conflicts with `filename`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Source<wbr>Code<wbr>Hash<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Used to trigger updates. Must be set to a base64-encoded SHA256 hash of the package file specified with either `filename` or `s3_key`. The usual way to set this is `filebase64sha256(&#34;file.zip&#34;)` (this provider 0.11.12 and later) or `base64sha256(file(&#34;file.zip&#34;))` (this provider 0.11.11 and earlier), where &#34;file.zip&#34; is the local filename of the lambda function source archive.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Source<wbr>Code<wbr>Size<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The size in bytes of the function .zip file.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the object.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Timeout<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The amount of time your Lambda Function has to run in seconds. Defaults to `3`. See [Limits][5]
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tracing<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#functiontracingconfig">Function<wbr>Tracing<wbr>Config<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Version<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Latest published version of your Lambda Function.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Vpc<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#functionvpcconfig">Function<wbr>Vpc<wbr>Config<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}Provide this to allow your function to access your VPC. Fields documented below. See [Lambda in VPC][7]
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The Amazon Resource Name (ARN) identifying your Lambda Function.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Code<span class="property-indicator"></span>
        <span class="property-type">pulumi.Archive</span>
    </dt>
    <dd>{{% md %}}The path to the function&#39;s deployment package within the local filesystem. If defined, The `s3_`-prefixed options cannot be used.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Dead<wbr>Letter<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#functiondeadletterconfig">*Function<wbr>Dead<wbr>Letter<wbr>Config</a></span>
    </dt>
    <dd>{{% md %}}Nested block to configure the function&#39;s *dead letter queue*. See details below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Description<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Description of what your Lambda Function does.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Environment<span class="property-indicator"></span>
        <span class="property-type"><a href="#functionenvironment">*Function<wbr>Environment</a></span>
    </dt>
    <dd>{{% md %}}The Lambda environment&#39;s configuration settings. Fields documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Handler<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The function [entrypoint][3] in your code.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Invoke<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The ARN to be used for invoking Lambda Function from API Gateway - to be used in [`aws.apigateway.Integration`](https://www.terraform.io/docs/providers/aws/r/api_gateway_integration.html)&#39;s `uri`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Kms<wbr>Key<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The ARN for the KMS encryption key.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Last<wbr>Modified<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The date this resource was last modified.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Layers<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}List of Lambda Layer Version ARNs (maximum of 5) to attach to your Lambda Function. See [Lambda Layers][10]
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Memory<wbr>Size<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}Amount of memory in MB your Lambda Function can use at runtime. Defaults to `128`. See [Limits][5]
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}A unique name for your Lambda Function.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Publish<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Whether to publish creation/change as new Lambda Function Version. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Qualified<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The Amazon Resource Name (ARN) identifying your Lambda Function Version
(if versioning is enabled via `publish = true`).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Reserved<wbr>Concurrent<wbr>Executions<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The amount of reserved concurrent executions for this lambda function. A value of `0` disables lambda from being triggered and `-1` removes any concurrency limitations. Defaults to Unreserved Concurrency Limits `-1`. See [Managing Concurrency][9]
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Role<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}IAM role attached to the Lambda Function. This governs both who / what can invoke your Lambda Function, as well as what resources our Lambda Function has access to. See [Lambda Permission Model][4] for more details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Runtime<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}See [Runtimes][6] for valid values.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">S3Bucket<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The S3 bucket location containing the function&#39;s deployment package. Conflicts with `filename`. This bucket must reside in the same AWS region where you are creating the Lambda function.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">S3Key<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The S3 key of an object containing the function&#39;s deployment package. Conflicts with `filename`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">S3Object<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The object version containing the function&#39;s deployment package. Conflicts with `filename`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Source<wbr>Code<wbr>Hash<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Used to trigger updates. Must be set to a base64-encoded SHA256 hash of the package file specified with either `filename` or `s3_key`. The usual way to set this is `filebase64sha256(&#34;file.zip&#34;)` (this provider 0.11.12 and later) or `base64sha256(file(&#34;file.zip&#34;))` (this provider 0.11.11 and earlier), where &#34;file.zip&#34; is the local filename of the lambda function source archive.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Source<wbr>Code<wbr>Size<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The size in bytes of the function .zip file.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the object.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Timeout<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The amount of time your Lambda Function has to run in seconds. Defaults to `3`. See [Limits][5]
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tracing<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#functiontracingconfig">*Function<wbr>Tracing<wbr>Config</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Version<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Latest published version of your Lambda Function.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Vpc<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#functionvpcconfig">*Function<wbr>Vpc<wbr>Config</a></span>
    </dt>
    <dd>{{% md %}}Provide this to allow your function to access your VPC. Fields documented below. See [Lambda in VPC][7]
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The Amazon Resource Name (ARN) identifying your Lambda Function.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">code<span class="property-indicator"></span>
        <span class="property-type">pulumi.asset.Archive?</span>
    </dt>
    <dd>{{% md %}}The path to the function&#39;s deployment package within the local filesystem. If defined, The `s3_`-prefixed options cannot be used.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">dead<wbr>Letter<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#functiondeadletterconfig">Function<wbr>Dead<wbr>Letter<wbr>Config?</a></span>
    </dt>
    <dd>{{% md %}}Nested block to configure the function&#39;s *dead letter queue*. See details below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">description<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Description of what your Lambda Function does.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">environment<span class="property-indicator"></span>
        <span class="property-type"><a href="#functionenvironment">Function<wbr>Environment?</a></span>
    </dt>
    <dd>{{% md %}}The Lambda environment&#39;s configuration settings. Fields documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">handler<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The function [entrypoint][3] in your code.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">invoke<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ARN to be used for invoking Lambda Function from API Gateway - to be used in [`aws.apigateway.Integration`](https://www.terraform.io/docs/providers/aws/r/api_gateway_integration.html)&#39;s `uri`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">kms<wbr>Key<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ARN for the KMS encryption key.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">last<wbr>Modified<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The date this resource was last modified.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">layers<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}List of Lambda Layer Version ARNs (maximum of 5) to attach to your Lambda Function. See [Lambda Layers][10]
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">memory<wbr>Size<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}Amount of memory in MB your Lambda Function can use at runtime. Defaults to `128`. See [Limits][5]
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A unique name for your Lambda Function.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">publish<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Whether to publish creation/change as new Lambda Function Version. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">qualified<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The Amazon Resource Name (ARN) identifying your Lambda Function Version
(if versioning is enabled via `publish = true`).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">reserved<wbr>Concurrent<wbr>Executions<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The amount of reserved concurrent executions for this lambda function. A value of `0` disables lambda from being triggered and `-1` removes any concurrency limitations. Defaults to Unreserved Concurrency Limits `-1`. See [Managing Concurrency][9]
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">role<span class="property-indicator"></span>
        <span class="property-type">ARN?</span>
    </dt>
    <dd>{{% md %}}IAM role attached to the Lambda Function. This governs both who / what can invoke your Lambda Function, as well as what resources our Lambda Function has access to. See [Lambda Permission Model][4] for more details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">runtime<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}See [Runtimes][6] for valid values.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">s3Bucket<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The S3 bucket location containing the function&#39;s deployment package. Conflicts with `filename`. This bucket must reside in the same AWS region where you are creating the Lambda function.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">s3Key<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The S3 key of an object containing the function&#39;s deployment package. Conflicts with `filename`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">s3Object<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The object version containing the function&#39;s deployment package. Conflicts with `filename`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">source<wbr>Code<wbr>Hash<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Used to trigger updates. Must be set to a base64-encoded SHA256 hash of the package file specified with either `filename` or `s3_key`. The usual way to set this is `filebase64sha256(&#34;file.zip&#34;)` (this provider 0.11.12 and later) or `base64sha256(file(&#34;file.zip&#34;))` (this provider 0.11.11 and earlier), where &#34;file.zip&#34; is the local filename of the lambda function source archive.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">source<wbr>Code<wbr>Size<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The size in bytes of the function .zip file.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the object.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">timeout<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The amount of time your Lambda Function has to run in seconds. Defaults to `3`. See [Limits][5]
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tracing<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#functiontracingconfig">Function<wbr>Tracing<wbr>Config?</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">version<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Latest published version of your Lambda Function.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">vpc<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#functionvpcconfig">Function<wbr>Vpc<wbr>Config?</a></span>
    </dt>
    <dd>{{% md %}}Provide this to allow your function to access your VPC. Fields documented below. See [Lambda in VPC][7]
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The Amazon Resource Name (ARN) identifying your Lambda Function.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">code<span class="property-indicator"></span>
        <span class="property-type">pulumi.Archive</span>
    </dt>
    <dd>{{% md %}}The path to the function&#39;s deployment package within the local filesystem. If defined, The `s3_`-prefixed options cannot be used.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">dead_<wbr>letter_<wbr>config<span class="property-indicator"></span>
        <span class="property-type"><a href="#functiondeadletterconfig">Dict[Function<wbr>Dead<wbr>Letter<wbr>Config]</a></span>
    </dt>
    <dd>{{% md %}}Nested block to configure the function&#39;s *dead letter queue*. See details below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">description<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Description of what your Lambda Function does.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">environment<span class="property-indicator"></span>
        <span class="property-type"><a href="#functionenvironment">Dict[Function<wbr>Environment]</a></span>
    </dt>
    <dd>{{% md %}}The Lambda environment&#39;s configuration settings. Fields documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">handler<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The function [entrypoint][3] in your code.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">invoke_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ARN to be used for invoking Lambda Function from API Gateway - to be used in [`aws.apigateway.Integration`](https://www.terraform.io/docs/providers/aws/r/api_gateway_integration.html)&#39;s `uri`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">kms_<wbr>key_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ARN for the KMS encryption key.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">last_<wbr>modified<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The date this resource was last modified.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">layers<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}List of Lambda Layer Version ARNs (maximum of 5) to attach to your Lambda Function. See [Lambda Layers][10]
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">memory_<wbr>size<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}Amount of memory in MB your Lambda Function can use at runtime. Defaults to `128`. See [Limits][5]
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A unique name for your Lambda Function.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">publish<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Whether to publish creation/change as new Lambda Function Version. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">qualified_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The Amazon Resource Name (ARN) identifying your Lambda Function Version
(if versioning is enabled via `publish = true`).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">reserved_<wbr>concurrent_<wbr>executions<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The amount of reserved concurrent executions for this lambda function. A value of `0` disables lambda from being triggered and `-1` removes any concurrency limitations. Defaults to Unreserved Concurrency Limits `-1`. See [Managing Concurrency][9]
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">role<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}IAM role attached to the Lambda Function. This governs both who / what can invoke your Lambda Function, as well as what resources our Lambda Function has access to. See [Lambda Permission Model][4] for more details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">runtime<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}See [Runtimes][6] for valid values.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">s3_<wbr>bucket<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The S3 bucket location containing the function&#39;s deployment package. Conflicts with `filename`. This bucket must reside in the same AWS region where you are creating the Lambda function.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">s3_<wbr>key<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The S3 key of an object containing the function&#39;s deployment package. Conflicts with `filename`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">s3_<wbr>object_<wbr>version<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The object version containing the function&#39;s deployment package. Conflicts with `filename`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">source_<wbr>code_<wbr>hash<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Used to trigger updates. Must be set to a base64-encoded SHA256 hash of the package file specified with either `filename` or `s3_key`. The usual way to set this is `filebase64sha256(&#34;file.zip&#34;)` (this provider 0.11.12 and later) or `base64sha256(file(&#34;file.zip&#34;))` (this provider 0.11.11 and earlier), where &#34;file.zip&#34; is the local filename of the lambda function source archive.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">source_<wbr>code_<wbr>size<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The size in bytes of the function .zip file.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the object.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">timeout<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The amount of time your Lambda Function has to run in seconds. Defaults to `3`. See [Limits][5]
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tracing_<wbr>config<span class="property-indicator"></span>
        <span class="property-type"><a href="#functiontracingconfig">Dict[Function<wbr>Tracing<wbr>Config]</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">version<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Latest published version of your Lambda Function.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">vpc_<wbr>config<span class="property-indicator"></span>
        <span class="property-type"><a href="#functionvpcconfig">Dict[Function<wbr>Vpc<wbr>Config]</a></span>
    </dt>
    <dd>{{% md %}}Provide this to allow your function to access your VPC. Fields documented below. See [Lambda in VPC][7]
{{% /md %}}</dd>

</dl>
{{% /choosable %}}







## Supporting Types

#### FunctionDeadLetterConfig
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#FunctionDeadLetterConfig">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#FunctionDeadLetterConfig">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/lambda?tab=doc#FunctionDeadLetterConfigArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/lambda?tab=doc#FunctionDeadLetterConfigOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Lambda.FunctionDeadLetterConfigArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Lambda.FunctionDeadLetterConfig.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Target<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of an SNS topic or SQS queue to notify when an invocation fails. If this
option is used, the function&#39;s IAM role must be granted suitable access to write to the target object,
which means allowing either the `sns:Publish` or `sqs:SendMessage` action on this ARN, depending on
which service is targeted.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Target<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of an SNS topic or SQS queue to notify when an invocation fails. If this
option is used, the function&#39;s IAM role must be granted suitable access to write to the target object,
which means allowing either the `sns:Publish` or `sqs:SendMessage` action on this ARN, depending on
which service is targeted.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">target<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of an SNS topic or SQS queue to notify when an invocation fails. If this
option is used, the function&#39;s IAM role must be granted suitable access to write to the target object,
which means allowing either the `sns:Publish` or `sqs:SendMessage` action on this ARN, depending on
which service is targeted.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">target_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ARN of an SNS topic or SQS queue to notify when an invocation fails. If this
option is used, the function&#39;s IAM role must be granted suitable access to write to the target object,
which means allowing either the `sns:Publish` or `sqs:SendMessage` action on this ARN, depending on
which service is targeted.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### FunctionEnvironment
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#FunctionEnvironment">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#FunctionEnvironment">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/lambda?tab=doc#FunctionEnvironmentArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/lambda?tab=doc#FunctionEnvironmentOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Lambda.FunctionEnvironmentArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Lambda.FunctionEnvironment.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Variables<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, string>?</span>
    </dt>
    <dd>{{% md %}}A map that defines environment variables for the Lambda function.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Variables<span class="property-indicator"></span>
        <span class="property-type">map[string]string</span>
    </dt>
    <dd>{{% md %}}A map that defines environment variables for the Lambda function.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">variables<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: string}?</span>
    </dt>
    <dd>{{% md %}}A map that defines environment variables for the Lambda function.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">variables<span class="property-indicator"></span>
        <span class="property-type">Dict[str, str]</span>
    </dt>
    <dd>{{% md %}}A map that defines environment variables for the Lambda function.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### FunctionTracingConfig
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#FunctionTracingConfig">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#FunctionTracingConfig">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/lambda?tab=doc#FunctionTracingConfigArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/lambda?tab=doc#FunctionTracingConfigOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Lambda.FunctionTracingConfigArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Lambda.FunctionTracingConfig.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Mode<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Can be either `PassThrough` or `Active`. If PassThrough, Lambda will only trace
the request from an upstream service if it contains a tracing header with
&#34;sampled=1&#34;. If Active, Lambda will respect any tracing header it receives
from an upstream service. If no tracing header is received, Lambda will call
X-Ray for a tracing decision.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Mode<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Can be either `PassThrough` or `Active`. If PassThrough, Lambda will only trace
the request from an upstream service if it contains a tracing header with
&#34;sampled=1&#34;. If Active, Lambda will respect any tracing header it receives
from an upstream service. If no tracing header is received, Lambda will call
X-Ray for a tracing decision.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">mode<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Can be either `PassThrough` or `Active`. If PassThrough, Lambda will only trace
the request from an upstream service if it contains a tracing header with
&#34;sampled=1&#34;. If Active, Lambda will respect any tracing header it receives
from an upstream service. If no tracing header is received, Lambda will call
X-Ray for a tracing decision.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">mode<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Can be either `PassThrough` or `Active`. If PassThrough, Lambda will only trace
the request from an upstream service if it contains a tracing header with
&#34;sampled=1&#34;. If Active, Lambda will respect any tracing header it receives
from an upstream service. If no tracing header is received, Lambda will call
X-Ray for a tracing decision.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### FunctionVpcConfig
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#FunctionVpcConfig">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#FunctionVpcConfig">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/lambda?tab=doc#FunctionVpcConfigArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/lambda?tab=doc#FunctionVpcConfigOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Lambda.FunctionVpcConfigArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Lambda.FunctionVpcConfig.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Security<wbr>Group<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">List<string></span>
    </dt>
    <dd>{{% md %}}A list of security group IDs associated with the Lambda function.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Subnet<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">List<string></span>
    </dt>
    <dd>{{% md %}}A list of subnet IDs associated with the Lambda function.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Vpc<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
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
    <dd>{{% md %}}A list of security group IDs associated with the Lambda function.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Subnet<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}A list of subnet IDs associated with the Lambda function.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Vpc<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
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
    <dd>{{% md %}}A list of security group IDs associated with the Lambda function.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">subnet<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">string[]</span>
    </dt>
    <dd>{{% md %}}A list of subnet IDs associated with the Lambda function.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">vpc<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
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
    <dd>{{% md %}}A list of security group IDs associated with the Lambda function.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">subnet_<wbr>ids<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}A list of subnet IDs associated with the Lambda function.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">vpc_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}








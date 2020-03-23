
---
title: "LayerVersion"
block_external_search_index: true
---

Provides a Lambda Layer Version resource. Lambda Layers allow you to reuse shared bits of code across multiple lambda functions.

For information about Lambda Layers and how to use them, see [AWS Lambda Layers][1]

## Example Usage

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const lambdaLayer = new aws.lambda.LayerVersion("lambda_layer", {
    compatibleRuntimes: ["nodejs8.10"],
    code: new pulumi.asset.FileArchive("lambda_layer_payload.zip"),
    layerName: "lambda_layer_name",
});
```

## Specifying the Deployment Package

AWS Lambda Layers expect source code to be provided as a deployment package whose structure varies depending on which `compatible_runtimes` this layer specifies.
See [Runtimes][2] for the valid values of `compatible_runtimes`.

Once you have created your deployment package you can specify it either directly as a local file (using the `filename` argument) or
indirectly via Amazon S3 (using the `s3_bucket`, `s3_key` and `s3_object_version` arguments). When providing the deployment
package via S3 it may be useful to use the `aws.s3.BucketObject` resource to upload it.

For larger deployment packages it is recommended by Amazon to upload via S3, since the S3 API has better support for uploading
large files efficiently.

> This content is derived from https://github.com/terraform-providers/terraform-provider-aws/blob/master/website/docs/r/lambda_layer_version.html.markdown.



## Create a LayerVersion Resource

{{< chooser language "javascript,typescript,python,go,csharp" / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/lambda/#LayerVersion">LayerVersion</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/lambda/#LayerVersionArgs">LayerVersionArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">LayerVersion</span><span class="p">(resource_name, opts=None, </span>code=None<span class="p">, </span>compatible_runtimes=None<span class="p">, </span>description=None<span class="p">, </span>layer_name=None<span class="p">, </span>license_info=None<span class="p">, </span>s3_bucket=None<span class="p">, </span>s3_key=None<span class="p">, </span>s3_object_version=None<span class="p">, </span>source_code_hash=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewLayerVersion<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/lambda?tab=doc#LayerVersionArgs">LayerVersionArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/lambda?tab=doc#LayerVersion">LayerVersion</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Lambda.LayerVersion.html">LayerVersion</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Lambda.LayerVersionArgs.html">LayerVersionArgs</a></span> <span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
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
            title="Optional">Compatible<wbr>Runtimes<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}A list of [Runtimes][2] this layer is compatible with. Up to 5 runtimes can be specified.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Description<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Description of what your Lambda Layer does.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Layer<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}A unique name for your Lambda Layer
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">License<wbr>Info<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}License info for your Lambda Layer. See [License Info][3].
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
    <dd>{{% md %}}Used to trigger updates. Must be set to a base64-encoded SHA256 hash of the package file specified with either `filename` or `s3_key`. The usual way to set this is `${filebase64sha256(&#34;file.zip&#34;)}` (this provider 0.11.12 or later) or `${base64sha256(file(&#34;file.zip&#34;))}` (this provider 0.11.11 and earlier), where &#34;file.zip&#34; is the local filename of the lambda layer source archive.
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
            title="Optional">Compatible<wbr>Runtimes<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}A list of [Runtimes][2] this layer is compatible with. Up to 5 runtimes can be specified.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Description<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Description of what your Lambda Layer does.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Layer<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}A unique name for your Lambda Layer
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">License<wbr>Info<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}License info for your Lambda Layer. See [License Info][3].
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
    <dd>{{% md %}}Used to trigger updates. Must be set to a base64-encoded SHA256 hash of the package file specified with either `filename` or `s3_key`. The usual way to set this is `${filebase64sha256(&#34;file.zip&#34;)}` (this provider 0.11.12 or later) or `${base64sha256(file(&#34;file.zip&#34;))}` (this provider 0.11.11 and earlier), where &#34;file.zip&#34; is the local filename of the lambda layer source archive.
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
            title="Optional">compatible<wbr>Runtimes<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}A list of [Runtimes][2] this layer is compatible with. Up to 5 runtimes can be specified.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">description<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Description of what your Lambda Layer does.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">layer<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}A unique name for your Lambda Layer
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">license<wbr>Info<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}License info for your Lambda Layer. See [License Info][3].
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
    <dd>{{% md %}}Used to trigger updates. Must be set to a base64-encoded SHA256 hash of the package file specified with either `filename` or `s3_key`. The usual way to set this is `${filebase64sha256(&#34;file.zip&#34;)}` (this provider 0.11.12 or later) or `${base64sha256(file(&#34;file.zip&#34;))}` (this provider 0.11.11 and earlier), where &#34;file.zip&#34; is the local filename of the lambda layer source archive.
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
            title="Optional">compatible_<wbr>runtimes<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}A list of [Runtimes][2] this layer is compatible with. Up to 5 runtimes can be specified.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">description<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Description of what your Lambda Layer does.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">layer_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A unique name for your Lambda Layer
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">license_<wbr>info<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}License info for your Lambda Layer. See [License Info][3].
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
    <dd>{{% md %}}Used to trigger updates. Must be set to a base64-encoded SHA256 hash of the package file specified with either `filename` or `s3_key`. The usual way to set this is `${filebase64sha256(&#34;file.zip&#34;)}` (this provider 0.11.12 or later) or `${base64sha256(file(&#34;file.zip&#34;))}` (this provider 0.11.11 and earlier), where &#34;file.zip&#34; is the local filename of the lambda layer source archive.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}




## LayerVersion Output Properties

The following output properties are available:




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Amazon Resource Name (ARN) of the Lambda Layer with version.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Code<span class="property-indicator"></span>
        <span class="property-type">Archive?</span>
    </dt>
    <dd>{{% md %}}The path to the function&#39;s deployment package within the local filesystem. If defined, The `s3_`-prefixed options cannot be used.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Compatible<wbr>Runtimes<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}A list of [Runtimes][2] this layer is compatible with. Up to 5 runtimes can be specified.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Created<wbr>Date<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The date this resource was created.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Description<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Description of what your Lambda Layer does.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Layer<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Amazon Resource Name (ARN) of the Lambda Layer without version.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Layer<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}A unique name for your Lambda Layer
{{% /md %}}</dd>

    <dt class="property-"
            title="">License<wbr>Info<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}License info for your Lambda Layer. See [License Info][3].
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
    <dd>{{% md %}}Used to trigger updates. Must be set to a base64-encoded SHA256 hash of the package file specified with either `filename` or `s3_key`. The usual way to set this is `${filebase64sha256(&#34;file.zip&#34;)}` (this provider 0.11.12 or later) or `${base64sha256(file(&#34;file.zip&#34;))}` (this provider 0.11.11 and earlier), where &#34;file.zip&#34; is the local filename of the lambda layer source archive.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Source<wbr>Code<wbr>Size<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The size in bytes of the function .zip file.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Version<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}This Lamba Layer version.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Amazon Resource Name (ARN) of the Lambda Layer with version.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Code<span class="property-indicator"></span>
        <span class="property-type">pulumi.Archive</span>
    </dt>
    <dd>{{% md %}}The path to the function&#39;s deployment package within the local filesystem. If defined, The `s3_`-prefixed options cannot be used.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Compatible<wbr>Runtimes<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}A list of [Runtimes][2] this layer is compatible with. Up to 5 runtimes can be specified.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Created<wbr>Date<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The date this resource was created.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Description<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Description of what your Lambda Layer does.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Layer<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Amazon Resource Name (ARN) of the Lambda Layer without version.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Layer<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}A unique name for your Lambda Layer
{{% /md %}}</dd>

    <dt class="property-"
            title="">License<wbr>Info<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}License info for your Lambda Layer. See [License Info][3].
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
    <dd>{{% md %}}Used to trigger updates. Must be set to a base64-encoded SHA256 hash of the package file specified with either `filename` or `s3_key`. The usual way to set this is `${filebase64sha256(&#34;file.zip&#34;)}` (this provider 0.11.12 or later) or `${base64sha256(file(&#34;file.zip&#34;))}` (this provider 0.11.11 and earlier), where &#34;file.zip&#34; is the local filename of the lambda layer source archive.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Source<wbr>Code<wbr>Size<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The size in bytes of the function .zip file.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Version<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}This Lamba Layer version.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Amazon Resource Name (ARN) of the Lambda Layer with version.
{{% /md %}}</dd>

    <dt class="property-"
            title="">code<span class="property-indicator"></span>
        <span class="property-type">pulumi.asset.Archive?</span>
    </dt>
    <dd>{{% md %}}The path to the function&#39;s deployment package within the local filesystem. If defined, The `s3_`-prefixed options cannot be used.
{{% /md %}}</dd>

    <dt class="property-"
            title="">compatible<wbr>Runtimes<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}A list of [Runtimes][2] this layer is compatible with. Up to 5 runtimes can be specified.
{{% /md %}}</dd>

    <dt class="property-"
            title="">created<wbr>Date<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The date this resource was created.
{{% /md %}}</dd>

    <dt class="property-"
            title="">description<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Description of what your Lambda Layer does.
{{% /md %}}</dd>

    <dt class="property-"
            title="">layer<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Amazon Resource Name (ARN) of the Lambda Layer without version.
{{% /md %}}</dd>

    <dt class="property-"
            title="">layer<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}A unique name for your Lambda Layer
{{% /md %}}</dd>

    <dt class="property-"
            title="">license<wbr>Info<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}License info for your Lambda Layer. See [License Info][3].
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
    <dd>{{% md %}}Used to trigger updates. Must be set to a base64-encoded SHA256 hash of the package file specified with either `filename` or `s3_key`. The usual way to set this is `${filebase64sha256(&#34;file.zip&#34;)}` (this provider 0.11.12 or later) or `${base64sha256(file(&#34;file.zip&#34;))}` (this provider 0.11.11 and earlier), where &#34;file.zip&#34; is the local filename of the lambda layer source archive.
{{% /md %}}</dd>

    <dt class="property-"
            title="">source<wbr>Code<wbr>Size<span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}The size in bytes of the function .zip file.
{{% /md %}}</dd>

    <dt class="property-"
            title="">version<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}This Lamba Layer version.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The Amazon Resource Name (ARN) of the Lambda Layer with version.
{{% /md %}}</dd>

    <dt class="property-"
            title="">code<span class="property-indicator"></span>
        <span class="property-type">pulumi.Archive</span>
    </dt>
    <dd>{{% md %}}The path to the function&#39;s deployment package within the local filesystem. If defined, The `s3_`-prefixed options cannot be used.
{{% /md %}}</dd>

    <dt class="property-"
            title="">compatible_<wbr>runtimes<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}A list of [Runtimes][2] this layer is compatible with. Up to 5 runtimes can be specified.
{{% /md %}}</dd>

    <dt class="property-"
            title="">created_<wbr>date<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The date this resource was created.
{{% /md %}}</dd>

    <dt class="property-"
            title="">description<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Description of what your Lambda Layer does.
{{% /md %}}</dd>

    <dt class="property-"
            title="">layer_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The Amazon Resource Name (ARN) of the Lambda Layer without version.
{{% /md %}}</dd>

    <dt class="property-"
            title="">layer_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A unique name for your Lambda Layer
{{% /md %}}</dd>

    <dt class="property-"
            title="">license_<wbr>info<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}License info for your Lambda Layer. See [License Info][3].
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
    <dd>{{% md %}}Used to trigger updates. Must be set to a base64-encoded SHA256 hash of the package file specified with either `filename` or `s3_key`. The usual way to set this is `${filebase64sha256(&#34;file.zip&#34;)}` (this provider 0.11.12 or later) or `${base64sha256(file(&#34;file.zip&#34;))}` (this provider 0.11.11 and earlier), where &#34;file.zip&#34; is the local filename of the lambda layer source archive.
{{% /md %}}</dd>

    <dt class="property-"
            title="">source_<wbr>code_<wbr>size<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The size in bytes of the function .zip file.
{{% /md %}}</dd>

    <dt class="property-"
            title="">version<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}This Lamba Layer version.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





## Look up an Existing LayerVersion Resource

{{< chooser language "javascript,typescript,python,go,csharp  " / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">pulumi.Input&lt;pulumi.ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/lambda/#LayerVersionState">LayerVersionState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/lambda/#LayerVersion">LayerVersion</a></span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>arn=None<span class="p">, </span>code=None<span class="p">, </span>compatible_runtimes=None<span class="p">, </span>created_date=None<span class="p">, </span>description=None<span class="p">, </span>layer_arn=None<span class="p">, </span>layer_name=None<span class="p">, </span>license_info=None<span class="p">, </span>s3_bucket=None<span class="p">, </span>s3_key=None<span class="p">, </span>s3_object_version=None<span class="p">, </span>source_code_hash=None<span class="p">, </span>source_code_size=None<span class="p">, </span>version=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetLayerVersion<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">pulumi.IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/lambda?tab=doc#LayerVersionState">LayerVersionState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/lambda?tab=doc#LayerVersion">LayerVersion</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Lambda.LayerVersion.html">LayerVersion</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Pulumi.Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Lambda.LayerVersionState.html">LayerVersionState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
{{% /choosable %}}

Get an existing LayerVersion resource's state with the given name, ID, and optional extra properties used to qualify the lookup.

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
    <dd>{{% md %}}The Amazon Resource Name (ARN) of the Lambda Layer with version.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Code<span class="property-indicator"></span>
        <span class="property-type">Archive?</span>
    </dt>
    <dd>{{% md %}}The path to the function&#39;s deployment package within the local filesystem. If defined, The `s3_`-prefixed options cannot be used.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Compatible<wbr>Runtimes<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}A list of [Runtimes][2] this layer is compatible with. Up to 5 runtimes can be specified.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Created<wbr>Date<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The date this resource was created.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Description<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Description of what your Lambda Layer does.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Layer<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The Amazon Resource Name (ARN) of the Lambda Layer without version.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Layer<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A unique name for your Lambda Layer
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">License<wbr>Info<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}License info for your Lambda Layer. See [License Info][3].
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
    <dd>{{% md %}}Used to trigger updates. Must be set to a base64-encoded SHA256 hash of the package file specified with either `filename` or `s3_key`. The usual way to set this is `${filebase64sha256(&#34;file.zip&#34;)}` (this provider 0.11.12 or later) or `${base64sha256(file(&#34;file.zip&#34;))}` (this provider 0.11.11 and earlier), where &#34;file.zip&#34; is the local filename of the lambda layer source archive.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Source<wbr>Code<wbr>Size<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The size in bytes of the function .zip file.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Version<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}This Lamba Layer version.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The Amazon Resource Name (ARN) of the Lambda Layer with version.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Code<span class="property-indicator"></span>
        <span class="property-type">pulumi.Archive</span>
    </dt>
    <dd>{{% md %}}The path to the function&#39;s deployment package within the local filesystem. If defined, The `s3_`-prefixed options cannot be used.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Compatible<wbr>Runtimes<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}A list of [Runtimes][2] this layer is compatible with. Up to 5 runtimes can be specified.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Created<wbr>Date<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The date this resource was created.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Description<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Description of what your Lambda Layer does.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Layer<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The Amazon Resource Name (ARN) of the Lambda Layer without version.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Layer<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}A unique name for your Lambda Layer
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">License<wbr>Info<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}License info for your Lambda Layer. See [License Info][3].
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
    <dd>{{% md %}}Used to trigger updates. Must be set to a base64-encoded SHA256 hash of the package file specified with either `filename` or `s3_key`. The usual way to set this is `${filebase64sha256(&#34;file.zip&#34;)}` (this provider 0.11.12 or later) or `${base64sha256(file(&#34;file.zip&#34;))}` (this provider 0.11.11 and earlier), where &#34;file.zip&#34; is the local filename of the lambda layer source archive.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Source<wbr>Code<wbr>Size<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The size in bytes of the function .zip file.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Version<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}This Lamba Layer version.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The Amazon Resource Name (ARN) of the Lambda Layer with version.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">code<span class="property-indicator"></span>
        <span class="property-type">pulumi.asset.Archive?</span>
    </dt>
    <dd>{{% md %}}The path to the function&#39;s deployment package within the local filesystem. If defined, The `s3_`-prefixed options cannot be used.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">compatible<wbr>Runtimes<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}A list of [Runtimes][2] this layer is compatible with. Up to 5 runtimes can be specified.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">created<wbr>Date<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The date this resource was created.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">description<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Description of what your Lambda Layer does.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">layer<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The Amazon Resource Name (ARN) of the Lambda Layer without version.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">layer<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A unique name for your Lambda Layer
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">license<wbr>Info<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}License info for your Lambda Layer. See [License Info][3].
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
    <dd>{{% md %}}Used to trigger updates. Must be set to a base64-encoded SHA256 hash of the package file specified with either `filename` or `s3_key`. The usual way to set this is `${filebase64sha256(&#34;file.zip&#34;)}` (this provider 0.11.12 or later) or `${base64sha256(file(&#34;file.zip&#34;))}` (this provider 0.11.11 and earlier), where &#34;file.zip&#34; is the local filename of the lambda layer source archive.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">source<wbr>Code<wbr>Size<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The size in bytes of the function .zip file.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">version<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}This Lamba Layer version.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The Amazon Resource Name (ARN) of the Lambda Layer with version.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">code<span class="property-indicator"></span>
        <span class="property-type">pulumi.Archive</span>
    </dt>
    <dd>{{% md %}}The path to the function&#39;s deployment package within the local filesystem. If defined, The `s3_`-prefixed options cannot be used.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">compatible_<wbr>runtimes<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}A list of [Runtimes][2] this layer is compatible with. Up to 5 runtimes can be specified.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">created_<wbr>date<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The date this resource was created.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">description<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Description of what your Lambda Layer does.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">layer_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The Amazon Resource Name (ARN) of the Lambda Layer without version.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">layer_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A unique name for your Lambda Layer
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">license_<wbr>info<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}License info for your Lambda Layer. See [License Info][3].
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
    <dd>{{% md %}}Used to trigger updates. Must be set to a base64-encoded SHA256 hash of the package file specified with either `filename` or `s3_key`. The usual way to set this is `${filebase64sha256(&#34;file.zip&#34;)}` (this provider 0.11.12 or later) or `${base64sha256(file(&#34;file.zip&#34;))}` (this provider 0.11.11 and earlier), where &#34;file.zip&#34; is the local filename of the lambda layer source archive.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">source_<wbr>code_<wbr>size<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The size in bytes of the function .zip file.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">version<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}This Lamba Layer version.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}







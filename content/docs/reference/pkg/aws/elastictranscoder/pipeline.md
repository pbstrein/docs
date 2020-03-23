
---
title: "Pipeline"
block_external_search_index: true
---

Provides an Elastic Transcoder pipeline resource.

## Example Usage

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const bar = new aws.elastictranscoder.Pipeline("bar", {
    contentConfig: {
        bucket: aws_s3_bucket_content_bucket.bucket,
        storageClass: "Standard",
    },
    inputBucket: aws_s3_bucket_input_bucket.bucket,
    role: aws_iam_role_test_role.arn,
    thumbnailConfig: {
        bucket: aws_s3_bucket_thumb_bucket.bucket,
        storageClass: "Standard",
    },
});
```

> This content is derived from https://github.com/terraform-providers/terraform-provider-aws/blob/master/website/docs/r/elastictranscoder_pipeline.html.markdown.



## Create a Pipeline Resource

{{< chooser language "javascript,typescript,python,go,csharp" / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/elastictranscoder/#Pipeline">Pipeline</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/elastictranscoder/#PipelineArgs">PipelineArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">Pipeline</span><span class="p">(resource_name, opts=None, </span>aws_kms_key_arn=None<span class="p">, </span>content_config=None<span class="p">, </span>content_config_permissions=None<span class="p">, </span>input_bucket=None<span class="p">, </span>name=None<span class="p">, </span>notifications=None<span class="p">, </span>output_bucket=None<span class="p">, </span>role=None<span class="p">, </span>thumbnail_config=None<span class="p">, </span>thumbnail_config_permissions=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewPipeline<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/elastictranscoder?tab=doc#PipelineArgs">PipelineArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/elastictranscoder?tab=doc#Pipeline">Pipeline</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Elastictranscoder.Pipeline.html">Pipeline</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Elastictranscoder.PipelineArgs.html">PipelineArgs</a></span> <span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
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
            title="Optional">Aws<wbr>Kms<wbr>Key<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The AWS Key Management Service (AWS KMS) key that you want to use with this pipeline.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Content<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#pipelinecontentconfig">Pipeline<wbr>Content<wbr>Config<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}The ContentConfig object specifies information about the Amazon S3 bucket in which you want Elastic Transcoder to save transcoded files and playlists. (documented below)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Content<wbr>Config<wbr>Permissions<span class="property-indicator"></span>
        <span class="property-type"><a href="#pipelinecontentconfigpermission">List&lt;Pipeline<wbr>Content<wbr>Config<wbr>Permission<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}The permissions for the `content_config` object. (documented below)
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Input<wbr>Bucket<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Amazon S3 bucket in which you saved the media files that you want to transcode and the graphics that you want to use as watermarks.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the pipeline. Maximum 40 characters
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Notifications<span class="property-indicator"></span>
        <span class="property-type"><a href="#pipelinenotifications">Pipeline<wbr>Notifications<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}The Amazon Simple Notification Service (Amazon SNS) topic that you want to notify to report job status. (documented below)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Output<wbr>Bucket<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The Amazon S3 bucket in which you want Elastic Transcoder to save the transcoded files.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Role<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The IAM Amazon Resource Name (ARN) for the role that you want Elastic Transcoder to use to transcode jobs for this pipeline.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Thumbnail<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#pipelinethumbnailconfig">Pipeline<wbr>Thumbnail<wbr>Config<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}The ThumbnailConfig object specifies information about the Amazon S3 bucket in which you want Elastic Transcoder to save thumbnail files. (documented below)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Thumbnail<wbr>Config<wbr>Permissions<span class="property-indicator"></span>
        <span class="property-type"><a href="#pipelinethumbnailconfigpermission">List&lt;Pipeline<wbr>Thumbnail<wbr>Config<wbr>Permission<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}The permissions for the `thumbnail_config` object. (documented below)
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Aws<wbr>Kms<wbr>Key<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The AWS Key Management Service (AWS KMS) key that you want to use with this pipeline.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Content<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#pipelinecontentconfig">*Pipeline<wbr>Content<wbr>Config</a></span>
    </dt>
    <dd>{{% md %}}The ContentConfig object specifies information about the Amazon S3 bucket in which you want Elastic Transcoder to save transcoded files and playlists. (documented below)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Content<wbr>Config<wbr>Permissions<span class="property-indicator"></span>
        <span class="property-type"><a href="#pipelinecontentconfigpermission">[]Pipeline<wbr>Content<wbr>Config<wbr>Permission</a></span>
    </dt>
    <dd>{{% md %}}The permissions for the `content_config` object. (documented below)
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Input<wbr>Bucket<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Amazon S3 bucket in which you saved the media files that you want to transcode and the graphics that you want to use as watermarks.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name of the pipeline. Maximum 40 characters
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Notifications<span class="property-indicator"></span>
        <span class="property-type"><a href="#pipelinenotifications">*Pipeline<wbr>Notifications</a></span>
    </dt>
    <dd>{{% md %}}The Amazon Simple Notification Service (Amazon SNS) topic that you want to notify to report job status. (documented below)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Output<wbr>Bucket<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The Amazon S3 bucket in which you want Elastic Transcoder to save the transcoded files.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Role<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The IAM Amazon Resource Name (ARN) for the role that you want Elastic Transcoder to use to transcode jobs for this pipeline.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Thumbnail<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#pipelinethumbnailconfig">*Pipeline<wbr>Thumbnail<wbr>Config</a></span>
    </dt>
    <dd>{{% md %}}The ThumbnailConfig object specifies information about the Amazon S3 bucket in which you want Elastic Transcoder to save thumbnail files. (documented below)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Thumbnail<wbr>Config<wbr>Permissions<span class="property-indicator"></span>
        <span class="property-type"><a href="#pipelinethumbnailconfigpermission">[]Pipeline<wbr>Thumbnail<wbr>Config<wbr>Permission</a></span>
    </dt>
    <dd>{{% md %}}The permissions for the `thumbnail_config` object. (documented below)
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">aws<wbr>Kms<wbr>Key<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The AWS Key Management Service (AWS KMS) key that you want to use with this pipeline.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">content<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#pipelinecontentconfig">Pipeline<wbr>Content<wbr>Config?</a></span>
    </dt>
    <dd>{{% md %}}The ContentConfig object specifies information about the Amazon S3 bucket in which you want Elastic Transcoder to save transcoded files and playlists. (documented below)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">content<wbr>Config<wbr>Permissions<span class="property-indicator"></span>
        <span class="property-type"><a href="#pipelinecontentconfigpermission">Pipeline<wbr>Content<wbr>Config<wbr>Permission[]?</a></span>
    </dt>
    <dd>{{% md %}}The permissions for the `content_config` object. (documented below)
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">input<wbr>Bucket<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Amazon S3 bucket in which you saved the media files that you want to transcode and the graphics that you want to use as watermarks.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the pipeline. Maximum 40 characters
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">notifications<span class="property-indicator"></span>
        <span class="property-type"><a href="#pipelinenotifications">Pipeline<wbr>Notifications?</a></span>
    </dt>
    <dd>{{% md %}}The Amazon Simple Notification Service (Amazon SNS) topic that you want to notify to report job status. (documented below)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">output<wbr>Bucket<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The Amazon S3 bucket in which you want Elastic Transcoder to save the transcoded files.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">role<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The IAM Amazon Resource Name (ARN) for the role that you want Elastic Transcoder to use to transcode jobs for this pipeline.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">thumbnail<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#pipelinethumbnailconfig">Pipeline<wbr>Thumbnail<wbr>Config?</a></span>
    </dt>
    <dd>{{% md %}}The ThumbnailConfig object specifies information about the Amazon S3 bucket in which you want Elastic Transcoder to save thumbnail files. (documented below)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">thumbnail<wbr>Config<wbr>Permissions<span class="property-indicator"></span>
        <span class="property-type"><a href="#pipelinethumbnailconfigpermission">Pipeline<wbr>Thumbnail<wbr>Config<wbr>Permission[]?</a></span>
    </dt>
    <dd>{{% md %}}The permissions for the `thumbnail_config` object. (documented below)
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">aws_<wbr>kms_<wbr>key_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The AWS Key Management Service (AWS KMS) key that you want to use with this pipeline.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">content_<wbr>config<span class="property-indicator"></span>
        <span class="property-type"><a href="#pipelinecontentconfig">Dict[Pipeline<wbr>Content<wbr>Config]</a></span>
    </dt>
    <dd>{{% md %}}The ContentConfig object specifies information about the Amazon S3 bucket in which you want Elastic Transcoder to save transcoded files and playlists. (documented below)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">content_<wbr>config_<wbr>permissions<span class="property-indicator"></span>
        <span class="property-type"><a href="#pipelinecontentconfigpermission">List[Pipeline<wbr>Content<wbr>Config<wbr>Permission]</a></span>
    </dt>
    <dd>{{% md %}}The permissions for the `content_config` object. (documented below)
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">input_<wbr>bucket<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The Amazon S3 bucket in which you saved the media files that you want to transcode and the graphics that you want to use as watermarks.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the pipeline. Maximum 40 characters
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">notifications<span class="property-indicator"></span>
        <span class="property-type"><a href="#pipelinenotifications">Dict[Pipeline<wbr>Notifications]</a></span>
    </dt>
    <dd>{{% md %}}The Amazon Simple Notification Service (Amazon SNS) topic that you want to notify to report job status. (documented below)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">output_<wbr>bucket<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The Amazon S3 bucket in which you want Elastic Transcoder to save the transcoded files.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">role<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The IAM Amazon Resource Name (ARN) for the role that you want Elastic Transcoder to use to transcode jobs for this pipeline.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">thumbnail_<wbr>config<span class="property-indicator"></span>
        <span class="property-type"><a href="#pipelinethumbnailconfig">Dict[Pipeline<wbr>Thumbnail<wbr>Config]</a></span>
    </dt>
    <dd>{{% md %}}The ThumbnailConfig object specifies information about the Amazon S3 bucket in which you want Elastic Transcoder to save thumbnail files. (documented below)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">thumbnail_<wbr>config_<wbr>permissions<span class="property-indicator"></span>
        <span class="property-type"><a href="#pipelinethumbnailconfigpermission">List[Pipeline<wbr>Thumbnail<wbr>Config<wbr>Permission]</a></span>
    </dt>
    <dd>{{% md %}}The permissions for the `thumbnail_config` object. (documented below)
{{% /md %}}</dd>

</dl>
{{% /choosable %}}




## Pipeline Output Properties

The following output properties are available:




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">Aws<wbr>Kms<wbr>Key<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The AWS Key Management Service (AWS KMS) key that you want to use with this pipeline.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Content<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#pipelinecontentconfig">Pipeline<wbr>Content<wbr>Config</a></span>
    </dt>
    <dd>{{% md %}}The ContentConfig object specifies information about the Amazon S3 bucket in which you want Elastic Transcoder to save transcoded files and playlists. (documented below)
{{% /md %}}</dd>

    <dt class="property-"
            title="">Content<wbr>Config<wbr>Permissions<span class="property-indicator"></span>
        <span class="property-type"><a href="#pipelinecontentconfigpermission">List&lt;Pipeline<wbr>Content<wbr>Config<wbr>Permission&gt;?</a></span>
    </dt>
    <dd>{{% md %}}The permissions for the `content_config` object. (documented below)
{{% /md %}}</dd>

    <dt class="property-"
            title="">Input<wbr>Bucket<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Amazon S3 bucket in which you saved the media files that you want to transcode and the graphics that you want to use as watermarks.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the pipeline. Maximum 40 characters
{{% /md %}}</dd>

    <dt class="property-"
            title="">Notifications<span class="property-indicator"></span>
        <span class="property-type"><a href="#pipelinenotifications">Pipeline<wbr>Notifications?</a></span>
    </dt>
    <dd>{{% md %}}The Amazon Simple Notification Service (Amazon SNS) topic that you want to notify to report job status. (documented below)
{{% /md %}}</dd>

    <dt class="property-"
            title="">Output<wbr>Bucket<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Amazon S3 bucket in which you want Elastic Transcoder to save the transcoded files.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Role<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The IAM Amazon Resource Name (ARN) for the role that you want Elastic Transcoder to use to transcode jobs for this pipeline.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Thumbnail<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#pipelinethumbnailconfig">Pipeline<wbr>Thumbnail<wbr>Config</a></span>
    </dt>
    <dd>{{% md %}}The ThumbnailConfig object specifies information about the Amazon S3 bucket in which you want Elastic Transcoder to save thumbnail files. (documented below)
{{% /md %}}</dd>

    <dt class="property-"
            title="">Thumbnail<wbr>Config<wbr>Permissions<span class="property-indicator"></span>
        <span class="property-type"><a href="#pipelinethumbnailconfigpermission">List&lt;Pipeline<wbr>Thumbnail<wbr>Config<wbr>Permission&gt;?</a></span>
    </dt>
    <dd>{{% md %}}The permissions for the `thumbnail_config` object. (documented below)
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">Aws<wbr>Kms<wbr>Key<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The AWS Key Management Service (AWS KMS) key that you want to use with this pipeline.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Content<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#pipelinecontentconfig">Pipeline<wbr>Content<wbr>Config</a></span>
    </dt>
    <dd>{{% md %}}The ContentConfig object specifies information about the Amazon S3 bucket in which you want Elastic Transcoder to save transcoded files and playlists. (documented below)
{{% /md %}}</dd>

    <dt class="property-"
            title="">Content<wbr>Config<wbr>Permissions<span class="property-indicator"></span>
        <span class="property-type"><a href="#pipelinecontentconfigpermission">[]Pipeline<wbr>Content<wbr>Config<wbr>Permission</a></span>
    </dt>
    <dd>{{% md %}}The permissions for the `content_config` object. (documented below)
{{% /md %}}</dd>

    <dt class="property-"
            title="">Input<wbr>Bucket<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Amazon S3 bucket in which you saved the media files that you want to transcode and the graphics that you want to use as watermarks.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the pipeline. Maximum 40 characters
{{% /md %}}</dd>

    <dt class="property-"
            title="">Notifications<span class="property-indicator"></span>
        <span class="property-type"><a href="#pipelinenotifications">*Pipeline<wbr>Notifications</a></span>
    </dt>
    <dd>{{% md %}}The Amazon Simple Notification Service (Amazon SNS) topic that you want to notify to report job status. (documented below)
{{% /md %}}</dd>

    <dt class="property-"
            title="">Output<wbr>Bucket<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Amazon S3 bucket in which you want Elastic Transcoder to save the transcoded files.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Role<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The IAM Amazon Resource Name (ARN) for the role that you want Elastic Transcoder to use to transcode jobs for this pipeline.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Thumbnail<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#pipelinethumbnailconfig">Pipeline<wbr>Thumbnail<wbr>Config</a></span>
    </dt>
    <dd>{{% md %}}The ThumbnailConfig object specifies information about the Amazon S3 bucket in which you want Elastic Transcoder to save thumbnail files. (documented below)
{{% /md %}}</dd>

    <dt class="property-"
            title="">Thumbnail<wbr>Config<wbr>Permissions<span class="property-indicator"></span>
        <span class="property-type"><a href="#pipelinethumbnailconfigpermission">[]Pipeline<wbr>Thumbnail<wbr>Config<wbr>Permission</a></span>
    </dt>
    <dd>{{% md %}}The permissions for the `thumbnail_config` object. (documented below)
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">aws<wbr>Kms<wbr>Key<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The AWS Key Management Service (AWS KMS) key that you want to use with this pipeline.
{{% /md %}}</dd>

    <dt class="property-"
            title="">content<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#pipelinecontentconfig">Pipeline<wbr>Content<wbr>Config</a></span>
    </dt>
    <dd>{{% md %}}The ContentConfig object specifies information about the Amazon S3 bucket in which you want Elastic Transcoder to save transcoded files and playlists. (documented below)
{{% /md %}}</dd>

    <dt class="property-"
            title="">content<wbr>Config<wbr>Permissions<span class="property-indicator"></span>
        <span class="property-type"><a href="#pipelinecontentconfigpermission">Pipeline<wbr>Content<wbr>Config<wbr>Permission[]?</a></span>
    </dt>
    <dd>{{% md %}}The permissions for the `content_config` object. (documented below)
{{% /md %}}</dd>

    <dt class="property-"
            title="">input<wbr>Bucket<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Amazon S3 bucket in which you saved the media files that you want to transcode and the graphics that you want to use as watermarks.
{{% /md %}}</dd>

    <dt class="property-"
            title="">name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the pipeline. Maximum 40 characters
{{% /md %}}</dd>

    <dt class="property-"
            title="">notifications<span class="property-indicator"></span>
        <span class="property-type"><a href="#pipelinenotifications">Pipeline<wbr>Notifications?</a></span>
    </dt>
    <dd>{{% md %}}The Amazon Simple Notification Service (Amazon SNS) topic that you want to notify to report job status. (documented below)
{{% /md %}}</dd>

    <dt class="property-"
            title="">output<wbr>Bucket<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Amazon S3 bucket in which you want Elastic Transcoder to save the transcoded files.
{{% /md %}}</dd>

    <dt class="property-"
            title="">role<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The IAM Amazon Resource Name (ARN) for the role that you want Elastic Transcoder to use to transcode jobs for this pipeline.
{{% /md %}}</dd>

    <dt class="property-"
            title="">thumbnail<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#pipelinethumbnailconfig">Pipeline<wbr>Thumbnail<wbr>Config</a></span>
    </dt>
    <dd>{{% md %}}The ThumbnailConfig object specifies information about the Amazon S3 bucket in which you want Elastic Transcoder to save thumbnail files. (documented below)
{{% /md %}}</dd>

    <dt class="property-"
            title="">thumbnail<wbr>Config<wbr>Permissions<span class="property-indicator"></span>
        <span class="property-type"><a href="#pipelinethumbnailconfigpermission">Pipeline<wbr>Thumbnail<wbr>Config<wbr>Permission[]?</a></span>
    </dt>
    <dd>{{% md %}}The permissions for the `thumbnail_config` object. (documented below)
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">aws_<wbr>kms_<wbr>key_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The AWS Key Management Service (AWS KMS) key that you want to use with this pipeline.
{{% /md %}}</dd>

    <dt class="property-"
            title="">content_<wbr>config<span class="property-indicator"></span>
        <span class="property-type"><a href="#pipelinecontentconfig">Dict[Pipeline<wbr>Content<wbr>Config]</a></span>
    </dt>
    <dd>{{% md %}}The ContentConfig object specifies information about the Amazon S3 bucket in which you want Elastic Transcoder to save transcoded files and playlists. (documented below)
{{% /md %}}</dd>

    <dt class="property-"
            title="">content_<wbr>config_<wbr>permissions<span class="property-indicator"></span>
        <span class="property-type"><a href="#pipelinecontentconfigpermission">List[Pipeline<wbr>Content<wbr>Config<wbr>Permission]</a></span>
    </dt>
    <dd>{{% md %}}The permissions for the `content_config` object. (documented below)
{{% /md %}}</dd>

    <dt class="property-"
            title="">input_<wbr>bucket<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The Amazon S3 bucket in which you saved the media files that you want to transcode and the graphics that you want to use as watermarks.
{{% /md %}}</dd>

    <dt class="property-"
            title="">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the pipeline. Maximum 40 characters
{{% /md %}}</dd>

    <dt class="property-"
            title="">notifications<span class="property-indicator"></span>
        <span class="property-type"><a href="#pipelinenotifications">Dict[Pipeline<wbr>Notifications]</a></span>
    </dt>
    <dd>{{% md %}}The Amazon Simple Notification Service (Amazon SNS) topic that you want to notify to report job status. (documented below)
{{% /md %}}</dd>

    <dt class="property-"
            title="">output_<wbr>bucket<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The Amazon S3 bucket in which you want Elastic Transcoder to save the transcoded files.
{{% /md %}}</dd>

    <dt class="property-"
            title="">role<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The IAM Amazon Resource Name (ARN) for the role that you want Elastic Transcoder to use to transcode jobs for this pipeline.
{{% /md %}}</dd>

    <dt class="property-"
            title="">thumbnail_<wbr>config<span class="property-indicator"></span>
        <span class="property-type"><a href="#pipelinethumbnailconfig">Dict[Pipeline<wbr>Thumbnail<wbr>Config]</a></span>
    </dt>
    <dd>{{% md %}}The ThumbnailConfig object specifies information about the Amazon S3 bucket in which you want Elastic Transcoder to save thumbnail files. (documented below)
{{% /md %}}</dd>

    <dt class="property-"
            title="">thumbnail_<wbr>config_<wbr>permissions<span class="property-indicator"></span>
        <span class="property-type"><a href="#pipelinethumbnailconfigpermission">List[Pipeline<wbr>Thumbnail<wbr>Config<wbr>Permission]</a></span>
    </dt>
    <dd>{{% md %}}The permissions for the `thumbnail_config` object. (documented below)
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





## Look up an Existing Pipeline Resource

{{< chooser language "javascript,typescript,python,go,csharp  " / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">pulumi.Input&lt;pulumi.ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/elastictranscoder/#PipelineState">PipelineState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/elastictranscoder/#Pipeline">Pipeline</a></span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>arn=None<span class="p">, </span>aws_kms_key_arn=None<span class="p">, </span>content_config=None<span class="p">, </span>content_config_permissions=None<span class="p">, </span>input_bucket=None<span class="p">, </span>name=None<span class="p">, </span>notifications=None<span class="p">, </span>output_bucket=None<span class="p">, </span>role=None<span class="p">, </span>thumbnail_config=None<span class="p">, </span>thumbnail_config_permissions=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetPipeline<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">pulumi.IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/elastictranscoder?tab=doc#PipelineState">PipelineState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/elastictranscoder?tab=doc#Pipeline">Pipeline</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Elastictranscoder.Pipeline.html">Pipeline</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Pulumi.Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Elastictranscoder.PipelineState.html">PipelineState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
{{% /choosable %}}

Get an existing Pipeline resource's state with the given name, ID, and optional extra properties used to qualify the lookup.

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
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Aws<wbr>Kms<wbr>Key<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The AWS Key Management Service (AWS KMS) key that you want to use with this pipeline.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Content<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#pipelinecontentconfig">Pipeline<wbr>Content<wbr>Config<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}The ContentConfig object specifies information about the Amazon S3 bucket in which you want Elastic Transcoder to save transcoded files and playlists. (documented below)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Content<wbr>Config<wbr>Permissions<span class="property-indicator"></span>
        <span class="property-type"><a href="#pipelinecontentconfigpermission">List&lt;Pipeline<wbr>Content<wbr>Config<wbr>Permission<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}The permissions for the `content_config` object. (documented below)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Input<wbr>Bucket<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The Amazon S3 bucket in which you saved the media files that you want to transcode and the graphics that you want to use as watermarks.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the pipeline. Maximum 40 characters
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Notifications<span class="property-indicator"></span>
        <span class="property-type"><a href="#pipelinenotifications">Pipeline<wbr>Notifications<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}The Amazon Simple Notification Service (Amazon SNS) topic that you want to notify to report job status. (documented below)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Output<wbr>Bucket<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The Amazon S3 bucket in which you want Elastic Transcoder to save the transcoded files.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Role<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The IAM Amazon Resource Name (ARN) for the role that you want Elastic Transcoder to use to transcode jobs for this pipeline.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Thumbnail<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#pipelinethumbnailconfig">Pipeline<wbr>Thumbnail<wbr>Config<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}The ThumbnailConfig object specifies information about the Amazon S3 bucket in which you want Elastic Transcoder to save thumbnail files. (documented below)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Thumbnail<wbr>Config<wbr>Permissions<span class="property-indicator"></span>
        <span class="property-type"><a href="#pipelinethumbnailconfigpermission">List&lt;Pipeline<wbr>Thumbnail<wbr>Config<wbr>Permission<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}The permissions for the `thumbnail_config` object. (documented below)
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Aws<wbr>Kms<wbr>Key<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The AWS Key Management Service (AWS KMS) key that you want to use with this pipeline.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Content<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#pipelinecontentconfig">*Pipeline<wbr>Content<wbr>Config</a></span>
    </dt>
    <dd>{{% md %}}The ContentConfig object specifies information about the Amazon S3 bucket in which you want Elastic Transcoder to save transcoded files and playlists. (documented below)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Content<wbr>Config<wbr>Permissions<span class="property-indicator"></span>
        <span class="property-type"><a href="#pipelinecontentconfigpermission">[]Pipeline<wbr>Content<wbr>Config<wbr>Permission</a></span>
    </dt>
    <dd>{{% md %}}The permissions for the `content_config` object. (documented below)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Input<wbr>Bucket<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The Amazon S3 bucket in which you saved the media files that you want to transcode and the graphics that you want to use as watermarks.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name of the pipeline. Maximum 40 characters
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Notifications<span class="property-indicator"></span>
        <span class="property-type"><a href="#pipelinenotifications">*Pipeline<wbr>Notifications</a></span>
    </dt>
    <dd>{{% md %}}The Amazon Simple Notification Service (Amazon SNS) topic that you want to notify to report job status. (documented below)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Output<wbr>Bucket<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The Amazon S3 bucket in which you want Elastic Transcoder to save the transcoded files.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Role<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The IAM Amazon Resource Name (ARN) for the role that you want Elastic Transcoder to use to transcode jobs for this pipeline.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Thumbnail<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#pipelinethumbnailconfig">*Pipeline<wbr>Thumbnail<wbr>Config</a></span>
    </dt>
    <dd>{{% md %}}The ThumbnailConfig object specifies information about the Amazon S3 bucket in which you want Elastic Transcoder to save thumbnail files. (documented below)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Thumbnail<wbr>Config<wbr>Permissions<span class="property-indicator"></span>
        <span class="property-type"><a href="#pipelinethumbnailconfigpermission">[]Pipeline<wbr>Thumbnail<wbr>Config<wbr>Permission</a></span>
    </dt>
    <dd>{{% md %}}The permissions for the `thumbnail_config` object. (documented below)
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">aws<wbr>Kms<wbr>Key<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The AWS Key Management Service (AWS KMS) key that you want to use with this pipeline.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">content<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#pipelinecontentconfig">Pipeline<wbr>Content<wbr>Config?</a></span>
    </dt>
    <dd>{{% md %}}The ContentConfig object specifies information about the Amazon S3 bucket in which you want Elastic Transcoder to save transcoded files and playlists. (documented below)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">content<wbr>Config<wbr>Permissions<span class="property-indicator"></span>
        <span class="property-type"><a href="#pipelinecontentconfigpermission">Pipeline<wbr>Content<wbr>Config<wbr>Permission[]?</a></span>
    </dt>
    <dd>{{% md %}}The permissions for the `content_config` object. (documented below)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">input<wbr>Bucket<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The Amazon S3 bucket in which you saved the media files that you want to transcode and the graphics that you want to use as watermarks.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the pipeline. Maximum 40 characters
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">notifications<span class="property-indicator"></span>
        <span class="property-type"><a href="#pipelinenotifications">Pipeline<wbr>Notifications?</a></span>
    </dt>
    <dd>{{% md %}}The Amazon Simple Notification Service (Amazon SNS) topic that you want to notify to report job status. (documented below)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">output<wbr>Bucket<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The Amazon S3 bucket in which you want Elastic Transcoder to save the transcoded files.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">role<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The IAM Amazon Resource Name (ARN) for the role that you want Elastic Transcoder to use to transcode jobs for this pipeline.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">thumbnail<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#pipelinethumbnailconfig">Pipeline<wbr>Thumbnail<wbr>Config?</a></span>
    </dt>
    <dd>{{% md %}}The ThumbnailConfig object specifies information about the Amazon S3 bucket in which you want Elastic Transcoder to save thumbnail files. (documented below)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">thumbnail<wbr>Config<wbr>Permissions<span class="property-indicator"></span>
        <span class="property-type"><a href="#pipelinethumbnailconfigpermission">Pipeline<wbr>Thumbnail<wbr>Config<wbr>Permission[]?</a></span>
    </dt>
    <dd>{{% md %}}The permissions for the `thumbnail_config` object. (documented below)
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">aws_<wbr>kms_<wbr>key_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The AWS Key Management Service (AWS KMS) key that you want to use with this pipeline.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">content_<wbr>config<span class="property-indicator"></span>
        <span class="property-type"><a href="#pipelinecontentconfig">Dict[Pipeline<wbr>Content<wbr>Config]</a></span>
    </dt>
    <dd>{{% md %}}The ContentConfig object specifies information about the Amazon S3 bucket in which you want Elastic Transcoder to save transcoded files and playlists. (documented below)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">content_<wbr>config_<wbr>permissions<span class="property-indicator"></span>
        <span class="property-type"><a href="#pipelinecontentconfigpermission">List[Pipeline<wbr>Content<wbr>Config<wbr>Permission]</a></span>
    </dt>
    <dd>{{% md %}}The permissions for the `content_config` object. (documented below)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">input_<wbr>bucket<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The Amazon S3 bucket in which you saved the media files that you want to transcode and the graphics that you want to use as watermarks.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the pipeline. Maximum 40 characters
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">notifications<span class="property-indicator"></span>
        <span class="property-type"><a href="#pipelinenotifications">Dict[Pipeline<wbr>Notifications]</a></span>
    </dt>
    <dd>{{% md %}}The Amazon Simple Notification Service (Amazon SNS) topic that you want to notify to report job status. (documented below)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">output_<wbr>bucket<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The Amazon S3 bucket in which you want Elastic Transcoder to save the transcoded files.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">role<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The IAM Amazon Resource Name (ARN) for the role that you want Elastic Transcoder to use to transcode jobs for this pipeline.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">thumbnail_<wbr>config<span class="property-indicator"></span>
        <span class="property-type"><a href="#pipelinethumbnailconfig">Dict[Pipeline<wbr>Thumbnail<wbr>Config]</a></span>
    </dt>
    <dd>{{% md %}}The ThumbnailConfig object specifies information about the Amazon S3 bucket in which you want Elastic Transcoder to save thumbnail files. (documented below)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">thumbnail_<wbr>config_<wbr>permissions<span class="property-indicator"></span>
        <span class="property-type"><a href="#pipelinethumbnailconfigpermission">List[Pipeline<wbr>Thumbnail<wbr>Config<wbr>Permission]</a></span>
    </dt>
    <dd>{{% md %}}The permissions for the `thumbnail_config` object. (documented below)
{{% /md %}}</dd>

</dl>
{{% /choosable %}}







## Supporting Types

#### PipelineContentConfig
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#PipelineContentConfig">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#PipelineContentConfig">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/elastictranscoder?tab=doc#PipelineContentConfigArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/elastictranscoder?tab=doc#PipelineContentConfigOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Elastictranscoder.PipelineContentConfigArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Elastictranscoder.PipelineContentConfig.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Bucket<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The Amazon S3 bucket in which you want Elastic Transcoder to save thumbnail files.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Storage<wbr>Class<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The Amazon S3 storage class, Standard or ReducedRedundancy, that you want Elastic Transcoder to assign to the thumbnails that it stores in your Amazon S3 bucket.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Bucket<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The Amazon S3 bucket in which you want Elastic Transcoder to save thumbnail files.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Storage<wbr>Class<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The Amazon S3 storage class, Standard or ReducedRedundancy, that you want Elastic Transcoder to assign to the thumbnails that it stores in your Amazon S3 bucket.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">bucket<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The Amazon S3 bucket in which you want Elastic Transcoder to save thumbnail files.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">storage<wbr>Class<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The Amazon S3 storage class, Standard or ReducedRedundancy, that you want Elastic Transcoder to assign to the thumbnails that it stores in your Amazon S3 bucket.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">bucket<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The Amazon S3 bucket in which you want Elastic Transcoder to save thumbnail files.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">storage_<wbr>class<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The Amazon S3 storage class, Standard or ReducedRedundancy, that you want Elastic Transcoder to assign to the thumbnails that it stores in your Amazon S3 bucket.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### PipelineContentConfigPermission
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#PipelineContentConfigPermission">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#PipelineContentConfigPermission">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/elastictranscoder?tab=doc#PipelineContentConfigPermissionArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/elastictranscoder?tab=doc#PipelineContentConfigPermissionOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Elastictranscoder.PipelineContentConfigPermissionArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Elastictranscoder.PipelineContentConfigPermission.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Accesses<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}The permission that you want to give to the AWS user that you specified in `thumbnail_config_permissions.grantee`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Grantee<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The AWS user or group that you want to have access to thumbnail files.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Grantee<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Specify the type of value that appears in the `thumbnail_config_permissions.grantee` object.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Accesses<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}The permission that you want to give to the AWS user that you specified in `thumbnail_config_permissions.grantee`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Grantee<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The AWS user or group that you want to have access to thumbnail files.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Grantee<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Specify the type of value that appears in the `thumbnail_config_permissions.grantee` object.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">accesses<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}The permission that you want to give to the AWS user that you specified in `thumbnail_config_permissions.grantee`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">grantee<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The AWS user or group that you want to have access to thumbnail files.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">grantee<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Specify the type of value that appears in the `thumbnail_config_permissions.grantee` object.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">accesses<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}The permission that you want to give to the AWS user that you specified in `thumbnail_config_permissions.grantee`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">grantee<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The AWS user or group that you want to have access to thumbnail files.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">grantee<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Specify the type of value that appears in the `thumbnail_config_permissions.grantee` object.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### PipelineNotifications
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#PipelineNotifications">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#PipelineNotifications">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/elastictranscoder?tab=doc#PipelineNotificationsArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/elastictranscoder?tab=doc#PipelineNotificationsOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Elastictranscoder.PipelineNotificationsArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Elastictranscoder.PipelineNotifications.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Completed<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The topic ARN for the Amazon SNS topic that you want to notify when Elastic Transcoder has finished processing a job in this pipeline.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Error<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The topic ARN for the Amazon SNS topic that you want to notify when Elastic Transcoder encounters an error condition while processing a job in this pipeline.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Progressing<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The topic ARN for the Amazon Simple Notification Service (Amazon SNS) topic that you want to notify when Elastic Transcoder has started to process a job in this pipeline.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Warning<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The topic ARN for the Amazon SNS topic that you want to notify when Elastic Transcoder encounters a warning condition while processing a job in this pipeline.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Completed<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The topic ARN for the Amazon SNS topic that you want to notify when Elastic Transcoder has finished processing a job in this pipeline.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Error<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The topic ARN for the Amazon SNS topic that you want to notify when Elastic Transcoder encounters an error condition while processing a job in this pipeline.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Progressing<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The topic ARN for the Amazon Simple Notification Service (Amazon SNS) topic that you want to notify when Elastic Transcoder has started to process a job in this pipeline.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Warning<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The topic ARN for the Amazon SNS topic that you want to notify when Elastic Transcoder encounters a warning condition while processing a job in this pipeline.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">completed<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The topic ARN for the Amazon SNS topic that you want to notify when Elastic Transcoder has finished processing a job in this pipeline.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">error<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The topic ARN for the Amazon SNS topic that you want to notify when Elastic Transcoder encounters an error condition while processing a job in this pipeline.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">progressing<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The topic ARN for the Amazon Simple Notification Service (Amazon SNS) topic that you want to notify when Elastic Transcoder has started to process a job in this pipeline.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">warning<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The topic ARN for the Amazon SNS topic that you want to notify when Elastic Transcoder encounters a warning condition while processing a job in this pipeline.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">completed<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The topic ARN for the Amazon SNS topic that you want to notify when Elastic Transcoder has finished processing a job in this pipeline.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">error<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The topic ARN for the Amazon SNS topic that you want to notify when Elastic Transcoder encounters an error condition while processing a job in this pipeline.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">progressing<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The topic ARN for the Amazon Simple Notification Service (Amazon SNS) topic that you want to notify when Elastic Transcoder has started to process a job in this pipeline.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">warning<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The topic ARN for the Amazon SNS topic that you want to notify when Elastic Transcoder encounters a warning condition while processing a job in this pipeline.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### PipelineThumbnailConfig
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#PipelineThumbnailConfig">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#PipelineThumbnailConfig">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/elastictranscoder?tab=doc#PipelineThumbnailConfigArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/elastictranscoder?tab=doc#PipelineThumbnailConfigOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Elastictranscoder.PipelineThumbnailConfigArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Elastictranscoder.PipelineThumbnailConfig.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Bucket<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The Amazon S3 bucket in which you want Elastic Transcoder to save thumbnail files.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Storage<wbr>Class<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The Amazon S3 storage class, Standard or ReducedRedundancy, that you want Elastic Transcoder to assign to the thumbnails that it stores in your Amazon S3 bucket.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Bucket<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The Amazon S3 bucket in which you want Elastic Transcoder to save thumbnail files.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Storage<wbr>Class<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The Amazon S3 storage class, Standard or ReducedRedundancy, that you want Elastic Transcoder to assign to the thumbnails that it stores in your Amazon S3 bucket.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">bucket<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The Amazon S3 bucket in which you want Elastic Transcoder to save thumbnail files.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">storage<wbr>Class<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The Amazon S3 storage class, Standard or ReducedRedundancy, that you want Elastic Transcoder to assign to the thumbnails that it stores in your Amazon S3 bucket.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">bucket<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The Amazon S3 bucket in which you want Elastic Transcoder to save thumbnail files.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">storage_<wbr>class<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The Amazon S3 storage class, Standard or ReducedRedundancy, that you want Elastic Transcoder to assign to the thumbnails that it stores in your Amazon S3 bucket.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### PipelineThumbnailConfigPermission
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#PipelineThumbnailConfigPermission">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#PipelineThumbnailConfigPermission">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/elastictranscoder?tab=doc#PipelineThumbnailConfigPermissionArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/elastictranscoder?tab=doc#PipelineThumbnailConfigPermissionOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Elastictranscoder.PipelineThumbnailConfigPermissionArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Elastictranscoder.PipelineThumbnailConfigPermission.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Accesses<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}The permission that you want to give to the AWS user that you specified in `thumbnail_config_permissions.grantee`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Grantee<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The AWS user or group that you want to have access to thumbnail files.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Grantee<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Specify the type of value that appears in the `thumbnail_config_permissions.grantee` object.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Accesses<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}The permission that you want to give to the AWS user that you specified in `thumbnail_config_permissions.grantee`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Grantee<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The AWS user or group that you want to have access to thumbnail files.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Grantee<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Specify the type of value that appears in the `thumbnail_config_permissions.grantee` object.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">accesses<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}The permission that you want to give to the AWS user that you specified in `thumbnail_config_permissions.grantee`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">grantee<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The AWS user or group that you want to have access to thumbnail files.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">grantee<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Specify the type of value that appears in the `thumbnail_config_permissions.grantee` object.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">accesses<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}The permission that you want to give to the AWS user that you specified in `thumbnail_config_permissions.grantee`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">grantee<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The AWS user or group that you want to have access to thumbnail files.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">grantee<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Specify the type of value that appears in the `thumbnail_config_permissions.grantee` object.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}









---
title: "S3BucketAssociation"
block_external_search_index: true
---

Associates an S3 resource with Amazon Macie for monitoring and data classification.

> **NOTE:** Before using Amazon Macie for the first time it must be enabled manually. Instructions are [here](https://docs.aws.amazon.com/macie/latest/userguide/macie-setting-up.html#macie-setting-up-enable).

## Example Usage

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const example = new aws.macie.S3BucketAssociation("example", {
    bucketName: "tf-macie-example",
    classificationType: {
        oneTime: "FULL",
    },
    prefix: "data",
});
```

> This content is derived from https://github.com/terraform-providers/terraform-provider-aws/blob/master/website/docs/r/macie_s3_bucket_association.html.markdown.



## Create a S3BucketAssociation Resource

{{< chooser language "javascript,typescript,python,go,csharp" / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/macie/#S3BucketAssociation">S3BucketAssociation</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/macie/#S3BucketAssociationArgs">S3BucketAssociationArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">S3BucketAssociation</span><span class="p">(resource_name, opts=None, </span>bucket_name=None<span class="p">, </span>classification_type=None<span class="p">, </span>member_account_id=None<span class="p">, </span>prefix=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewS3BucketAssociation<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/macie?tab=doc#S3BucketAssociationArgs">S3BucketAssociationArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/macie?tab=doc#S3BucketAssociation">S3BucketAssociation</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Macie.S3BucketAssociation.html">S3BucketAssociation</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Macie.S3BucketAssociationArgs.html">S3BucketAssociationArgs</a></span> <span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
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
            title="Required">Bucket<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the S3 bucket that you want to associate with Amazon Macie.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Classification<wbr>Type<span class="property-indicator"></span>
        <span class="property-type"><a href="#s3bucketassociationclassificationtype">S3Bucket<wbr>Association<wbr>Classification<wbr>Type<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}The configuration of how Amazon Macie classifies the S3 objects.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Member<wbr>Account<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ID of the Amazon Macie member account whose S3 resources you want to associate with Macie. If `member_account_id` isn&#39;t specified, the action associates specified S3 resources with Macie for the current master account.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Prefix<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Object key prefix identifying one or more S3 objects to which the association applies.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Bucket<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the S3 bucket that you want to associate with Amazon Macie.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Classification<wbr>Type<span class="property-indicator"></span>
        <span class="property-type"><a href="#s3bucketassociationclassificationtype">*S3Bucket<wbr>Association<wbr>Classification<wbr>Type</a></span>
    </dt>
    <dd>{{% md %}}The configuration of how Amazon Macie classifies the S3 objects.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Member<wbr>Account<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The ID of the Amazon Macie member account whose S3 resources you want to associate with Macie. If `member_account_id` isn&#39;t specified, the action associates specified S3 resources with Macie for the current master account.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Prefix<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Object key prefix identifying one or more S3 objects to which the association applies.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">bucket<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the S3 bucket that you want to associate with Amazon Macie.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">classification<wbr>Type<span class="property-indicator"></span>
        <span class="property-type"><a href="#s3bucketassociationclassificationtype">S3Bucket<wbr>Association<wbr>Classification<wbr>Type?</a></span>
    </dt>
    <dd>{{% md %}}The configuration of how Amazon Macie classifies the S3 objects.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">member<wbr>Account<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ID of the Amazon Macie member account whose S3 resources you want to associate with Macie. If `member_account_id` isn&#39;t specified, the action associates specified S3 resources with Macie for the current master account.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">prefix<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Object key prefix identifying one or more S3 objects to which the association applies.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">bucket_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the S3 bucket that you want to associate with Amazon Macie.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">classification_<wbr>type<span class="property-indicator"></span>
        <span class="property-type"><a href="#s3bucketassociationclassificationtype">Dict[S3Bucket<wbr>Association<wbr>Classification<wbr>Type]</a></span>
    </dt>
    <dd>{{% md %}}The configuration of how Amazon Macie classifies the S3 objects.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">member_<wbr>account_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ID of the Amazon Macie member account whose S3 resources you want to associate with Macie. If `member_account_id` isn&#39;t specified, the action associates specified S3 resources with Macie for the current master account.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">prefix<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Object key prefix identifying one or more S3 objects to which the association applies.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}




## S3BucketAssociation Output Properties

The following output properties are available:




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Bucket<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the S3 bucket that you want to associate with Amazon Macie.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Classification<wbr>Type<span class="property-indicator"></span>
        <span class="property-type"><a href="#s3bucketassociationclassificationtype">S3Bucket<wbr>Association<wbr>Classification<wbr>Type</a></span>
    </dt>
    <dd>{{% md %}}The configuration of how Amazon Macie classifies the S3 objects.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Member<wbr>Account<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ID of the Amazon Macie member account whose S3 resources you want to associate with Macie. If `member_account_id` isn&#39;t specified, the action associates specified S3 resources with Macie for the current master account.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Prefix<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Object key prefix identifying one or more S3 objects to which the association applies.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Bucket<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the S3 bucket that you want to associate with Amazon Macie.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Classification<wbr>Type<span class="property-indicator"></span>
        <span class="property-type"><a href="#s3bucketassociationclassificationtype">S3Bucket<wbr>Association<wbr>Classification<wbr>Type</a></span>
    </dt>
    <dd>{{% md %}}The configuration of how Amazon Macie classifies the S3 objects.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Member<wbr>Account<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The ID of the Amazon Macie member account whose S3 resources you want to associate with Macie. If `member_account_id` isn&#39;t specified, the action associates specified S3 resources with Macie for the current master account.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Prefix<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Object key prefix identifying one or more S3 objects to which the association applies.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">bucket<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the S3 bucket that you want to associate with Amazon Macie.
{{% /md %}}</dd>

    <dt class="property-"
            title="">classification<wbr>Type<span class="property-indicator"></span>
        <span class="property-type"><a href="#s3bucketassociationclassificationtype">S3Bucket<wbr>Association<wbr>Classification<wbr>Type</a></span>
    </dt>
    <dd>{{% md %}}The configuration of how Amazon Macie classifies the S3 objects.
{{% /md %}}</dd>

    <dt class="property-"
            title="">member<wbr>Account<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ID of the Amazon Macie member account whose S3 resources you want to associate with Macie. If `member_account_id` isn&#39;t specified, the action associates specified S3 resources with Macie for the current master account.
{{% /md %}}</dd>

    <dt class="property-"
            title="">prefix<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Object key prefix identifying one or more S3 objects to which the association applies.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">bucket_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the S3 bucket that you want to associate with Amazon Macie.
{{% /md %}}</dd>

    <dt class="property-"
            title="">classification_<wbr>type<span class="property-indicator"></span>
        <span class="property-type"><a href="#s3bucketassociationclassificationtype">Dict[S3Bucket<wbr>Association<wbr>Classification<wbr>Type]</a></span>
    </dt>
    <dd>{{% md %}}The configuration of how Amazon Macie classifies the S3 objects.
{{% /md %}}</dd>

    <dt class="property-"
            title="">member_<wbr>account_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ID of the Amazon Macie member account whose S3 resources you want to associate with Macie. If `member_account_id` isn&#39;t specified, the action associates specified S3 resources with Macie for the current master account.
{{% /md %}}</dd>

    <dt class="property-"
            title="">prefix<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Object key prefix identifying one or more S3 objects to which the association applies.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





## Look up an Existing S3BucketAssociation Resource

{{< chooser language "javascript,typescript,python,go,csharp  " / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">pulumi.Input&lt;pulumi.ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/macie/#S3BucketAssociationState">S3BucketAssociationState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/macie/#S3BucketAssociation">S3BucketAssociation</a></span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>bucket_name=None<span class="p">, </span>classification_type=None<span class="p">, </span>member_account_id=None<span class="p">, </span>prefix=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetS3BucketAssociation<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">pulumi.IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/macie?tab=doc#S3BucketAssociationState">S3BucketAssociationState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/macie?tab=doc#S3BucketAssociation">S3BucketAssociation</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Macie.S3BucketAssociation.html">S3BucketAssociation</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Pulumi.Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Macie.S3BucketAssociationState.html">S3BucketAssociationState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
{{% /choosable %}}

Get an existing S3BucketAssociation resource's state with the given name, ID, and optional extra properties used to qualify the lookup.

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
            title="Optional">Bucket<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the S3 bucket that you want to associate with Amazon Macie.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Classification<wbr>Type<span class="property-indicator"></span>
        <span class="property-type"><a href="#s3bucketassociationclassificationtype">S3Bucket<wbr>Association<wbr>Classification<wbr>Type<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}The configuration of how Amazon Macie classifies the S3 objects.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Member<wbr>Account<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ID of the Amazon Macie member account whose S3 resources you want to associate with Macie. If `member_account_id` isn&#39;t specified, the action associates specified S3 resources with Macie for the current master account.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Prefix<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Object key prefix identifying one or more S3 objects to which the association applies.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Bucket<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name of the S3 bucket that you want to associate with Amazon Macie.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Classification<wbr>Type<span class="property-indicator"></span>
        <span class="property-type"><a href="#s3bucketassociationclassificationtype">*S3Bucket<wbr>Association<wbr>Classification<wbr>Type</a></span>
    </dt>
    <dd>{{% md %}}The configuration of how Amazon Macie classifies the S3 objects.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Member<wbr>Account<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The ID of the Amazon Macie member account whose S3 resources you want to associate with Macie. If `member_account_id` isn&#39;t specified, the action associates specified S3 resources with Macie for the current master account.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Prefix<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Object key prefix identifying one or more S3 objects to which the association applies.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">bucket<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the S3 bucket that you want to associate with Amazon Macie.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">classification<wbr>Type<span class="property-indicator"></span>
        <span class="property-type"><a href="#s3bucketassociationclassificationtype">S3Bucket<wbr>Association<wbr>Classification<wbr>Type?</a></span>
    </dt>
    <dd>{{% md %}}The configuration of how Amazon Macie classifies the S3 objects.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">member<wbr>Account<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ID of the Amazon Macie member account whose S3 resources you want to associate with Macie. If `member_account_id` isn&#39;t specified, the action associates specified S3 resources with Macie for the current master account.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">prefix<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Object key prefix identifying one or more S3 objects to which the association applies.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">bucket_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the S3 bucket that you want to associate with Amazon Macie.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">classification_<wbr>type<span class="property-indicator"></span>
        <span class="property-type"><a href="#s3bucketassociationclassificationtype">Dict[S3Bucket<wbr>Association<wbr>Classification<wbr>Type]</a></span>
    </dt>
    <dd>{{% md %}}The configuration of how Amazon Macie classifies the S3 objects.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">member_<wbr>account_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ID of the Amazon Macie member account whose S3 resources you want to associate with Macie. If `member_account_id` isn&#39;t specified, the action associates specified S3 resources with Macie for the current master account.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">prefix<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Object key prefix identifying one or more S3 objects to which the association applies.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}







## Supporting Types

#### S3BucketAssociationClassificationType
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#S3BucketAssociationClassificationType">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#S3BucketAssociationClassificationType">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/macie?tab=doc#S3BucketAssociationClassificationTypeArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/macie?tab=doc#S3BucketAssociationClassificationTypeOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Macie.S3BucketAssociationClassificationTypeArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Macie.S3BucketAssociationClassificationType.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Continuous<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A string value indicating that Macie perform a one-time classification of all of the existing objects in the bucket.
The only valid value is the default value, `FULL`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">One<wbr>Time<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A string value indicating whether or not Macie performs a one-time classification of all of the existing objects in the bucket.
Valid values are `NONE` and `FULL`. Defaults to `NONE` indicating that Macie only classifies objects that are added after the association was created.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Continuous<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}A string value indicating that Macie perform a one-time classification of all of the existing objects in the bucket.
The only valid value is the default value, `FULL`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">One<wbr>Time<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}A string value indicating whether or not Macie performs a one-time classification of all of the existing objects in the bucket.
Valid values are `NONE` and `FULL`. Defaults to `NONE` indicating that Macie only classifies objects that are added after the association was created.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">continuous<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A string value indicating that Macie perform a one-time classification of all of the existing objects in the bucket.
The only valid value is the default value, `FULL`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">one<wbr>Time<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A string value indicating whether or not Macie performs a one-time classification of all of the existing objects in the bucket.
Valid values are `NONE` and `FULL`. Defaults to `NONE` indicating that Macie only classifies objects that are added after the association was created.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">continuous<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A string value indicating that Macie perform a one-time classification of all of the existing objects in the bucket.
The only valid value is the default value, `FULL`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">one<wbr>Time<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A string value indicating whether or not Macie performs a one-time classification of all of the existing objects in the bucket.
Valid values are `NONE` and `FULL`. Defaults to `NONE` indicating that Macie only classifies objects that are added after the association was created.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}








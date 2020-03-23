
---
title: "AccessPoint"
block_external_search_index: true
---




## Create a AccessPoint Resource

{{< chooser language "javascript,typescript,python,go,csharp" / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/s3/#AccessPoint">AccessPoint</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/s3/#AccessPointArgs">AccessPointArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">AccessPoint</span><span class="p">(resource_name, opts=None, </span>account_id=None<span class="p">, </span>bucket=None<span class="p">, </span>name=None<span class="p">, </span>policy=None<span class="p">, </span>public_access_block_configuration=None<span class="p">, </span>vpc_configuration=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewAccessPoint<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/s3?tab=doc#AccessPointArgs">AccessPointArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/s3?tab=doc#AccessPoint">AccessPoint</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.S3.AccessPoint.html">AccessPoint</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.S3.AccessPointArgs.html">AccessPointArgs</a></span> <span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
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
            title="Optional">Account<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Bucket<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the bucket that you want to associate this access point with.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name you want to assign to this access point.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Policy<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A valid JSON document that specifies the policy that you want to apply to this access point.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Public<wbr>Access<wbr>Block<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#accesspointpublicaccessblockconfiguration">Access<wbr>Point<wbr>Public<wbr>Access<wbr>Block<wbr>Configuration<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}Configuration block to manage the `PublicAccessBlock` configuration that you want to apply to this Amazon S3 bucket. You can enable the configuration options in any combination. Detailed below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Vpc<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#accesspointvpcconfiguration">Access<wbr>Point<wbr>Vpc<wbr>Configuration<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}Configuration block to restrict access to this access point to requests from the specified Virtual Private Cloud (VPC). Detailed below.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Account<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Bucket<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the bucket that you want to associate this access point with.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name you want to assign to this access point.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Policy<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}A valid JSON document that specifies the policy that you want to apply to this access point.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Public<wbr>Access<wbr>Block<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#accesspointpublicaccessblockconfiguration">*Access<wbr>Point<wbr>Public<wbr>Access<wbr>Block<wbr>Configuration</a></span>
    </dt>
    <dd>{{% md %}}Configuration block to manage the `PublicAccessBlock` configuration that you want to apply to this Amazon S3 bucket. You can enable the configuration options in any combination. Detailed below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Vpc<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#accesspointvpcconfiguration">*Access<wbr>Point<wbr>Vpc<wbr>Configuration</a></span>
    </dt>
    <dd>{{% md %}}Configuration block to restrict access to this access point to requests from the specified Virtual Private Cloud (VPC). Detailed below.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">account<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">bucket<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the bucket that you want to associate this access point with.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name you want to assign to this access point.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">policy<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A valid JSON document that specifies the policy that you want to apply to this access point.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">public<wbr>Access<wbr>Block<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#accesspointpublicaccessblockconfiguration">Access<wbr>Point<wbr>Public<wbr>Access<wbr>Block<wbr>Configuration?</a></span>
    </dt>
    <dd>{{% md %}}Configuration block to manage the `PublicAccessBlock` configuration that you want to apply to this Amazon S3 bucket. You can enable the configuration options in any combination. Detailed below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">vpc<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#accesspointvpcconfiguration">Access<wbr>Point<wbr>Vpc<wbr>Configuration?</a></span>
    </dt>
    <dd>{{% md %}}Configuration block to restrict access to this access point to requests from the specified Virtual Private Cloud (VPC). Detailed below.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">account_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">bucket<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the bucket that you want to associate this access point with.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name you want to assign to this access point.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">policy<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A valid JSON document that specifies the policy that you want to apply to this access point.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">public_<wbr>access_<wbr>block_<wbr>configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#accesspointpublicaccessblockconfiguration">Dict[Access<wbr>Point<wbr>Public<wbr>Access<wbr>Block<wbr>Configuration]</a></span>
    </dt>
    <dd>{{% md %}}Configuration block to manage the `PublicAccessBlock` configuration that you want to apply to this Amazon S3 bucket. You can enable the configuration options in any combination. Detailed below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">vpc_<wbr>configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#accesspointvpcconfiguration">Dict[Access<wbr>Point<wbr>Vpc<wbr>Configuration]</a></span>
    </dt>
    <dd>{{% md %}}Configuration block to restrict access to this access point to requests from the specified Virtual Private Cloud (VPC). Detailed below.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}




## AccessPoint Output Properties

The following output properties are available:




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Account<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of the S3 Access Point.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Bucket<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the bucket that you want to associate this access point with.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Domain<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The DNS domain name of the S3 Access Point in the format _`name`_-_`account_id`_.s3-accesspoint._region_.amazonaws.com.
Note: S3 access points only support secure access by HTTPS. HTTP isn&#39;t supported.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Has<wbr>Public<wbr>Access<wbr>Policy<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Indicates whether this access point currently has a policy that allows public access.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name you want to assign to this access point.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Network<wbr>Origin<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Indicates whether this access point allows access from the public Internet. Values are `VPC` (the access point doesn&#39;t allow access from the public Internet) and `Internet` (the access point allows access from the public Internet, subject to the access point and bucket access policies).
{{% /md %}}</dd>

    <dt class="property-"
            title="">Policy<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A valid JSON document that specifies the policy that you want to apply to this access point.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Public<wbr>Access<wbr>Block<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#accesspointpublicaccessblockconfiguration">Access<wbr>Point<wbr>Public<wbr>Access<wbr>Block<wbr>Configuration?</a></span>
    </dt>
    <dd>{{% md %}}Configuration block to manage the `PublicAccessBlock` configuration that you want to apply to this Amazon S3 bucket. You can enable the configuration options in any combination. Detailed below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Vpc<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#accesspointvpcconfiguration">Access<wbr>Point<wbr>Vpc<wbr>Configuration?</a></span>
    </dt>
    <dd>{{% md %}}Configuration block to restrict access to this access point to requests from the specified Virtual Private Cloud (VPC). Detailed below.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Account<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of the S3 Access Point.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Bucket<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the bucket that you want to associate this access point with.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Domain<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The DNS domain name of the S3 Access Point in the format _`name`_-_`account_id`_.s3-accesspoint._region_.amazonaws.com.
Note: S3 access points only support secure access by HTTPS. HTTP isn&#39;t supported.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Has<wbr>Public<wbr>Access<wbr>Policy<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Indicates whether this access point currently has a policy that allows public access.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name you want to assign to this access point.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Network<wbr>Origin<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Indicates whether this access point allows access from the public Internet. Values are `VPC` (the access point doesn&#39;t allow access from the public Internet) and `Internet` (the access point allows access from the public Internet, subject to the access point and bucket access policies).
{{% /md %}}</dd>

    <dt class="property-"
            title="">Policy<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}A valid JSON document that specifies the policy that you want to apply to this access point.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Public<wbr>Access<wbr>Block<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#accesspointpublicaccessblockconfiguration">*Access<wbr>Point<wbr>Public<wbr>Access<wbr>Block<wbr>Configuration</a></span>
    </dt>
    <dd>{{% md %}}Configuration block to manage the `PublicAccessBlock` configuration that you want to apply to this Amazon S3 bucket. You can enable the configuration options in any combination. Detailed below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Vpc<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#accesspointvpcconfiguration">*Access<wbr>Point<wbr>Vpc<wbr>Configuration</a></span>
    </dt>
    <dd>{{% md %}}Configuration block to restrict access to this access point to requests from the specified Virtual Private Cloud (VPC). Detailed below.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">account<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of the S3 Access Point.
{{% /md %}}</dd>

    <dt class="property-"
            title="">bucket<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the bucket that you want to associate this access point with.
{{% /md %}}</dd>

    <dt class="property-"
            title="">domain<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The DNS domain name of the S3 Access Point in the format _`name`_-_`account_id`_.s3-accesspoint._region_.amazonaws.com.
Note: S3 access points only support secure access by HTTPS. HTTP isn&#39;t supported.
{{% /md %}}</dd>

    <dt class="property-"
            title="">has<wbr>Public<wbr>Access<wbr>Policy<span class="property-indicator"></span>
        <span class="property-type">boolean</span>
    </dt>
    <dd>{{% md %}}Indicates whether this access point currently has a policy that allows public access.
{{% /md %}}</dd>

    <dt class="property-"
            title="">name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name you want to assign to this access point.
{{% /md %}}</dd>

    <dt class="property-"
            title="">network<wbr>Origin<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Indicates whether this access point allows access from the public Internet. Values are `VPC` (the access point doesn&#39;t allow access from the public Internet) and `Internet` (the access point allows access from the public Internet, subject to the access point and bucket access policies).
{{% /md %}}</dd>

    <dt class="property-"
            title="">policy<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A valid JSON document that specifies the policy that you want to apply to this access point.
{{% /md %}}</dd>

    <dt class="property-"
            title="">public<wbr>Access<wbr>Block<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#accesspointpublicaccessblockconfiguration">Access<wbr>Point<wbr>Public<wbr>Access<wbr>Block<wbr>Configuration?</a></span>
    </dt>
    <dd>{{% md %}}Configuration block to manage the `PublicAccessBlock` configuration that you want to apply to this Amazon S3 bucket. You can enable the configuration options in any combination. Detailed below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">vpc<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#accesspointvpcconfiguration">Access<wbr>Point<wbr>Vpc<wbr>Configuration?</a></span>
    </dt>
    <dd>{{% md %}}Configuration block to restrict access to this access point to requests from the specified Virtual Private Cloud (VPC). Detailed below.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">account_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of the S3 Access Point.
{{% /md %}}</dd>

    <dt class="property-"
            title="">bucket<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the bucket that you want to associate this access point with.
{{% /md %}}</dd>

    <dt class="property-"
            title="">domain_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The DNS domain name of the S3 Access Point in the format _`name`_-_`account_id`_.s3-accesspoint._region_.amazonaws.com.
Note: S3 access points only support secure access by HTTPS. HTTP isn&#39;t supported.
{{% /md %}}</dd>

    <dt class="property-"
            title="">has_<wbr>public_<wbr>access_<wbr>policy<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Indicates whether this access point currently has a policy that allows public access.
{{% /md %}}</dd>

    <dt class="property-"
            title="">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name you want to assign to this access point.
{{% /md %}}</dd>

    <dt class="property-"
            title="">network_<wbr>origin<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Indicates whether this access point allows access from the public Internet. Values are `VPC` (the access point doesn&#39;t allow access from the public Internet) and `Internet` (the access point allows access from the public Internet, subject to the access point and bucket access policies).
{{% /md %}}</dd>

    <dt class="property-"
            title="">policy<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A valid JSON document that specifies the policy that you want to apply to this access point.
{{% /md %}}</dd>

    <dt class="property-"
            title="">public_<wbr>access_<wbr>block_<wbr>configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#accesspointpublicaccessblockconfiguration">Dict[Access<wbr>Point<wbr>Public<wbr>Access<wbr>Block<wbr>Configuration]</a></span>
    </dt>
    <dd>{{% md %}}Configuration block to manage the `PublicAccessBlock` configuration that you want to apply to this Amazon S3 bucket. You can enable the configuration options in any combination. Detailed below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">vpc_<wbr>configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#accesspointvpcconfiguration">Dict[Access<wbr>Point<wbr>Vpc<wbr>Configuration]</a></span>
    </dt>
    <dd>{{% md %}}Configuration block to restrict access to this access point to requests from the specified Virtual Private Cloud (VPC). Detailed below.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





## Look up an Existing AccessPoint Resource

{{< chooser language "javascript,typescript,python,go,csharp  " / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">pulumi.Input&lt;pulumi.ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/s3/#AccessPointState">AccessPointState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/s3/#AccessPoint">AccessPoint</a></span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>account_id=None<span class="p">, </span>arn=None<span class="p">, </span>bucket=None<span class="p">, </span>domain_name=None<span class="p">, </span>has_public_access_policy=None<span class="p">, </span>name=None<span class="p">, </span>network_origin=None<span class="p">, </span>policy=None<span class="p">, </span>public_access_block_configuration=None<span class="p">, </span>vpc_configuration=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetAccessPoint<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">pulumi.IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/s3?tab=doc#AccessPointState">AccessPointState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/s3?tab=doc#AccessPoint">AccessPoint</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.S3.AccessPoint.html">AccessPoint</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Pulumi.Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.S3.AccessPointState.html">AccessPointState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
{{% /choosable %}}

Get an existing AccessPoint resource's state with the given name, ID, and optional extra properties used to qualify the lookup.

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
            title="Optional">Account<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of the S3 Access Point.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Bucket<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the bucket that you want to associate this access point with.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Domain<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The DNS domain name of the S3 Access Point in the format _`name`_-_`account_id`_.s3-accesspoint._region_.amazonaws.com.
Note: S3 access points only support secure access by HTTPS. HTTP isn&#39;t supported.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Has<wbr>Public<wbr>Access<wbr>Policy<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Indicates whether this access point currently has a policy that allows public access.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name you want to assign to this access point.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Network<wbr>Origin<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Indicates whether this access point allows access from the public Internet. Values are `VPC` (the access point doesn&#39;t allow access from the public Internet) and `Internet` (the access point allows access from the public Internet, subject to the access point and bucket access policies).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Policy<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A valid JSON document that specifies the policy that you want to apply to this access point.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Public<wbr>Access<wbr>Block<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#accesspointpublicaccessblockconfiguration">Access<wbr>Point<wbr>Public<wbr>Access<wbr>Block<wbr>Configuration<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}Configuration block to manage the `PublicAccessBlock` configuration that you want to apply to this Amazon S3 bucket. You can enable the configuration options in any combination. Detailed below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Vpc<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#accesspointvpcconfiguration">Access<wbr>Point<wbr>Vpc<wbr>Configuration<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}Configuration block to restrict access to this access point to requests from the specified Virtual Private Cloud (VPC). Detailed below.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Account<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of the S3 Access Point.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Bucket<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name of the bucket that you want to associate this access point with.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Domain<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The DNS domain name of the S3 Access Point in the format _`name`_-_`account_id`_.s3-accesspoint._region_.amazonaws.com.
Note: S3 access points only support secure access by HTTPS. HTTP isn&#39;t supported.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Has<wbr>Public<wbr>Access<wbr>Policy<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Indicates whether this access point currently has a policy that allows public access.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name you want to assign to this access point.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Network<wbr>Origin<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Indicates whether this access point allows access from the public Internet. Values are `VPC` (the access point doesn&#39;t allow access from the public Internet) and `Internet` (the access point allows access from the public Internet, subject to the access point and bucket access policies).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Policy<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}A valid JSON document that specifies the policy that you want to apply to this access point.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Public<wbr>Access<wbr>Block<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#accesspointpublicaccessblockconfiguration">*Access<wbr>Point<wbr>Public<wbr>Access<wbr>Block<wbr>Configuration</a></span>
    </dt>
    <dd>{{% md %}}Configuration block to manage the `PublicAccessBlock` configuration that you want to apply to this Amazon S3 bucket. You can enable the configuration options in any combination. Detailed below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Vpc<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#accesspointvpcconfiguration">*Access<wbr>Point<wbr>Vpc<wbr>Configuration</a></span>
    </dt>
    <dd>{{% md %}}Configuration block to restrict access to this access point to requests from the specified Virtual Private Cloud (VPC). Detailed below.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">account<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of the S3 Access Point.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">bucket<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the bucket that you want to associate this access point with.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">domain<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The DNS domain name of the S3 Access Point in the format _`name`_-_`account_id`_.s3-accesspoint._region_.amazonaws.com.
Note: S3 access points only support secure access by HTTPS. HTTP isn&#39;t supported.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">has<wbr>Public<wbr>Access<wbr>Policy<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Indicates whether this access point currently has a policy that allows public access.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name you want to assign to this access point.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">network<wbr>Origin<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Indicates whether this access point allows access from the public Internet. Values are `VPC` (the access point doesn&#39;t allow access from the public Internet) and `Internet` (the access point allows access from the public Internet, subject to the access point and bucket access policies).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">policy<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A valid JSON document that specifies the policy that you want to apply to this access point.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">public<wbr>Access<wbr>Block<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#accesspointpublicaccessblockconfiguration">Access<wbr>Point<wbr>Public<wbr>Access<wbr>Block<wbr>Configuration?</a></span>
    </dt>
    <dd>{{% md %}}Configuration block to manage the `PublicAccessBlock` configuration that you want to apply to this Amazon S3 bucket. You can enable the configuration options in any combination. Detailed below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">vpc<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#accesspointvpcconfiguration">Access<wbr>Point<wbr>Vpc<wbr>Configuration?</a></span>
    </dt>
    <dd>{{% md %}}Configuration block to restrict access to this access point to requests from the specified Virtual Private Cloud (VPC). Detailed below.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">account_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of the S3 Access Point.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">bucket<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the bucket that you want to associate this access point with.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">domain_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The DNS domain name of the S3 Access Point in the format _`name`_-_`account_id`_.s3-accesspoint._region_.amazonaws.com.
Note: S3 access points only support secure access by HTTPS. HTTP isn&#39;t supported.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">has_<wbr>public_<wbr>access_<wbr>policy<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Indicates whether this access point currently has a policy that allows public access.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name you want to assign to this access point.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">network_<wbr>origin<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Indicates whether this access point allows access from the public Internet. Values are `VPC` (the access point doesn&#39;t allow access from the public Internet) and `Internet` (the access point allows access from the public Internet, subject to the access point and bucket access policies).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">policy<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A valid JSON document that specifies the policy that you want to apply to this access point.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">public_<wbr>access_<wbr>block_<wbr>configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#accesspointpublicaccessblockconfiguration">Dict[Access<wbr>Point<wbr>Public<wbr>Access<wbr>Block<wbr>Configuration]</a></span>
    </dt>
    <dd>{{% md %}}Configuration block to manage the `PublicAccessBlock` configuration that you want to apply to this Amazon S3 bucket. You can enable the configuration options in any combination. Detailed below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">vpc_<wbr>configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#accesspointvpcconfiguration">Dict[Access<wbr>Point<wbr>Vpc<wbr>Configuration]</a></span>
    </dt>
    <dd>{{% md %}}Configuration block to restrict access to this access point to requests from the specified Virtual Private Cloud (VPC). Detailed below.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}







## Supporting Types

#### AccessPointPublicAccessBlockConfiguration
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#AccessPointPublicAccessBlockConfiguration">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#AccessPointPublicAccessBlockConfiguration">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/s3?tab=doc#AccessPointPublicAccessBlockConfigurationArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/s3?tab=doc#AccessPointPublicAccessBlockConfigurationOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.S3.AccessPointPublicAccessBlockConfigurationArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.S3.AccessPointPublicAccessBlockConfiguration.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Block<wbr>Public<wbr>Acls<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Whether Amazon S3 should block public ACLs for buckets in this account. Defaults to `true`. Enabling this setting does not affect existing policies or ACLs. When set to `true` causes the following behavior:
* PUT Bucket acl and PUT Object acl calls fail if the specified ACL is public.
* PUT Object calls fail if the request includes a public ACL.
* PUT Bucket calls fail if the request includes a public ACL.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Block<wbr>Public<wbr>Policy<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Whether Amazon S3 should block public bucket policies for buckets in this account. Defaults to `true`. Enabling this setting does not affect existing bucket policies. When set to `true` causes Amazon S3 to:
* Reject calls to PUT Bucket policy if the specified bucket policy allows public access.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ignore<wbr>Public<wbr>Acls<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Whether Amazon S3 should ignore public ACLs for buckets in this account. Defaults to `true`. Enabling this setting does not affect the persistence of any existing ACLs and doesn&#39;t prevent new public ACLs from being set. When set to `true` causes Amazon S3 to:
* Ignore all public ACLs on buckets in this account and any objects that they contain.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Restrict<wbr>Public<wbr>Buckets<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Whether Amazon S3 should restrict public bucket policies for buckets in this account. Defaults to `true`. Enabling this setting does not affect previously stored bucket policies, except that public and cross-account access within any public bucket policy, including non-public delegation to specific accounts, is blocked. When set to `true`:
* Only the bucket owner and AWS Services can access buckets with public policies.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Block<wbr>Public<wbr>Acls<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Whether Amazon S3 should block public ACLs for buckets in this account. Defaults to `true`. Enabling this setting does not affect existing policies or ACLs. When set to `true` causes the following behavior:
* PUT Bucket acl and PUT Object acl calls fail if the specified ACL is public.
* PUT Object calls fail if the request includes a public ACL.
* PUT Bucket calls fail if the request includes a public ACL.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Block<wbr>Public<wbr>Policy<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Whether Amazon S3 should block public bucket policies for buckets in this account. Defaults to `true`. Enabling this setting does not affect existing bucket policies. When set to `true` causes Amazon S3 to:
* Reject calls to PUT Bucket policy if the specified bucket policy allows public access.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ignore<wbr>Public<wbr>Acls<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Whether Amazon S3 should ignore public ACLs for buckets in this account. Defaults to `true`. Enabling this setting does not affect the persistence of any existing ACLs and doesn&#39;t prevent new public ACLs from being set. When set to `true` causes Amazon S3 to:
* Ignore all public ACLs on buckets in this account and any objects that they contain.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Restrict<wbr>Public<wbr>Buckets<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Whether Amazon S3 should restrict public bucket policies for buckets in this account. Defaults to `true`. Enabling this setting does not affect previously stored bucket policies, except that public and cross-account access within any public bucket policy, including non-public delegation to specific accounts, is blocked. When set to `true`:
* Only the bucket owner and AWS Services can access buckets with public policies.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">block<wbr>Public<wbr>Acls<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Whether Amazon S3 should block public ACLs for buckets in this account. Defaults to `true`. Enabling this setting does not affect existing policies or ACLs. When set to `true` causes the following behavior:
* PUT Bucket acl and PUT Object acl calls fail if the specified ACL is public.
* PUT Object calls fail if the request includes a public ACL.
* PUT Bucket calls fail if the request includes a public ACL.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">block<wbr>Public<wbr>Policy<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Whether Amazon S3 should block public bucket policies for buckets in this account. Defaults to `true`. Enabling this setting does not affect existing bucket policies. When set to `true` causes Amazon S3 to:
* Reject calls to PUT Bucket policy if the specified bucket policy allows public access.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ignore<wbr>Public<wbr>Acls<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Whether Amazon S3 should ignore public ACLs for buckets in this account. Defaults to `true`. Enabling this setting does not affect the persistence of any existing ACLs and doesn&#39;t prevent new public ACLs from being set. When set to `true` causes Amazon S3 to:
* Ignore all public ACLs on buckets in this account and any objects that they contain.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">restrict<wbr>Public<wbr>Buckets<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Whether Amazon S3 should restrict public bucket policies for buckets in this account. Defaults to `true`. Enabling this setting does not affect previously stored bucket policies, except that public and cross-account access within any public bucket policy, including non-public delegation to specific accounts, is blocked. When set to `true`:
* Only the bucket owner and AWS Services can access buckets with public policies.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">block_<wbr>public_<wbr>acls<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Whether Amazon S3 should block public ACLs for buckets in this account. Defaults to `true`. Enabling this setting does not affect existing policies or ACLs. When set to `true` causes the following behavior:
* PUT Bucket acl and PUT Object acl calls fail if the specified ACL is public.
* PUT Object calls fail if the request includes a public ACL.
* PUT Bucket calls fail if the request includes a public ACL.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">block_<wbr>public_<wbr>policy<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Whether Amazon S3 should block public bucket policies for buckets in this account. Defaults to `true`. Enabling this setting does not affect existing bucket policies. When set to `true` causes Amazon S3 to:
* Reject calls to PUT Bucket policy if the specified bucket policy allows public access.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ignore_<wbr>public_<wbr>acls<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Whether Amazon S3 should ignore public ACLs for buckets in this account. Defaults to `true`. Enabling this setting does not affect the persistence of any existing ACLs and doesn&#39;t prevent new public ACLs from being set. When set to `true` causes Amazon S3 to:
* Ignore all public ACLs on buckets in this account and any objects that they contain.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">restrict_<wbr>public_<wbr>buckets<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Whether Amazon S3 should restrict public bucket policies for buckets in this account. Defaults to `true`. Enabling this setting does not affect previously stored bucket policies, except that public and cross-account access within any public bucket policy, including non-public delegation to specific accounts, is blocked. When set to `true`:
* Only the bucket owner and AWS Services can access buckets with public policies.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### AccessPointVpcConfiguration
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#AccessPointVpcConfiguration">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#AccessPointVpcConfiguration">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/s3?tab=doc#AccessPointVpcConfigurationArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/s3?tab=doc#AccessPointVpcConfigurationOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.S3.AccessPointVpcConfigurationArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.S3.AccessPointVpcConfiguration.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Vpc<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}This access point will only allow connections from the specified VPC ID.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Vpc<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}This access point will only allow connections from the specified VPC ID.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">vpc<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}This access point will only allow connections from the specified VPC ID.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">vpc_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}This access point will only allow connections from the specified VPC ID.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}








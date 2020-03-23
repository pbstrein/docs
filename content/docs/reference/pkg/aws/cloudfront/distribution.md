
---
title: "Distribution"
block_external_search_index: true
---

Creates an Amazon CloudFront web distribution.

For information about CloudFront distributions, see the
[Amazon CloudFront Developer Guide][1]. For specific information about creating
CloudFront web distributions, see the [POST Distribution][2] page in the Amazon
CloudFront API Reference.

> **NOTE:** CloudFront distributions take about 15 minutes to a deployed state
after creation or modification. During this time, deletes to resources will be
blocked. If you need to delete a distribution that is enabled and you do not
want to wait, you need to use the `retain_on_delete` flag.

## Example Usage

The following example below creates a CloudFront distribution with an S3 origin.

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const bucket = new aws.s3.Bucket("b", {
    acl: "private",
    tags: {
        Name: "My bucket",
    },
});
const s3OriginId = "myS3Origin";
const s3Distribution = new aws.cloudfront.Distribution("s3_distribution", {
    aliases: [
        "mysite.example.com",
        "yoursite.example.com",
    ],
    comment: "Some comment",
    defaultCacheBehavior: {
        allowedMethods: [
            "DELETE",
            "GET",
            "HEAD",
            "OPTIONS",
            "PATCH",
            "POST",
            "PUT",
        ],
        cachedMethods: [
            "GET",
            "HEAD",
        ],
        defaultTtl: 3600,
        forwardedValues: {
            cookies: {
                forward: "none",
            },
            queryString: false,
        },
        maxTtl: 86400,
        minTtl: 0,
        targetOriginId: s3OriginId,
        viewerProtocolPolicy: "allow-all",
    },
    defaultRootObject: "index.html",
    enabled: true,
    isIpv6Enabled: true,
    loggingConfig: {
        bucket: "mylogs.s3.amazonaws.com",
        includeCookies: false,
        prefix: "myprefix",
    },
    orderedCacheBehaviors: [
        // Cache behavior with precedence 0
        {
            allowedMethods: [
                "GET",
                "HEAD",
                "OPTIONS",
            ],
            cachedMethods: [
                "GET",
                "HEAD",
                "OPTIONS",
            ],
            compress: true,
            defaultTtl: 86400,
            forwardedValues: {
                cookies: {
                    forward: "none",
                },
                headers: ["Origin"],
                queryString: false,
            },
            maxTtl: 31536000,
            minTtl: 0,
            pathPattern: "/content/immutable/*",
            targetOriginId: s3OriginId,
            viewerProtocolPolicy: "redirect-to-https",
        },
        // Cache behavior with precedence 1
        {
            allowedMethods: [
                "GET",
                "HEAD",
                "OPTIONS",
            ],
            cachedMethods: [
                "GET",
                "HEAD",
            ],
            compress: true,
            defaultTtl: 3600,
            forwardedValues: {
                cookies: {
                    forward: "none",
                },
                queryString: false,
            },
            maxTtl: 86400,
            minTtl: 0,
            pathPattern: "/content/*",
            targetOriginId: s3OriginId,
            viewerProtocolPolicy: "redirect-to-https",
        },
    ],
    origins: [{
        domainName: bucket.bucketRegionalDomainName,
        originId: s3OriginId,
        s3OriginConfig: {
            originAccessIdentity: "origin-access-identity/cloudfront/ABCDEFG1234567",
        },
    }],
    priceClass: "PriceClass_200",
    restrictions: {
        geoRestriction: {
            locations: [
                "US",
                "CA",
                "GB",
                "DE",
            ],
            restrictionType: "whitelist",
        },
    },
    tags: {
        Environment: "production",
    },
    viewerCertificate: {
        cloudfrontDefaultCertificate: true,
    },
});
```

The following example below creates a Cloudfront distribution with an origin group for failover routing:

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const s3Distribution = new aws.cloudfront.Distribution("s3_distribution", {
    defaultCacheBehavior: {
        // ... other configuration ...
        targetOriginId: "groupS3",
    },
    origins: [
        {
            domainName: aws_s3_bucket_primary.bucketRegionalDomainName,
            originId: "primaryS3",
            s3OriginConfig: {
                originAccessIdentity: aws_cloudfront_origin_access_identity_default.cloudfrontAccessIdentityPath,
            },
        },
        {
            domainName: aws_s3_bucket_failover.bucketRegionalDomainName,
            originId: "failoverS3",
            s3OriginConfig: {
                originAccessIdentity: aws_cloudfront_origin_access_identity_default.cloudfrontAccessIdentityPath,
            },
        },
    ],
    originGroups: [{
        failoverCriteria: {
            statusCodes: [
                403,
                404,
                500,
                502,
            ],
        },
        members: [
            {
                originId: "primaryS3",
            },
            {
                originId: "failoverS3",
            },
        ],
        originId: "groupS3",
    }],
});
```

> This content is derived from https://github.com/terraform-providers/terraform-provider-aws/blob/master/website/docs/r/cloudfront_distribution.html.markdown.



## Create a Distribution Resource

{{< chooser language "javascript,typescript,python,go,csharp" / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/cloudfront/#Distribution">Distribution</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/cloudfront/#DistributionArgs">DistributionArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">Distribution</span><span class="p">(resource_name, opts=None, </span>aliases=None<span class="p">, </span>comment=None<span class="p">, </span>custom_error_responses=None<span class="p">, </span>default_cache_behavior=None<span class="p">, </span>default_root_object=None<span class="p">, </span>enabled=None<span class="p">, </span>http_version=None<span class="p">, </span>is_ipv6_enabled=None<span class="p">, </span>logging_config=None<span class="p">, </span>ordered_cache_behaviors=None<span class="p">, </span>origin_groups=None<span class="p">, </span>origins=None<span class="p">, </span>price_class=None<span class="p">, </span>restrictions=None<span class="p">, </span>retain_on_delete=None<span class="p">, </span>tags=None<span class="p">, </span>viewer_certificate=None<span class="p">, </span>wait_for_deployment=None<span class="p">, </span>web_acl_id=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewDistribution<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/cloudfront?tab=doc#DistributionArgs">DistributionArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/cloudfront?tab=doc#Distribution">Distribution</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Cloudfront.Distribution.html">Distribution</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Cloudfront.DistributionArgs.html">DistributionArgs</a></span> <span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
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
            title="Optional">Aliases<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}Extra CNAMEs (alternate domain names), if any, for
this distribution.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Comment<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Any comments you want to include about the
distribution.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Custom<wbr>Error<wbr>Responses<span class="property-indicator"></span>
        <span class="property-type"><a href="#distributioncustomerrorresponse">List&lt;Distribution<wbr>Custom<wbr>Error<wbr>Response<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}One or more custom error response elements (multiples allowed).
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Default<wbr>Cache<wbr>Behavior<span class="property-indicator"></span>
        <span class="property-type"><a href="#distributiondefaultcachebehavior">Distribution<wbr>Default<wbr>Cache<wbr>Behavior<wbr>Args</a></span>
    </dt>
    <dd>{{% md %}}The default cache behavior for this distribution (maximum
one).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Default<wbr>Root<wbr>Object<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The object that you want CloudFront to
return (for example, index.html) when an end user requests the root URL.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Enabled<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Whether the distribution is enabled to accept end
user requests for content.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Http<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The maximum HTTP version to support on the
distribution. Allowed values are `http1.1` and `http2`. The default is
`http2`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Is<wbr>Ipv6Enabled<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Whether the IPv6 is enabled for the distribution.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Logging<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#distributionloggingconfig">Distribution<wbr>Logging<wbr>Config<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}The logging
configuration that controls how logs are written
to your distribution (maximum one).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ordered<wbr>Cache<wbr>Behaviors<span class="property-indicator"></span>
        <span class="property-type"><a href="#distributionorderedcachebehavior">List&lt;Distribution<wbr>Ordered<wbr>Cache<wbr>Behavior<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}An ordered list of cache behaviors
resource for this distribution. List from top to bottom
in order of precedence. The topmost cache behavior will have precedence 0.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Origin<wbr>Groups<span class="property-indicator"></span>
        <span class="property-type"><a href="#distributionorigingroup">List&lt;Distribution<wbr>Origin<wbr>Group<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}One or more origin_group for this
distribution (multiples allowed).
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Origins<span class="property-indicator"></span>
        <span class="property-type"><a href="#distributionorigin">List&lt;Distribution<wbr>Origin<wbr>Args&gt;</a></span>
    </dt>
    <dd>{{% md %}}One or more origins for this
distribution (multiples allowed).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Price<wbr>Class<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The price class for this distribution. One of
`PriceClass_All`, `PriceClass_200`, `PriceClass_100`
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Restrictions<span class="property-indicator"></span>
        <span class="property-type"><a href="#distributionrestrictions">Distribution<wbr>Restrictions<wbr>Args</a></span>
    </dt>
    <dd>{{% md %}}The restriction
configuration for this distribution (maximum one).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Retain<wbr>On<wbr>Delete<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Disables the distribution instead of
deleting it when destroying the resource. If this is set,
the distribution needs to be deleted manually afterwards. Default: `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Viewer<wbr>Certificate<span class="property-indicator"></span>
        <span class="property-type"><a href="#distributionviewercertificate">Distribution<wbr>Viewer<wbr>Certificate<wbr>Args</a></span>
    </dt>
    <dd>{{% md %}}The SSL
configuration for this distribution (maximum
one).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Wait<wbr>For<wbr>Deployment<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}If enabled, the resource will wait for
the distribution status to change from `InProgress` to `Deployed`. Setting
this to`false` will skip the process. Default: `true`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Web<wbr>Acl<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}If you&#39;re using AWS WAF to filter CloudFront
requests, the Id of the AWS WAF web ACL that is associated with the
distribution. The WAF Web ACL must exist in the WAF Global (CloudFront)
region and the credentials configuring this argument must have
`waf:GetWebACL` permissions assigned.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Aliases<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}Extra CNAMEs (alternate domain names), if any, for
this distribution.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Comment<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Any comments you want to include about the
distribution.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Custom<wbr>Error<wbr>Responses<span class="property-indicator"></span>
        <span class="property-type"><a href="#distributioncustomerrorresponse">[]Distribution<wbr>Custom<wbr>Error<wbr>Response</a></span>
    </dt>
    <dd>{{% md %}}One or more custom error response elements (multiples allowed).
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Default<wbr>Cache<wbr>Behavior<span class="property-indicator"></span>
        <span class="property-type"><a href="#distributiondefaultcachebehavior">Distribution<wbr>Default<wbr>Cache<wbr>Behavior</a></span>
    </dt>
    <dd>{{% md %}}The default cache behavior for this distribution (maximum
one).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Default<wbr>Root<wbr>Object<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The object that you want CloudFront to
return (for example, index.html) when an end user requests the root URL.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Enabled<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Whether the distribution is enabled to accept end
user requests for content.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Http<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The maximum HTTP version to support on the
distribution. Allowed values are `http1.1` and `http2`. The default is
`http2`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Is<wbr>Ipv6Enabled<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Whether the IPv6 is enabled for the distribution.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Logging<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#distributionloggingconfig">*Distribution<wbr>Logging<wbr>Config</a></span>
    </dt>
    <dd>{{% md %}}The logging
configuration that controls how logs are written
to your distribution (maximum one).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ordered<wbr>Cache<wbr>Behaviors<span class="property-indicator"></span>
        <span class="property-type"><a href="#distributionorderedcachebehavior">[]Distribution<wbr>Ordered<wbr>Cache<wbr>Behavior</a></span>
    </dt>
    <dd>{{% md %}}An ordered list of cache behaviors
resource for this distribution. List from top to bottom
in order of precedence. The topmost cache behavior will have precedence 0.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Origin<wbr>Groups<span class="property-indicator"></span>
        <span class="property-type"><a href="#distributionorigingroup">[]Distribution<wbr>Origin<wbr>Group</a></span>
    </dt>
    <dd>{{% md %}}One or more origin_group for this
distribution (multiples allowed).
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Origins<span class="property-indicator"></span>
        <span class="property-type"><a href="#distributionorigin">[]Distribution<wbr>Origin</a></span>
    </dt>
    <dd>{{% md %}}One or more origins for this
distribution (multiples allowed).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Price<wbr>Class<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The price class for this distribution. One of
`PriceClass_All`, `PriceClass_200`, `PriceClass_100`
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Restrictions<span class="property-indicator"></span>
        <span class="property-type"><a href="#distributionrestrictions">Distribution<wbr>Restrictions</a></span>
    </dt>
    <dd>{{% md %}}The restriction
configuration for this distribution (maximum one).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Retain<wbr>On<wbr>Delete<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Disables the distribution instead of
deleting it when destroying the resource. If this is set,
the distribution needs to be deleted manually afterwards. Default: `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Viewer<wbr>Certificate<span class="property-indicator"></span>
        <span class="property-type"><a href="#distributionviewercertificate">Distribution<wbr>Viewer<wbr>Certificate</a></span>
    </dt>
    <dd>{{% md %}}The SSL
configuration for this distribution (maximum
one).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Wait<wbr>For<wbr>Deployment<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}If enabled, the resource will wait for
the distribution status to change from `InProgress` to `Deployed`. Setting
this to`false` will skip the process. Default: `true`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Web<wbr>Acl<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}If you&#39;re using AWS WAF to filter CloudFront
requests, the Id of the AWS WAF web ACL that is associated with the
distribution. The WAF Web ACL must exist in the WAF Global (CloudFront)
region and the credentials configuring this argument must have
`waf:GetWebACL` permissions assigned.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">aliases<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}Extra CNAMEs (alternate domain names), if any, for
this distribution.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">comment<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Any comments you want to include about the
distribution.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">custom<wbr>Error<wbr>Responses<span class="property-indicator"></span>
        <span class="property-type"><a href="#distributioncustomerrorresponse">Distribution<wbr>Custom<wbr>Error<wbr>Response[]?</a></span>
    </dt>
    <dd>{{% md %}}One or more custom error response elements (multiples allowed).
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">default<wbr>Cache<wbr>Behavior<span class="property-indicator"></span>
        <span class="property-type"><a href="#distributiondefaultcachebehavior">Distribution<wbr>Default<wbr>Cache<wbr>Behavior</a></span>
    </dt>
    <dd>{{% md %}}The default cache behavior for this distribution (maximum
one).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">default<wbr>Root<wbr>Object<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The object that you want CloudFront to
return (for example, index.html) when an end user requests the root URL.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">enabled<span class="property-indicator"></span>
        <span class="property-type">boolean</span>
    </dt>
    <dd>{{% md %}}Whether the distribution is enabled to accept end
user requests for content.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">http<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The maximum HTTP version to support on the
distribution. Allowed values are `http1.1` and `http2`. The default is
`http2`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">is<wbr>Ipv6Enabled<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Whether the IPv6 is enabled for the distribution.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">logging<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#distributionloggingconfig">Distribution<wbr>Logging<wbr>Config?</a></span>
    </dt>
    <dd>{{% md %}}The logging
configuration that controls how logs are written
to your distribution (maximum one).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ordered<wbr>Cache<wbr>Behaviors<span class="property-indicator"></span>
        <span class="property-type"><a href="#distributionorderedcachebehavior">Distribution<wbr>Ordered<wbr>Cache<wbr>Behavior[]?</a></span>
    </dt>
    <dd>{{% md %}}An ordered list of cache behaviors
resource for this distribution. List from top to bottom
in order of precedence. The topmost cache behavior will have precedence 0.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">origin<wbr>Groups<span class="property-indicator"></span>
        <span class="property-type"><a href="#distributionorigingroup">Distribution<wbr>Origin<wbr>Group[]?</a></span>
    </dt>
    <dd>{{% md %}}One or more origin_group for this
distribution (multiples allowed).
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">origins<span class="property-indicator"></span>
        <span class="property-type"><a href="#distributionorigin">Distribution<wbr>Origin[]</a></span>
    </dt>
    <dd>{{% md %}}One or more origins for this
distribution (multiples allowed).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">price<wbr>Class<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The price class for this distribution. One of
`PriceClass_All`, `PriceClass_200`, `PriceClass_100`
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">restrictions<span class="property-indicator"></span>
        <span class="property-type"><a href="#distributionrestrictions">Distribution<wbr>Restrictions</a></span>
    </dt>
    <dd>{{% md %}}The restriction
configuration for this distribution (maximum one).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">retain<wbr>On<wbr>Delete<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Disables the distribution instead of
deleting it when destroying the resource. If this is set,
the distribution needs to be deleted manually afterwards. Default: `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">viewer<wbr>Certificate<span class="property-indicator"></span>
        <span class="property-type"><a href="#distributionviewercertificate">Distribution<wbr>Viewer<wbr>Certificate</a></span>
    </dt>
    <dd>{{% md %}}The SSL
configuration for this distribution (maximum
one).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">wait<wbr>For<wbr>Deployment<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}If enabled, the resource will wait for
the distribution status to change from `InProgress` to `Deployed`. Setting
this to`false` will skip the process. Default: `true`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">web<wbr>Acl<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}If you&#39;re using AWS WAF to filter CloudFront
requests, the Id of the AWS WAF web ACL that is associated with the
distribution. The WAF Web ACL must exist in the WAF Global (CloudFront)
region and the credentials configuring this argument must have
`waf:GetWebACL` permissions assigned.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">aliases<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}Extra CNAMEs (alternate domain names), if any, for
this distribution.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">comment<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Any comments you want to include about the
distribution.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">custom_<wbr>error_<wbr>responses<span class="property-indicator"></span>
        <span class="property-type"><a href="#distributioncustomerrorresponse">List[Distribution<wbr>Custom<wbr>Error<wbr>Response]</a></span>
    </dt>
    <dd>{{% md %}}One or more custom error response elements (multiples allowed).
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">default_<wbr>cache_<wbr>behavior<span class="property-indicator"></span>
        <span class="property-type"><a href="#distributiondefaultcachebehavior">Dict[Distribution<wbr>Default<wbr>Cache<wbr>Behavior]</a></span>
    </dt>
    <dd>{{% md %}}The default cache behavior for this distribution (maximum
one).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">default_<wbr>root_<wbr>object<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The object that you want CloudFront to
return (for example, index.html) when an end user requests the root URL.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">enabled<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Whether the distribution is enabled to accept end
user requests for content.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">http_<wbr>version<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The maximum HTTP version to support on the
distribution. Allowed values are `http1.1` and `http2`. The default is
`http2`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">is_<wbr>ipv6_<wbr>enabled<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Whether the IPv6 is enabled for the distribution.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">logging_<wbr>config<span class="property-indicator"></span>
        <span class="property-type"><a href="#distributionloggingconfig">Dict[Distribution<wbr>Logging<wbr>Config]</a></span>
    </dt>
    <dd>{{% md %}}The logging
configuration that controls how logs are written
to your distribution (maximum one).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ordered_<wbr>cache_<wbr>behaviors<span class="property-indicator"></span>
        <span class="property-type"><a href="#distributionorderedcachebehavior">List[Distribution<wbr>Ordered<wbr>Cache<wbr>Behavior]</a></span>
    </dt>
    <dd>{{% md %}}An ordered list of cache behaviors
resource for this distribution. List from top to bottom
in order of precedence. The topmost cache behavior will have precedence 0.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">origin_<wbr>groups<span class="property-indicator"></span>
        <span class="property-type"><a href="#distributionorigingroup">List[Distribution<wbr>Origin<wbr>Group]</a></span>
    </dt>
    <dd>{{% md %}}One or more origin_group for this
distribution (multiples allowed).
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">origins<span class="property-indicator"></span>
        <span class="property-type"><a href="#distributionorigin">List[Distribution<wbr>Origin]</a></span>
    </dt>
    <dd>{{% md %}}One or more origins for this
distribution (multiples allowed).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">price_<wbr>class<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The price class for this distribution. One of
`PriceClass_All`, `PriceClass_200`, `PriceClass_100`
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">restrictions<span class="property-indicator"></span>
        <span class="property-type"><a href="#distributionrestrictions">Dict[Distribution<wbr>Restrictions]</a></span>
    </dt>
    <dd>{{% md %}}The restriction
configuration for this distribution (maximum one).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">retain_<wbr>on_<wbr>delete<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Disables the distribution instead of
deleting it when destroying the resource. If this is set,
the distribution needs to be deleted manually afterwards. Default: `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">viewer_<wbr>certificate<span class="property-indicator"></span>
        <span class="property-type"><a href="#distributionviewercertificate">Dict[Distribution<wbr>Viewer<wbr>Certificate]</a></span>
    </dt>
    <dd>{{% md %}}The SSL
configuration for this distribution (maximum
one).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">wait_<wbr>for_<wbr>deployment<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}If enabled, the resource will wait for
the distribution status to change from `InProgress` to `Deployed`. Setting
this to`false` will skip the process. Default: `true`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">web_<wbr>acl_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}If you&#39;re using AWS WAF to filter CloudFront
requests, the Id of the AWS WAF web ACL that is associated with the
distribution. The WAF Web ACL must exist in the WAF Global (CloudFront)
region and the credentials configuring this argument must have
`waf:GetWebACL` permissions assigned.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}




## Distribution Output Properties

The following output properties are available:




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Active<wbr>Trusted<wbr>Signers<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object></span>
    </dt>
    <dd>{{% md %}}The key pair IDs that CloudFront is aware of for
each trusted signer, if the distribution is set up to serve private content
with signed URLs.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Aliases<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}Extra CNAMEs (alternate domain names), if any, for
this distribution.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN (Amazon Resource Name) for the distribution. For example: arn:aws:cloudfront::123456789012:distribution/EDFDVBD632BHDS5, where 123456789012 is your AWS account ID.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Caller<wbr>Reference<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Internal value used by CloudFront to allow future
updates to the distribution configuration.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Comment<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Any comments you want to include about the
distribution.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Custom<wbr>Error<wbr>Responses<span class="property-indicator"></span>
        <span class="property-type"><a href="#distributioncustomerrorresponse">List&lt;Distribution<wbr>Custom<wbr>Error<wbr>Response&gt;?</a></span>
    </dt>
    <dd>{{% md %}}One or more custom error response elements (multiples allowed).
{{% /md %}}</dd>

    <dt class="property-"
            title="">Default<wbr>Cache<wbr>Behavior<span class="property-indicator"></span>
        <span class="property-type"><a href="#distributiondefaultcachebehavior">Distribution<wbr>Default<wbr>Cache<wbr>Behavior</a></span>
    </dt>
    <dd>{{% md %}}The default cache behavior for this distribution (maximum
one).
{{% /md %}}</dd>

    <dt class="property-"
            title="">Default<wbr>Root<wbr>Object<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The object that you want CloudFront to
return (for example, index.html) when an end user requests the root URL.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Domain<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The DNS domain name of either the S3 bucket, or
web site of your custom origin.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Enabled<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Whether the distribution is enabled to accept end
user requests for content.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Etag<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The current version of the distribution&#39;s information. For example:
`E2QWRUHAPOMQZL`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Hosted<wbr>Zone<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The CloudFront Route 53 zone ID that can be used to
route an [Alias Resource Record Set][7] to. This attribute is simply an
alias for the zone ID `Z2FDTNDATAQYW2`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Http<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The maximum HTTP version to support on the
distribution. Allowed values are `http1.1` and `http2`. The default is
`http2`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">In<wbr>Progress<wbr>Validation<wbr>Batches<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The number of invalidation batches
currently in progress.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Is<wbr>Ipv6Enabled<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Whether the IPv6 is enabled for the distribution.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Last<wbr>Modified<wbr>Time<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The date and time the distribution was last modified.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Logging<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#distributionloggingconfig">Distribution<wbr>Logging<wbr>Config?</a></span>
    </dt>
    <dd>{{% md %}}The logging
configuration that controls how logs are written
to your distribution (maximum one).
{{% /md %}}</dd>

    <dt class="property-"
            title="">Ordered<wbr>Cache<wbr>Behaviors<span class="property-indicator"></span>
        <span class="property-type"><a href="#distributionorderedcachebehavior">List&lt;Distribution<wbr>Ordered<wbr>Cache<wbr>Behavior&gt;?</a></span>
    </dt>
    <dd>{{% md %}}An ordered list of cache behaviors
resource for this distribution. List from top to bottom
in order of precedence. The topmost cache behavior will have precedence 0.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Origin<wbr>Groups<span class="property-indicator"></span>
        <span class="property-type"><a href="#distributionorigingroup">List&lt;Distribution<wbr>Origin<wbr>Group&gt;?</a></span>
    </dt>
    <dd>{{% md %}}One or more origin_group for this
distribution (multiples allowed).
{{% /md %}}</dd>

    <dt class="property-"
            title="">Origins<span class="property-indicator"></span>
        <span class="property-type"><a href="#distributionorigin">List&lt;Distribution<wbr>Origin&gt;</a></span>
    </dt>
    <dd>{{% md %}}One or more origins for this
distribution (multiples allowed).
{{% /md %}}</dd>

    <dt class="property-"
            title="">Price<wbr>Class<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The price class for this distribution. One of
`PriceClass_All`, `PriceClass_200`, `PriceClass_100`
{{% /md %}}</dd>

    <dt class="property-"
            title="">Restrictions<span class="property-indicator"></span>
        <span class="property-type"><a href="#distributionrestrictions">Distribution<wbr>Restrictions</a></span>
    </dt>
    <dd>{{% md %}}The restriction
configuration for this distribution (maximum one).
{{% /md %}}</dd>

    <dt class="property-"
            title="">Retain<wbr>On<wbr>Delete<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Disables the distribution instead of
deleting it when destroying the resource. If this is set,
the distribution needs to be deleted manually afterwards. Default: `false`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Status<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The current status of the distribution. `Deployed` if the
distribution&#39;s information is fully propagated throughout the Amazon
CloudFront system.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Viewer<wbr>Certificate<span class="property-indicator"></span>
        <span class="property-type"><a href="#distributionviewercertificate">Distribution<wbr>Viewer<wbr>Certificate</a></span>
    </dt>
    <dd>{{% md %}}The SSL
configuration for this distribution (maximum
one).
{{% /md %}}</dd>

    <dt class="property-"
            title="">Wait<wbr>For<wbr>Deployment<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}If enabled, the resource will wait for
the distribution status to change from `InProgress` to `Deployed`. Setting
this to`false` will skip the process. Default: `true`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Web<wbr>Acl<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}If you&#39;re using AWS WAF to filter CloudFront
requests, the Id of the AWS WAF web ACL that is associated with the
distribution. The WAF Web ACL must exist in the WAF Global (CloudFront)
region and the credentials configuring this argument must have
`waf:GetWebACL` permissions assigned.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Active<wbr>Trusted<wbr>Signers<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}The key pair IDs that CloudFront is aware of for
each trusted signer, if the distribution is set up to serve private content
with signed URLs.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Aliases<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}Extra CNAMEs (alternate domain names), if any, for
this distribution.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN (Amazon Resource Name) for the distribution. For example: arn:aws:cloudfront::123456789012:distribution/EDFDVBD632BHDS5, where 123456789012 is your AWS account ID.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Caller<wbr>Reference<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Internal value used by CloudFront to allow future
updates to the distribution configuration.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Comment<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Any comments you want to include about the
distribution.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Custom<wbr>Error<wbr>Responses<span class="property-indicator"></span>
        <span class="property-type"><a href="#distributioncustomerrorresponse">[]Distribution<wbr>Custom<wbr>Error<wbr>Response</a></span>
    </dt>
    <dd>{{% md %}}One or more custom error response elements (multiples allowed).
{{% /md %}}</dd>

    <dt class="property-"
            title="">Default<wbr>Cache<wbr>Behavior<span class="property-indicator"></span>
        <span class="property-type"><a href="#distributiondefaultcachebehavior">Distribution<wbr>Default<wbr>Cache<wbr>Behavior</a></span>
    </dt>
    <dd>{{% md %}}The default cache behavior for this distribution (maximum
one).
{{% /md %}}</dd>

    <dt class="property-"
            title="">Default<wbr>Root<wbr>Object<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The object that you want CloudFront to
return (for example, index.html) when an end user requests the root URL.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Domain<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The DNS domain name of either the S3 bucket, or
web site of your custom origin.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Enabled<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Whether the distribution is enabled to accept end
user requests for content.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Etag<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The current version of the distribution&#39;s information. For example:
`E2QWRUHAPOMQZL`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Hosted<wbr>Zone<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The CloudFront Route 53 zone ID that can be used to
route an [Alias Resource Record Set][7] to. This attribute is simply an
alias for the zone ID `Z2FDTNDATAQYW2`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Http<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The maximum HTTP version to support on the
distribution. Allowed values are `http1.1` and `http2`. The default is
`http2`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">In<wbr>Progress<wbr>Validation<wbr>Batches<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The number of invalidation batches
currently in progress.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Is<wbr>Ipv6Enabled<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Whether the IPv6 is enabled for the distribution.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Last<wbr>Modified<wbr>Time<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The date and time the distribution was last modified.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Logging<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#distributionloggingconfig">*Distribution<wbr>Logging<wbr>Config</a></span>
    </dt>
    <dd>{{% md %}}The logging
configuration that controls how logs are written
to your distribution (maximum one).
{{% /md %}}</dd>

    <dt class="property-"
            title="">Ordered<wbr>Cache<wbr>Behaviors<span class="property-indicator"></span>
        <span class="property-type"><a href="#distributionorderedcachebehavior">[]Distribution<wbr>Ordered<wbr>Cache<wbr>Behavior</a></span>
    </dt>
    <dd>{{% md %}}An ordered list of cache behaviors
resource for this distribution. List from top to bottom
in order of precedence. The topmost cache behavior will have precedence 0.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Origin<wbr>Groups<span class="property-indicator"></span>
        <span class="property-type"><a href="#distributionorigingroup">[]Distribution<wbr>Origin<wbr>Group</a></span>
    </dt>
    <dd>{{% md %}}One or more origin_group for this
distribution (multiples allowed).
{{% /md %}}</dd>

    <dt class="property-"
            title="">Origins<span class="property-indicator"></span>
        <span class="property-type"><a href="#distributionorigin">[]Distribution<wbr>Origin</a></span>
    </dt>
    <dd>{{% md %}}One or more origins for this
distribution (multiples allowed).
{{% /md %}}</dd>

    <dt class="property-"
            title="">Price<wbr>Class<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The price class for this distribution. One of
`PriceClass_All`, `PriceClass_200`, `PriceClass_100`
{{% /md %}}</dd>

    <dt class="property-"
            title="">Restrictions<span class="property-indicator"></span>
        <span class="property-type"><a href="#distributionrestrictions">Distribution<wbr>Restrictions</a></span>
    </dt>
    <dd>{{% md %}}The restriction
configuration for this distribution (maximum one).
{{% /md %}}</dd>

    <dt class="property-"
            title="">Retain<wbr>On<wbr>Delete<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Disables the distribution instead of
deleting it when destroying the resource. If this is set,
the distribution needs to be deleted manually afterwards. Default: `false`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Status<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The current status of the distribution. `Deployed` if the
distribution&#39;s information is fully propagated throughout the Amazon
CloudFront system.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Viewer<wbr>Certificate<span class="property-indicator"></span>
        <span class="property-type"><a href="#distributionviewercertificate">Distribution<wbr>Viewer<wbr>Certificate</a></span>
    </dt>
    <dd>{{% md %}}The SSL
configuration for this distribution (maximum
one).
{{% /md %}}</dd>

    <dt class="property-"
            title="">Wait<wbr>For<wbr>Deployment<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}If enabled, the resource will wait for
the distribution status to change from `InProgress` to `Deployed`. Setting
this to`false` will skip the process. Default: `true`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Web<wbr>Acl<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}If you&#39;re using AWS WAF to filter CloudFront
requests, the Id of the AWS WAF web ACL that is associated with the
distribution. The WAF Web ACL must exist in the WAF Global (CloudFront)
region and the credentials configuring this argument must have
`waf:GetWebACL` permissions assigned.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">active<wbr>Trusted<wbr>Signers<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}</span>
    </dt>
    <dd>{{% md %}}The key pair IDs that CloudFront is aware of for
each trusted signer, if the distribution is set up to serve private content
with signed URLs.
{{% /md %}}</dd>

    <dt class="property-"
            title="">aliases<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}Extra CNAMEs (alternate domain names), if any, for
this distribution.
{{% /md %}}</dd>

    <dt class="property-"
            title="">arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN (Amazon Resource Name) for the distribution. For example: arn:aws:cloudfront::123456789012:distribution/EDFDVBD632BHDS5, where 123456789012 is your AWS account ID.
{{% /md %}}</dd>

    <dt class="property-"
            title="">caller<wbr>Reference<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Internal value used by CloudFront to allow future
updates to the distribution configuration.
{{% /md %}}</dd>

    <dt class="property-"
            title="">comment<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Any comments you want to include about the
distribution.
{{% /md %}}</dd>

    <dt class="property-"
            title="">custom<wbr>Error<wbr>Responses<span class="property-indicator"></span>
        <span class="property-type"><a href="#distributioncustomerrorresponse">Distribution<wbr>Custom<wbr>Error<wbr>Response[]?</a></span>
    </dt>
    <dd>{{% md %}}One or more custom error response elements (multiples allowed).
{{% /md %}}</dd>

    <dt class="property-"
            title="">default<wbr>Cache<wbr>Behavior<span class="property-indicator"></span>
        <span class="property-type"><a href="#distributiondefaultcachebehavior">Distribution<wbr>Default<wbr>Cache<wbr>Behavior</a></span>
    </dt>
    <dd>{{% md %}}The default cache behavior for this distribution (maximum
one).
{{% /md %}}</dd>

    <dt class="property-"
            title="">default<wbr>Root<wbr>Object<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The object that you want CloudFront to
return (for example, index.html) when an end user requests the root URL.
{{% /md %}}</dd>

    <dt class="property-"
            title="">domain<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The DNS domain name of either the S3 bucket, or
web site of your custom origin.
{{% /md %}}</dd>

    <dt class="property-"
            title="">enabled<span class="property-indicator"></span>
        <span class="property-type">boolean</span>
    </dt>
    <dd>{{% md %}}Whether the distribution is enabled to accept end
user requests for content.
{{% /md %}}</dd>

    <dt class="property-"
            title="">etag<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The current version of the distribution&#39;s information. For example:
`E2QWRUHAPOMQZL`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">hosted<wbr>Zone<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The CloudFront Route 53 zone ID that can be used to
route an [Alias Resource Record Set][7] to. This attribute is simply an
alias for the zone ID `Z2FDTNDATAQYW2`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">http<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The maximum HTTP version to support on the
distribution. Allowed values are `http1.1` and `http2`. The default is
`http2`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">in<wbr>Progress<wbr>Validation<wbr>Batches<span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}The number of invalidation batches
currently in progress.
{{% /md %}}</dd>

    <dt class="property-"
            title="">is<wbr>Ipv6Enabled<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Whether the IPv6 is enabled for the distribution.
{{% /md %}}</dd>

    <dt class="property-"
            title="">last<wbr>Modified<wbr>Time<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The date and time the distribution was last modified.
{{% /md %}}</dd>

    <dt class="property-"
            title="">logging<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#distributionloggingconfig">Distribution<wbr>Logging<wbr>Config?</a></span>
    </dt>
    <dd>{{% md %}}The logging
configuration that controls how logs are written
to your distribution (maximum one).
{{% /md %}}</dd>

    <dt class="property-"
            title="">ordered<wbr>Cache<wbr>Behaviors<span class="property-indicator"></span>
        <span class="property-type"><a href="#distributionorderedcachebehavior">Distribution<wbr>Ordered<wbr>Cache<wbr>Behavior[]?</a></span>
    </dt>
    <dd>{{% md %}}An ordered list of cache behaviors
resource for this distribution. List from top to bottom
in order of precedence. The topmost cache behavior will have precedence 0.
{{% /md %}}</dd>

    <dt class="property-"
            title="">origin<wbr>Groups<span class="property-indicator"></span>
        <span class="property-type"><a href="#distributionorigingroup">Distribution<wbr>Origin<wbr>Group[]?</a></span>
    </dt>
    <dd>{{% md %}}One or more origin_group for this
distribution (multiples allowed).
{{% /md %}}</dd>

    <dt class="property-"
            title="">origins<span class="property-indicator"></span>
        <span class="property-type"><a href="#distributionorigin">Distribution<wbr>Origin[]</a></span>
    </dt>
    <dd>{{% md %}}One or more origins for this
distribution (multiples allowed).
{{% /md %}}</dd>

    <dt class="property-"
            title="">price<wbr>Class<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The price class for this distribution. One of
`PriceClass_All`, `PriceClass_200`, `PriceClass_100`
{{% /md %}}</dd>

    <dt class="property-"
            title="">restrictions<span class="property-indicator"></span>
        <span class="property-type"><a href="#distributionrestrictions">Distribution<wbr>Restrictions</a></span>
    </dt>
    <dd>{{% md %}}The restriction
configuration for this distribution (maximum one).
{{% /md %}}</dd>

    <dt class="property-"
            title="">retain<wbr>On<wbr>Delete<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Disables the distribution instead of
deleting it when destroying the resource. If this is set,
the distribution needs to be deleted manually afterwards. Default: `false`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">status<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The current status of the distribution. `Deployed` if the
distribution&#39;s information is fully propagated throughout the Amazon
CloudFront system.
{{% /md %}}</dd>

    <dt class="property-"
            title="">tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-"
            title="">viewer<wbr>Certificate<span class="property-indicator"></span>
        <span class="property-type"><a href="#distributionviewercertificate">Distribution<wbr>Viewer<wbr>Certificate</a></span>
    </dt>
    <dd>{{% md %}}The SSL
configuration for this distribution (maximum
one).
{{% /md %}}</dd>

    <dt class="property-"
            title="">wait<wbr>For<wbr>Deployment<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}If enabled, the resource will wait for
the distribution status to change from `InProgress` to `Deployed`. Setting
this to`false` will skip the process. Default: `true`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">web<wbr>Acl<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}If you&#39;re using AWS WAF to filter CloudFront
requests, the Id of the AWS WAF web ACL that is associated with the
distribution. The WAF Web ACL must exist in the WAF Global (CloudFront)
region and the credentials configuring this argument must have
`waf:GetWebACL` permissions assigned.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">active_<wbr>trusted_<wbr>signers<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}The key pair IDs that CloudFront is aware of for
each trusted signer, if the distribution is set up to serve private content
with signed URLs.
{{% /md %}}</dd>

    <dt class="property-"
            title="">aliases<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}Extra CNAMEs (alternate domain names), if any, for
this distribution.
{{% /md %}}</dd>

    <dt class="property-"
            title="">arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ARN (Amazon Resource Name) for the distribution. For example: arn:aws:cloudfront::123456789012:distribution/EDFDVBD632BHDS5, where 123456789012 is your AWS account ID.
{{% /md %}}</dd>

    <dt class="property-"
            title="">caller_<wbr>reference<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Internal value used by CloudFront to allow future
updates to the distribution configuration.
{{% /md %}}</dd>

    <dt class="property-"
            title="">comment<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Any comments you want to include about the
distribution.
{{% /md %}}</dd>

    <dt class="property-"
            title="">custom_<wbr>error_<wbr>responses<span class="property-indicator"></span>
        <span class="property-type"><a href="#distributioncustomerrorresponse">List[Distribution<wbr>Custom<wbr>Error<wbr>Response]</a></span>
    </dt>
    <dd>{{% md %}}One or more custom error response elements (multiples allowed).
{{% /md %}}</dd>

    <dt class="property-"
            title="">default_<wbr>cache_<wbr>behavior<span class="property-indicator"></span>
        <span class="property-type"><a href="#distributiondefaultcachebehavior">Dict[Distribution<wbr>Default<wbr>Cache<wbr>Behavior]</a></span>
    </dt>
    <dd>{{% md %}}The default cache behavior for this distribution (maximum
one).
{{% /md %}}</dd>

    <dt class="property-"
            title="">default_<wbr>root_<wbr>object<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The object that you want CloudFront to
return (for example, index.html) when an end user requests the root URL.
{{% /md %}}</dd>

    <dt class="property-"
            title="">domain_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The DNS domain name of either the S3 bucket, or
web site of your custom origin.
{{% /md %}}</dd>

    <dt class="property-"
            title="">enabled<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Whether the distribution is enabled to accept end
user requests for content.
{{% /md %}}</dd>

    <dt class="property-"
            title="">etag<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The current version of the distribution&#39;s information. For example:
`E2QWRUHAPOMQZL`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">hosted_<wbr>zone_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The CloudFront Route 53 zone ID that can be used to
route an [Alias Resource Record Set][7] to. This attribute is simply an
alias for the zone ID `Z2FDTNDATAQYW2`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">http_<wbr>version<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The maximum HTTP version to support on the
distribution. Allowed values are `http1.1` and `http2`. The default is
`http2`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">in_<wbr>progress_<wbr>validation_<wbr>batches<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The number of invalidation batches
currently in progress.
{{% /md %}}</dd>

    <dt class="property-"
            title="">is_<wbr>ipv6_<wbr>enabled<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Whether the IPv6 is enabled for the distribution.
{{% /md %}}</dd>

    <dt class="property-"
            title="">last_<wbr>modified_<wbr>time<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The date and time the distribution was last modified.
{{% /md %}}</dd>

    <dt class="property-"
            title="">logging_<wbr>config<span class="property-indicator"></span>
        <span class="property-type"><a href="#distributionloggingconfig">Dict[Distribution<wbr>Logging<wbr>Config]</a></span>
    </dt>
    <dd>{{% md %}}The logging
configuration that controls how logs are written
to your distribution (maximum one).
{{% /md %}}</dd>

    <dt class="property-"
            title="">ordered_<wbr>cache_<wbr>behaviors<span class="property-indicator"></span>
        <span class="property-type"><a href="#distributionorderedcachebehavior">List[Distribution<wbr>Ordered<wbr>Cache<wbr>Behavior]</a></span>
    </dt>
    <dd>{{% md %}}An ordered list of cache behaviors
resource for this distribution. List from top to bottom
in order of precedence. The topmost cache behavior will have precedence 0.
{{% /md %}}</dd>

    <dt class="property-"
            title="">origin_<wbr>groups<span class="property-indicator"></span>
        <span class="property-type"><a href="#distributionorigingroup">List[Distribution<wbr>Origin<wbr>Group]</a></span>
    </dt>
    <dd>{{% md %}}One or more origin_group for this
distribution (multiples allowed).
{{% /md %}}</dd>

    <dt class="property-"
            title="">origins<span class="property-indicator"></span>
        <span class="property-type"><a href="#distributionorigin">List[Distribution<wbr>Origin]</a></span>
    </dt>
    <dd>{{% md %}}One or more origins for this
distribution (multiples allowed).
{{% /md %}}</dd>

    <dt class="property-"
            title="">price_<wbr>class<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The price class for this distribution. One of
`PriceClass_All`, `PriceClass_200`, `PriceClass_100`
{{% /md %}}</dd>

    <dt class="property-"
            title="">restrictions<span class="property-indicator"></span>
        <span class="property-type"><a href="#distributionrestrictions">Dict[Distribution<wbr>Restrictions]</a></span>
    </dt>
    <dd>{{% md %}}The restriction
configuration for this distribution (maximum one).
{{% /md %}}</dd>

    <dt class="property-"
            title="">retain_<wbr>on_<wbr>delete<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Disables the distribution instead of
deleting it when destroying the resource. If this is set,
the distribution needs to be deleted manually afterwards. Default: `false`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">status<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The current status of the distribution. `Deployed` if the
distribution&#39;s information is fully propagated throughout the Amazon
CloudFront system.
{{% /md %}}</dd>

    <dt class="property-"
            title="">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-"
            title="">viewer_<wbr>certificate<span class="property-indicator"></span>
        <span class="property-type"><a href="#distributionviewercertificate">Dict[Distribution<wbr>Viewer<wbr>Certificate]</a></span>
    </dt>
    <dd>{{% md %}}The SSL
configuration for this distribution (maximum
one).
{{% /md %}}</dd>

    <dt class="property-"
            title="">wait_<wbr>for_<wbr>deployment<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}If enabled, the resource will wait for
the distribution status to change from `InProgress` to `Deployed`. Setting
this to`false` will skip the process. Default: `true`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">web_<wbr>acl_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}If you&#39;re using AWS WAF to filter CloudFront
requests, the Id of the AWS WAF web ACL that is associated with the
distribution. The WAF Web ACL must exist in the WAF Global (CloudFront)
region and the credentials configuring this argument must have
`waf:GetWebACL` permissions assigned.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





## Look up an Existing Distribution Resource

{{< chooser language "javascript,typescript,python,go,csharp  " / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">pulumi.Input&lt;pulumi.ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/cloudfront/#DistributionState">DistributionState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/cloudfront/#Distribution">Distribution</a></span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>active_trusted_signers=None<span class="p">, </span>aliases=None<span class="p">, </span>arn=None<span class="p">, </span>caller_reference=None<span class="p">, </span>comment=None<span class="p">, </span>custom_error_responses=None<span class="p">, </span>default_cache_behavior=None<span class="p">, </span>default_root_object=None<span class="p">, </span>domain_name=None<span class="p">, </span>enabled=None<span class="p">, </span>etag=None<span class="p">, </span>hosted_zone_id=None<span class="p">, </span>http_version=None<span class="p">, </span>in_progress_validation_batches=None<span class="p">, </span>is_ipv6_enabled=None<span class="p">, </span>last_modified_time=None<span class="p">, </span>logging_config=None<span class="p">, </span>ordered_cache_behaviors=None<span class="p">, </span>origin_groups=None<span class="p">, </span>origins=None<span class="p">, </span>price_class=None<span class="p">, </span>restrictions=None<span class="p">, </span>retain_on_delete=None<span class="p">, </span>status=None<span class="p">, </span>tags=None<span class="p">, </span>viewer_certificate=None<span class="p">, </span>wait_for_deployment=None<span class="p">, </span>web_acl_id=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetDistribution<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">pulumi.IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/cloudfront?tab=doc#DistributionState">DistributionState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/cloudfront?tab=doc#Distribution">Distribution</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Cloudfront.Distribution.html">Distribution</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Pulumi.Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Cloudfront.DistributionState.html">DistributionState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
{{% /choosable %}}

Get an existing Distribution resource's state with the given name, ID, and optional extra properties used to qualify the lookup.

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
            title="Optional">Active<wbr>Trusted<wbr>Signers<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}The key pair IDs that CloudFront is aware of for
each trusted signer, if the distribution is set up to serve private content
with signed URLs.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Aliases<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}Extra CNAMEs (alternate domain names), if any, for
this distribution.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ARN (Amazon Resource Name) for the distribution. For example: arn:aws:cloudfront::123456789012:distribution/EDFDVBD632BHDS5, where 123456789012 is your AWS account ID.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Caller<wbr>Reference<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Internal value used by CloudFront to allow future
updates to the distribution configuration.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Comment<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Any comments you want to include about the
distribution.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Custom<wbr>Error<wbr>Responses<span class="property-indicator"></span>
        <span class="property-type"><a href="#distributioncustomerrorresponse">List&lt;Distribution<wbr>Custom<wbr>Error<wbr>Response<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}One or more custom error response elements (multiples allowed).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Default<wbr>Cache<wbr>Behavior<span class="property-indicator"></span>
        <span class="property-type"><a href="#distributiondefaultcachebehavior">Distribution<wbr>Default<wbr>Cache<wbr>Behavior<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}The default cache behavior for this distribution (maximum
one).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Default<wbr>Root<wbr>Object<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The object that you want CloudFront to
return (for example, index.html) when an end user requests the root URL.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Domain<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The DNS domain name of either the S3 bucket, or
web site of your custom origin.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Enabled<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Whether the distribution is enabled to accept end
user requests for content.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Etag<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The current version of the distribution&#39;s information. For example:
`E2QWRUHAPOMQZL`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Hosted<wbr>Zone<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The CloudFront Route 53 zone ID that can be used to
route an [Alias Resource Record Set][7] to. This attribute is simply an
alias for the zone ID `Z2FDTNDATAQYW2`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Http<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The maximum HTTP version to support on the
distribution. Allowed values are `http1.1` and `http2`. The default is
`http2`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">In<wbr>Progress<wbr>Validation<wbr>Batches<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The number of invalidation batches
currently in progress.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Is<wbr>Ipv6Enabled<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Whether the IPv6 is enabled for the distribution.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Last<wbr>Modified<wbr>Time<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The date and time the distribution was last modified.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Logging<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#distributionloggingconfig">Distribution<wbr>Logging<wbr>Config<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}The logging
configuration that controls how logs are written
to your distribution (maximum one).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ordered<wbr>Cache<wbr>Behaviors<span class="property-indicator"></span>
        <span class="property-type"><a href="#distributionorderedcachebehavior">List&lt;Distribution<wbr>Ordered<wbr>Cache<wbr>Behavior<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}An ordered list of cache behaviors
resource for this distribution. List from top to bottom
in order of precedence. The topmost cache behavior will have precedence 0.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Origin<wbr>Groups<span class="property-indicator"></span>
        <span class="property-type"><a href="#distributionorigingroup">List&lt;Distribution<wbr>Origin<wbr>Group<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}One or more origin_group for this
distribution (multiples allowed).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Origins<span class="property-indicator"></span>
        <span class="property-type"><a href="#distributionorigin">List&lt;Distribution<wbr>Origin<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}One or more origins for this
distribution (multiples allowed).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Price<wbr>Class<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The price class for this distribution. One of
`PriceClass_All`, `PriceClass_200`, `PriceClass_100`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Restrictions<span class="property-indicator"></span>
        <span class="property-type"><a href="#distributionrestrictions">Distribution<wbr>Restrictions<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}The restriction
configuration for this distribution (maximum one).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Retain<wbr>On<wbr>Delete<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Disables the distribution instead of
deleting it when destroying the resource. If this is set,
the distribution needs to be deleted manually afterwards. Default: `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Status<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The current status of the distribution. `Deployed` if the
distribution&#39;s information is fully propagated throughout the Amazon
CloudFront system.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Viewer<wbr>Certificate<span class="property-indicator"></span>
        <span class="property-type"><a href="#distributionviewercertificate">Distribution<wbr>Viewer<wbr>Certificate<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}The SSL
configuration for this distribution (maximum
one).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Wait<wbr>For<wbr>Deployment<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}If enabled, the resource will wait for
the distribution status to change from `InProgress` to `Deployed`. Setting
this to`false` will skip the process. Default: `true`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Web<wbr>Acl<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}If you&#39;re using AWS WAF to filter CloudFront
requests, the Id of the AWS WAF web ACL that is associated with the
distribution. The WAF Web ACL must exist in the WAF Global (CloudFront)
region and the credentials configuring this argument must have
`waf:GetWebACL` permissions assigned.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Active<wbr>Trusted<wbr>Signers<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}The key pair IDs that CloudFront is aware of for
each trusted signer, if the distribution is set up to serve private content
with signed URLs.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Aliases<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}Extra CNAMEs (alternate domain names), if any, for
this distribution.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The ARN (Amazon Resource Name) for the distribution. For example: arn:aws:cloudfront::123456789012:distribution/EDFDVBD632BHDS5, where 123456789012 is your AWS account ID.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Caller<wbr>Reference<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Internal value used by CloudFront to allow future
updates to the distribution configuration.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Comment<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Any comments you want to include about the
distribution.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Custom<wbr>Error<wbr>Responses<span class="property-indicator"></span>
        <span class="property-type"><a href="#distributioncustomerrorresponse">[]Distribution<wbr>Custom<wbr>Error<wbr>Response</a></span>
    </dt>
    <dd>{{% md %}}One or more custom error response elements (multiples allowed).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Default<wbr>Cache<wbr>Behavior<span class="property-indicator"></span>
        <span class="property-type"><a href="#distributiondefaultcachebehavior">*Distribution<wbr>Default<wbr>Cache<wbr>Behavior</a></span>
    </dt>
    <dd>{{% md %}}The default cache behavior for this distribution (maximum
one).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Default<wbr>Root<wbr>Object<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The object that you want CloudFront to
return (for example, index.html) when an end user requests the root URL.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Domain<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The DNS domain name of either the S3 bucket, or
web site of your custom origin.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Enabled<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Whether the distribution is enabled to accept end
user requests for content.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Etag<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The current version of the distribution&#39;s information. For example:
`E2QWRUHAPOMQZL`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Hosted<wbr>Zone<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The CloudFront Route 53 zone ID that can be used to
route an [Alias Resource Record Set][7] to. This attribute is simply an
alias for the zone ID `Z2FDTNDATAQYW2`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Http<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The maximum HTTP version to support on the
distribution. Allowed values are `http1.1` and `http2`. The default is
`http2`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">In<wbr>Progress<wbr>Validation<wbr>Batches<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The number of invalidation batches
currently in progress.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Is<wbr>Ipv6Enabled<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Whether the IPv6 is enabled for the distribution.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Last<wbr>Modified<wbr>Time<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The date and time the distribution was last modified.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Logging<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#distributionloggingconfig">*Distribution<wbr>Logging<wbr>Config</a></span>
    </dt>
    <dd>{{% md %}}The logging
configuration that controls how logs are written
to your distribution (maximum one).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ordered<wbr>Cache<wbr>Behaviors<span class="property-indicator"></span>
        <span class="property-type"><a href="#distributionorderedcachebehavior">[]Distribution<wbr>Ordered<wbr>Cache<wbr>Behavior</a></span>
    </dt>
    <dd>{{% md %}}An ordered list of cache behaviors
resource for this distribution. List from top to bottom
in order of precedence. The topmost cache behavior will have precedence 0.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Origin<wbr>Groups<span class="property-indicator"></span>
        <span class="property-type"><a href="#distributionorigingroup">[]Distribution<wbr>Origin<wbr>Group</a></span>
    </dt>
    <dd>{{% md %}}One or more origin_group for this
distribution (multiples allowed).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Origins<span class="property-indicator"></span>
        <span class="property-type"><a href="#distributionorigin">[]Distribution<wbr>Origin</a></span>
    </dt>
    <dd>{{% md %}}One or more origins for this
distribution (multiples allowed).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Price<wbr>Class<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The price class for this distribution. One of
`PriceClass_All`, `PriceClass_200`, `PriceClass_100`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Restrictions<span class="property-indicator"></span>
        <span class="property-type"><a href="#distributionrestrictions">*Distribution<wbr>Restrictions</a></span>
    </dt>
    <dd>{{% md %}}The restriction
configuration for this distribution (maximum one).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Retain<wbr>On<wbr>Delete<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Disables the distribution instead of
deleting it when destroying the resource. If this is set,
the distribution needs to be deleted manually afterwards. Default: `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Status<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The current status of the distribution. `Deployed` if the
distribution&#39;s information is fully propagated throughout the Amazon
CloudFront system.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Viewer<wbr>Certificate<span class="property-indicator"></span>
        <span class="property-type"><a href="#distributionviewercertificate">*Distribution<wbr>Viewer<wbr>Certificate</a></span>
    </dt>
    <dd>{{% md %}}The SSL
configuration for this distribution (maximum
one).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Wait<wbr>For<wbr>Deployment<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}If enabled, the resource will wait for
the distribution status to change from `InProgress` to `Deployed`. Setting
this to`false` will skip the process. Default: `true`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Web<wbr>Acl<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}If you&#39;re using AWS WAF to filter CloudFront
requests, the Id of the AWS WAF web ACL that is associated with the
distribution. The WAF Web ACL must exist in the WAF Global (CloudFront)
region and the credentials configuring this argument must have
`waf:GetWebACL` permissions assigned.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">active<wbr>Trusted<wbr>Signers<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}The key pair IDs that CloudFront is aware of for
each trusted signer, if the distribution is set up to serve private content
with signed URLs.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">aliases<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}Extra CNAMEs (alternate domain names), if any, for
this distribution.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ARN (Amazon Resource Name) for the distribution. For example: arn:aws:cloudfront::123456789012:distribution/EDFDVBD632BHDS5, where 123456789012 is your AWS account ID.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">caller<wbr>Reference<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Internal value used by CloudFront to allow future
updates to the distribution configuration.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">comment<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Any comments you want to include about the
distribution.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">custom<wbr>Error<wbr>Responses<span class="property-indicator"></span>
        <span class="property-type"><a href="#distributioncustomerrorresponse">Distribution<wbr>Custom<wbr>Error<wbr>Response[]?</a></span>
    </dt>
    <dd>{{% md %}}One or more custom error response elements (multiples allowed).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">default<wbr>Cache<wbr>Behavior<span class="property-indicator"></span>
        <span class="property-type"><a href="#distributiondefaultcachebehavior">Distribution<wbr>Default<wbr>Cache<wbr>Behavior?</a></span>
    </dt>
    <dd>{{% md %}}The default cache behavior for this distribution (maximum
one).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">default<wbr>Root<wbr>Object<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The object that you want CloudFront to
return (for example, index.html) when an end user requests the root URL.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">domain<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The DNS domain name of either the S3 bucket, or
web site of your custom origin.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">enabled<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Whether the distribution is enabled to accept end
user requests for content.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">etag<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The current version of the distribution&#39;s information. For example:
`E2QWRUHAPOMQZL`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">hosted<wbr>Zone<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The CloudFront Route 53 zone ID that can be used to
route an [Alias Resource Record Set][7] to. This attribute is simply an
alias for the zone ID `Z2FDTNDATAQYW2`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">http<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The maximum HTTP version to support on the
distribution. Allowed values are `http1.1` and `http2`. The default is
`http2`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">in<wbr>Progress<wbr>Validation<wbr>Batches<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The number of invalidation batches
currently in progress.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">is<wbr>Ipv6Enabled<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Whether the IPv6 is enabled for the distribution.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">last<wbr>Modified<wbr>Time<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The date and time the distribution was last modified.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">logging<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#distributionloggingconfig">Distribution<wbr>Logging<wbr>Config?</a></span>
    </dt>
    <dd>{{% md %}}The logging
configuration that controls how logs are written
to your distribution (maximum one).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ordered<wbr>Cache<wbr>Behaviors<span class="property-indicator"></span>
        <span class="property-type"><a href="#distributionorderedcachebehavior">Distribution<wbr>Ordered<wbr>Cache<wbr>Behavior[]?</a></span>
    </dt>
    <dd>{{% md %}}An ordered list of cache behaviors
resource for this distribution. List from top to bottom
in order of precedence. The topmost cache behavior will have precedence 0.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">origin<wbr>Groups<span class="property-indicator"></span>
        <span class="property-type"><a href="#distributionorigingroup">Distribution<wbr>Origin<wbr>Group[]?</a></span>
    </dt>
    <dd>{{% md %}}One or more origin_group for this
distribution (multiples allowed).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">origins<span class="property-indicator"></span>
        <span class="property-type"><a href="#distributionorigin">Distribution<wbr>Origin[]?</a></span>
    </dt>
    <dd>{{% md %}}One or more origins for this
distribution (multiples allowed).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">price<wbr>Class<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The price class for this distribution. One of
`PriceClass_All`, `PriceClass_200`, `PriceClass_100`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">restrictions<span class="property-indicator"></span>
        <span class="property-type"><a href="#distributionrestrictions">Distribution<wbr>Restrictions?</a></span>
    </dt>
    <dd>{{% md %}}The restriction
configuration for this distribution (maximum one).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">retain<wbr>On<wbr>Delete<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Disables the distribution instead of
deleting it when destroying the resource. If this is set,
the distribution needs to be deleted manually afterwards. Default: `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">status<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The current status of the distribution. `Deployed` if the
distribution&#39;s information is fully propagated throughout the Amazon
CloudFront system.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">viewer<wbr>Certificate<span class="property-indicator"></span>
        <span class="property-type"><a href="#distributionviewercertificate">Distribution<wbr>Viewer<wbr>Certificate?</a></span>
    </dt>
    <dd>{{% md %}}The SSL
configuration for this distribution (maximum
one).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">wait<wbr>For<wbr>Deployment<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}If enabled, the resource will wait for
the distribution status to change from `InProgress` to `Deployed`. Setting
this to`false` will skip the process. Default: `true`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">web<wbr>Acl<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}If you&#39;re using AWS WAF to filter CloudFront
requests, the Id of the AWS WAF web ACL that is associated with the
distribution. The WAF Web ACL must exist in the WAF Global (CloudFront)
region and the credentials configuring this argument must have
`waf:GetWebACL` permissions assigned.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">active_<wbr>trusted_<wbr>signers<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}The key pair IDs that CloudFront is aware of for
each trusted signer, if the distribution is set up to serve private content
with signed URLs.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">aliases<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}Extra CNAMEs (alternate domain names), if any, for
this distribution.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ARN (Amazon Resource Name) for the distribution. For example: arn:aws:cloudfront::123456789012:distribution/EDFDVBD632BHDS5, where 123456789012 is your AWS account ID.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">caller_<wbr>reference<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Internal value used by CloudFront to allow future
updates to the distribution configuration.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">comment<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Any comments you want to include about the
distribution.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">custom_<wbr>error_<wbr>responses<span class="property-indicator"></span>
        <span class="property-type"><a href="#distributioncustomerrorresponse">List[Distribution<wbr>Custom<wbr>Error<wbr>Response]</a></span>
    </dt>
    <dd>{{% md %}}One or more custom error response elements (multiples allowed).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">default_<wbr>cache_<wbr>behavior<span class="property-indicator"></span>
        <span class="property-type"><a href="#distributiondefaultcachebehavior">Dict[Distribution<wbr>Default<wbr>Cache<wbr>Behavior]</a></span>
    </dt>
    <dd>{{% md %}}The default cache behavior for this distribution (maximum
one).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">default_<wbr>root_<wbr>object<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The object that you want CloudFront to
return (for example, index.html) when an end user requests the root URL.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">domain_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The DNS domain name of either the S3 bucket, or
web site of your custom origin.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">enabled<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Whether the distribution is enabled to accept end
user requests for content.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">etag<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The current version of the distribution&#39;s information. For example:
`E2QWRUHAPOMQZL`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">hosted_<wbr>zone_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The CloudFront Route 53 zone ID that can be used to
route an [Alias Resource Record Set][7] to. This attribute is simply an
alias for the zone ID `Z2FDTNDATAQYW2`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">http_<wbr>version<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The maximum HTTP version to support on the
distribution. Allowed values are `http1.1` and `http2`. The default is
`http2`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">in_<wbr>progress_<wbr>validation_<wbr>batches<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The number of invalidation batches
currently in progress.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">is_<wbr>ipv6_<wbr>enabled<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Whether the IPv6 is enabled for the distribution.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">last_<wbr>modified_<wbr>time<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The date and time the distribution was last modified.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">logging_<wbr>config<span class="property-indicator"></span>
        <span class="property-type"><a href="#distributionloggingconfig">Dict[Distribution<wbr>Logging<wbr>Config]</a></span>
    </dt>
    <dd>{{% md %}}The logging
configuration that controls how logs are written
to your distribution (maximum one).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ordered_<wbr>cache_<wbr>behaviors<span class="property-indicator"></span>
        <span class="property-type"><a href="#distributionorderedcachebehavior">List[Distribution<wbr>Ordered<wbr>Cache<wbr>Behavior]</a></span>
    </dt>
    <dd>{{% md %}}An ordered list of cache behaviors
resource for this distribution. List from top to bottom
in order of precedence. The topmost cache behavior will have precedence 0.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">origin_<wbr>groups<span class="property-indicator"></span>
        <span class="property-type"><a href="#distributionorigingroup">List[Distribution<wbr>Origin<wbr>Group]</a></span>
    </dt>
    <dd>{{% md %}}One or more origin_group for this
distribution (multiples allowed).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">origins<span class="property-indicator"></span>
        <span class="property-type"><a href="#distributionorigin">List[Distribution<wbr>Origin]</a></span>
    </dt>
    <dd>{{% md %}}One or more origins for this
distribution (multiples allowed).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">price_<wbr>class<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The price class for this distribution. One of
`PriceClass_All`, `PriceClass_200`, `PriceClass_100`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">restrictions<span class="property-indicator"></span>
        <span class="property-type"><a href="#distributionrestrictions">Dict[Distribution<wbr>Restrictions]</a></span>
    </dt>
    <dd>{{% md %}}The restriction
configuration for this distribution (maximum one).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">retain_<wbr>on_<wbr>delete<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Disables the distribution instead of
deleting it when destroying the resource. If this is set,
the distribution needs to be deleted manually afterwards. Default: `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">status<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The current status of the distribution. `Deployed` if the
distribution&#39;s information is fully propagated throughout the Amazon
CloudFront system.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">viewer_<wbr>certificate<span class="property-indicator"></span>
        <span class="property-type"><a href="#distributionviewercertificate">Dict[Distribution<wbr>Viewer<wbr>Certificate]</a></span>
    </dt>
    <dd>{{% md %}}The SSL
configuration for this distribution (maximum
one).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">wait_<wbr>for_<wbr>deployment<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}If enabled, the resource will wait for
the distribution status to change from `InProgress` to `Deployed`. Setting
this to`false` will skip the process. Default: `true`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">web_<wbr>acl_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}If you&#39;re using AWS WAF to filter CloudFront
requests, the Id of the AWS WAF web ACL that is associated with the
distribution. The WAF Web ACL must exist in the WAF Global (CloudFront)
region and the credentials configuring this argument must have
`waf:GetWebACL` permissions assigned.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}







## Supporting Types

#### DistributionCustomErrorResponse
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#DistributionCustomErrorResponse">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#DistributionCustomErrorResponse">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/cloudfront?tab=doc#DistributionCustomErrorResponseArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/cloudfront?tab=doc#DistributionCustomErrorResponseOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Cloudfront.DistributionCustomErrorResponseArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Cloudfront.DistributionCustomErrorResponse.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Error<wbr>Caching<wbr>Min<wbr>Ttl<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The minimum amount of time you want
HTTP error codes to stay in CloudFront caches before CloudFront queries your
origin to see whether the object has been updated.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Error<wbr>Code<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The 4xx or 5xx HTTP status code that you want to
customize.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Response<wbr>Code<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The HTTP status code that you want CloudFront
to return with the custom error page to the viewer.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Response<wbr>Page<wbr>Path<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The path of the custom error page (for
example, `/custom_404.html`).
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Error<wbr>Caching<wbr>Min<wbr>Ttl<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The minimum amount of time you want
HTTP error codes to stay in CloudFront caches before CloudFront queries your
origin to see whether the object has been updated.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Error<wbr>Code<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The 4xx or 5xx HTTP status code that you want to
customize.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Response<wbr>Code<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The HTTP status code that you want CloudFront
to return with the custom error page to the viewer.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Response<wbr>Page<wbr>Path<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The path of the custom error page (for
example, `/custom_404.html`).
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">error<wbr>Caching<wbr>Min<wbr>Ttl<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The minimum amount of time you want
HTTP error codes to stay in CloudFront caches before CloudFront queries your
origin to see whether the object has been updated.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">error<wbr>Code<span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}The 4xx or 5xx HTTP status code that you want to
customize.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">response<wbr>Code<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The HTTP status code that you want CloudFront
to return with the custom error page to the viewer.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">response<wbr>Page<wbr>Path<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The path of the custom error page (for
example, `/custom_404.html`).
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">error<wbr>Caching<wbr>Min<wbr>Ttl<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The minimum amount of time you want
HTTP error codes to stay in CloudFront caches before CloudFront queries your
origin to see whether the object has been updated.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">error<wbr>Code<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The 4xx or 5xx HTTP status code that you want to
customize.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">response<wbr>Code<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The HTTP status code that you want CloudFront
to return with the custom error page to the viewer.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">response<wbr>Page<wbr>Path<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The path of the custom error page (for
example, `/custom_404.html`).
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### DistributionDefaultCacheBehavior
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#DistributionDefaultCacheBehavior">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#DistributionDefaultCacheBehavior">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/cloudfront?tab=doc#DistributionDefaultCacheBehaviorArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/cloudfront?tab=doc#DistributionDefaultCacheBehaviorOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Cloudfront.DistributionDefaultCacheBehaviorArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Cloudfront.DistributionDefaultCacheBehavior.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Allowed<wbr>Methods<span class="property-indicator"></span>
        <span class="property-type">List<string></span>
    </dt>
    <dd>{{% md %}}Controls which HTTP methods CloudFront
processes and forwards to your Amazon S3 bucket or your custom origin.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Cached<wbr>Methods<span class="property-indicator"></span>
        <span class="property-type">List<string></span>
    </dt>
    <dd>{{% md %}}Controls whether CloudFront caches the
response to requests using the specified HTTP methods.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Compress<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Whether you want CloudFront to automatically
compress content for web requests that include `Accept-Encoding: gzip` in
the request header (default: `false`).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Default<wbr>Ttl<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The default amount of time (in seconds) that an
object is in a CloudFront cache before CloudFront forwards another request
in the absence of an `Cache-Control max-age` or `Expires` header. Defaults to
1 day.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Field<wbr>Level<wbr>Encryption<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Field level encryption configuration ID
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Forwarded<wbr>Values<span class="property-indicator"></span>
        <span class="property-type"><a href="#distributiondefaultcachebehaviorforwardedvalues">Distribution<wbr>Default<wbr>Cache<wbr>Behavior<wbr>Forwarded<wbr>Values<wbr>Args</a></span>
    </dt>
    <dd>{{% md %}}The forwarded values configuration that specifies how CloudFront
handles query strings, cookies and headers (maximum one).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Lambda<wbr>Function<wbr>Associations<span class="property-indicator"></span>
        <span class="property-type"><a href="#distributiondefaultcachebehaviorlambdafunctionassociation">List&lt;Distribution<wbr>Default<wbr>Cache<wbr>Behavior<wbr>Lambda<wbr>Function<wbr>Association<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}A config block that triggers a lambda function with
specific actions. Defined below, maximum 4.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Max<wbr>Ttl<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The maximum amount of time (in seconds) that an
object is in a CloudFront cache before CloudFront forwards another request
to your origin to determine whether the object has been updated. Only
effective in the presence of `Cache-Control max-age`, `Cache-Control
s-maxage`, and `Expires` headers. Defaults to 365 days.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Min<wbr>Ttl<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The minimum amount of time that you want objects to
stay in CloudFront caches before CloudFront queries your origin to see
whether the object has been updated. Defaults to 0 seconds.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Smooth<wbr>Streaming<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Indicates whether you want to distribute
media files in Microsoft Smooth Streaming format using the origin that is
associated with this cache behavior.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Target<wbr>Origin<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The value of ID for the origin that you want
CloudFront to route requests to when a request matches the path pattern
either for a cache behavior or for the default cache behavior.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Trusted<wbr>Signers<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}The AWS accounts, if any, that you want to
allow to create signed URLs for private content.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Viewer<wbr>Protocol<wbr>Policy<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Use this element to specify the
protocol that users can use to access the files in the origin specified by
TargetOriginId when a request matches the path pattern in PathPattern. One
of `allow-all`, `https-only`, or `redirect-to-https`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Allowed<wbr>Methods<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}Controls which HTTP methods CloudFront
processes and forwards to your Amazon S3 bucket or your custom origin.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Cached<wbr>Methods<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}Controls whether CloudFront caches the
response to requests using the specified HTTP methods.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Compress<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Whether you want CloudFront to automatically
compress content for web requests that include `Accept-Encoding: gzip` in
the request header (default: `false`).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Default<wbr>Ttl<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The default amount of time (in seconds) that an
object is in a CloudFront cache before CloudFront forwards another request
in the absence of an `Cache-Control max-age` or `Expires` header. Defaults to
1 day.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Field<wbr>Level<wbr>Encryption<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Field level encryption configuration ID
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Forwarded<wbr>Values<span class="property-indicator"></span>
        <span class="property-type"><a href="#distributiondefaultcachebehaviorforwardedvalues">Distribution<wbr>Default<wbr>Cache<wbr>Behavior<wbr>Forwarded<wbr>Values</a></span>
    </dt>
    <dd>{{% md %}}The forwarded values configuration that specifies how CloudFront
handles query strings, cookies and headers (maximum one).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Lambda<wbr>Function<wbr>Associations<span class="property-indicator"></span>
        <span class="property-type"><a href="#distributiondefaultcachebehaviorlambdafunctionassociation">[]Distribution<wbr>Default<wbr>Cache<wbr>Behavior<wbr>Lambda<wbr>Function<wbr>Association</a></span>
    </dt>
    <dd>{{% md %}}A config block that triggers a lambda function with
specific actions. Defined below, maximum 4.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Max<wbr>Ttl<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The maximum amount of time (in seconds) that an
object is in a CloudFront cache before CloudFront forwards another request
to your origin to determine whether the object has been updated. Only
effective in the presence of `Cache-Control max-age`, `Cache-Control
s-maxage`, and `Expires` headers. Defaults to 365 days.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Min<wbr>Ttl<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The minimum amount of time that you want objects to
stay in CloudFront caches before CloudFront queries your origin to see
whether the object has been updated. Defaults to 0 seconds.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Smooth<wbr>Streaming<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Indicates whether you want to distribute
media files in Microsoft Smooth Streaming format using the origin that is
associated with this cache behavior.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Target<wbr>Origin<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The value of ID for the origin that you want
CloudFront to route requests to when a request matches the path pattern
either for a cache behavior or for the default cache behavior.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Trusted<wbr>Signers<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}The AWS accounts, if any, that you want to
allow to create signed URLs for private content.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Viewer<wbr>Protocol<wbr>Policy<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Use this element to specify the
protocol that users can use to access the files in the origin specified by
TargetOriginId when a request matches the path pattern in PathPattern. One
of `allow-all`, `https-only`, or `redirect-to-https`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">allowed<wbr>Methods<span class="property-indicator"></span>
        <span class="property-type">string[]</span>
    </dt>
    <dd>{{% md %}}Controls which HTTP methods CloudFront
processes and forwards to your Amazon S3 bucket or your custom origin.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">cached<wbr>Methods<span class="property-indicator"></span>
        <span class="property-type">string[]</span>
    </dt>
    <dd>{{% md %}}Controls whether CloudFront caches the
response to requests using the specified HTTP methods.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">compress<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Whether you want CloudFront to automatically
compress content for web requests that include `Accept-Encoding: gzip` in
the request header (default: `false`).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">default<wbr>Ttl<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The default amount of time (in seconds) that an
object is in a CloudFront cache before CloudFront forwards another request
in the absence of an `Cache-Control max-age` or `Expires` header. Defaults to
1 day.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">field<wbr>Level<wbr>Encryption<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Field level encryption configuration ID
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">forwarded<wbr>Values<span class="property-indicator"></span>
        <span class="property-type"><a href="#distributiondefaultcachebehaviorforwardedvalues">Distribution<wbr>Default<wbr>Cache<wbr>Behavior<wbr>Forwarded<wbr>Values</a></span>
    </dt>
    <dd>{{% md %}}The forwarded values configuration that specifies how CloudFront
handles query strings, cookies and headers (maximum one).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">lambda<wbr>Function<wbr>Associations<span class="property-indicator"></span>
        <span class="property-type"><a href="#distributiondefaultcachebehaviorlambdafunctionassociation">Distribution<wbr>Default<wbr>Cache<wbr>Behavior<wbr>Lambda<wbr>Function<wbr>Association[]?</a></span>
    </dt>
    <dd>{{% md %}}A config block that triggers a lambda function with
specific actions. Defined below, maximum 4.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">max<wbr>Ttl<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The maximum amount of time (in seconds) that an
object is in a CloudFront cache before CloudFront forwards another request
to your origin to determine whether the object has been updated. Only
effective in the presence of `Cache-Control max-age`, `Cache-Control
s-maxage`, and `Expires` headers. Defaults to 365 days.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">min<wbr>Ttl<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The minimum amount of time that you want objects to
stay in CloudFront caches before CloudFront queries your origin to see
whether the object has been updated. Defaults to 0 seconds.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">smooth<wbr>Streaming<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Indicates whether you want to distribute
media files in Microsoft Smooth Streaming format using the origin that is
associated with this cache behavior.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">target<wbr>Origin<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The value of ID for the origin that you want
CloudFront to route requests to when a request matches the path pattern
either for a cache behavior or for the default cache behavior.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">trusted<wbr>Signers<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}The AWS accounts, if any, that you want to
allow to create signed URLs for private content.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">viewer<wbr>Protocol<wbr>Policy<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Use this element to specify the
protocol that users can use to access the files in the origin specified by
TargetOriginId when a request matches the path pattern in PathPattern. One
of `allow-all`, `https-only`, or `redirect-to-https`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">allowed<wbr>Methods<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}Controls which HTTP methods CloudFront
processes and forwards to your Amazon S3 bucket or your custom origin.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">cached<wbr>Methods<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}Controls whether CloudFront caches the
response to requests using the specified HTTP methods.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">compress<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Whether you want CloudFront to automatically
compress content for web requests that include `Accept-Encoding: gzip` in
the request header (default: `false`).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">default<wbr>Ttl<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The default amount of time (in seconds) that an
object is in a CloudFront cache before CloudFront forwards another request
in the absence of an `Cache-Control max-age` or `Expires` header. Defaults to
1 day.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">field<wbr>Level<wbr>Encryption<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Field level encryption configuration ID
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">forwarded<wbr>Values<span class="property-indicator"></span>
        <span class="property-type"><a href="#distributiondefaultcachebehaviorforwardedvalues">Dict[Distribution<wbr>Default<wbr>Cache<wbr>Behavior<wbr>Forwarded<wbr>Values]</a></span>
    </dt>
    <dd>{{% md %}}The forwarded values configuration that specifies how CloudFront
handles query strings, cookies and headers (maximum one).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">lambda<wbr>Function<wbr>Associations<span class="property-indicator"></span>
        <span class="property-type"><a href="#distributiondefaultcachebehaviorlambdafunctionassociation">List[Distribution<wbr>Default<wbr>Cache<wbr>Behavior<wbr>Lambda<wbr>Function<wbr>Association]</a></span>
    </dt>
    <dd>{{% md %}}A config block that triggers a lambda function with
specific actions. Defined below, maximum 4.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">max<wbr>Ttl<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The maximum amount of time (in seconds) that an
object is in a CloudFront cache before CloudFront forwards another request
to your origin to determine whether the object has been updated. Only
effective in the presence of `Cache-Control max-age`, `Cache-Control
s-maxage`, and `Expires` headers. Defaults to 365 days.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">min<wbr>Ttl<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The minimum amount of time that you want objects to
stay in CloudFront caches before CloudFront queries your origin to see
whether the object has been updated. Defaults to 0 seconds.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">smooth<wbr>Streaming<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Indicates whether you want to distribute
media files in Microsoft Smooth Streaming format using the origin that is
associated with this cache behavior.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">target<wbr>Origin<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The value of ID for the origin that you want
CloudFront to route requests to when a request matches the path pattern
either for a cache behavior or for the default cache behavior.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">trusted<wbr>Signers<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}The AWS accounts, if any, that you want to
allow to create signed URLs for private content.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">viewer<wbr>Protocol<wbr>Policy<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Use this element to specify the
protocol that users can use to access the files in the origin specified by
TargetOriginId when a request matches the path pattern in PathPattern. One
of `allow-all`, `https-only`, or `redirect-to-https`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### DistributionDefaultCacheBehaviorForwardedValues
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#DistributionDefaultCacheBehaviorForwardedValues">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#DistributionDefaultCacheBehaviorForwardedValues">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/cloudfront?tab=doc#DistributionDefaultCacheBehaviorForwardedValuesArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/cloudfront?tab=doc#DistributionDefaultCacheBehaviorForwardedValuesOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Cloudfront.DistributionDefaultCacheBehaviorForwardedValuesArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Cloudfront.DistributionDefaultCacheBehaviorForwardedValues.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Cookies<span class="property-indicator"></span>
        <span class="property-type"><a href="#distributiondefaultcachebehaviorforwardedvaluescookies">Distribution<wbr>Default<wbr>Cache<wbr>Behavior<wbr>Forwarded<wbr>Values<wbr>Cookies<wbr>Args</a></span>
    </dt>
    <dd>{{% md %}}The forwarded values cookies
that specifies how CloudFront handles cookies (maximum one).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Headers<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}Specifies the Headers, if any, that you want
CloudFront to vary upon for this cache behavior. Specify `*` to include all
headers.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Query<wbr>String<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Indicates whether you want CloudFront to forward
query strings to the origin that is associated with this cache behavior.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Query<wbr>String<wbr>Cache<wbr>Keys<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}When specified, along with a value of
`true` for `query_string`, all query strings are forwarded, however only the
query string keys listed in this argument are cached. When omitted with a
value of `true` for `query_string`, all query string keys are cached.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Cookies<span class="property-indicator"></span>
        <span class="property-type"><a href="#distributiondefaultcachebehaviorforwardedvaluescookies">Distribution<wbr>Default<wbr>Cache<wbr>Behavior<wbr>Forwarded<wbr>Values<wbr>Cookies</a></span>
    </dt>
    <dd>{{% md %}}The forwarded values cookies
that specifies how CloudFront handles cookies (maximum one).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Headers<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}Specifies the Headers, if any, that you want
CloudFront to vary upon for this cache behavior. Specify `*` to include all
headers.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Query<wbr>String<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Indicates whether you want CloudFront to forward
query strings to the origin that is associated with this cache behavior.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Query<wbr>String<wbr>Cache<wbr>Keys<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}When specified, along with a value of
`true` for `query_string`, all query strings are forwarded, however only the
query string keys listed in this argument are cached. When omitted with a
value of `true` for `query_string`, all query string keys are cached.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">cookies<span class="property-indicator"></span>
        <span class="property-type"><a href="#distributiondefaultcachebehaviorforwardedvaluescookies">Distribution<wbr>Default<wbr>Cache<wbr>Behavior<wbr>Forwarded<wbr>Values<wbr>Cookies</a></span>
    </dt>
    <dd>{{% md %}}The forwarded values cookies
that specifies how CloudFront handles cookies (maximum one).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">headers<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}Specifies the Headers, if any, that you want
CloudFront to vary upon for this cache behavior. Specify `*` to include all
headers.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">query<wbr>String<span class="property-indicator"></span>
        <span class="property-type">boolean</span>
    </dt>
    <dd>{{% md %}}Indicates whether you want CloudFront to forward
query strings to the origin that is associated with this cache behavior.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">query<wbr>String<wbr>Cache<wbr>Keys<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}When specified, along with a value of
`true` for `query_string`, all query strings are forwarded, however only the
query string keys listed in this argument are cached. When omitted with a
value of `true` for `query_string`, all query string keys are cached.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">cookies<span class="property-indicator"></span>
        <span class="property-type"><a href="#distributiondefaultcachebehaviorforwardedvaluescookies">Dict[Distribution<wbr>Default<wbr>Cache<wbr>Behavior<wbr>Forwarded<wbr>Values<wbr>Cookies]</a></span>
    </dt>
    <dd>{{% md %}}The forwarded values cookies
that specifies how CloudFront handles cookies (maximum one).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">headers<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}Specifies the Headers, if any, that you want
CloudFront to vary upon for this cache behavior. Specify `*` to include all
headers.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">query<wbr>String<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Indicates whether you want CloudFront to forward
query strings to the origin that is associated with this cache behavior.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">query<wbr>String<wbr>Cache<wbr>Keys<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}When specified, along with a value of
`true` for `query_string`, all query strings are forwarded, however only the
query string keys listed in this argument are cached. When omitted with a
value of `true` for `query_string`, all query string keys are cached.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### DistributionDefaultCacheBehaviorForwardedValuesCookies
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#DistributionDefaultCacheBehaviorForwardedValuesCookies">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#DistributionDefaultCacheBehaviorForwardedValuesCookies">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/cloudfront?tab=doc#DistributionDefaultCacheBehaviorForwardedValuesCookiesArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/cloudfront?tab=doc#DistributionDefaultCacheBehaviorForwardedValuesCookiesOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Cloudfront.DistributionDefaultCacheBehaviorForwardedValuesCookiesArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Cloudfront.DistributionDefaultCacheBehaviorForwardedValuesCookies.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Forward<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Specifies whether you want CloudFront to forward
cookies to the origin that is associated with this cache behavior. You can
specify `all`, `none` or `whitelist`. If `whitelist`, you must include the
subsequent `whitelisted_names`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Whitelisted<wbr>Names<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}If you have specified `whitelist` to
`forward`, the whitelisted cookies that you want CloudFront to forward to
your origin.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Forward<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Specifies whether you want CloudFront to forward
cookies to the origin that is associated with this cache behavior. You can
specify `all`, `none` or `whitelist`. If `whitelist`, you must include the
subsequent `whitelisted_names`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Whitelisted<wbr>Names<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}If you have specified `whitelist` to
`forward`, the whitelisted cookies that you want CloudFront to forward to
your origin.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">forward<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Specifies whether you want CloudFront to forward
cookies to the origin that is associated with this cache behavior. You can
specify `all`, `none` or `whitelist`. If `whitelist`, you must include the
subsequent `whitelisted_names`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">whitelisted<wbr>Names<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}If you have specified `whitelist` to
`forward`, the whitelisted cookies that you want CloudFront to forward to
your origin.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">forward<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Specifies whether you want CloudFront to forward
cookies to the origin that is associated with this cache behavior. You can
specify `all`, `none` or `whitelist`. If `whitelist`, you must include the
subsequent `whitelisted_names`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">whitelisted<wbr>Names<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}If you have specified `whitelist` to
`forward`, the whitelisted cookies that you want CloudFront to forward to
your origin.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### DistributionDefaultCacheBehaviorLambdaFunctionAssociation
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#DistributionDefaultCacheBehaviorLambdaFunctionAssociation">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#DistributionDefaultCacheBehaviorLambdaFunctionAssociation">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/cloudfront?tab=doc#DistributionDefaultCacheBehaviorLambdaFunctionAssociationArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/cloudfront?tab=doc#DistributionDefaultCacheBehaviorLambdaFunctionAssociationOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Cloudfront.DistributionDefaultCacheBehaviorLambdaFunctionAssociationArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Cloudfront.DistributionDefaultCacheBehaviorLambdaFunctionAssociation.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Event<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The specific event to trigger this function.
Valid values: `viewer-request`, `origin-request`, `viewer-response`,
`origin-response`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Include<wbr>Body<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}When set to true it exposes the request body to the lambda function. Defaults to false. Valid values: `true`, `false`.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Lambda<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}ARN of the Lambda function.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Event<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The specific event to trigger this function.
Valid values: `viewer-request`, `origin-request`, `viewer-response`,
`origin-response`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Include<wbr>Body<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}When set to true it exposes the request body to the lambda function. Defaults to false. Valid values: `true`, `false`.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Lambda<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}ARN of the Lambda function.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">event<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The specific event to trigger this function.
Valid values: `viewer-request`, `origin-request`, `viewer-response`,
`origin-response`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">include<wbr>Body<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}When set to true it exposes the request body to the lambda function. Defaults to false. Valid values: `true`, `false`.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">lambda<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}ARN of the Lambda function.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">event<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The specific event to trigger this function.
Valid values: `viewer-request`, `origin-request`, `viewer-response`,
`origin-response`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">include<wbr>Body<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}When set to true it exposes the request body to the lambda function. Defaults to false. Valid values: `true`, `false`.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">lambda<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}ARN of the Lambda function.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### DistributionLoggingConfig
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#DistributionLoggingConfig">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#DistributionLoggingConfig">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/cloudfront?tab=doc#DistributionLoggingConfigArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/cloudfront?tab=doc#DistributionLoggingConfigOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Cloudfront.DistributionLoggingConfigArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Cloudfront.DistributionLoggingConfig.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Bucket<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Amazon S3 bucket to store the access logs in, for
example, `myawslogbucket.s3.amazonaws.com`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Include<wbr>Cookies<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Specifies whether you want CloudFront to
include cookies in access logs (default: `false`).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Prefix<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}An optional string that you want CloudFront to prefix
to the access log filenames for this distribution, for example, `myprefix/`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Bucket<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Amazon S3 bucket to store the access logs in, for
example, `myawslogbucket.s3.amazonaws.com`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Include<wbr>Cookies<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Specifies whether you want CloudFront to
include cookies in access logs (default: `false`).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Prefix<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}An optional string that you want CloudFront to prefix
to the access log filenames for this distribution, for example, `myprefix/`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">bucket<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Amazon S3 bucket to store the access logs in, for
example, `myawslogbucket.s3.amazonaws.com`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">include<wbr>Cookies<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Specifies whether you want CloudFront to
include cookies in access logs (default: `false`).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">prefix<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}An optional string that you want CloudFront to prefix
to the access log filenames for this distribution, for example, `myprefix/`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">bucket<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The Amazon S3 bucket to store the access logs in, for
example, `myawslogbucket.s3.amazonaws.com`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">include<wbr>Cookies<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Specifies whether you want CloudFront to
include cookies in access logs (default: `false`).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">prefix<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}An optional string that you want CloudFront to prefix
to the access log filenames for this distribution, for example, `myprefix/`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### DistributionOrderedCacheBehavior
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#DistributionOrderedCacheBehavior">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#DistributionOrderedCacheBehavior">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/cloudfront?tab=doc#DistributionOrderedCacheBehaviorArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/cloudfront?tab=doc#DistributionOrderedCacheBehaviorOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Cloudfront.DistributionOrderedCacheBehaviorArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Cloudfront.DistributionOrderedCacheBehavior.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Allowed<wbr>Methods<span class="property-indicator"></span>
        <span class="property-type">List<string></span>
    </dt>
    <dd>{{% md %}}Controls which HTTP methods CloudFront
processes and forwards to your Amazon S3 bucket or your custom origin.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Cached<wbr>Methods<span class="property-indicator"></span>
        <span class="property-type">List<string></span>
    </dt>
    <dd>{{% md %}}Controls whether CloudFront caches the
response to requests using the specified HTTP methods.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Compress<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Whether you want CloudFront to automatically
compress content for web requests that include `Accept-Encoding: gzip` in
the request header (default: `false`).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Default<wbr>Ttl<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The default amount of time (in seconds) that an
object is in a CloudFront cache before CloudFront forwards another request
in the absence of an `Cache-Control max-age` or `Expires` header. Defaults to
1 day.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Field<wbr>Level<wbr>Encryption<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Field level encryption configuration ID
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Forwarded<wbr>Values<span class="property-indicator"></span>
        <span class="property-type"><a href="#distributionorderedcachebehaviorforwardedvalues">Distribution<wbr>Ordered<wbr>Cache<wbr>Behavior<wbr>Forwarded<wbr>Values<wbr>Args</a></span>
    </dt>
    <dd>{{% md %}}The forwarded values configuration that specifies how CloudFront
handles query strings, cookies and headers (maximum one).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Lambda<wbr>Function<wbr>Associations<span class="property-indicator"></span>
        <span class="property-type"><a href="#distributionorderedcachebehaviorlambdafunctionassociation">List&lt;Distribution<wbr>Ordered<wbr>Cache<wbr>Behavior<wbr>Lambda<wbr>Function<wbr>Association<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}A config block that triggers a lambda function with
specific actions. Defined below, maximum 4.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Max<wbr>Ttl<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The maximum amount of time (in seconds) that an
object is in a CloudFront cache before CloudFront forwards another request
to your origin to determine whether the object has been updated. Only
effective in the presence of `Cache-Control max-age`, `Cache-Control
s-maxage`, and `Expires` headers. Defaults to 365 days.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Min<wbr>Ttl<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The minimum amount of time that you want objects to
stay in CloudFront caches before CloudFront queries your origin to see
whether the object has been updated. Defaults to 0 seconds.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Path<wbr>Pattern<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The pattern (for example, `images/*.jpg)` that
specifies which requests you want this cache behavior to apply to.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Smooth<wbr>Streaming<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Indicates whether you want to distribute
media files in Microsoft Smooth Streaming format using the origin that is
associated with this cache behavior.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Target<wbr>Origin<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The value of ID for the origin that you want
CloudFront to route requests to when a request matches the path pattern
either for a cache behavior or for the default cache behavior.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Trusted<wbr>Signers<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}The AWS accounts, if any, that you want to
allow to create signed URLs for private content.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Viewer<wbr>Protocol<wbr>Policy<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Use this element to specify the
protocol that users can use to access the files in the origin specified by
TargetOriginId when a request matches the path pattern in PathPattern. One
of `allow-all`, `https-only`, or `redirect-to-https`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Allowed<wbr>Methods<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}Controls which HTTP methods CloudFront
processes and forwards to your Amazon S3 bucket or your custom origin.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Cached<wbr>Methods<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}Controls whether CloudFront caches the
response to requests using the specified HTTP methods.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Compress<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Whether you want CloudFront to automatically
compress content for web requests that include `Accept-Encoding: gzip` in
the request header (default: `false`).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Default<wbr>Ttl<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The default amount of time (in seconds) that an
object is in a CloudFront cache before CloudFront forwards another request
in the absence of an `Cache-Control max-age` or `Expires` header. Defaults to
1 day.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Field<wbr>Level<wbr>Encryption<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Field level encryption configuration ID
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Forwarded<wbr>Values<span class="property-indicator"></span>
        <span class="property-type"><a href="#distributionorderedcachebehaviorforwardedvalues">Distribution<wbr>Ordered<wbr>Cache<wbr>Behavior<wbr>Forwarded<wbr>Values</a></span>
    </dt>
    <dd>{{% md %}}The forwarded values configuration that specifies how CloudFront
handles query strings, cookies and headers (maximum one).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Lambda<wbr>Function<wbr>Associations<span class="property-indicator"></span>
        <span class="property-type"><a href="#distributionorderedcachebehaviorlambdafunctionassociation">[]Distribution<wbr>Ordered<wbr>Cache<wbr>Behavior<wbr>Lambda<wbr>Function<wbr>Association</a></span>
    </dt>
    <dd>{{% md %}}A config block that triggers a lambda function with
specific actions. Defined below, maximum 4.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Max<wbr>Ttl<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The maximum amount of time (in seconds) that an
object is in a CloudFront cache before CloudFront forwards another request
to your origin to determine whether the object has been updated. Only
effective in the presence of `Cache-Control max-age`, `Cache-Control
s-maxage`, and `Expires` headers. Defaults to 365 days.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Min<wbr>Ttl<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The minimum amount of time that you want objects to
stay in CloudFront caches before CloudFront queries your origin to see
whether the object has been updated. Defaults to 0 seconds.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Path<wbr>Pattern<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The pattern (for example, `images/*.jpg)` that
specifies which requests you want this cache behavior to apply to.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Smooth<wbr>Streaming<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Indicates whether you want to distribute
media files in Microsoft Smooth Streaming format using the origin that is
associated with this cache behavior.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Target<wbr>Origin<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The value of ID for the origin that you want
CloudFront to route requests to when a request matches the path pattern
either for a cache behavior or for the default cache behavior.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Trusted<wbr>Signers<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}The AWS accounts, if any, that you want to
allow to create signed URLs for private content.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Viewer<wbr>Protocol<wbr>Policy<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Use this element to specify the
protocol that users can use to access the files in the origin specified by
TargetOriginId when a request matches the path pattern in PathPattern. One
of `allow-all`, `https-only`, or `redirect-to-https`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">allowed<wbr>Methods<span class="property-indicator"></span>
        <span class="property-type">string[]</span>
    </dt>
    <dd>{{% md %}}Controls which HTTP methods CloudFront
processes and forwards to your Amazon S3 bucket or your custom origin.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">cached<wbr>Methods<span class="property-indicator"></span>
        <span class="property-type">string[]</span>
    </dt>
    <dd>{{% md %}}Controls whether CloudFront caches the
response to requests using the specified HTTP methods.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">compress<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Whether you want CloudFront to automatically
compress content for web requests that include `Accept-Encoding: gzip` in
the request header (default: `false`).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">default<wbr>Ttl<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The default amount of time (in seconds) that an
object is in a CloudFront cache before CloudFront forwards another request
in the absence of an `Cache-Control max-age` or `Expires` header. Defaults to
1 day.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">field<wbr>Level<wbr>Encryption<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Field level encryption configuration ID
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">forwarded<wbr>Values<span class="property-indicator"></span>
        <span class="property-type"><a href="#distributionorderedcachebehaviorforwardedvalues">Distribution<wbr>Ordered<wbr>Cache<wbr>Behavior<wbr>Forwarded<wbr>Values</a></span>
    </dt>
    <dd>{{% md %}}The forwarded values configuration that specifies how CloudFront
handles query strings, cookies and headers (maximum one).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">lambda<wbr>Function<wbr>Associations<span class="property-indicator"></span>
        <span class="property-type"><a href="#distributionorderedcachebehaviorlambdafunctionassociation">Distribution<wbr>Ordered<wbr>Cache<wbr>Behavior<wbr>Lambda<wbr>Function<wbr>Association[]?</a></span>
    </dt>
    <dd>{{% md %}}A config block that triggers a lambda function with
specific actions. Defined below, maximum 4.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">max<wbr>Ttl<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The maximum amount of time (in seconds) that an
object is in a CloudFront cache before CloudFront forwards another request
to your origin to determine whether the object has been updated. Only
effective in the presence of `Cache-Control max-age`, `Cache-Control
s-maxage`, and `Expires` headers. Defaults to 365 days.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">min<wbr>Ttl<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The minimum amount of time that you want objects to
stay in CloudFront caches before CloudFront queries your origin to see
whether the object has been updated. Defaults to 0 seconds.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">path<wbr>Pattern<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The pattern (for example, `images/*.jpg)` that
specifies which requests you want this cache behavior to apply to.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">smooth<wbr>Streaming<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Indicates whether you want to distribute
media files in Microsoft Smooth Streaming format using the origin that is
associated with this cache behavior.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">target<wbr>Origin<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The value of ID for the origin that you want
CloudFront to route requests to when a request matches the path pattern
either for a cache behavior or for the default cache behavior.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">trusted<wbr>Signers<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}The AWS accounts, if any, that you want to
allow to create signed URLs for private content.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">viewer<wbr>Protocol<wbr>Policy<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Use this element to specify the
protocol that users can use to access the files in the origin specified by
TargetOriginId when a request matches the path pattern in PathPattern. One
of `allow-all`, `https-only`, or `redirect-to-https`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">allowed<wbr>Methods<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}Controls which HTTP methods CloudFront
processes and forwards to your Amazon S3 bucket or your custom origin.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">cached<wbr>Methods<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}Controls whether CloudFront caches the
response to requests using the specified HTTP methods.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">compress<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Whether you want CloudFront to automatically
compress content for web requests that include `Accept-Encoding: gzip` in
the request header (default: `false`).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">default<wbr>Ttl<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The default amount of time (in seconds) that an
object is in a CloudFront cache before CloudFront forwards another request
in the absence of an `Cache-Control max-age` or `Expires` header. Defaults to
1 day.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">field<wbr>Level<wbr>Encryption<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Field level encryption configuration ID
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">forwarded<wbr>Values<span class="property-indicator"></span>
        <span class="property-type"><a href="#distributionorderedcachebehaviorforwardedvalues">Dict[Distribution<wbr>Ordered<wbr>Cache<wbr>Behavior<wbr>Forwarded<wbr>Values]</a></span>
    </dt>
    <dd>{{% md %}}The forwarded values configuration that specifies how CloudFront
handles query strings, cookies and headers (maximum one).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">lambda<wbr>Function<wbr>Associations<span class="property-indicator"></span>
        <span class="property-type"><a href="#distributionorderedcachebehaviorlambdafunctionassociation">List[Distribution<wbr>Ordered<wbr>Cache<wbr>Behavior<wbr>Lambda<wbr>Function<wbr>Association]</a></span>
    </dt>
    <dd>{{% md %}}A config block that triggers a lambda function with
specific actions. Defined below, maximum 4.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">max<wbr>Ttl<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The maximum amount of time (in seconds) that an
object is in a CloudFront cache before CloudFront forwards another request
to your origin to determine whether the object has been updated. Only
effective in the presence of `Cache-Control max-age`, `Cache-Control
s-maxage`, and `Expires` headers. Defaults to 365 days.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">min<wbr>Ttl<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The minimum amount of time that you want objects to
stay in CloudFront caches before CloudFront queries your origin to see
whether the object has been updated. Defaults to 0 seconds.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">path<wbr>Pattern<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The pattern (for example, `images/*.jpg)` that
specifies which requests you want this cache behavior to apply to.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">smooth<wbr>Streaming<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Indicates whether you want to distribute
media files in Microsoft Smooth Streaming format using the origin that is
associated with this cache behavior.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">target<wbr>Origin<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The value of ID for the origin that you want
CloudFront to route requests to when a request matches the path pattern
either for a cache behavior or for the default cache behavior.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">trusted<wbr>Signers<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}The AWS accounts, if any, that you want to
allow to create signed URLs for private content.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">viewer<wbr>Protocol<wbr>Policy<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Use this element to specify the
protocol that users can use to access the files in the origin specified by
TargetOriginId when a request matches the path pattern in PathPattern. One
of `allow-all`, `https-only`, or `redirect-to-https`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### DistributionOrderedCacheBehaviorForwardedValues
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#DistributionOrderedCacheBehaviorForwardedValues">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#DistributionOrderedCacheBehaviorForwardedValues">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/cloudfront?tab=doc#DistributionOrderedCacheBehaviorForwardedValuesArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/cloudfront?tab=doc#DistributionOrderedCacheBehaviorForwardedValuesOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Cloudfront.DistributionOrderedCacheBehaviorForwardedValuesArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Cloudfront.DistributionOrderedCacheBehaviorForwardedValues.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Cookies<span class="property-indicator"></span>
        <span class="property-type"><a href="#distributionorderedcachebehaviorforwardedvaluescookies">Distribution<wbr>Ordered<wbr>Cache<wbr>Behavior<wbr>Forwarded<wbr>Values<wbr>Cookies<wbr>Args</a></span>
    </dt>
    <dd>{{% md %}}The forwarded values cookies
that specifies how CloudFront handles cookies (maximum one).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Headers<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}Specifies the Headers, if any, that you want
CloudFront to vary upon for this cache behavior. Specify `*` to include all
headers.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Query<wbr>String<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Indicates whether you want CloudFront to forward
query strings to the origin that is associated with this cache behavior.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Query<wbr>String<wbr>Cache<wbr>Keys<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}When specified, along with a value of
`true` for `query_string`, all query strings are forwarded, however only the
query string keys listed in this argument are cached. When omitted with a
value of `true` for `query_string`, all query string keys are cached.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Cookies<span class="property-indicator"></span>
        <span class="property-type"><a href="#distributionorderedcachebehaviorforwardedvaluescookies">Distribution<wbr>Ordered<wbr>Cache<wbr>Behavior<wbr>Forwarded<wbr>Values<wbr>Cookies</a></span>
    </dt>
    <dd>{{% md %}}The forwarded values cookies
that specifies how CloudFront handles cookies (maximum one).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Headers<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}Specifies the Headers, if any, that you want
CloudFront to vary upon for this cache behavior. Specify `*` to include all
headers.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Query<wbr>String<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Indicates whether you want CloudFront to forward
query strings to the origin that is associated with this cache behavior.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Query<wbr>String<wbr>Cache<wbr>Keys<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}When specified, along with a value of
`true` for `query_string`, all query strings are forwarded, however only the
query string keys listed in this argument are cached. When omitted with a
value of `true` for `query_string`, all query string keys are cached.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">cookies<span class="property-indicator"></span>
        <span class="property-type"><a href="#distributionorderedcachebehaviorforwardedvaluescookies">Distribution<wbr>Ordered<wbr>Cache<wbr>Behavior<wbr>Forwarded<wbr>Values<wbr>Cookies</a></span>
    </dt>
    <dd>{{% md %}}The forwarded values cookies
that specifies how CloudFront handles cookies (maximum one).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">headers<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}Specifies the Headers, if any, that you want
CloudFront to vary upon for this cache behavior. Specify `*` to include all
headers.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">query<wbr>String<span class="property-indicator"></span>
        <span class="property-type">boolean</span>
    </dt>
    <dd>{{% md %}}Indicates whether you want CloudFront to forward
query strings to the origin that is associated with this cache behavior.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">query<wbr>String<wbr>Cache<wbr>Keys<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}When specified, along with a value of
`true` for `query_string`, all query strings are forwarded, however only the
query string keys listed in this argument are cached. When omitted with a
value of `true` for `query_string`, all query string keys are cached.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">cookies<span class="property-indicator"></span>
        <span class="property-type"><a href="#distributionorderedcachebehaviorforwardedvaluescookies">Dict[Distribution<wbr>Ordered<wbr>Cache<wbr>Behavior<wbr>Forwarded<wbr>Values<wbr>Cookies]</a></span>
    </dt>
    <dd>{{% md %}}The forwarded values cookies
that specifies how CloudFront handles cookies (maximum one).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">headers<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}Specifies the Headers, if any, that you want
CloudFront to vary upon for this cache behavior. Specify `*` to include all
headers.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">query<wbr>String<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Indicates whether you want CloudFront to forward
query strings to the origin that is associated with this cache behavior.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">query<wbr>String<wbr>Cache<wbr>Keys<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}When specified, along with a value of
`true` for `query_string`, all query strings are forwarded, however only the
query string keys listed in this argument are cached. When omitted with a
value of `true` for `query_string`, all query string keys are cached.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### DistributionOrderedCacheBehaviorForwardedValuesCookies
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#DistributionOrderedCacheBehaviorForwardedValuesCookies">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#DistributionOrderedCacheBehaviorForwardedValuesCookies">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/cloudfront?tab=doc#DistributionOrderedCacheBehaviorForwardedValuesCookiesArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/cloudfront?tab=doc#DistributionOrderedCacheBehaviorForwardedValuesCookiesOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Cloudfront.DistributionOrderedCacheBehaviorForwardedValuesCookiesArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Cloudfront.DistributionOrderedCacheBehaviorForwardedValuesCookies.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Forward<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Specifies whether you want CloudFront to forward
cookies to the origin that is associated with this cache behavior. You can
specify `all`, `none` or `whitelist`. If `whitelist`, you must include the
subsequent `whitelisted_names`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Whitelisted<wbr>Names<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}If you have specified `whitelist` to
`forward`, the whitelisted cookies that you want CloudFront to forward to
your origin.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Forward<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Specifies whether you want CloudFront to forward
cookies to the origin that is associated with this cache behavior. You can
specify `all`, `none` or `whitelist`. If `whitelist`, you must include the
subsequent `whitelisted_names`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Whitelisted<wbr>Names<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}If you have specified `whitelist` to
`forward`, the whitelisted cookies that you want CloudFront to forward to
your origin.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">forward<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Specifies whether you want CloudFront to forward
cookies to the origin that is associated with this cache behavior. You can
specify `all`, `none` or `whitelist`. If `whitelist`, you must include the
subsequent `whitelisted_names`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">whitelisted<wbr>Names<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}If you have specified `whitelist` to
`forward`, the whitelisted cookies that you want CloudFront to forward to
your origin.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">forward<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Specifies whether you want CloudFront to forward
cookies to the origin that is associated with this cache behavior. You can
specify `all`, `none` or `whitelist`. If `whitelist`, you must include the
subsequent `whitelisted_names`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">whitelisted<wbr>Names<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}If you have specified `whitelist` to
`forward`, the whitelisted cookies that you want CloudFront to forward to
your origin.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### DistributionOrderedCacheBehaviorLambdaFunctionAssociation
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#DistributionOrderedCacheBehaviorLambdaFunctionAssociation">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#DistributionOrderedCacheBehaviorLambdaFunctionAssociation">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/cloudfront?tab=doc#DistributionOrderedCacheBehaviorLambdaFunctionAssociationArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/cloudfront?tab=doc#DistributionOrderedCacheBehaviorLambdaFunctionAssociationOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Cloudfront.DistributionOrderedCacheBehaviorLambdaFunctionAssociationArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Cloudfront.DistributionOrderedCacheBehaviorLambdaFunctionAssociation.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Event<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The specific event to trigger this function.
Valid values: `viewer-request`, `origin-request`, `viewer-response`,
`origin-response`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Include<wbr>Body<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}When set to true it exposes the request body to the lambda function. Defaults to false. Valid values: `true`, `false`.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Lambda<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}ARN of the Lambda function.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Event<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The specific event to trigger this function.
Valid values: `viewer-request`, `origin-request`, `viewer-response`,
`origin-response`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Include<wbr>Body<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}When set to true it exposes the request body to the lambda function. Defaults to false. Valid values: `true`, `false`.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Lambda<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}ARN of the Lambda function.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">event<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The specific event to trigger this function.
Valid values: `viewer-request`, `origin-request`, `viewer-response`,
`origin-response`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">include<wbr>Body<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}When set to true it exposes the request body to the lambda function. Defaults to false. Valid values: `true`, `false`.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">lambda<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}ARN of the Lambda function.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">event<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The specific event to trigger this function.
Valid values: `viewer-request`, `origin-request`, `viewer-response`,
`origin-response`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">include<wbr>Body<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}When set to true it exposes the request body to the lambda function. Defaults to false. Valid values: `true`, `false`.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">lambda<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}ARN of the Lambda function.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### DistributionOrigin
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#DistributionOrigin">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#DistributionOrigin">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/cloudfront?tab=doc#DistributionOriginArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/cloudfront?tab=doc#DistributionOriginOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Cloudfront.DistributionOriginArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Cloudfront.DistributionOrigin.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Custom<wbr>Headers<span class="property-indicator"></span>
        <span class="property-type"><a href="#distributionorigincustomheader">List&lt;Distribution<wbr>Origin<wbr>Custom<wbr>Header<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}One or more sub-resources with `name` and
`value` parameters that specify header data that will be sent to the origin
(multiples allowed).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Custom<wbr>Origin<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#distributionorigincustomoriginconfig">Distribution<wbr>Origin<wbr>Custom<wbr>Origin<wbr>Config<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}The CloudFront custom
origin configuration information. If an S3
origin is required, use `s3_origin_config` instead.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Domain<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The DNS domain name of either the S3 bucket, or
web site of your custom origin.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Origin<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The unique identifier of the member origin
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Origin<wbr>Path<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}An optional element that causes CloudFront to
request your content from a directory in your Amazon S3 bucket or your
custom origin.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">S3Origin<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#distributionorigins3originconfig">Distribution<wbr>Origin<wbr>S3Origin<wbr>Config<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}The CloudFront S3 origin
configuration information. If a custom origin is required, use
`custom_origin_config` instead.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Custom<wbr>Headers<span class="property-indicator"></span>
        <span class="property-type"><a href="#distributionorigincustomheader">[]Distribution<wbr>Origin<wbr>Custom<wbr>Header</a></span>
    </dt>
    <dd>{{% md %}}One or more sub-resources with `name` and
`value` parameters that specify header data that will be sent to the origin
(multiples allowed).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Custom<wbr>Origin<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#distributionorigincustomoriginconfig">*Distribution<wbr>Origin<wbr>Custom<wbr>Origin<wbr>Config</a></span>
    </dt>
    <dd>{{% md %}}The CloudFront custom
origin configuration information. If an S3
origin is required, use `s3_origin_config` instead.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Domain<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The DNS domain name of either the S3 bucket, or
web site of your custom origin.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Origin<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The unique identifier of the member origin
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Origin<wbr>Path<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}An optional element that causes CloudFront to
request your content from a directory in your Amazon S3 bucket or your
custom origin.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">S3Origin<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#distributionorigins3originconfig">*Distribution<wbr>Origin<wbr>S3Origin<wbr>Config</a></span>
    </dt>
    <dd>{{% md %}}The CloudFront S3 origin
configuration information. If a custom origin is required, use
`custom_origin_config` instead.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">custom<wbr>Headers<span class="property-indicator"></span>
        <span class="property-type"><a href="#distributionorigincustomheader">Distribution<wbr>Origin<wbr>Custom<wbr>Header[]?</a></span>
    </dt>
    <dd>{{% md %}}One or more sub-resources with `name` and
`value` parameters that specify header data that will be sent to the origin
(multiples allowed).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">custom<wbr>Origin<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#distributionorigincustomoriginconfig">Distribution<wbr>Origin<wbr>Custom<wbr>Origin<wbr>Config?</a></span>
    </dt>
    <dd>{{% md %}}The CloudFront custom
origin configuration information. If an S3
origin is required, use `s3_origin_config` instead.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">domain<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The DNS domain name of either the S3 bucket, or
web site of your custom origin.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">origin<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The unique identifier of the member origin
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">origin<wbr>Path<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}An optional element that causes CloudFront to
request your content from a directory in your Amazon S3 bucket or your
custom origin.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">s3Origin<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#distributionorigins3originconfig">Distribution<wbr>Origin<wbr>S3Origin<wbr>Config?</a></span>
    </dt>
    <dd>{{% md %}}The CloudFront S3 origin
configuration information. If a custom origin is required, use
`custom_origin_config` instead.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">custom<wbr>Headers<span class="property-indicator"></span>
        <span class="property-type"><a href="#distributionorigincustomheader">List[Distribution<wbr>Origin<wbr>Custom<wbr>Header]</a></span>
    </dt>
    <dd>{{% md %}}One or more sub-resources with `name` and
`value` parameters that specify header data that will be sent to the origin
(multiples allowed).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">custom<wbr>Origin<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#distributionorigincustomoriginconfig">Dict[Distribution<wbr>Origin<wbr>Custom<wbr>Origin<wbr>Config]</a></span>
    </dt>
    <dd>{{% md %}}The CloudFront custom
origin configuration information. If an S3
origin is required, use `s3_origin_config` instead.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">domain_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The DNS domain name of either the S3 bucket, or
web site of your custom origin.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">origin<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The unique identifier of the member origin
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">origin<wbr>Path<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}An optional element that causes CloudFront to
request your content from a directory in your Amazon S3 bucket or your
custom origin.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">s3Origin<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#distributionorigins3originconfig">Dict[Distribution<wbr>Origin<wbr>S3Origin<wbr>Config]</a></span>
    </dt>
    <dd>{{% md %}}The CloudFront S3 origin
configuration information. If a custom origin is required, use
`custom_origin_config` instead.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### DistributionOriginCustomHeader
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#DistributionOriginCustomHeader">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#DistributionOriginCustomHeader">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/cloudfront?tab=doc#DistributionOriginCustomHeaderArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/cloudfront?tab=doc#DistributionOriginCustomHeaderOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Cloudfront.DistributionOriginCustomHeaderArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Cloudfront.DistributionOriginCustomHeader.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Value<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Value<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">value<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">value<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### DistributionOriginCustomOriginConfig
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#DistributionOriginCustomOriginConfig">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#DistributionOriginCustomOriginConfig">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/cloudfront?tab=doc#DistributionOriginCustomOriginConfigArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/cloudfront?tab=doc#DistributionOriginCustomOriginConfigOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Cloudfront.DistributionOriginCustomOriginConfigArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Cloudfront.DistributionOriginCustomOriginConfig.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Http<wbr>Port<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The HTTP port the custom origin listens on.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Https<wbr>Port<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The HTTPS port the custom origin listens on.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Origin<wbr>Keepalive<wbr>Timeout<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The Custom KeepAlive timeout, in seconds. By default, AWS enforces a limit of `60`. But you can request an [increase](http://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/RequestAndResponseBehaviorCustomOrigin.html#request-custom-request-timeout).
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Origin<wbr>Protocol<wbr>Policy<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The origin protocol policy to apply to
your origin. One of `http-only`, `https-only`, or `match-viewer`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Origin<wbr>Read<wbr>Timeout<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The Custom Read timeout, in seconds. By default, AWS enforces a limit of `60`. But you can request an [increase](http://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/RequestAndResponseBehaviorCustomOrigin.html#request-custom-request-timeout).
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Origin<wbr>Ssl<wbr>Protocols<span class="property-indicator"></span>
        <span class="property-type">List<string></span>
    </dt>
    <dd>{{% md %}}The SSL/TLS protocols that you want
CloudFront to use when communicating with your origin over HTTPS. A list of
one or more of `SSLv3`, `TLSv1`, `TLSv1.1`, and `TLSv1.2`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Http<wbr>Port<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The HTTP port the custom origin listens on.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Https<wbr>Port<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The HTTPS port the custom origin listens on.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Origin<wbr>Keepalive<wbr>Timeout<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The Custom KeepAlive timeout, in seconds. By default, AWS enforces a limit of `60`. But you can request an [increase](http://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/RequestAndResponseBehaviorCustomOrigin.html#request-custom-request-timeout).
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Origin<wbr>Protocol<wbr>Policy<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The origin protocol policy to apply to
your origin. One of `http-only`, `https-only`, or `match-viewer`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Origin<wbr>Read<wbr>Timeout<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The Custom Read timeout, in seconds. By default, AWS enforces a limit of `60`. But you can request an [increase](http://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/RequestAndResponseBehaviorCustomOrigin.html#request-custom-request-timeout).
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Origin<wbr>Ssl<wbr>Protocols<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}The SSL/TLS protocols that you want
CloudFront to use when communicating with your origin over HTTPS. A list of
one or more of `SSLv3`, `TLSv1`, `TLSv1.1`, and `TLSv1.2`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">http<wbr>Port<span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}The HTTP port the custom origin listens on.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">https<wbr>Port<span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}The HTTPS port the custom origin listens on.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">origin<wbr>Keepalive<wbr>Timeout<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The Custom KeepAlive timeout, in seconds. By default, AWS enforces a limit of `60`. But you can request an [increase](http://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/RequestAndResponseBehaviorCustomOrigin.html#request-custom-request-timeout).
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">origin<wbr>Protocol<wbr>Policy<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The origin protocol policy to apply to
your origin. One of `http-only`, `https-only`, or `match-viewer`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">origin<wbr>Read<wbr>Timeout<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The Custom Read timeout, in seconds. By default, AWS enforces a limit of `60`. But you can request an [increase](http://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/RequestAndResponseBehaviorCustomOrigin.html#request-custom-request-timeout).
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">origin<wbr>Ssl<wbr>Protocols<span class="property-indicator"></span>
        <span class="property-type">string[]</span>
    </dt>
    <dd>{{% md %}}The SSL/TLS protocols that you want
CloudFront to use when communicating with your origin over HTTPS. A list of
one or more of `SSLv3`, `TLSv1`, `TLSv1.1`, and `TLSv1.2`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">http<wbr>Port<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The HTTP port the custom origin listens on.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">https<wbr>Port<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The HTTPS port the custom origin listens on.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">origin<wbr>Keepalive<wbr>Timeout<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The Custom KeepAlive timeout, in seconds. By default, AWS enforces a limit of `60`. But you can request an [increase](http://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/RequestAndResponseBehaviorCustomOrigin.html#request-custom-request-timeout).
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">origin<wbr>Protocol<wbr>Policy<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The origin protocol policy to apply to
your origin. One of `http-only`, `https-only`, or `match-viewer`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">origin<wbr>Read<wbr>Timeout<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The Custom Read timeout, in seconds. By default, AWS enforces a limit of `60`. But you can request an [increase](http://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/RequestAndResponseBehaviorCustomOrigin.html#request-custom-request-timeout).
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">origin<wbr>Ssl<wbr>Protocols<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}The SSL/TLS protocols that you want
CloudFront to use when communicating with your origin over HTTPS. A list of
one or more of `SSLv3`, `TLSv1`, `TLSv1.1`, and `TLSv1.2`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### DistributionOriginGroup
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#DistributionOriginGroup">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#DistributionOriginGroup">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/cloudfront?tab=doc#DistributionOriginGroupArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/cloudfront?tab=doc#DistributionOriginGroupOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Cloudfront.DistributionOriginGroupArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Cloudfront.DistributionOriginGroup.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Failover<wbr>Criteria<span class="property-indicator"></span>
        <span class="property-type"><a href="#distributionorigingroupfailovercriteria">Distribution<wbr>Origin<wbr>Group<wbr>Failover<wbr>Criteria<wbr>Args</a></span>
    </dt>
    <dd>{{% md %}}The failover criteria for when to failover to the secondary origin
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Members<span class="property-indicator"></span>
        <span class="property-type"><a href="#distributionorigingroupmember">List&lt;Distribution<wbr>Origin<wbr>Group<wbr>Member<wbr>Args&gt;</a></span>
    </dt>
    <dd>{{% md %}}Ordered member configuration blocks assigned to the origin group, where the first member is the primary origin. You must specify two members.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Origin<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The unique identifier of the member origin
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Failover<wbr>Criteria<span class="property-indicator"></span>
        <span class="property-type"><a href="#distributionorigingroupfailovercriteria">Distribution<wbr>Origin<wbr>Group<wbr>Failover<wbr>Criteria</a></span>
    </dt>
    <dd>{{% md %}}The failover criteria for when to failover to the secondary origin
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Members<span class="property-indicator"></span>
        <span class="property-type"><a href="#distributionorigingroupmember">[]Distribution<wbr>Origin<wbr>Group<wbr>Member</a></span>
    </dt>
    <dd>{{% md %}}Ordered member configuration blocks assigned to the origin group, where the first member is the primary origin. You must specify two members.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Origin<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The unique identifier of the member origin
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">failover<wbr>Criteria<span class="property-indicator"></span>
        <span class="property-type"><a href="#distributionorigingroupfailovercriteria">Distribution<wbr>Origin<wbr>Group<wbr>Failover<wbr>Criteria</a></span>
    </dt>
    <dd>{{% md %}}The failover criteria for when to failover to the secondary origin
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">members<span class="property-indicator"></span>
        <span class="property-type"><a href="#distributionorigingroupmember">Distribution<wbr>Origin<wbr>Group<wbr>Member[]</a></span>
    </dt>
    <dd>{{% md %}}Ordered member configuration blocks assigned to the origin group, where the first member is the primary origin. You must specify two members.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">origin<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The unique identifier of the member origin
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">failover<wbr>Criteria<span class="property-indicator"></span>
        <span class="property-type"><a href="#distributionorigingroupfailovercriteria">Dict[Distribution<wbr>Origin<wbr>Group<wbr>Failover<wbr>Criteria]</a></span>
    </dt>
    <dd>{{% md %}}The failover criteria for when to failover to the secondary origin
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">members<span class="property-indicator"></span>
        <span class="property-type"><a href="#distributionorigingroupmember">List[Distribution<wbr>Origin<wbr>Group<wbr>Member]</a></span>
    </dt>
    <dd>{{% md %}}Ordered member configuration blocks assigned to the origin group, where the first member is the primary origin. You must specify two members.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">origin<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The unique identifier of the member origin
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### DistributionOriginGroupFailoverCriteria
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#DistributionOriginGroupFailoverCriteria">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#DistributionOriginGroupFailoverCriteria">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/cloudfront?tab=doc#DistributionOriginGroupFailoverCriteriaArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/cloudfront?tab=doc#DistributionOriginGroupFailoverCriteriaOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Cloudfront.DistributionOriginGroupFailoverCriteriaArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Cloudfront.DistributionOriginGroupFailoverCriteria.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Status<wbr>Codes<span class="property-indicator"></span>
        <span class="property-type">List<int></span>
    </dt>
    <dd>{{% md %}}A list of HTTP status codes for the origin group
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Status<wbr>Codes<span class="property-indicator"></span>
        <span class="property-type">[]int</span>
    </dt>
    <dd>{{% md %}}A list of HTTP status codes for the origin group
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">status<wbr>Codes<span class="property-indicator"></span>
        <span class="property-type">number[]</span>
    </dt>
    <dd>{{% md %}}A list of HTTP status codes for the origin group
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">status<wbr>Codes<span class="property-indicator"></span>
        <span class="property-type">List[Integer]</span>
    </dt>
    <dd>{{% md %}}A list of HTTP status codes for the origin group
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### DistributionOriginGroupMember
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#DistributionOriginGroupMember">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#DistributionOriginGroupMember">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/cloudfront?tab=doc#DistributionOriginGroupMemberArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/cloudfront?tab=doc#DistributionOriginGroupMemberOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Cloudfront.DistributionOriginGroupMemberArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Cloudfront.DistributionOriginGroupMember.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Origin<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The unique identifier of the member origin
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Origin<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The unique identifier of the member origin
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">origin<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The unique identifier of the member origin
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">origin<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The unique identifier of the member origin
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### DistributionOriginS3OriginConfig
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#DistributionOriginS3OriginConfig">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#DistributionOriginS3OriginConfig">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/cloudfront?tab=doc#DistributionOriginS3OriginConfigArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/cloudfront?tab=doc#DistributionOriginS3OriginConfigOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Cloudfront.DistributionOriginS3OriginConfigArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Cloudfront.DistributionOriginS3OriginConfig.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Origin<wbr>Access<wbr>Identity<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The [CloudFront origin access
identity][5] to associate with the origin.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Origin<wbr>Access<wbr>Identity<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The [CloudFront origin access
identity][5] to associate with the origin.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">origin<wbr>Access<wbr>Identity<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The [CloudFront origin access
identity][5] to associate with the origin.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">origin<wbr>Access<wbr>Identity<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The [CloudFront origin access
identity][5] to associate with the origin.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### DistributionRestrictions
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#DistributionRestrictions">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#DistributionRestrictions">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/cloudfront?tab=doc#DistributionRestrictionsArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/cloudfront?tab=doc#DistributionRestrictionsOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Cloudfront.DistributionRestrictionsArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Cloudfront.DistributionRestrictions.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Geo<wbr>Restriction<span class="property-indicator"></span>
        <span class="property-type"><a href="#distributionrestrictionsgeorestriction">Distribution<wbr>Restrictions<wbr>Geo<wbr>Restriction<wbr>Args</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Geo<wbr>Restriction<span class="property-indicator"></span>
        <span class="property-type"><a href="#distributionrestrictionsgeorestriction">Distribution<wbr>Restrictions<wbr>Geo<wbr>Restriction</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">geo<wbr>Restriction<span class="property-indicator"></span>
        <span class="property-type"><a href="#distributionrestrictionsgeorestriction">Distribution<wbr>Restrictions<wbr>Geo<wbr>Restriction</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">geo<wbr>Restriction<span class="property-indicator"></span>
        <span class="property-type"><a href="#distributionrestrictionsgeorestriction">Dict[Distribution<wbr>Restrictions<wbr>Geo<wbr>Restriction]</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### DistributionRestrictionsGeoRestriction
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#DistributionRestrictionsGeoRestriction">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#DistributionRestrictionsGeoRestriction">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/cloudfront?tab=doc#DistributionRestrictionsGeoRestrictionArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/cloudfront?tab=doc#DistributionRestrictionsGeoRestrictionOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Cloudfront.DistributionRestrictionsGeoRestrictionArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Cloudfront.DistributionRestrictionsGeoRestriction.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Locations<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}The [ISO 3166-1-alpha-2 codes][4] for which you
want CloudFront either to distribute your content (`whitelist`) or not
distribute your content (`blacklist`).
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Restriction<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The method that you want to use to restrict
distribution of your content by country: `none`, `whitelist`, or
`blacklist`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Locations<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}The [ISO 3166-1-alpha-2 codes][4] for which you
want CloudFront either to distribute your content (`whitelist`) or not
distribute your content (`blacklist`).
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Restriction<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The method that you want to use to restrict
distribution of your content by country: `none`, `whitelist`, or
`blacklist`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">locations<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}The [ISO 3166-1-alpha-2 codes][4] for which you
want CloudFront either to distribute your content (`whitelist`) or not
distribute your content (`blacklist`).
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">restriction<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The method that you want to use to restrict
distribution of your content by country: `none`, `whitelist`, or
`blacklist`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">locations<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}The [ISO 3166-1-alpha-2 codes][4] for which you
want CloudFront either to distribute your content (`whitelist`) or not
distribute your content (`blacklist`).
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">restriction<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The method that you want to use to restrict
distribution of your content by country: `none`, `whitelist`, or
`blacklist`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### DistributionViewerCertificate
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#DistributionViewerCertificate">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#DistributionViewerCertificate">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/cloudfront?tab=doc#DistributionViewerCertificateArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/cloudfront?tab=doc#DistributionViewerCertificateOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Cloudfront.DistributionViewerCertificateArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Cloudfront.DistributionViewerCertificate.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Acm<wbr>Certificate<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ARN of the [AWS Certificate Manager][6]
certificate that you wish to use with this distribution. Specify this,
`cloudfront_default_certificate`, or `iam_certificate_id`.  The ACM
certificate must be in  US-EAST-1.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Cloudfront<wbr>Default<wbr>Certificate<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}`true` if you want viewers to use HTTPS
to request your objects and you&#39;re using the CloudFront domain name for your
distribution. Specify this, `acm_certificate_arn`, or `iam_certificate_id`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Iam<wbr>Certificate<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The IAM certificate identifier of the custom viewer
certificate for this distribution if you are using a custom domain. Specify
this, `acm_certificate_arn`, or `cloudfront_default_certificate`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Minimum<wbr>Protocol<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The minimum version of the SSL protocol that
you want CloudFront to use for HTTPS connections. Can only be set if
`cloudfront_default_certificate = false`. One of `SSLv3`, `TLSv1`,
`TLSv1_2016`, `TLSv1.1_2016` or `TLSv1.2_2018`. Default: `TLSv1`. **NOTE**:
If you are using a custom certificate (specified with `acm_certificate_arn`
or `iam_certificate_id`), and have specified `sni-only` in
`ssl_support_method`, `TLSv1` or later must be specified. If you have
specified `vip` in `ssl_support_method`, only `SSLv3` or `TLSv1` can be
specified. If you have specified `cloudfront_default_certificate`, `TLSv1`
must be specified.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ssl<wbr>Support<wbr>Method<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Acm<wbr>Certificate<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The ARN of the [AWS Certificate Manager][6]
certificate that you wish to use with this distribution. Specify this,
`cloudfront_default_certificate`, or `iam_certificate_id`.  The ACM
certificate must be in  US-EAST-1.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Cloudfront<wbr>Default<wbr>Certificate<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}`true` if you want viewers to use HTTPS
to request your objects and you&#39;re using the CloudFront domain name for your
distribution. Specify this, `acm_certificate_arn`, or `iam_certificate_id`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Iam<wbr>Certificate<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The IAM certificate identifier of the custom viewer
certificate for this distribution if you are using a custom domain. Specify
this, `acm_certificate_arn`, or `cloudfront_default_certificate`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Minimum<wbr>Protocol<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The minimum version of the SSL protocol that
you want CloudFront to use for HTTPS connections. Can only be set if
`cloudfront_default_certificate = false`. One of `SSLv3`, `TLSv1`,
`TLSv1_2016`, `TLSv1.1_2016` or `TLSv1.2_2018`. Default: `TLSv1`. **NOTE**:
If you are using a custom certificate (specified with `acm_certificate_arn`
or `iam_certificate_id`), and have specified `sni-only` in
`ssl_support_method`, `TLSv1` or later must be specified. If you have
specified `vip` in `ssl_support_method`, only `SSLv3` or `TLSv1` can be
specified. If you have specified `cloudfront_default_certificate`, `TLSv1`
must be specified.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ssl<wbr>Support<wbr>Method<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">acm<wbr>Certificate<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ARN of the [AWS Certificate Manager][6]
certificate that you wish to use with this distribution. Specify this,
`cloudfront_default_certificate`, or `iam_certificate_id`.  The ACM
certificate must be in  US-EAST-1.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">cloudfront<wbr>Default<wbr>Certificate<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}`true` if you want viewers to use HTTPS
to request your objects and you&#39;re using the CloudFront domain name for your
distribution. Specify this, `acm_certificate_arn`, or `iam_certificate_id`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">iam<wbr>Certificate<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The IAM certificate identifier of the custom viewer
certificate for this distribution if you are using a custom domain. Specify
this, `acm_certificate_arn`, or `cloudfront_default_certificate`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">minimum<wbr>Protocol<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The minimum version of the SSL protocol that
you want CloudFront to use for HTTPS connections. Can only be set if
`cloudfront_default_certificate = false`. One of `SSLv3`, `TLSv1`,
`TLSv1_2016`, `TLSv1.1_2016` or `TLSv1.2_2018`. Default: `TLSv1`. **NOTE**:
If you are using a custom certificate (specified with `acm_certificate_arn`
or `iam_certificate_id`), and have specified `sni-only` in
`ssl_support_method`, `TLSv1` or later must be specified. If you have
specified `vip` in `ssl_support_method`, only `SSLv3` or `TLSv1` can be
specified. If you have specified `cloudfront_default_certificate`, `TLSv1`
must be specified.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ssl<wbr>Support<wbr>Method<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">acm<wbr>Certificate<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ARN of the [AWS Certificate Manager][6]
certificate that you wish to use with this distribution. Specify this,
`cloudfront_default_certificate`, or `iam_certificate_id`.  The ACM
certificate must be in  US-EAST-1.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">cloudfront<wbr>Default<wbr>Certificate<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}`true` if you want viewers to use HTTPS
to request your objects and you&#39;re using the CloudFront domain name for your
distribution. Specify this, `acm_certificate_arn`, or `iam_certificate_id`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">iam<wbr>Certificate<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The IAM certificate identifier of the custom viewer
certificate for this distribution if you are using a custom domain. Specify
this, `acm_certificate_arn`, or `cloudfront_default_certificate`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">minimum<wbr>Protocol<wbr>Version<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The minimum version of the SSL protocol that
you want CloudFront to use for HTTPS connections. Can only be set if
`cloudfront_default_certificate = false`. One of `SSLv3`, `TLSv1`,
`TLSv1_2016`, `TLSv1.1_2016` or `TLSv1.2_2018`. Default: `TLSv1`. **NOTE**:
If you are using a custom certificate (specified with `acm_certificate_arn`
or `iam_certificate_id`), and have specified `sni-only` in
`ssl_support_method`, `TLSv1` or later must be specified. If you have
specified `vip` in `ssl_support_method`, only `SSLv3` or `TLSv1` can be
specified. If you have specified `cloudfront_default_certificate`, `TLSv1`
must be specified.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ssl<wbr>Support<wbr>Method<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}








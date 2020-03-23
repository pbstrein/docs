
---
title: "CertificateAuthority"
block_external_search_index: true
---

Provides a resource to manage AWS Certificate Manager Private Certificate Authorities (ACM PCA Certificate Authorities).

> **NOTE:** Creating this resource will leave the certificate authority in a `PENDING_CERTIFICATE` status, which means it cannot yet issue certificates. To complete this setup, you must fully sign the certificate authority CSR available in the `certificate_signing_request` attribute and import the signed certificate using the AWS SDK, CLI or Console. This provider can support another resource to manage that workflow automatically in the future.

## Example Usage

### Basic

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const example = new aws.acmpca.CertificateAuthority("example", {
    certificateAuthorityConfiguration: {
        keyAlgorithm: "RSA_4096",
        signingAlgorithm: "SHA512WITHRSA",
        subject: {
            commonName: "example.com",
        },
    },
    permanentDeletionTimeInDays: 7,
});
```

### Enable Certificate Revocation List

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const exampleBucket = new aws.s3.Bucket("example", {});
const acmpcaBucketAccess = pulumi.all([exampleBucket.arn, exampleBucket.arn]).apply(([exampleBucketArn, exampleBucketArn1]) => aws.iam.getPolicyDocument({
    statements: [{
        actions: [
            "s3:GetBucketAcl",
            "s3:GetBucketLocation",
            "s3:PutObject",
            "s3:PutObjectAcl",
        ],
        principals: [{
            identifiers: ["acm-pca.amazonaws.com"],
            type: "Service",
        }],
        resources: [
            exampleBucketArn,
            `${exampleBucketArn1}/*`,
        ],
    }],
}));
const exampleBucketPolicy = new aws.s3.BucketPolicy("example", {
    bucket: exampleBucket.id,
    policy: acmpcaBucketAccess.json,
});
const exampleCertificateAuthority = new aws.acmpca.CertificateAuthority("example", {
    certificateAuthorityConfiguration: {
        keyAlgorithm: "RSA_4096",
        signingAlgorithm: "SHA512WITHRSA",
        subject: {
            commonName: "example.com",
        },
    },
    revocationConfiguration: {
        crlConfiguration: {
            customCname: "crl.example.com",
            enabled: true,
            expirationInDays: 7,
            s3BucketName: exampleBucket.id,
        },
    },
}, {dependsOn: [exampleBucketPolicy]});
```

> This content is derived from https://github.com/terraform-providers/terraform-provider-aws/blob/master/website/docs/r/acmpca_certificate_authority.html.markdown.



## Create a CertificateAuthority Resource

{{< chooser language "javascript,typescript,python,go,csharp" / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/acmpca/#CertificateAuthority">CertificateAuthority</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/acmpca/#CertificateAuthorityArgs">CertificateAuthorityArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">CertificateAuthority</span><span class="p">(resource_name, opts=None, </span>certificate_authority_configuration=None<span class="p">, </span>enabled=None<span class="p">, </span>permanent_deletion_time_in_days=None<span class="p">, </span>revocation_configuration=None<span class="p">, </span>tags=None<span class="p">, </span>type=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewCertificateAuthority<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/acmpca?tab=doc#CertificateAuthorityArgs">CertificateAuthorityArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/acmpca?tab=doc#CertificateAuthority">CertificateAuthority</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Acmpca.CertificateAuthority.html">CertificateAuthority</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Acmpca.CertificateAuthorityArgs.html">CertificateAuthorityArgs</a></span> <span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
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
            title="Required">Certificate<wbr>Authority<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#certificateauthoritycertificateauthorityconfiguration">Certificate<wbr>Authority<wbr>Certificate<wbr>Authority<wbr>Configuration<wbr>Args</a></span>
    </dt>
    <dd>{{% md %}}Nested argument containing algorithms and certificate subject information. Defined below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Enabled<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Boolean value that specifies whether certificate revocation lists (CRLs) are enabled. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Permanent<wbr>Deletion<wbr>Time<wbr>In<wbr>Days<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The number of days to make a CA restorable after it has been deleted, must be between 7 to 30 days, with default to 30 days.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Revocation<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#certificateauthorityrevocationconfiguration">Certificate<wbr>Authority<wbr>Revocation<wbr>Configuration<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}Nested argument containing revocation configuration. Defined below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}Specifies a key-value map of user-defined tags that are attached to the certificate authority.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The type of the certificate authority. Defaults to `SUBORDINATE`. Valid values: `ROOT` and `SUBORDINATE`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Certificate<wbr>Authority<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#certificateauthoritycertificateauthorityconfiguration">Certificate<wbr>Authority<wbr>Certificate<wbr>Authority<wbr>Configuration</a></span>
    </dt>
    <dd>{{% md %}}Nested argument containing algorithms and certificate subject information. Defined below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Enabled<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Boolean value that specifies whether certificate revocation lists (CRLs) are enabled. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Permanent<wbr>Deletion<wbr>Time<wbr>In<wbr>Days<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The number of days to make a CA restorable after it has been deleted, must be between 7 to 30 days, with default to 30 days.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Revocation<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#certificateauthorityrevocationconfiguration">*Certificate<wbr>Authority<wbr>Revocation<wbr>Configuration</a></span>
    </dt>
    <dd>{{% md %}}Nested argument containing revocation configuration. Defined below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}Specifies a key-value map of user-defined tags that are attached to the certificate authority.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Type<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The type of the certificate authority. Defaults to `SUBORDINATE`. Valid values: `ROOT` and `SUBORDINATE`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">certificate<wbr>Authority<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#certificateauthoritycertificateauthorityconfiguration">Certificate<wbr>Authority<wbr>Certificate<wbr>Authority<wbr>Configuration</a></span>
    </dt>
    <dd>{{% md %}}Nested argument containing algorithms and certificate subject information. Defined below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">enabled<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Boolean value that specifies whether certificate revocation lists (CRLs) are enabled. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">permanent<wbr>Deletion<wbr>Time<wbr>In<wbr>Days<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The number of days to make a CA restorable after it has been deleted, must be between 7 to 30 days, with default to 30 days.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">revocation<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#certificateauthorityrevocationconfiguration">Certificate<wbr>Authority<wbr>Revocation<wbr>Configuration?</a></span>
    </dt>
    <dd>{{% md %}}Nested argument containing revocation configuration. Defined below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}Specifies a key-value map of user-defined tags that are attached to the certificate authority.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The type of the certificate authority. Defaults to `SUBORDINATE`. Valid values: `ROOT` and `SUBORDINATE`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">certificate_<wbr>authority_<wbr>configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#certificateauthoritycertificateauthorityconfiguration">Dict[Certificate<wbr>Authority<wbr>Certificate<wbr>Authority<wbr>Configuration]</a></span>
    </dt>
    <dd>{{% md %}}Nested argument containing algorithms and certificate subject information. Defined below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">enabled<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Boolean value that specifies whether certificate revocation lists (CRLs) are enabled. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">permanent_<wbr>deletion_<wbr>time_<wbr>in_<wbr>days<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The number of days to make a CA restorable after it has been deleted, must be between 7 to 30 days, with default to 30 days.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">revocation_<wbr>configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#certificateauthorityrevocationconfiguration">Dict[Certificate<wbr>Authority<wbr>Revocation<wbr>Configuration]</a></span>
    </dt>
    <dd>{{% md %}}Nested argument containing revocation configuration. Defined below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}Specifies a key-value map of user-defined tags that are attached to the certificate authority.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The type of the certificate authority. Defaults to `SUBORDINATE`. Valid values: `ROOT` and `SUBORDINATE`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}




## CertificateAuthority Output Properties

The following output properties are available:




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of the certificate authority.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Certificate<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Base64-encoded certificate authority (CA) certificate. Only available after the certificate authority certificate has been imported.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Certificate<wbr>Authority<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#certificateauthoritycertificateauthorityconfiguration">Certificate<wbr>Authority<wbr>Certificate<wbr>Authority<wbr>Configuration</a></span>
    </dt>
    <dd>{{% md %}}Nested argument containing algorithms and certificate subject information. Defined below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Certificate<wbr>Chain<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Base64-encoded certificate chain that includes any intermediate certificates and chains up to root on-premises certificate that you used to sign your private CA certificate. The chain does not include your private CA certificate. Only available after the certificate authority certificate has been imported.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Certificate<wbr>Signing<wbr>Request<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The base64 PEM-encoded certificate signing request (CSR) for your private CA certificate.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Enabled<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Boolean value that specifies whether certificate revocation lists (CRLs) are enabled. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Not<wbr>After<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Date and time after which the certificate authority is not valid. Only available after the certificate authority certificate has been imported.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Not<wbr>Before<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Date and time before which the certificate authority is not valid. Only available after the certificate authority certificate has been imported.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Permanent<wbr>Deletion<wbr>Time<wbr>In<wbr>Days<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The number of days to make a CA restorable after it has been deleted, must be between 7 to 30 days, with default to 30 days.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Revocation<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#certificateauthorityrevocationconfiguration">Certificate<wbr>Authority<wbr>Revocation<wbr>Configuration?</a></span>
    </dt>
    <dd>{{% md %}}Nested argument containing revocation configuration. Defined below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Serial<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Serial number of the certificate authority. Only available after the certificate authority certificate has been imported.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Status<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Status of the certificate authority.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}Specifies a key-value map of user-defined tags that are attached to the certificate authority.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The type of the certificate authority. Defaults to `SUBORDINATE`. Valid values: `ROOT` and `SUBORDINATE`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of the certificate authority.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Certificate<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Base64-encoded certificate authority (CA) certificate. Only available after the certificate authority certificate has been imported.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Certificate<wbr>Authority<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#certificateauthoritycertificateauthorityconfiguration">Certificate<wbr>Authority<wbr>Certificate<wbr>Authority<wbr>Configuration</a></span>
    </dt>
    <dd>{{% md %}}Nested argument containing algorithms and certificate subject information. Defined below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Certificate<wbr>Chain<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Base64-encoded certificate chain that includes any intermediate certificates and chains up to root on-premises certificate that you used to sign your private CA certificate. The chain does not include your private CA certificate. Only available after the certificate authority certificate has been imported.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Certificate<wbr>Signing<wbr>Request<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The base64 PEM-encoded certificate signing request (CSR) for your private CA certificate.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Enabled<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Boolean value that specifies whether certificate revocation lists (CRLs) are enabled. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Not<wbr>After<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Date and time after which the certificate authority is not valid. Only available after the certificate authority certificate has been imported.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Not<wbr>Before<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Date and time before which the certificate authority is not valid. Only available after the certificate authority certificate has been imported.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Permanent<wbr>Deletion<wbr>Time<wbr>In<wbr>Days<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The number of days to make a CA restorable after it has been deleted, must be between 7 to 30 days, with default to 30 days.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Revocation<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#certificateauthorityrevocationconfiguration">*Certificate<wbr>Authority<wbr>Revocation<wbr>Configuration</a></span>
    </dt>
    <dd>{{% md %}}Nested argument containing revocation configuration. Defined below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Serial<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Serial number of the certificate authority. Only available after the certificate authority certificate has been imported.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Status<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Status of the certificate authority.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}Specifies a key-value map of user-defined tags that are attached to the certificate authority.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Type<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The type of the certificate authority. Defaults to `SUBORDINATE`. Valid values: `ROOT` and `SUBORDINATE`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of the certificate authority.
{{% /md %}}</dd>

    <dt class="property-"
            title="">certificate<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Base64-encoded certificate authority (CA) certificate. Only available after the certificate authority certificate has been imported.
{{% /md %}}</dd>

    <dt class="property-"
            title="">certificate<wbr>Authority<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#certificateauthoritycertificateauthorityconfiguration">Certificate<wbr>Authority<wbr>Certificate<wbr>Authority<wbr>Configuration</a></span>
    </dt>
    <dd>{{% md %}}Nested argument containing algorithms and certificate subject information. Defined below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">certificate<wbr>Chain<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Base64-encoded certificate chain that includes any intermediate certificates and chains up to root on-premises certificate that you used to sign your private CA certificate. The chain does not include your private CA certificate. Only available after the certificate authority certificate has been imported.
{{% /md %}}</dd>

    <dt class="property-"
            title="">certificate<wbr>Signing<wbr>Request<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The base64 PEM-encoded certificate signing request (CSR) for your private CA certificate.
{{% /md %}}</dd>

    <dt class="property-"
            title="">enabled<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Boolean value that specifies whether certificate revocation lists (CRLs) are enabled. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">not<wbr>After<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Date and time after which the certificate authority is not valid. Only available after the certificate authority certificate has been imported.
{{% /md %}}</dd>

    <dt class="property-"
            title="">not<wbr>Before<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Date and time before which the certificate authority is not valid. Only available after the certificate authority certificate has been imported.
{{% /md %}}</dd>

    <dt class="property-"
            title="">permanent<wbr>Deletion<wbr>Time<wbr>In<wbr>Days<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The number of days to make a CA restorable after it has been deleted, must be between 7 to 30 days, with default to 30 days.
{{% /md %}}</dd>

    <dt class="property-"
            title="">revocation<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#certificateauthorityrevocationconfiguration">Certificate<wbr>Authority<wbr>Revocation<wbr>Configuration?</a></span>
    </dt>
    <dd>{{% md %}}Nested argument containing revocation configuration. Defined below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">serial<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Serial number of the certificate authority. Only available after the certificate authority certificate has been imported.
{{% /md %}}</dd>

    <dt class="property-"
            title="">status<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Status of the certificate authority.
{{% /md %}}</dd>

    <dt class="property-"
            title="">tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}Specifies a key-value map of user-defined tags that are attached to the certificate authority.
{{% /md %}}</dd>

    <dt class="property-"
            title="">type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The type of the certificate authority. Defaults to `SUBORDINATE`. Valid values: `ROOT` and `SUBORDINATE`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of the certificate authority.
{{% /md %}}</dd>

    <dt class="property-"
            title="">certificate<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Base64-encoded certificate authority (CA) certificate. Only available after the certificate authority certificate has been imported.
{{% /md %}}</dd>

    <dt class="property-"
            title="">certificate_<wbr>authority_<wbr>configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#certificateauthoritycertificateauthorityconfiguration">Dict[Certificate<wbr>Authority<wbr>Certificate<wbr>Authority<wbr>Configuration]</a></span>
    </dt>
    <dd>{{% md %}}Nested argument containing algorithms and certificate subject information. Defined below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">certificate_<wbr>chain<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Base64-encoded certificate chain that includes any intermediate certificates and chains up to root on-premises certificate that you used to sign your private CA certificate. The chain does not include your private CA certificate. Only available after the certificate authority certificate has been imported.
{{% /md %}}</dd>

    <dt class="property-"
            title="">certificate_<wbr>signing_<wbr>request<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The base64 PEM-encoded certificate signing request (CSR) for your private CA certificate.
{{% /md %}}</dd>

    <dt class="property-"
            title="">enabled<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Boolean value that specifies whether certificate revocation lists (CRLs) are enabled. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">not_<wbr>after<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Date and time after which the certificate authority is not valid. Only available after the certificate authority certificate has been imported.
{{% /md %}}</dd>

    <dt class="property-"
            title="">not_<wbr>before<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Date and time before which the certificate authority is not valid. Only available after the certificate authority certificate has been imported.
{{% /md %}}</dd>

    <dt class="property-"
            title="">permanent_<wbr>deletion_<wbr>time_<wbr>in_<wbr>days<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The number of days to make a CA restorable after it has been deleted, must be between 7 to 30 days, with default to 30 days.
{{% /md %}}</dd>

    <dt class="property-"
            title="">revocation_<wbr>configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#certificateauthorityrevocationconfiguration">Dict[Certificate<wbr>Authority<wbr>Revocation<wbr>Configuration]</a></span>
    </dt>
    <dd>{{% md %}}Nested argument containing revocation configuration. Defined below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">serial<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Serial number of the certificate authority. Only available after the certificate authority certificate has been imported.
{{% /md %}}</dd>

    <dt class="property-"
            title="">status<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Status of the certificate authority.
{{% /md %}}</dd>

    <dt class="property-"
            title="">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}Specifies a key-value map of user-defined tags that are attached to the certificate authority.
{{% /md %}}</dd>

    <dt class="property-"
            title="">type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The type of the certificate authority. Defaults to `SUBORDINATE`. Valid values: `ROOT` and `SUBORDINATE`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





## Look up an Existing CertificateAuthority Resource

{{< chooser language "javascript,typescript,python,go,csharp  " / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">pulumi.Input&lt;pulumi.ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/acmpca/#CertificateAuthorityState">CertificateAuthorityState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/acmpca/#CertificateAuthority">CertificateAuthority</a></span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>arn=None<span class="p">, </span>certificate=None<span class="p">, </span>certificate_authority_configuration=None<span class="p">, </span>certificate_chain=None<span class="p">, </span>certificate_signing_request=None<span class="p">, </span>enabled=None<span class="p">, </span>not_after=None<span class="p">, </span>not_before=None<span class="p">, </span>permanent_deletion_time_in_days=None<span class="p">, </span>revocation_configuration=None<span class="p">, </span>serial=None<span class="p">, </span>status=None<span class="p">, </span>tags=None<span class="p">, </span>type=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetCertificateAuthority<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">pulumi.IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/acmpca?tab=doc#CertificateAuthorityState">CertificateAuthorityState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/acmpca?tab=doc#CertificateAuthority">CertificateAuthority</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Acmpca.CertificateAuthority.html">CertificateAuthority</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Pulumi.Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Acmpca.CertificateAuthorityState.html">CertificateAuthorityState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
{{% /choosable %}}

Get an existing CertificateAuthority resource's state with the given name, ID, and optional extra properties used to qualify the lookup.

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
    <dd>{{% md %}}Amazon Resource Name (ARN) of the certificate authority.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Certificate<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Base64-encoded certificate authority (CA) certificate. Only available after the certificate authority certificate has been imported.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Certificate<wbr>Authority<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#certificateauthoritycertificateauthorityconfiguration">Certificate<wbr>Authority<wbr>Certificate<wbr>Authority<wbr>Configuration<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}Nested argument containing algorithms and certificate subject information. Defined below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Certificate<wbr>Chain<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Base64-encoded certificate chain that includes any intermediate certificates and chains up to root on-premises certificate that you used to sign your private CA certificate. The chain does not include your private CA certificate. Only available after the certificate authority certificate has been imported.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Certificate<wbr>Signing<wbr>Request<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The base64 PEM-encoded certificate signing request (CSR) for your private CA certificate.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Enabled<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Boolean value that specifies whether certificate revocation lists (CRLs) are enabled. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Not<wbr>After<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Date and time after which the certificate authority is not valid. Only available after the certificate authority certificate has been imported.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Not<wbr>Before<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Date and time before which the certificate authority is not valid. Only available after the certificate authority certificate has been imported.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Permanent<wbr>Deletion<wbr>Time<wbr>In<wbr>Days<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The number of days to make a CA restorable after it has been deleted, must be between 7 to 30 days, with default to 30 days.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Revocation<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#certificateauthorityrevocationconfiguration">Certificate<wbr>Authority<wbr>Revocation<wbr>Configuration<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}Nested argument containing revocation configuration. Defined below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Serial<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Serial number of the certificate authority. Only available after the certificate authority certificate has been imported.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Status<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Status of the certificate authority.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}Specifies a key-value map of user-defined tags that are attached to the certificate authority.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The type of the certificate authority. Defaults to `SUBORDINATE`. Valid values: `ROOT` and `SUBORDINATE`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of the certificate authority.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Certificate<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Base64-encoded certificate authority (CA) certificate. Only available after the certificate authority certificate has been imported.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Certificate<wbr>Authority<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#certificateauthoritycertificateauthorityconfiguration">*Certificate<wbr>Authority<wbr>Certificate<wbr>Authority<wbr>Configuration</a></span>
    </dt>
    <dd>{{% md %}}Nested argument containing algorithms and certificate subject information. Defined below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Certificate<wbr>Chain<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Base64-encoded certificate chain that includes any intermediate certificates and chains up to root on-premises certificate that you used to sign your private CA certificate. The chain does not include your private CA certificate. Only available after the certificate authority certificate has been imported.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Certificate<wbr>Signing<wbr>Request<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The base64 PEM-encoded certificate signing request (CSR) for your private CA certificate.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Enabled<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Boolean value that specifies whether certificate revocation lists (CRLs) are enabled. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Not<wbr>After<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Date and time after which the certificate authority is not valid. Only available after the certificate authority certificate has been imported.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Not<wbr>Before<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Date and time before which the certificate authority is not valid. Only available after the certificate authority certificate has been imported.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Permanent<wbr>Deletion<wbr>Time<wbr>In<wbr>Days<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The number of days to make a CA restorable after it has been deleted, must be between 7 to 30 days, with default to 30 days.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Revocation<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#certificateauthorityrevocationconfiguration">*Certificate<wbr>Authority<wbr>Revocation<wbr>Configuration</a></span>
    </dt>
    <dd>{{% md %}}Nested argument containing revocation configuration. Defined below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Serial<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Serial number of the certificate authority. Only available after the certificate authority certificate has been imported.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Status<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Status of the certificate authority.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}Specifies a key-value map of user-defined tags that are attached to the certificate authority.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Type<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The type of the certificate authority. Defaults to `SUBORDINATE`. Valid values: `ROOT` and `SUBORDINATE`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of the certificate authority.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">certificate<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Base64-encoded certificate authority (CA) certificate. Only available after the certificate authority certificate has been imported.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">certificate<wbr>Authority<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#certificateauthoritycertificateauthorityconfiguration">Certificate<wbr>Authority<wbr>Certificate<wbr>Authority<wbr>Configuration?</a></span>
    </dt>
    <dd>{{% md %}}Nested argument containing algorithms and certificate subject information. Defined below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">certificate<wbr>Chain<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Base64-encoded certificate chain that includes any intermediate certificates and chains up to root on-premises certificate that you used to sign your private CA certificate. The chain does not include your private CA certificate. Only available after the certificate authority certificate has been imported.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">certificate<wbr>Signing<wbr>Request<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The base64 PEM-encoded certificate signing request (CSR) for your private CA certificate.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">enabled<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Boolean value that specifies whether certificate revocation lists (CRLs) are enabled. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">not<wbr>After<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Date and time after which the certificate authority is not valid. Only available after the certificate authority certificate has been imported.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">not<wbr>Before<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Date and time before which the certificate authority is not valid. Only available after the certificate authority certificate has been imported.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">permanent<wbr>Deletion<wbr>Time<wbr>In<wbr>Days<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The number of days to make a CA restorable after it has been deleted, must be between 7 to 30 days, with default to 30 days.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">revocation<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#certificateauthorityrevocationconfiguration">Certificate<wbr>Authority<wbr>Revocation<wbr>Configuration?</a></span>
    </dt>
    <dd>{{% md %}}Nested argument containing revocation configuration. Defined below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">serial<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Serial number of the certificate authority. Only available after the certificate authority certificate has been imported.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">status<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Status of the certificate authority.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}Specifies a key-value map of user-defined tags that are attached to the certificate authority.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The type of the certificate authority. Defaults to `SUBORDINATE`. Valid values: `ROOT` and `SUBORDINATE`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of the certificate authority.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">certificate<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Base64-encoded certificate authority (CA) certificate. Only available after the certificate authority certificate has been imported.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">certificate_<wbr>authority_<wbr>configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#certificateauthoritycertificateauthorityconfiguration">Dict[Certificate<wbr>Authority<wbr>Certificate<wbr>Authority<wbr>Configuration]</a></span>
    </dt>
    <dd>{{% md %}}Nested argument containing algorithms and certificate subject information. Defined below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">certificate_<wbr>chain<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Base64-encoded certificate chain that includes any intermediate certificates and chains up to root on-premises certificate that you used to sign your private CA certificate. The chain does not include your private CA certificate. Only available after the certificate authority certificate has been imported.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">certificate_<wbr>signing_<wbr>request<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The base64 PEM-encoded certificate signing request (CSR) for your private CA certificate.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">enabled<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Boolean value that specifies whether certificate revocation lists (CRLs) are enabled. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">not_<wbr>after<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Date and time after which the certificate authority is not valid. Only available after the certificate authority certificate has been imported.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">not_<wbr>before<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Date and time before which the certificate authority is not valid. Only available after the certificate authority certificate has been imported.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">permanent_<wbr>deletion_<wbr>time_<wbr>in_<wbr>days<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The number of days to make a CA restorable after it has been deleted, must be between 7 to 30 days, with default to 30 days.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">revocation_<wbr>configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#certificateauthorityrevocationconfiguration">Dict[Certificate<wbr>Authority<wbr>Revocation<wbr>Configuration]</a></span>
    </dt>
    <dd>{{% md %}}Nested argument containing revocation configuration. Defined below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">serial<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Serial number of the certificate authority. Only available after the certificate authority certificate has been imported.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">status<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Status of the certificate authority.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}Specifies a key-value map of user-defined tags that are attached to the certificate authority.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The type of the certificate authority. Defaults to `SUBORDINATE`. Valid values: `ROOT` and `SUBORDINATE`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}







## Supporting Types

#### CertificateAuthorityCertificateAuthorityConfiguration
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#CertificateAuthorityCertificateAuthorityConfiguration">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#CertificateAuthorityCertificateAuthorityConfiguration">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/acmpca?tab=doc#CertificateAuthorityCertificateAuthorityConfigurationArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/acmpca?tab=doc#CertificateAuthorityCertificateAuthorityConfigurationOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Acmpca.CertificateAuthorityCertificateAuthorityConfigurationArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Acmpca.CertificateAuthorityCertificateAuthorityConfiguration.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Key<wbr>Algorithm<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Type of the public key algorithm and size, in bits, of the key pair that your key pair creates when it issues a certificate. Valid values can be found in the [ACM PCA Documentation](https://docs.aws.amazon.com/acm-pca/latest/APIReference/API_CertificateAuthorityConfiguration.html).
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Signing<wbr>Algorithm<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Name of the algorithm your private CA uses to sign certificate requests. Valid values can be found in the [ACM PCA Documentation](https://docs.aws.amazon.com/acm-pca/latest/APIReference/API_CertificateAuthorityConfiguration.html).
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Subject<span class="property-indicator"></span>
        <span class="property-type"><a href="#certificateauthoritycertificateauthorityconfigurationsubject">Certificate<wbr>Authority<wbr>Certificate<wbr>Authority<wbr>Configuration<wbr>Subject<wbr>Args</a></span>
    </dt>
    <dd>{{% md %}}Nested argument that contains X.500 distinguished name information. At least one nested attribute must be specified.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Key<wbr>Algorithm<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Type of the public key algorithm and size, in bits, of the key pair that your key pair creates when it issues a certificate. Valid values can be found in the [ACM PCA Documentation](https://docs.aws.amazon.com/acm-pca/latest/APIReference/API_CertificateAuthorityConfiguration.html).
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Signing<wbr>Algorithm<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Name of the algorithm your private CA uses to sign certificate requests. Valid values can be found in the [ACM PCA Documentation](https://docs.aws.amazon.com/acm-pca/latest/APIReference/API_CertificateAuthorityConfiguration.html).
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Subject<span class="property-indicator"></span>
        <span class="property-type"><a href="#certificateauthoritycertificateauthorityconfigurationsubject">Certificate<wbr>Authority<wbr>Certificate<wbr>Authority<wbr>Configuration<wbr>Subject</a></span>
    </dt>
    <dd>{{% md %}}Nested argument that contains X.500 distinguished name information. At least one nested attribute must be specified.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">key<wbr>Algorithm<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Type of the public key algorithm and size, in bits, of the key pair that your key pair creates when it issues a certificate. Valid values can be found in the [ACM PCA Documentation](https://docs.aws.amazon.com/acm-pca/latest/APIReference/API_CertificateAuthorityConfiguration.html).
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">signing<wbr>Algorithm<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Name of the algorithm your private CA uses to sign certificate requests. Valid values can be found in the [ACM PCA Documentation](https://docs.aws.amazon.com/acm-pca/latest/APIReference/API_CertificateAuthorityConfiguration.html).
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">subject<span class="property-indicator"></span>
        <span class="property-type"><a href="#certificateauthoritycertificateauthorityconfigurationsubject">Certificate<wbr>Authority<wbr>Certificate<wbr>Authority<wbr>Configuration<wbr>Subject</a></span>
    </dt>
    <dd>{{% md %}}Nested argument that contains X.500 distinguished name information. At least one nested attribute must be specified.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">key<wbr>Algorithm<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Type of the public key algorithm and size, in bits, of the key pair that your key pair creates when it issues a certificate. Valid values can be found in the [ACM PCA Documentation](https://docs.aws.amazon.com/acm-pca/latest/APIReference/API_CertificateAuthorityConfiguration.html).
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">signing<wbr>Algorithm<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Name of the algorithm your private CA uses to sign certificate requests. Valid values can be found in the [ACM PCA Documentation](https://docs.aws.amazon.com/acm-pca/latest/APIReference/API_CertificateAuthorityConfiguration.html).
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">subject<span class="property-indicator"></span>
        <span class="property-type"><a href="#certificateauthoritycertificateauthorityconfigurationsubject">Dict[Certificate<wbr>Authority<wbr>Certificate<wbr>Authority<wbr>Configuration<wbr>Subject]</a></span>
    </dt>
    <dd>{{% md %}}Nested argument that contains X.500 distinguished name information. At least one nested attribute must be specified.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### CertificateAuthorityCertificateAuthorityConfigurationSubject
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#CertificateAuthorityCertificateAuthorityConfigurationSubject">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#CertificateAuthorityCertificateAuthorityConfigurationSubject">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/acmpca?tab=doc#CertificateAuthorityCertificateAuthorityConfigurationSubjectArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/acmpca?tab=doc#CertificateAuthorityCertificateAuthorityConfigurationSubjectOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Acmpca.CertificateAuthorityCertificateAuthorityConfigurationSubjectArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Acmpca.CertificateAuthorityCertificateAuthorityConfigurationSubject.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Common<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Fully qualified domain name (FQDN) associated with the certificate subject.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Country<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Two digit code that specifies the country in which the certificate subject located.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Distinguished<wbr>Name<wbr>Qualifier<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Disambiguating information for the certificate subject.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Generation<wbr>Qualifier<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Typically a qualifier appended to the name of an individual. Examples include Jr. for junior, Sr. for senior, and III for third.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Given<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}First name.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Initials<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Concatenation that typically contains the first letter of the `given_name`, the first letter of the middle name if one exists, and the first letter of the `surname`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Locality<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The locality (such as a city or town) in which the certificate subject is located.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Organization<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Legal name of the organization with which the certificate subject is affiliated.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Organizational<wbr>Unit<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A subdivision or unit of the organization (such as sales or finance) with which the certificate subject is affiliated.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Pseudonym<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Typically a shortened version of a longer `given_name`. For example, Jonathan is often shortened to John. Elizabeth is often shortened to Beth, Liz, or Eliza.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">State<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}State in which the subject of the certificate is located.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Surname<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Family name. In the US and the UK for example, the surname of an individual is ordered last. In Asian cultures the surname is typically ordered first.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Title<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A title such as Mr. or Ms. which is pre-pended to the name to refer formally to the certificate subject.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Common<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Fully qualified domain name (FQDN) associated with the certificate subject.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Country<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Two digit code that specifies the country in which the certificate subject located.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Distinguished<wbr>Name<wbr>Qualifier<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Disambiguating information for the certificate subject.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Generation<wbr>Qualifier<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Typically a qualifier appended to the name of an individual. Examples include Jr. for junior, Sr. for senior, and III for third.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Given<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}First name.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Initials<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Concatenation that typically contains the first letter of the `given_name`, the first letter of the middle name if one exists, and the first letter of the `surname`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Locality<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The locality (such as a city or town) in which the certificate subject is located.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Organization<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Legal name of the organization with which the certificate subject is affiliated.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Organizational<wbr>Unit<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}A subdivision or unit of the organization (such as sales or finance) with which the certificate subject is affiliated.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Pseudonym<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Typically a shortened version of a longer `given_name`. For example, Jonathan is often shortened to John. Elizabeth is often shortened to Beth, Liz, or Eliza.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">State<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}State in which the subject of the certificate is located.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Surname<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Family name. In the US and the UK for example, the surname of an individual is ordered last. In Asian cultures the surname is typically ordered first.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Title<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}A title such as Mr. or Ms. which is pre-pended to the name to refer formally to the certificate subject.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">common<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Fully qualified domain name (FQDN) associated with the certificate subject.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">country<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Two digit code that specifies the country in which the certificate subject located.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">distinguished<wbr>Name<wbr>Qualifier<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Disambiguating information for the certificate subject.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">generation<wbr>Qualifier<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Typically a qualifier appended to the name of an individual. Examples include Jr. for junior, Sr. for senior, and III for third.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">given<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}First name.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">initials<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Concatenation that typically contains the first letter of the `given_name`, the first letter of the middle name if one exists, and the first letter of the `surname`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">locality<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The locality (such as a city or town) in which the certificate subject is located.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">organization<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Legal name of the organization with which the certificate subject is affiliated.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">organizational<wbr>Unit<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A subdivision or unit of the organization (such as sales or finance) with which the certificate subject is affiliated.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">pseudonym<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Typically a shortened version of a longer `given_name`. For example, Jonathan is often shortened to John. Elizabeth is often shortened to Beth, Liz, or Eliza.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">state<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}State in which the subject of the certificate is located.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">surname<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Family name. In the US and the UK for example, the surname of an individual is ordered last. In Asian cultures the surname is typically ordered first.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">title<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A title such as Mr. or Ms. which is pre-pended to the name to refer formally to the certificate subject.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">common<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Fully qualified domain name (FQDN) associated with the certificate subject.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">country<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Two digit code that specifies the country in which the certificate subject located.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">distinguished<wbr>Name<wbr>Qualifier<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Disambiguating information for the certificate subject.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">generation<wbr>Qualifier<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Typically a qualifier appended to the name of an individual. Examples include Jr. for junior, Sr. for senior, and III for third.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">given<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}First name.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">initials<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Concatenation that typically contains the first letter of the `given_name`, the first letter of the middle name if one exists, and the first letter of the `surname`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">locality<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The locality (such as a city or town) in which the certificate subject is located.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">organization<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Legal name of the organization with which the certificate subject is affiliated.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">organizational<wbr>Unit<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A subdivision or unit of the organization (such as sales or finance) with which the certificate subject is affiliated.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">pseudonym<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Typically a shortened version of a longer `given_name`. For example, Jonathan is often shortened to John. Elizabeth is often shortened to Beth, Liz, or Eliza.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">state<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}State in which the subject of the certificate is located.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">surname<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Family name. In the US and the UK for example, the surname of an individual is ordered last. In Asian cultures the surname is typically ordered first.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">title<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A title such as Mr. or Ms. which is pre-pended to the name to refer formally to the certificate subject.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### CertificateAuthorityRevocationConfiguration
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#CertificateAuthorityRevocationConfiguration">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#CertificateAuthorityRevocationConfiguration">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/acmpca?tab=doc#CertificateAuthorityRevocationConfigurationArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/acmpca?tab=doc#CertificateAuthorityRevocationConfigurationOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Acmpca.CertificateAuthorityRevocationConfigurationArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Acmpca.CertificateAuthorityRevocationConfiguration.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Crl<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#certificateauthorityrevocationconfigurationcrlconfiguration">Certificate<wbr>Authority<wbr>Revocation<wbr>Configuration<wbr>Crl<wbr>Configuration<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}Nested argument containing configuration of the certificate revocation list (CRL), if any, maintained by the certificate authority. Defined below.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Crl<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#certificateauthorityrevocationconfigurationcrlconfiguration">*Certificate<wbr>Authority<wbr>Revocation<wbr>Configuration<wbr>Crl<wbr>Configuration</a></span>
    </dt>
    <dd>{{% md %}}Nested argument containing configuration of the certificate revocation list (CRL), if any, maintained by the certificate authority. Defined below.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">crl<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#certificateauthorityrevocationconfigurationcrlconfiguration">Certificate<wbr>Authority<wbr>Revocation<wbr>Configuration<wbr>Crl<wbr>Configuration?</a></span>
    </dt>
    <dd>{{% md %}}Nested argument containing configuration of the certificate revocation list (CRL), if any, maintained by the certificate authority. Defined below.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">crl<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#certificateauthorityrevocationconfigurationcrlconfiguration">Dict[Certificate<wbr>Authority<wbr>Revocation<wbr>Configuration<wbr>Crl<wbr>Configuration]</a></span>
    </dt>
    <dd>{{% md %}}Nested argument containing configuration of the certificate revocation list (CRL), if any, maintained by the certificate authority. Defined below.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### CertificateAuthorityRevocationConfigurationCrlConfiguration
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#CertificateAuthorityRevocationConfigurationCrlConfiguration">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#CertificateAuthorityRevocationConfigurationCrlConfiguration">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/acmpca?tab=doc#CertificateAuthorityRevocationConfigurationCrlConfigurationArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/acmpca?tab=doc#CertificateAuthorityRevocationConfigurationCrlConfigurationOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Acmpca.CertificateAuthorityRevocationConfigurationCrlConfigurationArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Acmpca.CertificateAuthorityRevocationConfigurationCrlConfiguration.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Custom<wbr>Cname<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Name inserted into the certificate CRL Distribution Points extension that enables the use of an alias for the CRL distribution point. Use this value if you don&#39;t want the name of your S3 bucket to be public.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Enabled<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Boolean value that specifies whether certificate revocation lists (CRLs) are enabled. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Expiration<wbr>In<wbr>Days<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}Number of days until a certificate expires. Must be between 1 and 5000.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">S3Bucket<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Name of the S3 bucket that contains the CRL. If you do not provide a value for the `custom_cname` argument, the name of your S3 bucket is placed into the CRL Distribution Points extension of the issued certificate. You must specify a bucket policy that allows ACM PCA to write the CRL to your bucket.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Custom<wbr>Cname<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Name inserted into the certificate CRL Distribution Points extension that enables the use of an alias for the CRL distribution point. Use this value if you don&#39;t want the name of your S3 bucket to be public.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Enabled<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Boolean value that specifies whether certificate revocation lists (CRLs) are enabled. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Expiration<wbr>In<wbr>Days<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}Number of days until a certificate expires. Must be between 1 and 5000.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">S3Bucket<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Name of the S3 bucket that contains the CRL. If you do not provide a value for the `custom_cname` argument, the name of your S3 bucket is placed into the CRL Distribution Points extension of the issued certificate. You must specify a bucket policy that allows ACM PCA to write the CRL to your bucket.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">custom<wbr>Cname<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Name inserted into the certificate CRL Distribution Points extension that enables the use of an alias for the CRL distribution point. Use this value if you don&#39;t want the name of your S3 bucket to be public.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">enabled<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Boolean value that specifies whether certificate revocation lists (CRLs) are enabled. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">expiration<wbr>In<wbr>Days<span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}Number of days until a certificate expires. Must be between 1 and 5000.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">s3Bucket<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Name of the S3 bucket that contains the CRL. If you do not provide a value for the `custom_cname` argument, the name of your S3 bucket is placed into the CRL Distribution Points extension of the issued certificate. You must specify a bucket policy that allows ACM PCA to write the CRL to your bucket.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">custom<wbr>Cname<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Name inserted into the certificate CRL Distribution Points extension that enables the use of an alias for the CRL distribution point. Use this value if you don&#39;t want the name of your S3 bucket to be public.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">enabled<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Boolean value that specifies whether certificate revocation lists (CRLs) are enabled. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">expiration<wbr>In<wbr>Days<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}Number of days until a certificate expires. Must be between 1 and 5000.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">s3_<wbr>bucket_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Name of the S3 bucket that contains the CRL. If you do not provide a value for the `custom_cname` argument, the name of your S3 bucket is placed into the CRL Distribution Points extension of the issued certificate. You must specify a bucket policy that allows ACM PCA to write the CRL to your bucket.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}








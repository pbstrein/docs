
---
title: "Certificate"
block_external_search_index: true
---

The ACM certificate resource allows requesting and management of certificates
from the Amazon Certificate Manager.

It deals with requesting certificates and managing their attributes and life-cycle.
This resource does not deal with validation of a certificate but can provide inputs
for other resources implementing the validation. It does not wait for a certificate to be issued.
Use a `aws.acm.CertificateValidation` resource for this.

Most commonly, this resource is used to together with `aws.route53.Record` and
`aws.acm.CertificateValidation` to request a DNS validated certificate,
deploy the required validation records and wait for validation to complete.

Domain validation through E-Mail is also supported but should be avoided as it requires a manual step outside
of this provider.

It's recommended to specify `create_before_destroy = true` in a [lifecycle][1] block to replace a certificate
which is currently in use (eg, by `aws.lb.Listener`).

## Example Usage

### Certificate creation

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const cert = new aws.acm.Certificate("cert", {
    domainName: "example.com",
    tags: {
        Environment: "test",
    },
    validationMethod: "DNS",
});
```

### Importing an existing certificate

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";
import * as tls from "@pulumi/tls";

const examplePrivateKey = new tls.PrivateKey("example", {
    algorithm: "RSA",
});
const exampleSelfSignedCert = new tls.SelfSignedCert("example", {
    allowedUses: [
        "key_encipherment",
        "digital_signature",
        "server_auth",
    ],
    keyAlgorithm: "RSA",
    privateKeyPem: examplePrivateKey.privateKeyPem,
    subjects: [{
        commonName: "example.com",
        organization: "ACME Examples, Inc",
    }],
    validityPeriodHours: 12,
});
const cert = new aws.acm.Certificate("cert", {
    certificateBody: exampleSelfSignedCert.certPem,
    privateKey: examplePrivateKey.privateKeyPem,
});
```

## options Configuration Block

Supported nested arguments for the `options` configuration block:

* `certificate_transparency_logging_preference` - (Optional) Specifies whether certificate details should be added to a certificate transparency log. Valid values are `ENABLED` or `DISABLED`. See https://docs.aws.amazon.com/acm/latest/userguide/acm-concepts.html#concept-transparency for more details.

> This content is derived from https://github.com/terraform-providers/terraform-provider-aws/blob/master/website/docs/r/acm_certificate.html.markdown.



## Create a Certificate Resource

{{< chooser language "javascript,typescript,python,go,csharp" / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/acm/#Certificate">Certificate</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/acm/#CertificateArgs">CertificateArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">Certificate</span><span class="p">(resource_name, opts=None, </span>certificate_authority_arn=None<span class="p">, </span>certificate_body=None<span class="p">, </span>certificate_chain=None<span class="p">, </span>domain_name=None<span class="p">, </span>options=None<span class="p">, </span>private_key=None<span class="p">, </span>subject_alternative_names=None<span class="p">, </span>tags=None<span class="p">, </span>validation_method=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewCertificate<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/acm?tab=doc#CertificateArgs">CertificateArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/acm?tab=doc#Certificate">Certificate</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Acm.Certificate.html">Certificate</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Acm.CertificateArgs.html">CertificateArgs</a></span>? <span class="nx">args = null<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
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
            title="Optional">Certificate<wbr>Authority<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}ARN of an ACMPCA
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Certificate<wbr>Body<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The certificate&#39;s PEM-formatted public key
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Certificate<wbr>Chain<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The certificate&#39;s PEM-formatted chain
* Creating a private CA issued certificate
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Domain<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A domain name for which the certificate should be issued
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Options<span class="property-indicator"></span>
        <span class="property-type"><a href="#certificateoptions">Certificate<wbr>Options<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Private<wbr>Key<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The certificate&#39;s PEM-formatted private key
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Subject<wbr>Alternative<wbr>Names<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}A list of domains that should be SANs in the issued certificate
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Validation<wbr>Method<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Which method to use for validation. `DNS` or `EMAIL` are valid, `NONE` can be used for certificates that were imported into ACM and then into state managed by this provider.
* Importing an existing certificate
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Certificate<wbr>Authority<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}ARN of an ACMPCA
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Certificate<wbr>Body<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The certificate&#39;s PEM-formatted public key
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Certificate<wbr>Chain<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The certificate&#39;s PEM-formatted chain
* Creating a private CA issued certificate
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Domain<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}A domain name for which the certificate should be issued
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Options<span class="property-indicator"></span>
        <span class="property-type"><a href="#certificateoptions">*Certificate<wbr>Options</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Private<wbr>Key<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The certificate&#39;s PEM-formatted private key
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Subject<wbr>Alternative<wbr>Names<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}A list of domains that should be SANs in the issued certificate
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Validation<wbr>Method<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Which method to use for validation. `DNS` or `EMAIL` are valid, `NONE` can be used for certificates that were imported into ACM and then into state managed by this provider.
* Importing an existing certificate
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">certificate<wbr>Authority<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}ARN of an ACMPCA
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">certificate<wbr>Body<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The certificate&#39;s PEM-formatted public key
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">certificate<wbr>Chain<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The certificate&#39;s PEM-formatted chain
* Creating a private CA issued certificate
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">domain<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A domain name for which the certificate should be issued
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">options<span class="property-indicator"></span>
        <span class="property-type"><a href="#certificateoptions">Certificate<wbr>Options?</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">private<wbr>Key<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The certificate&#39;s PEM-formatted private key
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">subject<wbr>Alternative<wbr>Names<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}A list of domains that should be SANs in the issued certificate
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">validation<wbr>Method<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Which method to use for validation. `DNS` or `EMAIL` are valid, `NONE` can be used for certificates that were imported into ACM and then into state managed by this provider.
* Importing an existing certificate
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">certificate_<wbr>authority_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}ARN of an ACMPCA
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">certificate_<wbr>body<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The certificate&#39;s PEM-formatted public key
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">certificate_<wbr>chain<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The certificate&#39;s PEM-formatted chain
* Creating a private CA issued certificate
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">domain_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A domain name for which the certificate should be issued
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">options<span class="property-indicator"></span>
        <span class="property-type"><a href="#certificateoptions">Dict[Certificate<wbr>Options]</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">private_<wbr>key<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The certificate&#39;s PEM-formatted private key
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">subject_<wbr>alternative_<wbr>names<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}A list of domains that should be SANs in the issued certificate
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">validation_<wbr>method<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Which method to use for validation. `DNS` or `EMAIL` are valid, `NONE` can be used for certificates that were imported into ACM and then into state managed by this provider.
* Importing an existing certificate
{{% /md %}}</dd>

</dl>
{{% /choosable %}}




## Certificate Output Properties

The following output properties are available:




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of the certificate
{{% /md %}}</dd>

    <dt class="property-"
            title="">Certificate<wbr>Authority<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}ARN of an ACMPCA
{{% /md %}}</dd>

    <dt class="property-"
            title="">Certificate<wbr>Body<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The certificate&#39;s PEM-formatted public key
{{% /md %}}</dd>

    <dt class="property-"
            title="">Certificate<wbr>Chain<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The certificate&#39;s PEM-formatted chain
* Creating a private CA issued certificate
{{% /md %}}</dd>

    <dt class="property-"
            title="">Domain<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}A domain name for which the certificate should be issued
{{% /md %}}</dd>

    <dt class="property-"
            title="">Domain<wbr>Validation<wbr>Options<span class="property-indicator"></span>
        <span class="property-type"><a href="#certificatedomainvalidationoption">List&lt;Certificate<wbr>Domain<wbr>Validation<wbr>Option&gt;</a></span>
    </dt>
    <dd>{{% md %}}A list of attributes to feed into other resources to complete certificate validation. Can have more than one element, e.g. if SANs are defined. Only set if `DNS`-validation was used.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Options<span class="property-indicator"></span>
        <span class="property-type"><a href="#certificateoptions">Certificate<wbr>Options?</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">Private<wbr>Key<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The certificate&#39;s PEM-formatted private key
{{% /md %}}</dd>

    <dt class="property-"
            title="">Subject<wbr>Alternative<wbr>Names<span class="property-indicator"></span>
        <span class="property-type">List<string></span>
    </dt>
    <dd>{{% md %}}A list of domains that should be SANs in the issued certificate
{{% /md %}}</dd>

    <dt class="property-"
            title="">Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Validation<wbr>Emails<span class="property-indicator"></span>
        <span class="property-type">List<string></span>
    </dt>
    <dd>{{% md %}}A list of addresses that received a validation E-Mail. Only set if `EMAIL`-validation was used.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Validation<wbr>Method<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Which method to use for validation. `DNS` or `EMAIL` are valid, `NONE` can be used for certificates that were imported into ACM and then into state managed by this provider.
* Importing an existing certificate
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of the certificate
{{% /md %}}</dd>

    <dt class="property-"
            title="">Certificate<wbr>Authority<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}ARN of an ACMPCA
{{% /md %}}</dd>

    <dt class="property-"
            title="">Certificate<wbr>Body<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The certificate&#39;s PEM-formatted public key
{{% /md %}}</dd>

    <dt class="property-"
            title="">Certificate<wbr>Chain<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The certificate&#39;s PEM-formatted chain
* Creating a private CA issued certificate
{{% /md %}}</dd>

    <dt class="property-"
            title="">Domain<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}A domain name for which the certificate should be issued
{{% /md %}}</dd>

    <dt class="property-"
            title="">Domain<wbr>Validation<wbr>Options<span class="property-indicator"></span>
        <span class="property-type"><a href="#certificatedomainvalidationoption">[]Certificate<wbr>Domain<wbr>Validation<wbr>Option</a></span>
    </dt>
    <dd>{{% md %}}A list of attributes to feed into other resources to complete certificate validation. Can have more than one element, e.g. if SANs are defined. Only set if `DNS`-validation was used.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Options<span class="property-indicator"></span>
        <span class="property-type"><a href="#certificateoptions">*Certificate<wbr>Options</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">Private<wbr>Key<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The certificate&#39;s PEM-formatted private key
{{% /md %}}</dd>

    <dt class="property-"
            title="">Subject<wbr>Alternative<wbr>Names<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}A list of domains that should be SANs in the issued certificate
{{% /md %}}</dd>

    <dt class="property-"
            title="">Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Validation<wbr>Emails<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}A list of addresses that received a validation E-Mail. Only set if `EMAIL`-validation was used.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Validation<wbr>Method<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Which method to use for validation. `DNS` or `EMAIL` are valid, `NONE` can be used for certificates that were imported into ACM and then into state managed by this provider.
* Importing an existing certificate
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of the certificate
{{% /md %}}</dd>

    <dt class="property-"
            title="">certificate<wbr>Authority<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}ARN of an ACMPCA
{{% /md %}}</dd>

    <dt class="property-"
            title="">certificate<wbr>Body<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The certificate&#39;s PEM-formatted public key
{{% /md %}}</dd>

    <dt class="property-"
            title="">certificate<wbr>Chain<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The certificate&#39;s PEM-formatted chain
* Creating a private CA issued certificate
{{% /md %}}</dd>

    <dt class="property-"
            title="">domain<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}A domain name for which the certificate should be issued
{{% /md %}}</dd>

    <dt class="property-"
            title="">domain<wbr>Validation<wbr>Options<span class="property-indicator"></span>
        <span class="property-type"><a href="#certificatedomainvalidationoption">Certificate<wbr>Domain<wbr>Validation<wbr>Option[]</a></span>
    </dt>
    <dd>{{% md %}}A list of attributes to feed into other resources to complete certificate validation. Can have more than one element, e.g. if SANs are defined. Only set if `DNS`-validation was used.
{{% /md %}}</dd>

    <dt class="property-"
            title="">options<span class="property-indicator"></span>
        <span class="property-type"><a href="#certificateoptions">Certificate<wbr>Options?</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">private<wbr>Key<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The certificate&#39;s PEM-formatted private key
{{% /md %}}</dd>

    <dt class="property-"
            title="">subject<wbr>Alternative<wbr>Names<span class="property-indicator"></span>
        <span class="property-type">string[]</span>
    </dt>
    <dd>{{% md %}}A list of domains that should be SANs in the issued certificate
{{% /md %}}</dd>

    <dt class="property-"
            title="">tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-"
            title="">validation<wbr>Emails<span class="property-indicator"></span>
        <span class="property-type">string[]</span>
    </dt>
    <dd>{{% md %}}A list of addresses that received a validation E-Mail. Only set if `EMAIL`-validation was used.
{{% /md %}}</dd>

    <dt class="property-"
            title="">validation<wbr>Method<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Which method to use for validation. `DNS` or `EMAIL` are valid, `NONE` can be used for certificates that were imported into ACM and then into state managed by this provider.
* Importing an existing certificate
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ARN of the certificate
{{% /md %}}</dd>

    <dt class="property-"
            title="">certificate_<wbr>authority_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}ARN of an ACMPCA
{{% /md %}}</dd>

    <dt class="property-"
            title="">certificate_<wbr>body<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The certificate&#39;s PEM-formatted public key
{{% /md %}}</dd>

    <dt class="property-"
            title="">certificate_<wbr>chain<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The certificate&#39;s PEM-formatted chain
* Creating a private CA issued certificate
{{% /md %}}</dd>

    <dt class="property-"
            title="">domain_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A domain name for which the certificate should be issued
{{% /md %}}</dd>

    <dt class="property-"
            title="">domain_<wbr>validation_<wbr>options<span class="property-indicator"></span>
        <span class="property-type"><a href="#certificatedomainvalidationoption">List[Certificate<wbr>Domain<wbr>Validation<wbr>Option]</a></span>
    </dt>
    <dd>{{% md %}}A list of attributes to feed into other resources to complete certificate validation. Can have more than one element, e.g. if SANs are defined. Only set if `DNS`-validation was used.
{{% /md %}}</dd>

    <dt class="property-"
            title="">options<span class="property-indicator"></span>
        <span class="property-type"><a href="#certificateoptions">Dict[Certificate<wbr>Options]</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">private_<wbr>key<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The certificate&#39;s PEM-formatted private key
{{% /md %}}</dd>

    <dt class="property-"
            title="">subject_<wbr>alternative_<wbr>names<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}A list of domains that should be SANs in the issued certificate
{{% /md %}}</dd>

    <dt class="property-"
            title="">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-"
            title="">validation_<wbr>emails<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}A list of addresses that received a validation E-Mail. Only set if `EMAIL`-validation was used.
{{% /md %}}</dd>

    <dt class="property-"
            title="">validation_<wbr>method<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Which method to use for validation. `DNS` or `EMAIL` are valid, `NONE` can be used for certificates that were imported into ACM and then into state managed by this provider.
* Importing an existing certificate
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





## Look up an Existing Certificate Resource

{{< chooser language "javascript,typescript,python,go,csharp  " / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">pulumi.Input&lt;pulumi.ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/acm/#CertificateState">CertificateState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/acm/#Certificate">Certificate</a></span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>arn=None<span class="p">, </span>certificate_authority_arn=None<span class="p">, </span>certificate_body=None<span class="p">, </span>certificate_chain=None<span class="p">, </span>domain_name=None<span class="p">, </span>domain_validation_options=None<span class="p">, </span>options=None<span class="p">, </span>private_key=None<span class="p">, </span>subject_alternative_names=None<span class="p">, </span>tags=None<span class="p">, </span>validation_emails=None<span class="p">, </span>validation_method=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetCertificate<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">pulumi.IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/acm?tab=doc#CertificateState">CertificateState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/acm?tab=doc#Certificate">Certificate</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Acm.Certificate.html">Certificate</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Pulumi.Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Acm.CertificateState.html">CertificateState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
{{% /choosable %}}

Get an existing Certificate resource's state with the given name, ID, and optional extra properties used to qualify the lookup.

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
    <dd>{{% md %}}The ARN of the certificate
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Certificate<wbr>Authority<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}ARN of an ACMPCA
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Certificate<wbr>Body<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The certificate&#39;s PEM-formatted public key
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Certificate<wbr>Chain<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The certificate&#39;s PEM-formatted chain
* Creating a private CA issued certificate
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Domain<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A domain name for which the certificate should be issued
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Domain<wbr>Validation<wbr>Options<span class="property-indicator"></span>
        <span class="property-type"><a href="#certificatedomainvalidationoption">List&lt;Certificate<wbr>Domain<wbr>Validation<wbr>Option<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}A list of attributes to feed into other resources to complete certificate validation. Can have more than one element, e.g. if SANs are defined. Only set if `DNS`-validation was used.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Options<span class="property-indicator"></span>
        <span class="property-type"><a href="#certificateoptions">Certificate<wbr>Options<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Private<wbr>Key<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The certificate&#39;s PEM-formatted private key
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Subject<wbr>Alternative<wbr>Names<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}A list of domains that should be SANs in the issued certificate
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Validation<wbr>Emails<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}A list of addresses that received a validation E-Mail. Only set if `EMAIL`-validation was used.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Validation<wbr>Method<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Which method to use for validation. `DNS` or `EMAIL` are valid, `NONE` can be used for certificates that were imported into ACM and then into state managed by this provider.
* Importing an existing certificate
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The ARN of the certificate
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Certificate<wbr>Authority<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}ARN of an ACMPCA
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Certificate<wbr>Body<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The certificate&#39;s PEM-formatted public key
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Certificate<wbr>Chain<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The certificate&#39;s PEM-formatted chain
* Creating a private CA issued certificate
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Domain<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}A domain name for which the certificate should be issued
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Domain<wbr>Validation<wbr>Options<span class="property-indicator"></span>
        <span class="property-type"><a href="#certificatedomainvalidationoption">[]Certificate<wbr>Domain<wbr>Validation<wbr>Option</a></span>
    </dt>
    <dd>{{% md %}}A list of attributes to feed into other resources to complete certificate validation. Can have more than one element, e.g. if SANs are defined. Only set if `DNS`-validation was used.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Options<span class="property-indicator"></span>
        <span class="property-type"><a href="#certificateoptions">*Certificate<wbr>Options</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Private<wbr>Key<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The certificate&#39;s PEM-formatted private key
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Subject<wbr>Alternative<wbr>Names<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}A list of domains that should be SANs in the issued certificate
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Validation<wbr>Emails<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}A list of addresses that received a validation E-Mail. Only set if `EMAIL`-validation was used.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Validation<wbr>Method<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Which method to use for validation. `DNS` or `EMAIL` are valid, `NONE` can be used for certificates that were imported into ACM and then into state managed by this provider.
* Importing an existing certificate
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ARN of the certificate
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">certificate<wbr>Authority<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}ARN of an ACMPCA
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">certificate<wbr>Body<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The certificate&#39;s PEM-formatted public key
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">certificate<wbr>Chain<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The certificate&#39;s PEM-formatted chain
* Creating a private CA issued certificate
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">domain<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A domain name for which the certificate should be issued
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">domain<wbr>Validation<wbr>Options<span class="property-indicator"></span>
        <span class="property-type"><a href="#certificatedomainvalidationoption">Certificate<wbr>Domain<wbr>Validation<wbr>Option[]?</a></span>
    </dt>
    <dd>{{% md %}}A list of attributes to feed into other resources to complete certificate validation. Can have more than one element, e.g. if SANs are defined. Only set if `DNS`-validation was used.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">options<span class="property-indicator"></span>
        <span class="property-type"><a href="#certificateoptions">Certificate<wbr>Options?</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">private<wbr>Key<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The certificate&#39;s PEM-formatted private key
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">subject<wbr>Alternative<wbr>Names<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}A list of domains that should be SANs in the issued certificate
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">validation<wbr>Emails<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}A list of addresses that received a validation E-Mail. Only set if `EMAIL`-validation was used.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">validation<wbr>Method<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Which method to use for validation. `DNS` or `EMAIL` are valid, `NONE` can be used for certificates that were imported into ACM and then into state managed by this provider.
* Importing an existing certificate
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ARN of the certificate
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">certificate_<wbr>authority_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}ARN of an ACMPCA
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">certificate_<wbr>body<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The certificate&#39;s PEM-formatted public key
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">certificate_<wbr>chain<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The certificate&#39;s PEM-formatted chain
* Creating a private CA issued certificate
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">domain_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A domain name for which the certificate should be issued
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">domain_<wbr>validation_<wbr>options<span class="property-indicator"></span>
        <span class="property-type"><a href="#certificatedomainvalidationoption">List[Certificate<wbr>Domain<wbr>Validation<wbr>Option]</a></span>
    </dt>
    <dd>{{% md %}}A list of attributes to feed into other resources to complete certificate validation. Can have more than one element, e.g. if SANs are defined. Only set if `DNS`-validation was used.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">options<span class="property-indicator"></span>
        <span class="property-type"><a href="#certificateoptions">Dict[Certificate<wbr>Options]</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">private_<wbr>key<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The certificate&#39;s PEM-formatted private key
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">subject_<wbr>alternative_<wbr>names<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}A list of domains that should be SANs in the issued certificate
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">validation_<wbr>emails<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}A list of addresses that received a validation E-Mail. Only set if `EMAIL`-validation was used.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">validation_<wbr>method<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Which method to use for validation. `DNS` or `EMAIL` are valid, `NONE` can be used for certificates that were imported into ACM and then into state managed by this provider.
* Importing an existing certificate
{{% /md %}}</dd>

</dl>
{{% /choosable %}}







## Supporting Types

#### CertificateDomainValidationOption
{{% lang nodejs %}}
> See the   <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#CertificateDomainValidationOption">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the   <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/acm?tab=doc#CertificateDomainValidationOptionOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the   <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Acm.CertificateDomainValidationOption.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Domain<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A domain name for which the certificate should be issued
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Resource<wbr>Record<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the DNS record to create to validate the certificate
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Resource<wbr>Record<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The type of DNS record to create
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Resource<wbr>Record<wbr>Value<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The value the DNS record needs to have
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Domain<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}A domain name for which the certificate should be issued
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Resource<wbr>Record<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name of the DNS record to create to validate the certificate
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Resource<wbr>Record<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The type of DNS record to create
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Resource<wbr>Record<wbr>Value<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The value the DNS record needs to have
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">domain<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A domain name for which the certificate should be issued
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">resource<wbr>Record<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the DNS record to create to validate the certificate
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">resource<wbr>Record<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The type of DNS record to create
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">resource<wbr>Record<wbr>Value<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The value the DNS record needs to have
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">domain_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A domain name for which the certificate should be issued
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">resource<wbr>Record<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the DNS record to create to validate the certificate
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">resource<wbr>Record<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The type of DNS record to create
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">resource<wbr>Record<wbr>Value<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The value the DNS record needs to have
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### CertificateOptions
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#CertificateOptions">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#CertificateOptions">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/acm?tab=doc#CertificateOptionsArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/acm?tab=doc#CertificateOptionsOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Acm.CertificateOptionsArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Acm.CertificateOptions.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Certificate<wbr>Transparency<wbr>Logging<wbr>Preference<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Certificate<wbr>Transparency<wbr>Logging<wbr>Preference<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">certificate<wbr>Transparency<wbr>Logging<wbr>Preference<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">certificate<wbr>Transparency<wbr>Logging<wbr>Preference<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}








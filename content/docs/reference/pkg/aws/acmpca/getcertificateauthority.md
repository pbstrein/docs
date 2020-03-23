
---
title: "GetCertificateAuthority"
block_external_search_index: true
---

Get information on a AWS Certificate Manager Private Certificate Authority (ACM PCA Certificate Authority).

## Example Usage

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const example = aws.acmpca.getCertificateAuthority({
    arn: "arn:aws:acm-pca:us-east-1:123456789012:certificate-authority/12345678-1234-1234-1234-123456789012",
});
```

> This content is derived from https://github.com/terraform-providers/terraform-provider-aws/blob/master/website/docs/d/acmpca_certificate_authority.html.markdown.





## Using GetCertificateAuthority

{{< chooser language "typescript,python,go,csharp" >}}

{{% choosable language typescript %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">function </span>getCertificateAuthority<span class="p">(</span><span class="nx">args</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/acmpca/#GetCertificateAuthorityArgs">GetCertificateAuthorityArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#InvokeOptions">pulumi.InvokeOptions</a></span><span class="p">): Promise&lt;<span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/acmpca/#GetCertificateAuthorityResult">GetCertificateAuthorityResult</a></span>></span></code></pre></div>
{{% /choosable %}}" }}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">function </span> get_certificate_authority(</span>arn=None<span class="p">, </span>revocation_configurations=None<span class="p">, </span>tags=None<span class="p">, </span>opts=None<span class="p">)</span></code></pre></div>
{{% /choosable %}}" }}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>LookupCertificateAuthority<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">args</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/acmpca?tab=doc#LookupCertificateAuthorityArgs">LookupCertificateAuthorityArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#InvokeOption">pulumi.InvokeOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/acmpca?tab=doc#LookupCertificateAuthorityResult">LookupCertificateAuthorityResult</a></span>, error)</span></code></pre></div>
{{% /choosable %}}" }}

{{% choosable language csharp %}}
<div class="highlight">
<pre class="chroma">
<code class="language-csharp" data-lang="csharp"><span class="k">public static class </span><span class="nx">GetCertificateAuthority </span><span class="p">{</span>
    <span class="k">public static </span>Task&lt;<span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Acmpca.GetCertificateAuthorityResult.html">GetCertificateAuthorityResult</a></span>> <span class="p">InvokeAsync(</span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Acmpca.GetCertificateAuthorityArgs.html">GetCertificateAuthorityArgs</a></span> <span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/InvokeOptions.html">InvokeOptions</a></span>? <span class="nx">opts = null<span class="p">)</span>
<span class="p">}</span></code></pre>
</div>
{{% /choosable %}}" }}



The following arguments are supported:



{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of the certificate authority.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Revocation<wbr>Configurations<span class="property-indicator"></span>
        <span class="property-type"><a href="#getcertificateauthorityrevocationconfiguration">List&lt;Get<wbr>Certificate<wbr>Authority<wbr>Revocation<wbr>Configuration<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

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
            title="Required">Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of the certificate authority.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Revocation<wbr>Configurations<span class="property-indicator"></span>
        <span class="property-type"><a href="#getcertificateauthorityrevocationconfiguration">[]Get<wbr>Certificate<wbr>Authority<wbr>Revocation<wbr>Configuration</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

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
            title="Required">arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of the certificate authority.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">revocation<wbr>Configurations<span class="property-indicator"></span>
        <span class="property-type"><a href="#getcertificateauthorityrevocationconfiguration">Get<wbr>Certificate<wbr>Authority<wbr>Revocation<wbr>Configuration[]?</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

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
            title="Required">arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of the certificate authority.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">revocation_<wbr>configurations<span class="property-indicator"></span>
        <span class="property-type"><a href="#getcertificateauthorityrevocationconfiguration">List[Get<wbr>Certificate<wbr>Authority<wbr>Revocation<wbr>Configuration]</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}








## GetCertificateAuthority Result

The following output properties are available:




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">Certificate<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Base64-encoded certificate authority (CA) certificate. Only available after the certificate authority certificate has been imported.
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
            title="">Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}id is the provider-assigned unique ID for this managed resource.
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
            title="">Revocation<wbr>Configurations<span class="property-indicator"></span>
        <span class="property-type"><a href="#getcertificateauthorityrevocationconfiguration">List&lt;Get<wbr>Certificate<wbr>Authority<wbr>Revocation<wbr>Configuration&gt;</a></span>
    </dt>
    <dd>{{% md %}}Nested attribute containing revocation configuration.
* `revocation_configuration.0.crl_configuration` - Nested attribute containing configuration of the certificate revocation list (CRL), if any, maintained by the certificate authority.
* `revocation_configuration.0.crl_configuration.0.custom_cname` - Name inserted into the certificate CRL Distribution Points extension that enables the use of an alias for the CRL distribution point.
* `revocation_configuration.0.crl_configuration.0.enabled` - Boolean value that specifies whether certificate revocation lists (CRLs) are enabled.
* `revocation_configuration.0.crl_configuration.0.expiration_in_days` - Number of days until a certificate expires.
* `revocation_configuration.0.crl_configuration.0.s3_bucket_name` - Name of the S3 bucket that contains the CRL.
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
        <span class="property-type">Dictionary<string, object></span>
    </dt>
    <dd>{{% md %}}Specifies a key-value map of user-defined tags that are attached to the certificate authority.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type of the certificate authority.
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
            title="">Certificate<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Base64-encoded certificate authority (CA) certificate. Only available after the certificate authority certificate has been imported.
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
            title="">Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}id is the provider-assigned unique ID for this managed resource.
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
            title="">Revocation<wbr>Configurations<span class="property-indicator"></span>
        <span class="property-type"><a href="#getcertificateauthorityrevocationconfiguration">[]Get<wbr>Certificate<wbr>Authority<wbr>Revocation<wbr>Configuration</a></span>
    </dt>
    <dd>{{% md %}}Nested attribute containing revocation configuration.
* `revocation_configuration.0.crl_configuration` - Nested attribute containing configuration of the certificate revocation list (CRL), if any, maintained by the certificate authority.
* `revocation_configuration.0.crl_configuration.0.custom_cname` - Name inserted into the certificate CRL Distribution Points extension that enables the use of an alias for the CRL distribution point.
* `revocation_configuration.0.crl_configuration.0.enabled` - Boolean value that specifies whether certificate revocation lists (CRLs) are enabled.
* `revocation_configuration.0.crl_configuration.0.expiration_in_days` - Number of days until a certificate expires.
* `revocation_configuration.0.crl_configuration.0.s3_bucket_name` - Name of the S3 bucket that contains the CRL.
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
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type of the certificate authority.
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
            title="">certificate<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Base64-encoded certificate authority (CA) certificate. Only available after the certificate authority certificate has been imported.
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
            title="">id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}id is the provider-assigned unique ID for this managed resource.
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
            title="">revocation<wbr>Configurations<span class="property-indicator"></span>
        <span class="property-type"><a href="#getcertificateauthorityrevocationconfiguration">Get<wbr>Certificate<wbr>Authority<wbr>Revocation<wbr>Configuration[]</a></span>
    </dt>
    <dd>{{% md %}}Nested attribute containing revocation configuration.
* `revocation_configuration.0.crl_configuration` - Nested attribute containing configuration of the certificate revocation list (CRL), if any, maintained by the certificate authority.
* `revocation_configuration.0.crl_configuration.0.custom_cname` - Name inserted into the certificate CRL Distribution Points extension that enables the use of an alias for the CRL distribution point.
* `revocation_configuration.0.crl_configuration.0.enabled` - Boolean value that specifies whether certificate revocation lists (CRLs) are enabled.
* `revocation_configuration.0.crl_configuration.0.expiration_in_days` - Number of days until a certificate expires.
* `revocation_configuration.0.crl_configuration.0.s3_bucket_name` - Name of the S3 bucket that contains the CRL.
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
        <span class="property-type">{[key: string]: any}</span>
    </dt>
    <dd>{{% md %}}Specifies a key-value map of user-defined tags that are attached to the certificate authority.
{{% /md %}}</dd>

    <dt class="property-"
            title="">type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type of the certificate authority.
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
            title="">certificate<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Base64-encoded certificate authority (CA) certificate. Only available after the certificate authority certificate has been imported.
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
            title="">id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}id is the provider-assigned unique ID for this managed resource.
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
            title="">revocation_<wbr>configurations<span class="property-indicator"></span>
        <span class="property-type"><a href="#getcertificateauthorityrevocationconfiguration">List[Get<wbr>Certificate<wbr>Authority<wbr>Revocation<wbr>Configuration]</a></span>
    </dt>
    <dd>{{% md %}}Nested attribute containing revocation configuration.
* `revocation_configuration.0.crl_configuration` - Nested attribute containing configuration of the certificate revocation list (CRL), if any, maintained by the certificate authority.
* `revocation_configuration.0.crl_configuration.0.custom_cname` - Name inserted into the certificate CRL Distribution Points extension that enables the use of an alias for the CRL distribution point.
* `revocation_configuration.0.crl_configuration.0.enabled` - Boolean value that specifies whether certificate revocation lists (CRLs) are enabled.
* `revocation_configuration.0.crl_configuration.0.expiration_in_days` - Number of days until a certificate expires.
* `revocation_configuration.0.crl_configuration.0.s3_bucket_name` - Name of the S3 bucket that contains the CRL.
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
    <dd>{{% md %}}The type of the certificate authority.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}








## Supporting Types

#### GetCertificateAuthorityRevocationConfiguration
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#GetCertificateAuthorityRevocationConfiguration">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#GetCertificateAuthorityRevocationConfiguration">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/acmpca?tab=doc#GetCertificateAuthorityRevocationConfigurationArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/acmpca?tab=doc#GetCertificateAuthorityRevocationConfiguration">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Acmpca.GetCertificateAuthorityRevocationConfigurationArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Acmpca.GetCertificateAuthorityRevocationConfiguration.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Crl<wbr>Configurations<span class="property-indicator"></span>
        <span class="property-type"><a href="#getcertificateauthorityrevocationconfigurationcrlconfiguration">List&lt;Get<wbr>Certificate<wbr>Authority<wbr>Revocation<wbr>Configuration<wbr>Crl<wbr>Configuration<wbr>Args&gt;</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Crl<wbr>Configurations<span class="property-indicator"></span>
        <span class="property-type"><a href="#getcertificateauthorityrevocationconfigurationcrlconfiguration">[]Get<wbr>Certificate<wbr>Authority<wbr>Revocation<wbr>Configuration<wbr>Crl<wbr>Configuration</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">crl<wbr>Configurations<span class="property-indicator"></span>
        <span class="property-type"><a href="#getcertificateauthorityrevocationconfigurationcrlconfiguration">Get<wbr>Certificate<wbr>Authority<wbr>Revocation<wbr>Configuration<wbr>Crl<wbr>Configuration[]</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">crl<wbr>Configurations<span class="property-indicator"></span>
        <span class="property-type"><a href="#getcertificateauthorityrevocationconfigurationcrlconfiguration">List[Get<wbr>Certificate<wbr>Authority<wbr>Revocation<wbr>Configuration<wbr>Crl<wbr>Configuration]</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### GetCertificateAuthorityRevocationConfigurationCrlConfiguration
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#GetCertificateAuthorityRevocationConfigurationCrlConfiguration">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#GetCertificateAuthorityRevocationConfigurationCrlConfiguration">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/acmpca?tab=doc#GetCertificateAuthorityRevocationConfigurationCrlConfigurationArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/acmpca?tab=doc#GetCertificateAuthorityRevocationConfigurationCrlConfiguration">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Acmpca.GetCertificateAuthorityRevocationConfigurationCrlConfigurationArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Acmpca.GetCertificateAuthorityRevocationConfigurationCrlConfiguration.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Custom<wbr>Cname<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Enabled<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Expiration<wbr>In<wbr>Days<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">S3Bucket<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Custom<wbr>Cname<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Enabled<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Expiration<wbr>In<wbr>Days<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">S3Bucket<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">custom<wbr>Cname<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">enabled<span class="property-indicator"></span>
        <span class="property-type">boolean</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">expiration<wbr>In<wbr>Days<span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">s3Bucket<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">custom<wbr>Cname<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">enabled<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">expiration<wbr>In<wbr>Days<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">s3_<wbr>bucket_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}








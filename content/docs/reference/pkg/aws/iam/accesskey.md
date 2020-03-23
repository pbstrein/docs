
---
title: "AccessKey"
block_external_search_index: true
---

Provides an IAM access key. This is a set of credentials that allow API requests to be made as an IAM user.

> This content is derived from https://github.com/terraform-providers/terraform-provider-aws/blob/master/website/docs/r/iam_access_key.html.markdown.



## Create a AccessKey Resource

{{< chooser language "javascript,typescript,python,go,csharp" / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/iam/#AccessKey">AccessKey</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/iam/#AccessKeyArgs">AccessKeyArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">AccessKey</span><span class="p">(resource_name, opts=None, </span>pgp_key=None<span class="p">, </span>status=None<span class="p">, </span>user=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewAccessKey<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/iam?tab=doc#AccessKeyArgs">AccessKeyArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/iam?tab=doc#AccessKey">AccessKey</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Iam.AccessKey.html">AccessKey</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Iam.AccessKeyArgs.html">AccessKeyArgs</a></span> <span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
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
            title="Optional">Pgp<wbr>Key<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Either a base-64 encoded PGP public key, or a
keybase username in the form `keybase:some_person_that_exists`, for use
in the `encrypted_secret` output attribute.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Status<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The access key status to apply. Defaults to `Active`.
Valid values are `Active` and `Inactive`.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">User<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The IAM user to associate with this access key.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Pgp<wbr>Key<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Either a base-64 encoded PGP public key, or a
keybase username in the form `keybase:some_person_that_exists`, for use
in the `encrypted_secret` output attribute.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Status<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The access key status to apply. Defaults to `Active`.
Valid values are `Active` and `Inactive`.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">User<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The IAM user to associate with this access key.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">pgp<wbr>Key<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Either a base-64 encoded PGP public key, or a
keybase username in the form `keybase:some_person_that_exists`, for use
in the `encrypted_secret` output attribute.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">status<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The access key status to apply. Defaults to `Active`.
Valid values are `Active` and `Inactive`.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">user<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The IAM user to associate with this access key.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">pgp_<wbr>key<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Either a base-64 encoded PGP public key, or a
keybase username in the form `keybase:some_person_that_exists`, for use
in the `encrypted_secret` output attribute.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">status<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The access key status to apply. Defaults to `Active`.
Valid values are `Active` and `Inactive`.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">user<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The IAM user to associate with this access key.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}




## AccessKey Output Properties

The following output properties are available:




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Encrypted<wbr>Secret<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The encrypted secret, base64 encoded, if `pgp_key` was specified.
&gt; **NOTE:** The encrypted secret may be decrypted using the command line,
{{% /md %}}</dd>

    <dt class="property-"
            title="">Key<wbr>Fingerprint<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The fingerprint of the PGP key used to encrypt
the secret
{{% /md %}}</dd>

    <dt class="property-"
            title="">Pgp<wbr>Key<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Either a base-64 encoded PGP public key, or a
keybase username in the form `keybase:some_person_that_exists`, for use
in the `encrypted_secret` output attribute.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Secret<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The secret access key. Note that this will be written
to the state file. If you use this, please protect your backend state file
judiciously. Alternatively, you may supply a `pgp_key` instead, which will
prevent the secret from being stored in plaintext, at the cost of preventing
the use of the secret key in automation.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Ses<wbr>Smtp<wbr>Password<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}**DEPRECATED** The secret access key converted into an SES SMTP
password by applying [AWS&#39;s documented conversion
{{% /md %}}<span class="property-deprecated">AWS SigV2 for SES SMTP passwords isy deprecated.
Use &#39;ses_smtp_password_v4&#39; for region-specific AWS SigV4 signed SES SMTP password instead.</span></dd>

    <dt class="property-"
            title="">Ses<wbr>Smtp<wbr>Password<wbr>V4<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The secret access key converted into an SES SMTP
password by applying [AWS&#39;s documented Sigv4 conversion
algorithm](https://docs.aws.amazon.com/ses/latest/DeveloperGuide/smtp-credentials.html#smtp-credentials-convert).
As SigV4 is region specific, valid Provider regions are `ap-south-1`, `ap-southeast-2`, `eu-central-1`, `eu-west-1`, `us-east-1` and `us-west-2`. See current [AWS SES regions](https://docs.aws.amazon.com/general/latest/gr/rande.html#ses_region)
{{% /md %}}</dd>

    <dt class="property-"
            title="">Status<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The access key status to apply. Defaults to `Active`.
Valid values are `Active` and `Inactive`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">User<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The IAM user to associate with this access key.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Encrypted<wbr>Secret<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The encrypted secret, base64 encoded, if `pgp_key` was specified.
&gt; **NOTE:** The encrypted secret may be decrypted using the command line,
{{% /md %}}</dd>

    <dt class="property-"
            title="">Key<wbr>Fingerprint<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The fingerprint of the PGP key used to encrypt
the secret
{{% /md %}}</dd>

    <dt class="property-"
            title="">Pgp<wbr>Key<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Either a base-64 encoded PGP public key, or a
keybase username in the form `keybase:some_person_that_exists`, for use
in the `encrypted_secret` output attribute.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Secret<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The secret access key. Note that this will be written
to the state file. If you use this, please protect your backend state file
judiciously. Alternatively, you may supply a `pgp_key` instead, which will
prevent the secret from being stored in plaintext, at the cost of preventing
the use of the secret key in automation.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Ses<wbr>Smtp<wbr>Password<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}**DEPRECATED** The secret access key converted into an SES SMTP
password by applying [AWS&#39;s documented conversion
{{% /md %}}<span class="property-deprecated">AWS SigV2 for SES SMTP passwords isy deprecated.
Use &#39;ses_smtp_password_v4&#39; for region-specific AWS SigV4 signed SES SMTP password instead.</span></dd>

    <dt class="property-"
            title="">Ses<wbr>Smtp<wbr>Password<wbr>V4<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The secret access key converted into an SES SMTP
password by applying [AWS&#39;s documented Sigv4 conversion
algorithm](https://docs.aws.amazon.com/ses/latest/DeveloperGuide/smtp-credentials.html#smtp-credentials-convert).
As SigV4 is region specific, valid Provider regions are `ap-south-1`, `ap-southeast-2`, `eu-central-1`, `eu-west-1`, `us-east-1` and `us-west-2`. See current [AWS SES regions](https://docs.aws.amazon.com/general/latest/gr/rande.html#ses_region)
{{% /md %}}</dd>

    <dt class="property-"
            title="">Status<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The access key status to apply. Defaults to `Active`.
Valid values are `Active` and `Inactive`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">User<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The IAM user to associate with this access key.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">encrypted<wbr>Secret<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The encrypted secret, base64 encoded, if `pgp_key` was specified.
&gt; **NOTE:** The encrypted secret may be decrypted using the command line,
{{% /md %}}</dd>

    <dt class="property-"
            title="">key<wbr>Fingerprint<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The fingerprint of the PGP key used to encrypt
the secret
{{% /md %}}</dd>

    <dt class="property-"
            title="">pgp<wbr>Key<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Either a base-64 encoded PGP public key, or a
keybase username in the form `keybase:some_person_that_exists`, for use
in the `encrypted_secret` output attribute.
{{% /md %}}</dd>

    <dt class="property-"
            title="">secret<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The secret access key. Note that this will be written
to the state file. If you use this, please protect your backend state file
judiciously. Alternatively, you may supply a `pgp_key` instead, which will
prevent the secret from being stored in plaintext, at the cost of preventing
the use of the secret key in automation.
{{% /md %}}</dd>

    <dt class="property-"
            title="">ses<wbr>Smtp<wbr>Password<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}**DEPRECATED** The secret access key converted into an SES SMTP
password by applying [AWS&#39;s documented conversion
{{% /md %}}<span class="property-deprecated">AWS SigV2 for SES SMTP passwords isy deprecated.
Use &#39;ses_smtp_password_v4&#39; for region-specific AWS SigV4 signed SES SMTP password instead.</span></dd>

    <dt class="property-"
            title="">ses<wbr>Smtp<wbr>Password<wbr>V4<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The secret access key converted into an SES SMTP
password by applying [AWS&#39;s documented Sigv4 conversion
algorithm](https://docs.aws.amazon.com/ses/latest/DeveloperGuide/smtp-credentials.html#smtp-credentials-convert).
As SigV4 is region specific, valid Provider regions are `ap-south-1`, `ap-southeast-2`, `eu-central-1`, `eu-west-1`, `us-east-1` and `us-west-2`. See current [AWS SES regions](https://docs.aws.amazon.com/general/latest/gr/rande.html#ses_region)
{{% /md %}}</dd>

    <dt class="property-"
            title="">status<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The access key status to apply. Defaults to `Active`.
Valid values are `Active` and `Inactive`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">user<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The IAM user to associate with this access key.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">encrypted_<wbr>secret<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The encrypted secret, base64 encoded, if `pgp_key` was specified.
&gt; **NOTE:** The encrypted secret may be decrypted using the command line,
{{% /md %}}</dd>

    <dt class="property-"
            title="">key_<wbr>fingerprint<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The fingerprint of the PGP key used to encrypt
the secret
{{% /md %}}</dd>

    <dt class="property-"
            title="">pgp_<wbr>key<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Either a base-64 encoded PGP public key, or a
keybase username in the form `keybase:some_person_that_exists`, for use
in the `encrypted_secret` output attribute.
{{% /md %}}</dd>

    <dt class="property-"
            title="">secret<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The secret access key. Note that this will be written
to the state file. If you use this, please protect your backend state file
judiciously. Alternatively, you may supply a `pgp_key` instead, which will
prevent the secret from being stored in plaintext, at the cost of preventing
the use of the secret key in automation.
{{% /md %}}</dd>

    <dt class="property-"
            title="">ses_<wbr>smtp_<wbr>password<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}**DEPRECATED** The secret access key converted into an SES SMTP
password by applying [AWS&#39;s documented conversion
{{% /md %}}<span class="property-deprecated">AWS SigV2 for SES SMTP passwords isy deprecated.
Use &#39;ses_smtp_password_v4&#39; for region-specific AWS SigV4 signed SES SMTP password instead.</span></dd>

    <dt class="property-"
            title="">ses_<wbr>smtp_<wbr>password_<wbr>v4<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The secret access key converted into an SES SMTP
password by applying [AWS&#39;s documented Sigv4 conversion
algorithm](https://docs.aws.amazon.com/ses/latest/DeveloperGuide/smtp-credentials.html#smtp-credentials-convert).
As SigV4 is region specific, valid Provider regions are `ap-south-1`, `ap-southeast-2`, `eu-central-1`, `eu-west-1`, `us-east-1` and `us-west-2`. See current [AWS SES regions](https://docs.aws.amazon.com/general/latest/gr/rande.html#ses_region)
{{% /md %}}</dd>

    <dt class="property-"
            title="">status<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The access key status to apply. Defaults to `Active`.
Valid values are `Active` and `Inactive`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">user<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The IAM user to associate with this access key.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





## Look up an Existing AccessKey Resource

{{< chooser language "javascript,typescript,python,go,csharp  " / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">pulumi.Input&lt;pulumi.ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/iam/#AccessKeyState">AccessKeyState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/iam/#AccessKey">AccessKey</a></span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>encrypted_secret=None<span class="p">, </span>key_fingerprint=None<span class="p">, </span>pgp_key=None<span class="p">, </span>secret=None<span class="p">, </span>ses_smtp_password=None<span class="p">, </span>ses_smtp_password_v4=None<span class="p">, </span>status=None<span class="p">, </span>user=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetAccessKey<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">pulumi.IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/iam?tab=doc#AccessKeyState">AccessKeyState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/iam?tab=doc#AccessKey">AccessKey</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Iam.AccessKey.html">AccessKey</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Pulumi.Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Iam.AccessKeyState.html">AccessKeyState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
{{% /choosable %}}

Get an existing AccessKey resource's state with the given name, ID, and optional extra properties used to qualify the lookup.

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
            title="Optional">Encrypted<wbr>Secret<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The encrypted secret, base64 encoded, if `pgp_key` was specified.
&gt; **NOTE:** The encrypted secret may be decrypted using the command line,
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Key<wbr>Fingerprint<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The fingerprint of the PGP key used to encrypt
the secret
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Pgp<wbr>Key<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Either a base-64 encoded PGP public key, or a
keybase username in the form `keybase:some_person_that_exists`, for use
in the `encrypted_secret` output attribute.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Secret<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The secret access key. Note that this will be written
to the state file. If you use this, please protect your backend state file
judiciously. Alternatively, you may supply a `pgp_key` instead, which will
prevent the secret from being stored in plaintext, at the cost of preventing
the use of the secret key in automation.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ses<wbr>Smtp<wbr>Password<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}**DEPRECATED** The secret access key converted into an SES SMTP
password by applying [AWS&#39;s documented conversion
{{% /md %}}<span class="property-deprecated">AWS SigV2 for SES SMTP passwords isy deprecated.
Use &#39;ses_smtp_password_v4&#39; for region-specific AWS SigV4 signed SES SMTP password instead.</span></dd>

    <dt class="property-optional"
            title="Optional">Ses<wbr>Smtp<wbr>Password<wbr>V4<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The secret access key converted into an SES SMTP
password by applying [AWS&#39;s documented Sigv4 conversion
algorithm](https://docs.aws.amazon.com/ses/latest/DeveloperGuide/smtp-credentials.html#smtp-credentials-convert).
As SigV4 is region specific, valid Provider regions are `ap-south-1`, `ap-southeast-2`, `eu-central-1`, `eu-west-1`, `us-east-1` and `us-west-2`. See current [AWS SES regions](https://docs.aws.amazon.com/general/latest/gr/rande.html#ses_region)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Status<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The access key status to apply. Defaults to `Active`.
Valid values are `Active` and `Inactive`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">User<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The IAM user to associate with this access key.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Encrypted<wbr>Secret<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The encrypted secret, base64 encoded, if `pgp_key` was specified.
&gt; **NOTE:** The encrypted secret may be decrypted using the command line,
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Key<wbr>Fingerprint<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The fingerprint of the PGP key used to encrypt
the secret
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Pgp<wbr>Key<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Either a base-64 encoded PGP public key, or a
keybase username in the form `keybase:some_person_that_exists`, for use
in the `encrypted_secret` output attribute.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Secret<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The secret access key. Note that this will be written
to the state file. If you use this, please protect your backend state file
judiciously. Alternatively, you may supply a `pgp_key` instead, which will
prevent the secret from being stored in plaintext, at the cost of preventing
the use of the secret key in automation.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ses<wbr>Smtp<wbr>Password<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}**DEPRECATED** The secret access key converted into an SES SMTP
password by applying [AWS&#39;s documented conversion
{{% /md %}}<span class="property-deprecated">AWS SigV2 for SES SMTP passwords isy deprecated.
Use &#39;ses_smtp_password_v4&#39; for region-specific AWS SigV4 signed SES SMTP password instead.</span></dd>

    <dt class="property-optional"
            title="Optional">Ses<wbr>Smtp<wbr>Password<wbr>V4<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The secret access key converted into an SES SMTP
password by applying [AWS&#39;s documented Sigv4 conversion
algorithm](https://docs.aws.amazon.com/ses/latest/DeveloperGuide/smtp-credentials.html#smtp-credentials-convert).
As SigV4 is region specific, valid Provider regions are `ap-south-1`, `ap-southeast-2`, `eu-central-1`, `eu-west-1`, `us-east-1` and `us-west-2`. See current [AWS SES regions](https://docs.aws.amazon.com/general/latest/gr/rande.html#ses_region)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Status<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The access key status to apply. Defaults to `Active`.
Valid values are `Active` and `Inactive`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">User<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The IAM user to associate with this access key.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">encrypted<wbr>Secret<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The encrypted secret, base64 encoded, if `pgp_key` was specified.
&gt; **NOTE:** The encrypted secret may be decrypted using the command line,
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">key<wbr>Fingerprint<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The fingerprint of the PGP key used to encrypt
the secret
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">pgp<wbr>Key<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Either a base-64 encoded PGP public key, or a
keybase username in the form `keybase:some_person_that_exists`, for use
in the `encrypted_secret` output attribute.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">secret<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The secret access key. Note that this will be written
to the state file. If you use this, please protect your backend state file
judiciously. Alternatively, you may supply a `pgp_key` instead, which will
prevent the secret from being stored in plaintext, at the cost of preventing
the use of the secret key in automation.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ses<wbr>Smtp<wbr>Password<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}**DEPRECATED** The secret access key converted into an SES SMTP
password by applying [AWS&#39;s documented conversion
{{% /md %}}<span class="property-deprecated">AWS SigV2 for SES SMTP passwords isy deprecated.
Use &#39;ses_smtp_password_v4&#39; for region-specific AWS SigV4 signed SES SMTP password instead.</span></dd>

    <dt class="property-optional"
            title="Optional">ses<wbr>Smtp<wbr>Password<wbr>V4<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The secret access key converted into an SES SMTP
password by applying [AWS&#39;s documented Sigv4 conversion
algorithm](https://docs.aws.amazon.com/ses/latest/DeveloperGuide/smtp-credentials.html#smtp-credentials-convert).
As SigV4 is region specific, valid Provider regions are `ap-south-1`, `ap-southeast-2`, `eu-central-1`, `eu-west-1`, `us-east-1` and `us-west-2`. See current [AWS SES regions](https://docs.aws.amazon.com/general/latest/gr/rande.html#ses_region)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">status<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The access key status to apply. Defaults to `Active`.
Valid values are `Active` and `Inactive`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">user<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The IAM user to associate with this access key.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">encrypted_<wbr>secret<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The encrypted secret, base64 encoded, if `pgp_key` was specified.
&gt; **NOTE:** The encrypted secret may be decrypted using the command line,
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">key_<wbr>fingerprint<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The fingerprint of the PGP key used to encrypt
the secret
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">pgp_<wbr>key<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Either a base-64 encoded PGP public key, or a
keybase username in the form `keybase:some_person_that_exists`, for use
in the `encrypted_secret` output attribute.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">secret<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The secret access key. Note that this will be written
to the state file. If you use this, please protect your backend state file
judiciously. Alternatively, you may supply a `pgp_key` instead, which will
prevent the secret from being stored in plaintext, at the cost of preventing
the use of the secret key in automation.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ses_<wbr>smtp_<wbr>password<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}**DEPRECATED** The secret access key converted into an SES SMTP
password by applying [AWS&#39;s documented conversion
{{% /md %}}<span class="property-deprecated">AWS SigV2 for SES SMTP passwords isy deprecated.
Use &#39;ses_smtp_password_v4&#39; for region-specific AWS SigV4 signed SES SMTP password instead.</span></dd>

    <dt class="property-optional"
            title="Optional">ses_<wbr>smtp_<wbr>password_<wbr>v4<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The secret access key converted into an SES SMTP
password by applying [AWS&#39;s documented Sigv4 conversion
algorithm](https://docs.aws.amazon.com/ses/latest/DeveloperGuide/smtp-credentials.html#smtp-credentials-convert).
As SigV4 is region specific, valid Provider regions are `ap-south-1`, `ap-southeast-2`, `eu-central-1`, `eu-west-1`, `us-east-1` and `us-west-2`. See current [AWS SES regions](https://docs.aws.amazon.com/general/latest/gr/rande.html#ses_region)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">status<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The access key status to apply. Defaults to `Active`.
Valid values are `Active` and `Inactive`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">user<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The IAM user to associate with this access key.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}








---
title: "AccountPasswordPolicy"
block_external_search_index: true
---

> **Note:** There is only a single policy allowed per AWS account. An existing policy will be lost when using this resource as an effect of this limitation.

Manages Password Policy for the AWS Account.
See more about [Account Password Policy](http://docs.aws.amazon.com/IAM/latest/UserGuide/id_credentials_passwords_account-policy.html)
in the official AWS docs.

## Example Usage

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const strict = new aws.iam.AccountPasswordPolicy("strict", {
    allowUsersToChangePassword: true,
    minimumPasswordLength: 8,
    requireLowercaseCharacters: true,
    requireNumbers: true,
    requireSymbols: true,
    requireUppercaseCharacters: true,
});
```

> This content is derived from https://github.com/terraform-providers/terraform-provider-aws/blob/master/website/docs/r/iam_account_password_policy.html.markdown.



## Create a AccountPasswordPolicy Resource

{{< chooser language "javascript,typescript,python,go,csharp" / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/iam/#AccountPasswordPolicy">AccountPasswordPolicy</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/iam/#AccountPasswordPolicyArgs">AccountPasswordPolicyArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">AccountPasswordPolicy</span><span class="p">(resource_name, opts=None, </span>allow_users_to_change_password=None<span class="p">, </span>hard_expiry=None<span class="p">, </span>max_password_age=None<span class="p">, </span>minimum_password_length=None<span class="p">, </span>password_reuse_prevention=None<span class="p">, </span>require_lowercase_characters=None<span class="p">, </span>require_numbers=None<span class="p">, </span>require_symbols=None<span class="p">, </span>require_uppercase_characters=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewAccountPasswordPolicy<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/iam?tab=doc#AccountPasswordPolicyArgs">AccountPasswordPolicyArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/iam?tab=doc#AccountPasswordPolicy">AccountPasswordPolicy</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Iam.AccountPasswordPolicy.html">AccountPasswordPolicy</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Iam.AccountPasswordPolicyArgs.html">AccountPasswordPolicyArgs</a></span>? <span class="nx">args = null<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
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
            title="Optional">Allow<wbr>Users<wbr>To<wbr>Change<wbr>Password<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Whether to allow users to change their own password
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Hard<wbr>Expiry<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Whether users are prevented from setting a new password after their password has expired
(i.e. require administrator reset)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Max<wbr>Password<wbr>Age<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The number of days that an user password is valid.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Minimum<wbr>Password<wbr>Length<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}Minimum length to require for user passwords.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Password<wbr>Reuse<wbr>Prevention<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The number of previous passwords that users are prevented from reusing.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Require<wbr>Lowercase<wbr>Characters<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Whether to require lowercase characters for user passwords.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Require<wbr>Numbers<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Whether to require numbers for user passwords.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Require<wbr>Symbols<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Whether to require symbols for user passwords.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Require<wbr>Uppercase<wbr>Characters<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Whether to require uppercase characters for user passwords.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Allow<wbr>Users<wbr>To<wbr>Change<wbr>Password<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Whether to allow users to change their own password
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Hard<wbr>Expiry<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Whether users are prevented from setting a new password after their password has expired
(i.e. require administrator reset)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Max<wbr>Password<wbr>Age<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The number of days that an user password is valid.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Minimum<wbr>Password<wbr>Length<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}Minimum length to require for user passwords.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Password<wbr>Reuse<wbr>Prevention<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The number of previous passwords that users are prevented from reusing.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Require<wbr>Lowercase<wbr>Characters<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Whether to require lowercase characters for user passwords.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Require<wbr>Numbers<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Whether to require numbers for user passwords.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Require<wbr>Symbols<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Whether to require symbols for user passwords.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Require<wbr>Uppercase<wbr>Characters<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Whether to require uppercase characters for user passwords.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">allow<wbr>Users<wbr>To<wbr>Change<wbr>Password<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Whether to allow users to change their own password
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">hard<wbr>Expiry<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Whether users are prevented from setting a new password after their password has expired
(i.e. require administrator reset)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">max<wbr>Password<wbr>Age<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The number of days that an user password is valid.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">minimum<wbr>Password<wbr>Length<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}Minimum length to require for user passwords.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">password<wbr>Reuse<wbr>Prevention<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The number of previous passwords that users are prevented from reusing.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">require<wbr>Lowercase<wbr>Characters<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Whether to require lowercase characters for user passwords.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">require<wbr>Numbers<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Whether to require numbers for user passwords.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">require<wbr>Symbols<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Whether to require symbols for user passwords.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">require<wbr>Uppercase<wbr>Characters<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Whether to require uppercase characters for user passwords.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">allow_<wbr>users_<wbr>to_<wbr>change_<wbr>password<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Whether to allow users to change their own password
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">hard_<wbr>expiry<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Whether users are prevented from setting a new password after their password has expired
(i.e. require administrator reset)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">max_<wbr>password_<wbr>age<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The number of days that an user password is valid.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">minimum_<wbr>password_<wbr>length<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}Minimum length to require for user passwords.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">password_<wbr>reuse_<wbr>prevention<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The number of previous passwords that users are prevented from reusing.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">require_<wbr>lowercase_<wbr>characters<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Whether to require lowercase characters for user passwords.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">require_<wbr>numbers<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Whether to require numbers for user passwords.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">require_<wbr>symbols<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Whether to require symbols for user passwords.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">require_<wbr>uppercase_<wbr>characters<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Whether to require uppercase characters for user passwords.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}




## AccountPasswordPolicy Output Properties

The following output properties are available:




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Allow<wbr>Users<wbr>To<wbr>Change<wbr>Password<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Whether to allow users to change their own password
{{% /md %}}</dd>

    <dt class="property-"
            title="">Expire<wbr>Passwords<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Indicates whether passwords in the account expire.
Returns `true` if `max_password_age` contains a value greater than `0`.
Returns `false` if it is `0` or _not present_.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Hard<wbr>Expiry<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Whether users are prevented from setting a new password after their password has expired
(i.e. require administrator reset)
{{% /md %}}</dd>

    <dt class="property-"
            title="">Max<wbr>Password<wbr>Age<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The number of days that an user password is valid.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Minimum<wbr>Password<wbr>Length<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}Minimum length to require for user passwords.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Password<wbr>Reuse<wbr>Prevention<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The number of previous passwords that users are prevented from reusing.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Require<wbr>Lowercase<wbr>Characters<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Whether to require lowercase characters for user passwords.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Require<wbr>Numbers<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Whether to require numbers for user passwords.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Require<wbr>Symbols<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Whether to require symbols for user passwords.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Require<wbr>Uppercase<wbr>Characters<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Whether to require uppercase characters for user passwords.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Allow<wbr>Users<wbr>To<wbr>Change<wbr>Password<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Whether to allow users to change their own password
{{% /md %}}</dd>

    <dt class="property-"
            title="">Expire<wbr>Passwords<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Indicates whether passwords in the account expire.
Returns `true` if `max_password_age` contains a value greater than `0`.
Returns `false` if it is `0` or _not present_.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Hard<wbr>Expiry<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Whether users are prevented from setting a new password after their password has expired
(i.e. require administrator reset)
{{% /md %}}</dd>

    <dt class="property-"
            title="">Max<wbr>Password<wbr>Age<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The number of days that an user password is valid.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Minimum<wbr>Password<wbr>Length<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}Minimum length to require for user passwords.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Password<wbr>Reuse<wbr>Prevention<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The number of previous passwords that users are prevented from reusing.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Require<wbr>Lowercase<wbr>Characters<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Whether to require lowercase characters for user passwords.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Require<wbr>Numbers<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Whether to require numbers for user passwords.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Require<wbr>Symbols<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Whether to require symbols for user passwords.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Require<wbr>Uppercase<wbr>Characters<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Whether to require uppercase characters for user passwords.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">allow<wbr>Users<wbr>To<wbr>Change<wbr>Password<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Whether to allow users to change their own password
{{% /md %}}</dd>

    <dt class="property-"
            title="">expire<wbr>Passwords<span class="property-indicator"></span>
        <span class="property-type">boolean</span>
    </dt>
    <dd>{{% md %}}Indicates whether passwords in the account expire.
Returns `true` if `max_password_age` contains a value greater than `0`.
Returns `false` if it is `0` or _not present_.
{{% /md %}}</dd>

    <dt class="property-"
            title="">hard<wbr>Expiry<span class="property-indicator"></span>
        <span class="property-type">boolean</span>
    </dt>
    <dd>{{% md %}}Whether users are prevented from setting a new password after their password has expired
(i.e. require administrator reset)
{{% /md %}}</dd>

    <dt class="property-"
            title="">max<wbr>Password<wbr>Age<span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}The number of days that an user password is valid.
{{% /md %}}</dd>

    <dt class="property-"
            title="">minimum<wbr>Password<wbr>Length<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}Minimum length to require for user passwords.
{{% /md %}}</dd>

    <dt class="property-"
            title="">password<wbr>Reuse<wbr>Prevention<span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}The number of previous passwords that users are prevented from reusing.
{{% /md %}}</dd>

    <dt class="property-"
            title="">require<wbr>Lowercase<wbr>Characters<span class="property-indicator"></span>
        <span class="property-type">boolean</span>
    </dt>
    <dd>{{% md %}}Whether to require lowercase characters for user passwords.
{{% /md %}}</dd>

    <dt class="property-"
            title="">require<wbr>Numbers<span class="property-indicator"></span>
        <span class="property-type">boolean</span>
    </dt>
    <dd>{{% md %}}Whether to require numbers for user passwords.
{{% /md %}}</dd>

    <dt class="property-"
            title="">require<wbr>Symbols<span class="property-indicator"></span>
        <span class="property-type">boolean</span>
    </dt>
    <dd>{{% md %}}Whether to require symbols for user passwords.
{{% /md %}}</dd>

    <dt class="property-"
            title="">require<wbr>Uppercase<wbr>Characters<span class="property-indicator"></span>
        <span class="property-type">boolean</span>
    </dt>
    <dd>{{% md %}}Whether to require uppercase characters for user passwords.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">allow_<wbr>users_<wbr>to_<wbr>change_<wbr>password<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Whether to allow users to change their own password
{{% /md %}}</dd>

    <dt class="property-"
            title="">expire_<wbr>passwords<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Indicates whether passwords in the account expire.
Returns `true` if `max_password_age` contains a value greater than `0`.
Returns `false` if it is `0` or _not present_.
{{% /md %}}</dd>

    <dt class="property-"
            title="">hard_<wbr>expiry<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Whether users are prevented from setting a new password after their password has expired
(i.e. require administrator reset)
{{% /md %}}</dd>

    <dt class="property-"
            title="">max_<wbr>password_<wbr>age<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The number of days that an user password is valid.
{{% /md %}}</dd>

    <dt class="property-"
            title="">minimum_<wbr>password_<wbr>length<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}Minimum length to require for user passwords.
{{% /md %}}</dd>

    <dt class="property-"
            title="">password_<wbr>reuse_<wbr>prevention<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The number of previous passwords that users are prevented from reusing.
{{% /md %}}</dd>

    <dt class="property-"
            title="">require_<wbr>lowercase_<wbr>characters<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Whether to require lowercase characters for user passwords.
{{% /md %}}</dd>

    <dt class="property-"
            title="">require_<wbr>numbers<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Whether to require numbers for user passwords.
{{% /md %}}</dd>

    <dt class="property-"
            title="">require_<wbr>symbols<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Whether to require symbols for user passwords.
{{% /md %}}</dd>

    <dt class="property-"
            title="">require_<wbr>uppercase_<wbr>characters<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Whether to require uppercase characters for user passwords.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





## Look up an Existing AccountPasswordPolicy Resource

{{< chooser language "javascript,typescript,python,go,csharp  " / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">pulumi.Input&lt;pulumi.ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/iam/#AccountPasswordPolicyState">AccountPasswordPolicyState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/iam/#AccountPasswordPolicy">AccountPasswordPolicy</a></span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>allow_users_to_change_password=None<span class="p">, </span>expire_passwords=None<span class="p">, </span>hard_expiry=None<span class="p">, </span>max_password_age=None<span class="p">, </span>minimum_password_length=None<span class="p">, </span>password_reuse_prevention=None<span class="p">, </span>require_lowercase_characters=None<span class="p">, </span>require_numbers=None<span class="p">, </span>require_symbols=None<span class="p">, </span>require_uppercase_characters=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetAccountPasswordPolicy<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">pulumi.IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/iam?tab=doc#AccountPasswordPolicyState">AccountPasswordPolicyState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/iam?tab=doc#AccountPasswordPolicy">AccountPasswordPolicy</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Iam.AccountPasswordPolicy.html">AccountPasswordPolicy</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Pulumi.Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Iam.AccountPasswordPolicyState.html">AccountPasswordPolicyState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
{{% /choosable %}}

Get an existing AccountPasswordPolicy resource's state with the given name, ID, and optional extra properties used to qualify the lookup.

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
            title="Optional">Allow<wbr>Users<wbr>To<wbr>Change<wbr>Password<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Whether to allow users to change their own password
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Expire<wbr>Passwords<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Indicates whether passwords in the account expire.
Returns `true` if `max_password_age` contains a value greater than `0`.
Returns `false` if it is `0` or _not present_.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Hard<wbr>Expiry<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Whether users are prevented from setting a new password after their password has expired
(i.e. require administrator reset)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Max<wbr>Password<wbr>Age<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The number of days that an user password is valid.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Minimum<wbr>Password<wbr>Length<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}Minimum length to require for user passwords.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Password<wbr>Reuse<wbr>Prevention<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The number of previous passwords that users are prevented from reusing.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Require<wbr>Lowercase<wbr>Characters<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Whether to require lowercase characters for user passwords.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Require<wbr>Numbers<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Whether to require numbers for user passwords.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Require<wbr>Symbols<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Whether to require symbols for user passwords.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Require<wbr>Uppercase<wbr>Characters<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Whether to require uppercase characters for user passwords.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Allow<wbr>Users<wbr>To<wbr>Change<wbr>Password<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Whether to allow users to change their own password
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Expire<wbr>Passwords<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Indicates whether passwords in the account expire.
Returns `true` if `max_password_age` contains a value greater than `0`.
Returns `false` if it is `0` or _not present_.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Hard<wbr>Expiry<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Whether users are prevented from setting a new password after their password has expired
(i.e. require administrator reset)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Max<wbr>Password<wbr>Age<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The number of days that an user password is valid.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Minimum<wbr>Password<wbr>Length<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}Minimum length to require for user passwords.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Password<wbr>Reuse<wbr>Prevention<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The number of previous passwords that users are prevented from reusing.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Require<wbr>Lowercase<wbr>Characters<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Whether to require lowercase characters for user passwords.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Require<wbr>Numbers<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Whether to require numbers for user passwords.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Require<wbr>Symbols<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Whether to require symbols for user passwords.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Require<wbr>Uppercase<wbr>Characters<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Whether to require uppercase characters for user passwords.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">allow<wbr>Users<wbr>To<wbr>Change<wbr>Password<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Whether to allow users to change their own password
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">expire<wbr>Passwords<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Indicates whether passwords in the account expire.
Returns `true` if `max_password_age` contains a value greater than `0`.
Returns `false` if it is `0` or _not present_.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">hard<wbr>Expiry<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Whether users are prevented from setting a new password after their password has expired
(i.e. require administrator reset)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">max<wbr>Password<wbr>Age<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The number of days that an user password is valid.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">minimum<wbr>Password<wbr>Length<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}Minimum length to require for user passwords.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">password<wbr>Reuse<wbr>Prevention<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The number of previous passwords that users are prevented from reusing.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">require<wbr>Lowercase<wbr>Characters<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Whether to require lowercase characters for user passwords.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">require<wbr>Numbers<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Whether to require numbers for user passwords.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">require<wbr>Symbols<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Whether to require symbols for user passwords.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">require<wbr>Uppercase<wbr>Characters<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Whether to require uppercase characters for user passwords.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">allow_<wbr>users_<wbr>to_<wbr>change_<wbr>password<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Whether to allow users to change their own password
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">expire_<wbr>passwords<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Indicates whether passwords in the account expire.
Returns `true` if `max_password_age` contains a value greater than `0`.
Returns `false` if it is `0` or _not present_.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">hard_<wbr>expiry<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Whether users are prevented from setting a new password after their password has expired
(i.e. require administrator reset)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">max_<wbr>password_<wbr>age<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The number of days that an user password is valid.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">minimum_<wbr>password_<wbr>length<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}Minimum length to require for user passwords.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">password_<wbr>reuse_<wbr>prevention<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The number of previous passwords that users are prevented from reusing.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">require_<wbr>lowercase_<wbr>characters<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Whether to require lowercase characters for user passwords.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">require_<wbr>numbers<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Whether to require numbers for user passwords.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">require_<wbr>symbols<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Whether to require symbols for user passwords.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">require_<wbr>uppercase_<wbr>characters<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Whether to require uppercase characters for user passwords.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}








---
title: "UserPool"
block_external_search_index: true
---

Provides a Cognito User Pool resource.

## Example Usage

### Basic configuration

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const pool = new aws.cognito.UserPool("pool", {});
```

> This content is derived from https://github.com/terraform-providers/terraform-provider-aws/blob/master/website/docs/r/cognito_user_pool.markdown.



## Create a UserPool Resource

{{< chooser language "javascript,typescript,python,go,csharp" / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/cognito/#UserPool">UserPool</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/cognito/#UserPoolArgs">UserPoolArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">UserPool</span><span class="p">(resource_name, opts=None, </span>admin_create_user_config=None<span class="p">, </span>alias_attributes=None<span class="p">, </span>auto_verified_attributes=None<span class="p">, </span>device_configuration=None<span class="p">, </span>email_configuration=None<span class="p">, </span>email_verification_message=None<span class="p">, </span>email_verification_subject=None<span class="p">, </span>lambda_config=None<span class="p">, </span>mfa_configuration=None<span class="p">, </span>name=None<span class="p">, </span>password_policy=None<span class="p">, </span>schemas=None<span class="p">, </span>sms_authentication_message=None<span class="p">, </span>sms_configuration=None<span class="p">, </span>sms_verification_message=None<span class="p">, </span>tags=None<span class="p">, </span>user_pool_add_ons=None<span class="p">, </span>username_attributes=None<span class="p">, </span>verification_message_template=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewUserPool<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/cognito?tab=doc#UserPoolArgs">UserPoolArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/cognito?tab=doc#UserPool">UserPool</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Cognito.UserPool.html">UserPool</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Cognito.UserPoolArgs.html">UserPoolArgs</a></span>? <span class="nx">args = null<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
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
            title="Optional">Admin<wbr>Create<wbr>User<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#userpooladmincreateuserconfig">User<wbr>Pool<wbr>Admin<wbr>Create<wbr>User<wbr>Config<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}The configuration for AdminCreateUser requests.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Alias<wbr>Attributes<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}Attributes supported as an alias for this user pool. Possible values: phone_number, email, or preferred_username. Conflicts with `username_attributes`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Auto<wbr>Verified<wbr>Attributes<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}The attributes to be auto-verified. Possible values: email, phone_number.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Device<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#userpooldeviceconfiguration">User<wbr>Pool<wbr>Device<wbr>Configuration<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}The configuration for the user pool&#39;s device tracking.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Email<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#userpoolemailconfiguration">User<wbr>Pool<wbr>Email<wbr>Configuration<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}The Email Configuration.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Email<wbr>Verification<wbr>Message<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A string representing the email verification message. Conflicts with `verification_message_template` configuration block `email_message` argument.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Email<wbr>Verification<wbr>Subject<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A string representing the email verification subject. Conflicts with `verification_message_template` configuration block `email_subject` argument.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Lambda<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#userpoollambdaconfig">User<wbr>Pool<wbr>Lambda<wbr>Config<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}A container for the AWS Lambda triggers associated with the user pool.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Mfa<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Set to enable multi-factor authentication. Must be one of the following values (ON, OFF, OPTIONAL)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the attribute.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Password<wbr>Policy<span class="property-indicator"></span>
        <span class="property-type"><a href="#userpoolpasswordpolicy">User<wbr>Pool<wbr>Password<wbr>Policy<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}A container for information about the user pool password policy.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Schemas<span class="property-indicator"></span>
        <span class="property-type"><a href="#userpoolschema">List&lt;User<wbr>Pool<wbr>Schema<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}A container with the schema attributes of a user pool. Schema attributes from the [standard attribute set](https://docs.aws.amazon.com/cognito/latest/developerguide/user-pool-settings-attributes.html#cognito-user-pools-standard-attributes) only need to be specified if they are different from the default configuration. Maximum of 50 attributes.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Sms<wbr>Authentication<wbr>Message<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A string representing the SMS authentication message.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Sms<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#userpoolsmsconfiguration">User<wbr>Pool<wbr>Sms<wbr>Configuration<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}The SMS Configuration.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Sms<wbr>Verification<wbr>Message<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A string representing the SMS verification message. Conflicts with `verification_message_template` configuration block `sms_message` argument.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the User Pool.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">User<wbr>Pool<wbr>Add<wbr>Ons<span class="property-indicator"></span>
        <span class="property-type"><a href="#userpooluserpooladdons">User<wbr>Pool<wbr>User<wbr>Pool<wbr>Add<wbr>Ons<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}Configuration block for user pool add-ons to enable user pool advanced security mode features.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Username<wbr>Attributes<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}Specifies whether email addresses or phone numbers can be specified as usernames when a user signs up. Conflicts with `alias_attributes`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Verification<wbr>Message<wbr>Template<span class="property-indicator"></span>
        <span class="property-type"><a href="#userpoolverificationmessagetemplate">User<wbr>Pool<wbr>Verification<wbr>Message<wbr>Template<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}The verification message templates configuration.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Admin<wbr>Create<wbr>User<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#userpooladmincreateuserconfig">*User<wbr>Pool<wbr>Admin<wbr>Create<wbr>User<wbr>Config</a></span>
    </dt>
    <dd>{{% md %}}The configuration for AdminCreateUser requests.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Alias<wbr>Attributes<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}Attributes supported as an alias for this user pool. Possible values: phone_number, email, or preferred_username. Conflicts with `username_attributes`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Auto<wbr>Verified<wbr>Attributes<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}The attributes to be auto-verified. Possible values: email, phone_number.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Device<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#userpooldeviceconfiguration">*User<wbr>Pool<wbr>Device<wbr>Configuration</a></span>
    </dt>
    <dd>{{% md %}}The configuration for the user pool&#39;s device tracking.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Email<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#userpoolemailconfiguration">*User<wbr>Pool<wbr>Email<wbr>Configuration</a></span>
    </dt>
    <dd>{{% md %}}The Email Configuration.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Email<wbr>Verification<wbr>Message<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}A string representing the email verification message. Conflicts with `verification_message_template` configuration block `email_message` argument.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Email<wbr>Verification<wbr>Subject<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}A string representing the email verification subject. Conflicts with `verification_message_template` configuration block `email_subject` argument.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Lambda<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#userpoollambdaconfig">*User<wbr>Pool<wbr>Lambda<wbr>Config</a></span>
    </dt>
    <dd>{{% md %}}A container for the AWS Lambda triggers associated with the user pool.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Mfa<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Set to enable multi-factor authentication. Must be one of the following values (ON, OFF, OPTIONAL)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name of the attribute.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Password<wbr>Policy<span class="property-indicator"></span>
        <span class="property-type"><a href="#userpoolpasswordpolicy">*User<wbr>Pool<wbr>Password<wbr>Policy</a></span>
    </dt>
    <dd>{{% md %}}A container for information about the user pool password policy.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Schemas<span class="property-indicator"></span>
        <span class="property-type"><a href="#userpoolschema">[]User<wbr>Pool<wbr>Schema</a></span>
    </dt>
    <dd>{{% md %}}A container with the schema attributes of a user pool. Schema attributes from the [standard attribute set](https://docs.aws.amazon.com/cognito/latest/developerguide/user-pool-settings-attributes.html#cognito-user-pools-standard-attributes) only need to be specified if they are different from the default configuration. Maximum of 50 attributes.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Sms<wbr>Authentication<wbr>Message<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}A string representing the SMS authentication message.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Sms<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#userpoolsmsconfiguration">*User<wbr>Pool<wbr>Sms<wbr>Configuration</a></span>
    </dt>
    <dd>{{% md %}}The SMS Configuration.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Sms<wbr>Verification<wbr>Message<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}A string representing the SMS verification message. Conflicts with `verification_message_template` configuration block `sms_message` argument.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the User Pool.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">User<wbr>Pool<wbr>Add<wbr>Ons<span class="property-indicator"></span>
        <span class="property-type"><a href="#userpooluserpooladdons">*User<wbr>Pool<wbr>User<wbr>Pool<wbr>Add<wbr>Ons</a></span>
    </dt>
    <dd>{{% md %}}Configuration block for user pool add-ons to enable user pool advanced security mode features.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Username<wbr>Attributes<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}Specifies whether email addresses or phone numbers can be specified as usernames when a user signs up. Conflicts with `alias_attributes`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Verification<wbr>Message<wbr>Template<span class="property-indicator"></span>
        <span class="property-type"><a href="#userpoolverificationmessagetemplate">*User<wbr>Pool<wbr>Verification<wbr>Message<wbr>Template</a></span>
    </dt>
    <dd>{{% md %}}The verification message templates configuration.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">admin<wbr>Create<wbr>User<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#userpooladmincreateuserconfig">User<wbr>Pool<wbr>Admin<wbr>Create<wbr>User<wbr>Config?</a></span>
    </dt>
    <dd>{{% md %}}The configuration for AdminCreateUser requests.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">alias<wbr>Attributes<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}Attributes supported as an alias for this user pool. Possible values: phone_number, email, or preferred_username. Conflicts with `username_attributes`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">auto<wbr>Verified<wbr>Attributes<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}The attributes to be auto-verified. Possible values: email, phone_number.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">device<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#userpooldeviceconfiguration">User<wbr>Pool<wbr>Device<wbr>Configuration?</a></span>
    </dt>
    <dd>{{% md %}}The configuration for the user pool&#39;s device tracking.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">email<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#userpoolemailconfiguration">User<wbr>Pool<wbr>Email<wbr>Configuration?</a></span>
    </dt>
    <dd>{{% md %}}The Email Configuration.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">email<wbr>Verification<wbr>Message<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A string representing the email verification message. Conflicts with `verification_message_template` configuration block `email_message` argument.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">email<wbr>Verification<wbr>Subject<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A string representing the email verification subject. Conflicts with `verification_message_template` configuration block `email_subject` argument.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">lambda<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#userpoollambdaconfig">User<wbr>Pool<wbr>Lambda<wbr>Config?</a></span>
    </dt>
    <dd>{{% md %}}A container for the AWS Lambda triggers associated with the user pool.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">mfa<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Set to enable multi-factor authentication. Must be one of the following values (ON, OFF, OPTIONAL)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the attribute.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">password<wbr>Policy<span class="property-indicator"></span>
        <span class="property-type"><a href="#userpoolpasswordpolicy">User<wbr>Pool<wbr>Password<wbr>Policy?</a></span>
    </dt>
    <dd>{{% md %}}A container for information about the user pool password policy.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">schemas<span class="property-indicator"></span>
        <span class="property-type"><a href="#userpoolschema">User<wbr>Pool<wbr>Schema[]?</a></span>
    </dt>
    <dd>{{% md %}}A container with the schema attributes of a user pool. Schema attributes from the [standard attribute set](https://docs.aws.amazon.com/cognito/latest/developerguide/user-pool-settings-attributes.html#cognito-user-pools-standard-attributes) only need to be specified if they are different from the default configuration. Maximum of 50 attributes.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">sms<wbr>Authentication<wbr>Message<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A string representing the SMS authentication message.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">sms<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#userpoolsmsconfiguration">User<wbr>Pool<wbr>Sms<wbr>Configuration?</a></span>
    </dt>
    <dd>{{% md %}}The SMS Configuration.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">sms<wbr>Verification<wbr>Message<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A string representing the SMS verification message. Conflicts with `verification_message_template` configuration block `sms_message` argument.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the User Pool.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">user<wbr>Pool<wbr>Add<wbr>Ons<span class="property-indicator"></span>
        <span class="property-type"><a href="#userpooluserpooladdons">User<wbr>Pool<wbr>User<wbr>Pool<wbr>Add<wbr>Ons?</a></span>
    </dt>
    <dd>{{% md %}}Configuration block for user pool add-ons to enable user pool advanced security mode features.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">username<wbr>Attributes<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}Specifies whether email addresses or phone numbers can be specified as usernames when a user signs up. Conflicts with `alias_attributes`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">verification<wbr>Message<wbr>Template<span class="property-indicator"></span>
        <span class="property-type"><a href="#userpoolverificationmessagetemplate">User<wbr>Pool<wbr>Verification<wbr>Message<wbr>Template?</a></span>
    </dt>
    <dd>{{% md %}}The verification message templates configuration.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">admin_<wbr>create_<wbr>user_<wbr>config<span class="property-indicator"></span>
        <span class="property-type"><a href="#userpooladmincreateuserconfig">Dict[User<wbr>Pool<wbr>Admin<wbr>Create<wbr>User<wbr>Config]</a></span>
    </dt>
    <dd>{{% md %}}The configuration for AdminCreateUser requests.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">alias_<wbr>attributes<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}Attributes supported as an alias for this user pool. Possible values: phone_number, email, or preferred_username. Conflicts with `username_attributes`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">auto_<wbr>verified_<wbr>attributes<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}The attributes to be auto-verified. Possible values: email, phone_number.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">device_<wbr>configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#userpooldeviceconfiguration">Dict[User<wbr>Pool<wbr>Device<wbr>Configuration]</a></span>
    </dt>
    <dd>{{% md %}}The configuration for the user pool&#39;s device tracking.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">email_<wbr>configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#userpoolemailconfiguration">Dict[User<wbr>Pool<wbr>Email<wbr>Configuration]</a></span>
    </dt>
    <dd>{{% md %}}The Email Configuration.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">email_<wbr>verification_<wbr>message<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A string representing the email verification message. Conflicts with `verification_message_template` configuration block `email_message` argument.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">email_<wbr>verification_<wbr>subject<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A string representing the email verification subject. Conflicts with `verification_message_template` configuration block `email_subject` argument.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">lambda_<wbr>config<span class="property-indicator"></span>
        <span class="property-type"><a href="#userpoollambdaconfig">Dict[User<wbr>Pool<wbr>Lambda<wbr>Config]</a></span>
    </dt>
    <dd>{{% md %}}A container for the AWS Lambda triggers associated with the user pool.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">mfa_<wbr>configuration<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Set to enable multi-factor authentication. Must be one of the following values (ON, OFF, OPTIONAL)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the attribute.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">password_<wbr>policy<span class="property-indicator"></span>
        <span class="property-type"><a href="#userpoolpasswordpolicy">Dict[User<wbr>Pool<wbr>Password<wbr>Policy]</a></span>
    </dt>
    <dd>{{% md %}}A container for information about the user pool password policy.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">schemas<span class="property-indicator"></span>
        <span class="property-type"><a href="#userpoolschema">List[User<wbr>Pool<wbr>Schema]</a></span>
    </dt>
    <dd>{{% md %}}A container with the schema attributes of a user pool. Schema attributes from the [standard attribute set](https://docs.aws.amazon.com/cognito/latest/developerguide/user-pool-settings-attributes.html#cognito-user-pools-standard-attributes) only need to be specified if they are different from the default configuration. Maximum of 50 attributes.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">sms_<wbr>authentication_<wbr>message<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A string representing the SMS authentication message.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">sms_<wbr>configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#userpoolsmsconfiguration">Dict[User<wbr>Pool<wbr>Sms<wbr>Configuration]</a></span>
    </dt>
    <dd>{{% md %}}The SMS Configuration.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">sms_<wbr>verification_<wbr>message<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A string representing the SMS verification message. Conflicts with `verification_message_template` configuration block `sms_message` argument.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the User Pool.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">user_<wbr>pool_<wbr>add_<wbr>ons<span class="property-indicator"></span>
        <span class="property-type"><a href="#userpooluserpooladdons">Dict[User<wbr>Pool<wbr>User<wbr>Pool<wbr>Add<wbr>Ons]</a></span>
    </dt>
    <dd>{{% md %}}Configuration block for user pool add-ons to enable user pool advanced security mode features.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">username_<wbr>attributes<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}Specifies whether email addresses or phone numbers can be specified as usernames when a user signs up. Conflicts with `alias_attributes`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">verification_<wbr>message_<wbr>template<span class="property-indicator"></span>
        <span class="property-type"><a href="#userpoolverificationmessagetemplate">Dict[User<wbr>Pool<wbr>Verification<wbr>Message<wbr>Template]</a></span>
    </dt>
    <dd>{{% md %}}The verification message templates configuration.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}




## UserPool Output Properties

The following output properties are available:




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Admin<wbr>Create<wbr>User<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#userpooladmincreateuserconfig">User<wbr>Pool<wbr>Admin<wbr>Create<wbr>User<wbr>Config</a></span>
    </dt>
    <dd>{{% md %}}The configuration for AdminCreateUser requests.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Alias<wbr>Attributes<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}Attributes supported as an alias for this user pool. Possible values: phone_number, email, or preferred_username. Conflicts with `username_attributes`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of the user pool.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Auto<wbr>Verified<wbr>Attributes<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}The attributes to be auto-verified. Possible values: email, phone_number.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Creation<wbr>Date<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The date the user pool was created.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Device<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#userpooldeviceconfiguration">User<wbr>Pool<wbr>Device<wbr>Configuration?</a></span>
    </dt>
    <dd>{{% md %}}The configuration for the user pool&#39;s device tracking.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Email<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#userpoolemailconfiguration">User<wbr>Pool<wbr>Email<wbr>Configuration?</a></span>
    </dt>
    <dd>{{% md %}}The Email Configuration.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Email<wbr>Verification<wbr>Message<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}A string representing the email verification message. Conflicts with `verification_message_template` configuration block `email_message` argument.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Email<wbr>Verification<wbr>Subject<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}A string representing the email verification subject. Conflicts with `verification_message_template` configuration block `email_subject` argument.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Endpoint<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The endpoint name of the user pool. Example format: cognito-idp.REGION.amazonaws.com/xxxx_yyyyy
{{% /md %}}</dd>

    <dt class="property-"
            title="">Lambda<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#userpoollambdaconfig">User<wbr>Pool<wbr>Lambda<wbr>Config</a></span>
    </dt>
    <dd>{{% md %}}A container for the AWS Lambda triggers associated with the user pool.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Last<wbr>Modified<wbr>Date<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The date the user pool was last modified.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Mfa<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Set to enable multi-factor authentication. Must be one of the following values (ON, OFF, OPTIONAL)
{{% /md %}}</dd>

    <dt class="property-"
            title="">Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the attribute.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Password<wbr>Policy<span class="property-indicator"></span>
        <span class="property-type"><a href="#userpoolpasswordpolicy">User<wbr>Pool<wbr>Password<wbr>Policy</a></span>
    </dt>
    <dd>{{% md %}}A container for information about the user pool password policy.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Schemas<span class="property-indicator"></span>
        <span class="property-type"><a href="#userpoolschema">List&lt;User<wbr>Pool<wbr>Schema&gt;?</a></span>
    </dt>
    <dd>{{% md %}}A container with the schema attributes of a user pool. Schema attributes from the [standard attribute set](https://docs.aws.amazon.com/cognito/latest/developerguide/user-pool-settings-attributes.html#cognito-user-pools-standard-attributes) only need to be specified if they are different from the default configuration. Maximum of 50 attributes.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Sms<wbr>Authentication<wbr>Message<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A string representing the SMS authentication message.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Sms<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#userpoolsmsconfiguration">User<wbr>Pool<wbr>Sms<wbr>Configuration?</a></span>
    </dt>
    <dd>{{% md %}}The SMS Configuration.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Sms<wbr>Verification<wbr>Message<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}A string representing the SMS verification message. Conflicts with `verification_message_template` configuration block `sms_message` argument.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the User Pool.
{{% /md %}}</dd>

    <dt class="property-"
            title="">User<wbr>Pool<wbr>Add<wbr>Ons<span class="property-indicator"></span>
        <span class="property-type"><a href="#userpooluserpooladdons">User<wbr>Pool<wbr>User<wbr>Pool<wbr>Add<wbr>Ons?</a></span>
    </dt>
    <dd>{{% md %}}Configuration block for user pool add-ons to enable user pool advanced security mode features.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Username<wbr>Attributes<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}Specifies whether email addresses or phone numbers can be specified as usernames when a user signs up. Conflicts with `alias_attributes`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Verification<wbr>Message<wbr>Template<span class="property-indicator"></span>
        <span class="property-type"><a href="#userpoolverificationmessagetemplate">User<wbr>Pool<wbr>Verification<wbr>Message<wbr>Template</a></span>
    </dt>
    <dd>{{% md %}}The verification message templates configuration.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Admin<wbr>Create<wbr>User<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#userpooladmincreateuserconfig">User<wbr>Pool<wbr>Admin<wbr>Create<wbr>User<wbr>Config</a></span>
    </dt>
    <dd>{{% md %}}The configuration for AdminCreateUser requests.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Alias<wbr>Attributes<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}Attributes supported as an alias for this user pool. Possible values: phone_number, email, or preferred_username. Conflicts with `username_attributes`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of the user pool.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Auto<wbr>Verified<wbr>Attributes<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}The attributes to be auto-verified. Possible values: email, phone_number.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Creation<wbr>Date<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The date the user pool was created.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Device<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#userpooldeviceconfiguration">*User<wbr>Pool<wbr>Device<wbr>Configuration</a></span>
    </dt>
    <dd>{{% md %}}The configuration for the user pool&#39;s device tracking.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Email<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#userpoolemailconfiguration">*User<wbr>Pool<wbr>Email<wbr>Configuration</a></span>
    </dt>
    <dd>{{% md %}}The Email Configuration.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Email<wbr>Verification<wbr>Message<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}A string representing the email verification message. Conflicts with `verification_message_template` configuration block `email_message` argument.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Email<wbr>Verification<wbr>Subject<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}A string representing the email verification subject. Conflicts with `verification_message_template` configuration block `email_subject` argument.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Endpoint<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The endpoint name of the user pool. Example format: cognito-idp.REGION.amazonaws.com/xxxx_yyyyy
{{% /md %}}</dd>

    <dt class="property-"
            title="">Lambda<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#userpoollambdaconfig">User<wbr>Pool<wbr>Lambda<wbr>Config</a></span>
    </dt>
    <dd>{{% md %}}A container for the AWS Lambda triggers associated with the user pool.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Last<wbr>Modified<wbr>Date<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The date the user pool was last modified.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Mfa<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Set to enable multi-factor authentication. Must be one of the following values (ON, OFF, OPTIONAL)
{{% /md %}}</dd>

    <dt class="property-"
            title="">Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the attribute.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Password<wbr>Policy<span class="property-indicator"></span>
        <span class="property-type"><a href="#userpoolpasswordpolicy">User<wbr>Pool<wbr>Password<wbr>Policy</a></span>
    </dt>
    <dd>{{% md %}}A container for information about the user pool password policy.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Schemas<span class="property-indicator"></span>
        <span class="property-type"><a href="#userpoolschema">[]User<wbr>Pool<wbr>Schema</a></span>
    </dt>
    <dd>{{% md %}}A container with the schema attributes of a user pool. Schema attributes from the [standard attribute set](https://docs.aws.amazon.com/cognito/latest/developerguide/user-pool-settings-attributes.html#cognito-user-pools-standard-attributes) only need to be specified if they are different from the default configuration. Maximum of 50 attributes.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Sms<wbr>Authentication<wbr>Message<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}A string representing the SMS authentication message.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Sms<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#userpoolsmsconfiguration">*User<wbr>Pool<wbr>Sms<wbr>Configuration</a></span>
    </dt>
    <dd>{{% md %}}The SMS Configuration.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Sms<wbr>Verification<wbr>Message<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}A string representing the SMS verification message. Conflicts with `verification_message_template` configuration block `sms_message` argument.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the User Pool.
{{% /md %}}</dd>

    <dt class="property-"
            title="">User<wbr>Pool<wbr>Add<wbr>Ons<span class="property-indicator"></span>
        <span class="property-type"><a href="#userpooluserpooladdons">*User<wbr>Pool<wbr>User<wbr>Pool<wbr>Add<wbr>Ons</a></span>
    </dt>
    <dd>{{% md %}}Configuration block for user pool add-ons to enable user pool advanced security mode features.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Username<wbr>Attributes<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}Specifies whether email addresses or phone numbers can be specified as usernames when a user signs up. Conflicts with `alias_attributes`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Verification<wbr>Message<wbr>Template<span class="property-indicator"></span>
        <span class="property-type"><a href="#userpoolverificationmessagetemplate">User<wbr>Pool<wbr>Verification<wbr>Message<wbr>Template</a></span>
    </dt>
    <dd>{{% md %}}The verification message templates configuration.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">admin<wbr>Create<wbr>User<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#userpooladmincreateuserconfig">User<wbr>Pool<wbr>Admin<wbr>Create<wbr>User<wbr>Config</a></span>
    </dt>
    <dd>{{% md %}}The configuration for AdminCreateUser requests.
{{% /md %}}</dd>

    <dt class="property-"
            title="">alias<wbr>Attributes<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}Attributes supported as an alias for this user pool. Possible values: phone_number, email, or preferred_username. Conflicts with `username_attributes`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of the user pool.
{{% /md %}}</dd>

    <dt class="property-"
            title="">auto<wbr>Verified<wbr>Attributes<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}The attributes to be auto-verified. Possible values: email, phone_number.
{{% /md %}}</dd>

    <dt class="property-"
            title="">creation<wbr>Date<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The date the user pool was created.
{{% /md %}}</dd>

    <dt class="property-"
            title="">device<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#userpooldeviceconfiguration">User<wbr>Pool<wbr>Device<wbr>Configuration?</a></span>
    </dt>
    <dd>{{% md %}}The configuration for the user pool&#39;s device tracking.
{{% /md %}}</dd>

    <dt class="property-"
            title="">email<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#userpoolemailconfiguration">User<wbr>Pool<wbr>Email<wbr>Configuration?</a></span>
    </dt>
    <dd>{{% md %}}The Email Configuration.
{{% /md %}}</dd>

    <dt class="property-"
            title="">email<wbr>Verification<wbr>Message<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}A string representing the email verification message. Conflicts with `verification_message_template` configuration block `email_message` argument.
{{% /md %}}</dd>

    <dt class="property-"
            title="">email<wbr>Verification<wbr>Subject<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}A string representing the email verification subject. Conflicts with `verification_message_template` configuration block `email_subject` argument.
{{% /md %}}</dd>

    <dt class="property-"
            title="">endpoint<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The endpoint name of the user pool. Example format: cognito-idp.REGION.amazonaws.com/xxxx_yyyyy
{{% /md %}}</dd>

    <dt class="property-"
            title="">lambda<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#userpoollambdaconfig">User<wbr>Pool<wbr>Lambda<wbr>Config</a></span>
    </dt>
    <dd>{{% md %}}A container for the AWS Lambda triggers associated with the user pool.
{{% /md %}}</dd>

    <dt class="property-"
            title="">last<wbr>Modified<wbr>Date<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The date the user pool was last modified.
{{% /md %}}</dd>

    <dt class="property-"
            title="">mfa<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Set to enable multi-factor authentication. Must be one of the following values (ON, OFF, OPTIONAL)
{{% /md %}}</dd>

    <dt class="property-"
            title="">name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the attribute.
{{% /md %}}</dd>

    <dt class="property-"
            title="">password<wbr>Policy<span class="property-indicator"></span>
        <span class="property-type"><a href="#userpoolpasswordpolicy">User<wbr>Pool<wbr>Password<wbr>Policy</a></span>
    </dt>
    <dd>{{% md %}}A container for information about the user pool password policy.
{{% /md %}}</dd>

    <dt class="property-"
            title="">schemas<span class="property-indicator"></span>
        <span class="property-type"><a href="#userpoolschema">User<wbr>Pool<wbr>Schema[]?</a></span>
    </dt>
    <dd>{{% md %}}A container with the schema attributes of a user pool. Schema attributes from the [standard attribute set](https://docs.aws.amazon.com/cognito/latest/developerguide/user-pool-settings-attributes.html#cognito-user-pools-standard-attributes) only need to be specified if they are different from the default configuration. Maximum of 50 attributes.
{{% /md %}}</dd>

    <dt class="property-"
            title="">sms<wbr>Authentication<wbr>Message<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A string representing the SMS authentication message.
{{% /md %}}</dd>

    <dt class="property-"
            title="">sms<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#userpoolsmsconfiguration">User<wbr>Pool<wbr>Sms<wbr>Configuration?</a></span>
    </dt>
    <dd>{{% md %}}The SMS Configuration.
{{% /md %}}</dd>

    <dt class="property-"
            title="">sms<wbr>Verification<wbr>Message<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}A string representing the SMS verification message. Conflicts with `verification_message_template` configuration block `sms_message` argument.
{{% /md %}}</dd>

    <dt class="property-"
            title="">tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the User Pool.
{{% /md %}}</dd>

    <dt class="property-"
            title="">user<wbr>Pool<wbr>Add<wbr>Ons<span class="property-indicator"></span>
        <span class="property-type"><a href="#userpooluserpooladdons">User<wbr>Pool<wbr>User<wbr>Pool<wbr>Add<wbr>Ons?</a></span>
    </dt>
    <dd>{{% md %}}Configuration block for user pool add-ons to enable user pool advanced security mode features.
{{% /md %}}</dd>

    <dt class="property-"
            title="">username<wbr>Attributes<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}Specifies whether email addresses or phone numbers can be specified as usernames when a user signs up. Conflicts with `alias_attributes`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">verification<wbr>Message<wbr>Template<span class="property-indicator"></span>
        <span class="property-type"><a href="#userpoolverificationmessagetemplate">User<wbr>Pool<wbr>Verification<wbr>Message<wbr>Template</a></span>
    </dt>
    <dd>{{% md %}}The verification message templates configuration.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">admin_<wbr>create_<wbr>user_<wbr>config<span class="property-indicator"></span>
        <span class="property-type"><a href="#userpooladmincreateuserconfig">Dict[User<wbr>Pool<wbr>Admin<wbr>Create<wbr>User<wbr>Config]</a></span>
    </dt>
    <dd>{{% md %}}The configuration for AdminCreateUser requests.
{{% /md %}}</dd>

    <dt class="property-"
            title="">alias_<wbr>attributes<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}Attributes supported as an alias for this user pool. Possible values: phone_number, email, or preferred_username. Conflicts with `username_attributes`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ARN of the user pool.
{{% /md %}}</dd>

    <dt class="property-"
            title="">auto_<wbr>verified_<wbr>attributes<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}The attributes to be auto-verified. Possible values: email, phone_number.
{{% /md %}}</dd>

    <dt class="property-"
            title="">creation_<wbr>date<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The date the user pool was created.
{{% /md %}}</dd>

    <dt class="property-"
            title="">device_<wbr>configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#userpooldeviceconfiguration">Dict[User<wbr>Pool<wbr>Device<wbr>Configuration]</a></span>
    </dt>
    <dd>{{% md %}}The configuration for the user pool&#39;s device tracking.
{{% /md %}}</dd>

    <dt class="property-"
            title="">email_<wbr>configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#userpoolemailconfiguration">Dict[User<wbr>Pool<wbr>Email<wbr>Configuration]</a></span>
    </dt>
    <dd>{{% md %}}The Email Configuration.
{{% /md %}}</dd>

    <dt class="property-"
            title="">email_<wbr>verification_<wbr>message<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A string representing the email verification message. Conflicts with `verification_message_template` configuration block `email_message` argument.
{{% /md %}}</dd>

    <dt class="property-"
            title="">email_<wbr>verification_<wbr>subject<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A string representing the email verification subject. Conflicts with `verification_message_template` configuration block `email_subject` argument.
{{% /md %}}</dd>

    <dt class="property-"
            title="">endpoint<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The endpoint name of the user pool. Example format: cognito-idp.REGION.amazonaws.com/xxxx_yyyyy
{{% /md %}}</dd>

    <dt class="property-"
            title="">lambda_<wbr>config<span class="property-indicator"></span>
        <span class="property-type"><a href="#userpoollambdaconfig">Dict[User<wbr>Pool<wbr>Lambda<wbr>Config]</a></span>
    </dt>
    <dd>{{% md %}}A container for the AWS Lambda triggers associated with the user pool.
{{% /md %}}</dd>

    <dt class="property-"
            title="">last_<wbr>modified_<wbr>date<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The date the user pool was last modified.
{{% /md %}}</dd>

    <dt class="property-"
            title="">mfa_<wbr>configuration<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Set to enable multi-factor authentication. Must be one of the following values (ON, OFF, OPTIONAL)
{{% /md %}}</dd>

    <dt class="property-"
            title="">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the attribute.
{{% /md %}}</dd>

    <dt class="property-"
            title="">password_<wbr>policy<span class="property-indicator"></span>
        <span class="property-type"><a href="#userpoolpasswordpolicy">Dict[User<wbr>Pool<wbr>Password<wbr>Policy]</a></span>
    </dt>
    <dd>{{% md %}}A container for information about the user pool password policy.
{{% /md %}}</dd>

    <dt class="property-"
            title="">schemas<span class="property-indicator"></span>
        <span class="property-type"><a href="#userpoolschema">List[User<wbr>Pool<wbr>Schema]</a></span>
    </dt>
    <dd>{{% md %}}A container with the schema attributes of a user pool. Schema attributes from the [standard attribute set](https://docs.aws.amazon.com/cognito/latest/developerguide/user-pool-settings-attributes.html#cognito-user-pools-standard-attributes) only need to be specified if they are different from the default configuration. Maximum of 50 attributes.
{{% /md %}}</dd>

    <dt class="property-"
            title="">sms_<wbr>authentication_<wbr>message<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A string representing the SMS authentication message.
{{% /md %}}</dd>

    <dt class="property-"
            title="">sms_<wbr>configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#userpoolsmsconfiguration">Dict[User<wbr>Pool<wbr>Sms<wbr>Configuration]</a></span>
    </dt>
    <dd>{{% md %}}The SMS Configuration.
{{% /md %}}</dd>

    <dt class="property-"
            title="">sms_<wbr>verification_<wbr>message<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A string representing the SMS verification message. Conflicts with `verification_message_template` configuration block `sms_message` argument.
{{% /md %}}</dd>

    <dt class="property-"
            title="">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the User Pool.
{{% /md %}}</dd>

    <dt class="property-"
            title="">user_<wbr>pool_<wbr>add_<wbr>ons<span class="property-indicator"></span>
        <span class="property-type"><a href="#userpooluserpooladdons">Dict[User<wbr>Pool<wbr>User<wbr>Pool<wbr>Add<wbr>Ons]</a></span>
    </dt>
    <dd>{{% md %}}Configuration block for user pool add-ons to enable user pool advanced security mode features.
{{% /md %}}</dd>

    <dt class="property-"
            title="">username_<wbr>attributes<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}Specifies whether email addresses or phone numbers can be specified as usernames when a user signs up. Conflicts with `alias_attributes`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">verification_<wbr>message_<wbr>template<span class="property-indicator"></span>
        <span class="property-type"><a href="#userpoolverificationmessagetemplate">Dict[User<wbr>Pool<wbr>Verification<wbr>Message<wbr>Template]</a></span>
    </dt>
    <dd>{{% md %}}The verification message templates configuration.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





## Look up an Existing UserPool Resource

{{< chooser language "javascript,typescript,python,go,csharp  " / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">pulumi.Input&lt;pulumi.ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/cognito/#UserPoolState">UserPoolState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/cognito/#UserPool">UserPool</a></span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>admin_create_user_config=None<span class="p">, </span>alias_attributes=None<span class="p">, </span>arn=None<span class="p">, </span>auto_verified_attributes=None<span class="p">, </span>creation_date=None<span class="p">, </span>device_configuration=None<span class="p">, </span>email_configuration=None<span class="p">, </span>email_verification_message=None<span class="p">, </span>email_verification_subject=None<span class="p">, </span>endpoint=None<span class="p">, </span>lambda_config=None<span class="p">, </span>last_modified_date=None<span class="p">, </span>mfa_configuration=None<span class="p">, </span>name=None<span class="p">, </span>password_policy=None<span class="p">, </span>schemas=None<span class="p">, </span>sms_authentication_message=None<span class="p">, </span>sms_configuration=None<span class="p">, </span>sms_verification_message=None<span class="p">, </span>tags=None<span class="p">, </span>user_pool_add_ons=None<span class="p">, </span>username_attributes=None<span class="p">, </span>verification_message_template=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetUserPool<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">pulumi.IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/cognito?tab=doc#UserPoolState">UserPoolState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/cognito?tab=doc#UserPool">UserPool</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Cognito.UserPool.html">UserPool</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Pulumi.Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Cognito.UserPoolState.html">UserPoolState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
{{% /choosable %}}

Get an existing UserPool resource's state with the given name, ID, and optional extra properties used to qualify the lookup.

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
            title="Optional">Admin<wbr>Create<wbr>User<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#userpooladmincreateuserconfig">User<wbr>Pool<wbr>Admin<wbr>Create<wbr>User<wbr>Config<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}The configuration for AdminCreateUser requests.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Alias<wbr>Attributes<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}Attributes supported as an alias for this user pool. Possible values: phone_number, email, or preferred_username. Conflicts with `username_attributes`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ARN of the user pool.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Auto<wbr>Verified<wbr>Attributes<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}The attributes to be auto-verified. Possible values: email, phone_number.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Creation<wbr>Date<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The date the user pool was created.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Device<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#userpooldeviceconfiguration">User<wbr>Pool<wbr>Device<wbr>Configuration<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}The configuration for the user pool&#39;s device tracking.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Email<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#userpoolemailconfiguration">User<wbr>Pool<wbr>Email<wbr>Configuration<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}The Email Configuration.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Email<wbr>Verification<wbr>Message<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A string representing the email verification message. Conflicts with `verification_message_template` configuration block `email_message` argument.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Email<wbr>Verification<wbr>Subject<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A string representing the email verification subject. Conflicts with `verification_message_template` configuration block `email_subject` argument.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Endpoint<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The endpoint name of the user pool. Example format: cognito-idp.REGION.amazonaws.com/xxxx_yyyyy
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Lambda<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#userpoollambdaconfig">User<wbr>Pool<wbr>Lambda<wbr>Config<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}A container for the AWS Lambda triggers associated with the user pool.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Last<wbr>Modified<wbr>Date<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The date the user pool was last modified.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Mfa<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Set to enable multi-factor authentication. Must be one of the following values (ON, OFF, OPTIONAL)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the attribute.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Password<wbr>Policy<span class="property-indicator"></span>
        <span class="property-type"><a href="#userpoolpasswordpolicy">User<wbr>Pool<wbr>Password<wbr>Policy<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}A container for information about the user pool password policy.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Schemas<span class="property-indicator"></span>
        <span class="property-type"><a href="#userpoolschema">List&lt;User<wbr>Pool<wbr>Schema<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}A container with the schema attributes of a user pool. Schema attributes from the [standard attribute set](https://docs.aws.amazon.com/cognito/latest/developerguide/user-pool-settings-attributes.html#cognito-user-pools-standard-attributes) only need to be specified if they are different from the default configuration. Maximum of 50 attributes.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Sms<wbr>Authentication<wbr>Message<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A string representing the SMS authentication message.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Sms<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#userpoolsmsconfiguration">User<wbr>Pool<wbr>Sms<wbr>Configuration<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}The SMS Configuration.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Sms<wbr>Verification<wbr>Message<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A string representing the SMS verification message. Conflicts with `verification_message_template` configuration block `sms_message` argument.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the User Pool.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">User<wbr>Pool<wbr>Add<wbr>Ons<span class="property-indicator"></span>
        <span class="property-type"><a href="#userpooluserpooladdons">User<wbr>Pool<wbr>User<wbr>Pool<wbr>Add<wbr>Ons<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}Configuration block for user pool add-ons to enable user pool advanced security mode features.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Username<wbr>Attributes<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}Specifies whether email addresses or phone numbers can be specified as usernames when a user signs up. Conflicts with `alias_attributes`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Verification<wbr>Message<wbr>Template<span class="property-indicator"></span>
        <span class="property-type"><a href="#userpoolverificationmessagetemplate">User<wbr>Pool<wbr>Verification<wbr>Message<wbr>Template<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}The verification message templates configuration.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Admin<wbr>Create<wbr>User<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#userpooladmincreateuserconfig">*User<wbr>Pool<wbr>Admin<wbr>Create<wbr>User<wbr>Config</a></span>
    </dt>
    <dd>{{% md %}}The configuration for AdminCreateUser requests.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Alias<wbr>Attributes<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}Attributes supported as an alias for this user pool. Possible values: phone_number, email, or preferred_username. Conflicts with `username_attributes`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The ARN of the user pool.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Auto<wbr>Verified<wbr>Attributes<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}The attributes to be auto-verified. Possible values: email, phone_number.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Creation<wbr>Date<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The date the user pool was created.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Device<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#userpooldeviceconfiguration">*User<wbr>Pool<wbr>Device<wbr>Configuration</a></span>
    </dt>
    <dd>{{% md %}}The configuration for the user pool&#39;s device tracking.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Email<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#userpoolemailconfiguration">*User<wbr>Pool<wbr>Email<wbr>Configuration</a></span>
    </dt>
    <dd>{{% md %}}The Email Configuration.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Email<wbr>Verification<wbr>Message<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}A string representing the email verification message. Conflicts with `verification_message_template` configuration block `email_message` argument.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Email<wbr>Verification<wbr>Subject<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}A string representing the email verification subject. Conflicts with `verification_message_template` configuration block `email_subject` argument.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Endpoint<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The endpoint name of the user pool. Example format: cognito-idp.REGION.amazonaws.com/xxxx_yyyyy
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Lambda<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#userpoollambdaconfig">*User<wbr>Pool<wbr>Lambda<wbr>Config</a></span>
    </dt>
    <dd>{{% md %}}A container for the AWS Lambda triggers associated with the user pool.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Last<wbr>Modified<wbr>Date<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The date the user pool was last modified.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Mfa<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Set to enable multi-factor authentication. Must be one of the following values (ON, OFF, OPTIONAL)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name of the attribute.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Password<wbr>Policy<span class="property-indicator"></span>
        <span class="property-type"><a href="#userpoolpasswordpolicy">*User<wbr>Pool<wbr>Password<wbr>Policy</a></span>
    </dt>
    <dd>{{% md %}}A container for information about the user pool password policy.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Schemas<span class="property-indicator"></span>
        <span class="property-type"><a href="#userpoolschema">[]User<wbr>Pool<wbr>Schema</a></span>
    </dt>
    <dd>{{% md %}}A container with the schema attributes of a user pool. Schema attributes from the [standard attribute set](https://docs.aws.amazon.com/cognito/latest/developerguide/user-pool-settings-attributes.html#cognito-user-pools-standard-attributes) only need to be specified if they are different from the default configuration. Maximum of 50 attributes.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Sms<wbr>Authentication<wbr>Message<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}A string representing the SMS authentication message.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Sms<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#userpoolsmsconfiguration">*User<wbr>Pool<wbr>Sms<wbr>Configuration</a></span>
    </dt>
    <dd>{{% md %}}The SMS Configuration.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Sms<wbr>Verification<wbr>Message<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}A string representing the SMS verification message. Conflicts with `verification_message_template` configuration block `sms_message` argument.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the User Pool.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">User<wbr>Pool<wbr>Add<wbr>Ons<span class="property-indicator"></span>
        <span class="property-type"><a href="#userpooluserpooladdons">*User<wbr>Pool<wbr>User<wbr>Pool<wbr>Add<wbr>Ons</a></span>
    </dt>
    <dd>{{% md %}}Configuration block for user pool add-ons to enable user pool advanced security mode features.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Username<wbr>Attributes<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}Specifies whether email addresses or phone numbers can be specified as usernames when a user signs up. Conflicts with `alias_attributes`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Verification<wbr>Message<wbr>Template<span class="property-indicator"></span>
        <span class="property-type"><a href="#userpoolverificationmessagetemplate">*User<wbr>Pool<wbr>Verification<wbr>Message<wbr>Template</a></span>
    </dt>
    <dd>{{% md %}}The verification message templates configuration.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">admin<wbr>Create<wbr>User<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#userpooladmincreateuserconfig">User<wbr>Pool<wbr>Admin<wbr>Create<wbr>User<wbr>Config?</a></span>
    </dt>
    <dd>{{% md %}}The configuration for AdminCreateUser requests.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">alias<wbr>Attributes<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}Attributes supported as an alias for this user pool. Possible values: phone_number, email, or preferred_username. Conflicts with `username_attributes`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ARN of the user pool.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">auto<wbr>Verified<wbr>Attributes<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}The attributes to be auto-verified. Possible values: email, phone_number.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">creation<wbr>Date<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The date the user pool was created.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">device<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#userpooldeviceconfiguration">User<wbr>Pool<wbr>Device<wbr>Configuration?</a></span>
    </dt>
    <dd>{{% md %}}The configuration for the user pool&#39;s device tracking.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">email<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#userpoolemailconfiguration">User<wbr>Pool<wbr>Email<wbr>Configuration?</a></span>
    </dt>
    <dd>{{% md %}}The Email Configuration.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">email<wbr>Verification<wbr>Message<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A string representing the email verification message. Conflicts with `verification_message_template` configuration block `email_message` argument.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">email<wbr>Verification<wbr>Subject<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A string representing the email verification subject. Conflicts with `verification_message_template` configuration block `email_subject` argument.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">endpoint<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The endpoint name of the user pool. Example format: cognito-idp.REGION.amazonaws.com/xxxx_yyyyy
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">lambda<wbr>Config<span class="property-indicator"></span>
        <span class="property-type"><a href="#userpoollambdaconfig">User<wbr>Pool<wbr>Lambda<wbr>Config?</a></span>
    </dt>
    <dd>{{% md %}}A container for the AWS Lambda triggers associated with the user pool.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">last<wbr>Modified<wbr>Date<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The date the user pool was last modified.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">mfa<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Set to enable multi-factor authentication. Must be one of the following values (ON, OFF, OPTIONAL)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the attribute.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">password<wbr>Policy<span class="property-indicator"></span>
        <span class="property-type"><a href="#userpoolpasswordpolicy">User<wbr>Pool<wbr>Password<wbr>Policy?</a></span>
    </dt>
    <dd>{{% md %}}A container for information about the user pool password policy.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">schemas<span class="property-indicator"></span>
        <span class="property-type"><a href="#userpoolschema">User<wbr>Pool<wbr>Schema[]?</a></span>
    </dt>
    <dd>{{% md %}}A container with the schema attributes of a user pool. Schema attributes from the [standard attribute set](https://docs.aws.amazon.com/cognito/latest/developerguide/user-pool-settings-attributes.html#cognito-user-pools-standard-attributes) only need to be specified if they are different from the default configuration. Maximum of 50 attributes.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">sms<wbr>Authentication<wbr>Message<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A string representing the SMS authentication message.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">sms<wbr>Configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#userpoolsmsconfiguration">User<wbr>Pool<wbr>Sms<wbr>Configuration?</a></span>
    </dt>
    <dd>{{% md %}}The SMS Configuration.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">sms<wbr>Verification<wbr>Message<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A string representing the SMS verification message. Conflicts with `verification_message_template` configuration block `sms_message` argument.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the User Pool.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">user<wbr>Pool<wbr>Add<wbr>Ons<span class="property-indicator"></span>
        <span class="property-type"><a href="#userpooluserpooladdons">User<wbr>Pool<wbr>User<wbr>Pool<wbr>Add<wbr>Ons?</a></span>
    </dt>
    <dd>{{% md %}}Configuration block for user pool add-ons to enable user pool advanced security mode features.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">username<wbr>Attributes<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}Specifies whether email addresses or phone numbers can be specified as usernames when a user signs up. Conflicts with `alias_attributes`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">verification<wbr>Message<wbr>Template<span class="property-indicator"></span>
        <span class="property-type"><a href="#userpoolverificationmessagetemplate">User<wbr>Pool<wbr>Verification<wbr>Message<wbr>Template?</a></span>
    </dt>
    <dd>{{% md %}}The verification message templates configuration.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">admin_<wbr>create_<wbr>user_<wbr>config<span class="property-indicator"></span>
        <span class="property-type"><a href="#userpooladmincreateuserconfig">Dict[User<wbr>Pool<wbr>Admin<wbr>Create<wbr>User<wbr>Config]</a></span>
    </dt>
    <dd>{{% md %}}The configuration for AdminCreateUser requests.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">alias_<wbr>attributes<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}Attributes supported as an alias for this user pool. Possible values: phone_number, email, or preferred_username. Conflicts with `username_attributes`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ARN of the user pool.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">auto_<wbr>verified_<wbr>attributes<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}The attributes to be auto-verified. Possible values: email, phone_number.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">creation_<wbr>date<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The date the user pool was created.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">device_<wbr>configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#userpooldeviceconfiguration">Dict[User<wbr>Pool<wbr>Device<wbr>Configuration]</a></span>
    </dt>
    <dd>{{% md %}}The configuration for the user pool&#39;s device tracking.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">email_<wbr>configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#userpoolemailconfiguration">Dict[User<wbr>Pool<wbr>Email<wbr>Configuration]</a></span>
    </dt>
    <dd>{{% md %}}The Email Configuration.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">email_<wbr>verification_<wbr>message<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A string representing the email verification message. Conflicts with `verification_message_template` configuration block `email_message` argument.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">email_<wbr>verification_<wbr>subject<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A string representing the email verification subject. Conflicts with `verification_message_template` configuration block `email_subject` argument.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">endpoint<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The endpoint name of the user pool. Example format: cognito-idp.REGION.amazonaws.com/xxxx_yyyyy
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">lambda_<wbr>config<span class="property-indicator"></span>
        <span class="property-type"><a href="#userpoollambdaconfig">Dict[User<wbr>Pool<wbr>Lambda<wbr>Config]</a></span>
    </dt>
    <dd>{{% md %}}A container for the AWS Lambda triggers associated with the user pool.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">last_<wbr>modified_<wbr>date<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The date the user pool was last modified.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">mfa_<wbr>configuration<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Set to enable multi-factor authentication. Must be one of the following values (ON, OFF, OPTIONAL)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the attribute.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">password_<wbr>policy<span class="property-indicator"></span>
        <span class="property-type"><a href="#userpoolpasswordpolicy">Dict[User<wbr>Pool<wbr>Password<wbr>Policy]</a></span>
    </dt>
    <dd>{{% md %}}A container for information about the user pool password policy.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">schemas<span class="property-indicator"></span>
        <span class="property-type"><a href="#userpoolschema">List[User<wbr>Pool<wbr>Schema]</a></span>
    </dt>
    <dd>{{% md %}}A container with the schema attributes of a user pool. Schema attributes from the [standard attribute set](https://docs.aws.amazon.com/cognito/latest/developerguide/user-pool-settings-attributes.html#cognito-user-pools-standard-attributes) only need to be specified if they are different from the default configuration. Maximum of 50 attributes.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">sms_<wbr>authentication_<wbr>message<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A string representing the SMS authentication message.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">sms_<wbr>configuration<span class="property-indicator"></span>
        <span class="property-type"><a href="#userpoolsmsconfiguration">Dict[User<wbr>Pool<wbr>Sms<wbr>Configuration]</a></span>
    </dt>
    <dd>{{% md %}}The SMS Configuration.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">sms_<wbr>verification_<wbr>message<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A string representing the SMS verification message. Conflicts with `verification_message_template` configuration block `sms_message` argument.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the User Pool.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">user_<wbr>pool_<wbr>add_<wbr>ons<span class="property-indicator"></span>
        <span class="property-type"><a href="#userpooluserpooladdons">Dict[User<wbr>Pool<wbr>User<wbr>Pool<wbr>Add<wbr>Ons]</a></span>
    </dt>
    <dd>{{% md %}}Configuration block for user pool add-ons to enable user pool advanced security mode features.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">username_<wbr>attributes<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}Specifies whether email addresses or phone numbers can be specified as usernames when a user signs up. Conflicts with `alias_attributes`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">verification_<wbr>message_<wbr>template<span class="property-indicator"></span>
        <span class="property-type"><a href="#userpoolverificationmessagetemplate">Dict[User<wbr>Pool<wbr>Verification<wbr>Message<wbr>Template]</a></span>
    </dt>
    <dd>{{% md %}}The verification message templates configuration.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}







## Supporting Types

#### UserPoolAdminCreateUserConfig
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#UserPoolAdminCreateUserConfig">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#UserPoolAdminCreateUserConfig">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/cognito?tab=doc#UserPoolAdminCreateUserConfigArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/cognito?tab=doc#UserPoolAdminCreateUserConfigOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Cognito.UserPoolAdminCreateUserConfigArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Cognito.UserPoolAdminCreateUserConfig.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Allow<wbr>Admin<wbr>Create<wbr>User<wbr>Only<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Set to True if only the administrator is allowed to create user profiles. Set to False if users can sign themselves up via an app.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Invite<wbr>Message<wbr>Template<span class="property-indicator"></span>
        <span class="property-type"><a href="#userpooladmincreateuserconfiginvitemessagetemplate">User<wbr>Pool<wbr>Admin<wbr>Create<wbr>User<wbr>Config<wbr>Invite<wbr>Message<wbr>Template<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}The invite message template structure.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Unused<wbr>Account<wbr>Validity<wbr>Days<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}**DEPRECATED** Use password_policy.temporary_password_validity_days instead - The user account expiration limit, in days, after which the account is no longer usable.
{{% /md %}}<span class="property-deprecated">Use password_policy.temporary_password_validity_days instead</span></dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Allow<wbr>Admin<wbr>Create<wbr>User<wbr>Only<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Set to True if only the administrator is allowed to create user profiles. Set to False if users can sign themselves up via an app.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Invite<wbr>Message<wbr>Template<span class="property-indicator"></span>
        <span class="property-type"><a href="#userpooladmincreateuserconfiginvitemessagetemplate">*User<wbr>Pool<wbr>Admin<wbr>Create<wbr>User<wbr>Config<wbr>Invite<wbr>Message<wbr>Template</a></span>
    </dt>
    <dd>{{% md %}}The invite message template structure.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Unused<wbr>Account<wbr>Validity<wbr>Days<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}**DEPRECATED** Use password_policy.temporary_password_validity_days instead - The user account expiration limit, in days, after which the account is no longer usable.
{{% /md %}}<span class="property-deprecated">Use password_policy.temporary_password_validity_days instead</span></dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">allow<wbr>Admin<wbr>Create<wbr>User<wbr>Only<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Set to True if only the administrator is allowed to create user profiles. Set to False if users can sign themselves up via an app.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">invite<wbr>Message<wbr>Template<span class="property-indicator"></span>
        <span class="property-type"><a href="#userpooladmincreateuserconfiginvitemessagetemplate">User<wbr>Pool<wbr>Admin<wbr>Create<wbr>User<wbr>Config<wbr>Invite<wbr>Message<wbr>Template?</a></span>
    </dt>
    <dd>{{% md %}}The invite message template structure.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">unused<wbr>Account<wbr>Validity<wbr>Days<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}**DEPRECATED** Use password_policy.temporary_password_validity_days instead - The user account expiration limit, in days, after which the account is no longer usable.
{{% /md %}}<span class="property-deprecated">Use password_policy.temporary_password_validity_days instead</span></dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">allow<wbr>Admin<wbr>Create<wbr>User<wbr>Only<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Set to True if only the administrator is allowed to create user profiles. Set to False if users can sign themselves up via an app.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">invite<wbr>Message<wbr>Template<span class="property-indicator"></span>
        <span class="property-type"><a href="#userpooladmincreateuserconfiginvitemessagetemplate">Dict[User<wbr>Pool<wbr>Admin<wbr>Create<wbr>User<wbr>Config<wbr>Invite<wbr>Message<wbr>Template]</a></span>
    </dt>
    <dd>{{% md %}}The invite message template structure.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">unused<wbr>Account<wbr>Validity<wbr>Days<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}**DEPRECATED** Use password_policy.temporary_password_validity_days instead - The user account expiration limit, in days, after which the account is no longer usable.
{{% /md %}}<span class="property-deprecated">Use password_policy.temporary_password_validity_days instead</span></dd>

</dl>
{{% /choosable %}}





#### UserPoolAdminCreateUserConfigInviteMessageTemplate
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#UserPoolAdminCreateUserConfigInviteMessageTemplate">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#UserPoolAdminCreateUserConfigInviteMessageTemplate">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/cognito?tab=doc#UserPoolAdminCreateUserConfigInviteMessageTemplateArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/cognito?tab=doc#UserPoolAdminCreateUserConfigInviteMessageTemplateOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Cognito.UserPoolAdminCreateUserConfigInviteMessageTemplateArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Cognito.UserPoolAdminCreateUserConfigInviteMessageTemplate.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Email<wbr>Message<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The email message template. Must contain the `{####}` placeholder. Conflicts with `email_verification_message` argument.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Email<wbr>Subject<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The subject line for the email message template. Conflicts with `email_verification_subject` argument.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Sms<wbr>Message<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The SMS message template. Must contain the `{####}` placeholder. Conflicts with `sms_verification_message` argument.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Email<wbr>Message<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The email message template. Must contain the `{####}` placeholder. Conflicts with `email_verification_message` argument.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Email<wbr>Subject<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The subject line for the email message template. Conflicts with `email_verification_subject` argument.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Sms<wbr>Message<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The SMS message template. Must contain the `{####}` placeholder. Conflicts with `sms_verification_message` argument.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">email<wbr>Message<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The email message template. Must contain the `{####}` placeholder. Conflicts with `email_verification_message` argument.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">email<wbr>Subject<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The subject line for the email message template. Conflicts with `email_verification_subject` argument.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">sms<wbr>Message<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The SMS message template. Must contain the `{####}` placeholder. Conflicts with `sms_verification_message` argument.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">email<wbr>Message<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The email message template. Must contain the `{####}` placeholder. Conflicts with `email_verification_message` argument.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">email<wbr>Subject<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The subject line for the email message template. Conflicts with `email_verification_subject` argument.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">sms<wbr>Message<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The SMS message template. Must contain the `{####}` placeholder. Conflicts with `sms_verification_message` argument.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### UserPoolDeviceConfiguration
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#UserPoolDeviceConfiguration">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#UserPoolDeviceConfiguration">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/cognito?tab=doc#UserPoolDeviceConfigurationArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/cognito?tab=doc#UserPoolDeviceConfigurationOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Cognito.UserPoolDeviceConfigurationArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Cognito.UserPoolDeviceConfiguration.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Challenge<wbr>Required<wbr>On<wbr>New<wbr>Device<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Indicates whether a challenge is required on a new device. Only applicable to a new device.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Device<wbr>Only<wbr>Remembered<wbr>On<wbr>User<wbr>Prompt<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}If true, a device is only remembered on user prompt.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Challenge<wbr>Required<wbr>On<wbr>New<wbr>Device<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Indicates whether a challenge is required on a new device. Only applicable to a new device.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Device<wbr>Only<wbr>Remembered<wbr>On<wbr>User<wbr>Prompt<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}If true, a device is only remembered on user prompt.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">challenge<wbr>Required<wbr>On<wbr>New<wbr>Device<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Indicates whether a challenge is required on a new device. Only applicable to a new device.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">device<wbr>Only<wbr>Remembered<wbr>On<wbr>User<wbr>Prompt<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}If true, a device is only remembered on user prompt.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">challenge<wbr>Required<wbr>On<wbr>New<wbr>Device<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Indicates whether a challenge is required on a new device. Only applicable to a new device.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">device<wbr>Only<wbr>Remembered<wbr>On<wbr>User<wbr>Prompt<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}If true, a device is only remembered on user prompt.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### UserPoolEmailConfiguration
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#UserPoolEmailConfiguration">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#UserPoolEmailConfiguration">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/cognito?tab=doc#UserPoolEmailConfigurationArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/cognito?tab=doc#UserPoolEmailConfigurationOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Cognito.UserPoolEmailConfigurationArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Cognito.UserPoolEmailConfiguration.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Email<wbr>Sending<wbr>Account<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Instruct Cognito to either use its built-in functional or Amazon SES to send out emails.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Reply<wbr>To<wbr>Email<wbr>Address<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The REPLY-TO email address.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Source<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ARN of the email source.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Email<wbr>Sending<wbr>Account<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Instruct Cognito to either use its built-in functional or Amazon SES to send out emails.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Reply<wbr>To<wbr>Email<wbr>Address<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The REPLY-TO email address.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Source<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The ARN of the email source.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">email<wbr>Sending<wbr>Account<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Instruct Cognito to either use its built-in functional or Amazon SES to send out emails.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">reply<wbr>To<wbr>Email<wbr>Address<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The REPLY-TO email address.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">source<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ARN of the email source.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">email<wbr>Sending<wbr>Account<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Instruct Cognito to either use its built-in functional or Amazon SES to send out emails.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">reply<wbr>To<wbr>Email<wbr>Address<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The REPLY-TO email address.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">source_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ARN of the email source.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### UserPoolLambdaConfig
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#UserPoolLambdaConfig">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#UserPoolLambdaConfig">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/cognito?tab=doc#UserPoolLambdaConfigArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/cognito?tab=doc#UserPoolLambdaConfigOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Cognito.UserPoolLambdaConfigArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Cognito.UserPoolLambdaConfig.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Create<wbr>Auth<wbr>Challenge<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ARN of the lambda creating an authentication challenge.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Custom<wbr>Message<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A custom Message AWS Lambda trigger.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Define<wbr>Auth<wbr>Challenge<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Defines the authentication challenge.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Post<wbr>Authentication<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A post-authentication AWS Lambda trigger.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Post<wbr>Confirmation<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A post-confirmation AWS Lambda trigger.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Pre<wbr>Authentication<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A pre-authentication AWS Lambda trigger.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Pre<wbr>Sign<wbr>Up<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A pre-registration AWS Lambda trigger.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Pre<wbr>Token<wbr>Generation<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Allow to customize identity token claims before token generation.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">User<wbr>Migration<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The user migration Lambda config type.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Verify<wbr>Auth<wbr>Challenge<wbr>Response<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Verifies the authentication challenge response.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Create<wbr>Auth<wbr>Challenge<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The ARN of the lambda creating an authentication challenge.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Custom<wbr>Message<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}A custom Message AWS Lambda trigger.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Define<wbr>Auth<wbr>Challenge<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Defines the authentication challenge.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Post<wbr>Authentication<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}A post-authentication AWS Lambda trigger.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Post<wbr>Confirmation<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}A post-confirmation AWS Lambda trigger.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Pre<wbr>Authentication<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}A pre-authentication AWS Lambda trigger.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Pre<wbr>Sign<wbr>Up<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}A pre-registration AWS Lambda trigger.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Pre<wbr>Token<wbr>Generation<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Allow to customize identity token claims before token generation.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">User<wbr>Migration<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The user migration Lambda config type.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Verify<wbr>Auth<wbr>Challenge<wbr>Response<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Verifies the authentication challenge response.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">create<wbr>Auth<wbr>Challenge<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ARN of the lambda creating an authentication challenge.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">custom<wbr>Message<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A custom Message AWS Lambda trigger.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">define<wbr>Auth<wbr>Challenge<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Defines the authentication challenge.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">post<wbr>Authentication<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A post-authentication AWS Lambda trigger.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">post<wbr>Confirmation<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A post-confirmation AWS Lambda trigger.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">pre<wbr>Authentication<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A pre-authentication AWS Lambda trigger.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">pre<wbr>Sign<wbr>Up<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A pre-registration AWS Lambda trigger.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">pre<wbr>Token<wbr>Generation<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Allow to customize identity token claims before token generation.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">user<wbr>Migration<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The user migration Lambda config type.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">verify<wbr>Auth<wbr>Challenge<wbr>Response<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Verifies the authentication challenge response.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">create<wbr>Auth<wbr>Challenge<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ARN of the lambda creating an authentication challenge.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">custom<wbr>Message<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A custom Message AWS Lambda trigger.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">define<wbr>Auth<wbr>Challenge<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Defines the authentication challenge.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">post<wbr>Authentication<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A post-authentication AWS Lambda trigger.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">post<wbr>Confirmation<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A post-confirmation AWS Lambda trigger.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">pre<wbr>Authentication<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A pre-authentication AWS Lambda trigger.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">pre<wbr>Sign<wbr>Up<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A pre-registration AWS Lambda trigger.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">pre<wbr>Token<wbr>Generation<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Allow to customize identity token claims before token generation.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">user<wbr>Migration<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The user migration Lambda config type.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">verify<wbr>Auth<wbr>Challenge<wbr>Response<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Verifies the authentication challenge response.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### UserPoolPasswordPolicy
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#UserPoolPasswordPolicy">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#UserPoolPasswordPolicy">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/cognito?tab=doc#UserPoolPasswordPolicyArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/cognito?tab=doc#UserPoolPasswordPolicyOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Cognito.UserPoolPasswordPolicyArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Cognito.UserPoolPasswordPolicy.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Minimum<wbr>Length<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The minimum length of the password policy that you have set.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Require<wbr>Lowercase<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Whether you have required users to use at least one lowercase letter in their password.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Require<wbr>Numbers<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Whether you have required users to use at least one number in their password.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Require<wbr>Symbols<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Whether you have required users to use at least one symbol in their password.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Require<wbr>Uppercase<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Whether you have required users to use at least one uppercase letter in their password.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Temporary<wbr>Password<wbr>Validity<wbr>Days<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}In the password policy you have set, refers to the number of days a temporary password is valid. If the user does not sign-in during this time, their password will need to be reset by an administrator.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Minimum<wbr>Length<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The minimum length of the password policy that you have set.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Require<wbr>Lowercase<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Whether you have required users to use at least one lowercase letter in their password.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Require<wbr>Numbers<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Whether you have required users to use at least one number in their password.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Require<wbr>Symbols<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Whether you have required users to use at least one symbol in their password.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Require<wbr>Uppercase<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Whether you have required users to use at least one uppercase letter in their password.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Temporary<wbr>Password<wbr>Validity<wbr>Days<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}In the password policy you have set, refers to the number of days a temporary password is valid. If the user does not sign-in during this time, their password will need to be reset by an administrator.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">minimum<wbr>Length<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The minimum length of the password policy that you have set.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">require<wbr>Lowercase<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Whether you have required users to use at least one lowercase letter in their password.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">require<wbr>Numbers<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Whether you have required users to use at least one number in their password.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">require<wbr>Symbols<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Whether you have required users to use at least one symbol in their password.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">require<wbr>Uppercase<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Whether you have required users to use at least one uppercase letter in their password.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">temporary<wbr>Password<wbr>Validity<wbr>Days<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}In the password policy you have set, refers to the number of days a temporary password is valid. If the user does not sign-in during this time, their password will need to be reset by an administrator.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">minimum<wbr>Length<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The minimum length of the password policy that you have set.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">require<wbr>Lowercase<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Whether you have required users to use at least one lowercase letter in their password.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">require_<wbr>numbers<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Whether you have required users to use at least one number in their password.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">require_<wbr>symbols<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Whether you have required users to use at least one symbol in their password.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">require<wbr>Uppercase<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Whether you have required users to use at least one uppercase letter in their password.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">temporary<wbr>Password<wbr>Validity<wbr>Days<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}In the password policy you have set, refers to the number of days a temporary password is valid. If the user does not sign-in during this time, their password will need to be reset by an administrator.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### UserPoolSchema
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#UserPoolSchema">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#UserPoolSchema">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/cognito?tab=doc#UserPoolSchemaArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/cognito?tab=doc#UserPoolSchemaOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Cognito.UserPoolSchemaArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Cognito.UserPoolSchema.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Attribute<wbr>Data<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The attribute data type. Must be one of `Boolean`, `Number`, `String`, `DateTime`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Developer<wbr>Only<wbr>Attribute<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Specifies whether the attribute type is developer only.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Mutable<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Specifies whether the attribute can be changed once it has been created.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the attribute.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Number<wbr>Attribute<wbr>Constraints<span class="property-indicator"></span>
        <span class="property-type"><a href="#userpoolschemanumberattributeconstraints">User<wbr>Pool<wbr>Schema<wbr>Number<wbr>Attribute<wbr>Constraints<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}Specifies the constraints for an attribute of the number type.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Required<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Specifies whether a user pool attribute is required. If the attribute is required and the user does not provide a value, registration or sign-in will fail.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">String<wbr>Attribute<wbr>Constraints<span class="property-indicator"></span>
        <span class="property-type"><a href="#userpoolschemastringattributeconstraints">User<wbr>Pool<wbr>Schema<wbr>String<wbr>Attribute<wbr>Constraints<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}-Specifies the constraints for an attribute of the string type.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Attribute<wbr>Data<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The attribute data type. Must be one of `Boolean`, `Number`, `String`, `DateTime`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Developer<wbr>Only<wbr>Attribute<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Specifies whether the attribute type is developer only.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Mutable<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Specifies whether the attribute can be changed once it has been created.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the attribute.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Number<wbr>Attribute<wbr>Constraints<span class="property-indicator"></span>
        <span class="property-type"><a href="#userpoolschemanumberattributeconstraints">*User<wbr>Pool<wbr>Schema<wbr>Number<wbr>Attribute<wbr>Constraints</a></span>
    </dt>
    <dd>{{% md %}}Specifies the constraints for an attribute of the number type.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Required<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Specifies whether a user pool attribute is required. If the attribute is required and the user does not provide a value, registration or sign-in will fail.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">String<wbr>Attribute<wbr>Constraints<span class="property-indicator"></span>
        <span class="property-type"><a href="#userpoolschemastringattributeconstraints">*User<wbr>Pool<wbr>Schema<wbr>String<wbr>Attribute<wbr>Constraints</a></span>
    </dt>
    <dd>{{% md %}}-Specifies the constraints for an attribute of the string type.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">attribute<wbr>Data<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The attribute data type. Must be one of `Boolean`, `Number`, `String`, `DateTime`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">developer<wbr>Only<wbr>Attribute<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Specifies whether the attribute type is developer only.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">mutable<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Specifies whether the attribute can be changed once it has been created.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the attribute.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">number<wbr>Attribute<wbr>Constraints<span class="property-indicator"></span>
        <span class="property-type"><a href="#userpoolschemanumberattributeconstraints">User<wbr>Pool<wbr>Schema<wbr>Number<wbr>Attribute<wbr>Constraints?</a></span>
    </dt>
    <dd>{{% md %}}Specifies the constraints for an attribute of the number type.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">required<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Specifies whether a user pool attribute is required. If the attribute is required and the user does not provide a value, registration or sign-in will fail.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">string<wbr>Attribute<wbr>Constraints<span class="property-indicator"></span>
        <span class="property-type"><a href="#userpoolschemastringattributeconstraints">User<wbr>Pool<wbr>Schema<wbr>String<wbr>Attribute<wbr>Constraints?</a></span>
    </dt>
    <dd>{{% md %}}-Specifies the constraints for an attribute of the string type.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">attribute<wbr>Data<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The attribute data type. Must be one of `Boolean`, `Number`, `String`, `DateTime`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">developer<wbr>Only<wbr>Attribute<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Specifies whether the attribute type is developer only.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">mutable<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Specifies whether the attribute can be changed once it has been created.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the attribute.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">number<wbr>Attribute<wbr>Constraints<span class="property-indicator"></span>
        <span class="property-type"><a href="#userpoolschemanumberattributeconstraints">Dict[User<wbr>Pool<wbr>Schema<wbr>Number<wbr>Attribute<wbr>Constraints]</a></span>
    </dt>
    <dd>{{% md %}}Specifies the constraints for an attribute of the number type.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">required<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Specifies whether a user pool attribute is required. If the attribute is required and the user does not provide a value, registration or sign-in will fail.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">string<wbr>Attribute<wbr>Constraints<span class="property-indicator"></span>
        <span class="property-type"><a href="#userpoolschemastringattributeconstraints">Dict[User<wbr>Pool<wbr>Schema<wbr>String<wbr>Attribute<wbr>Constraints]</a></span>
    </dt>
    <dd>{{% md %}}-Specifies the constraints for an attribute of the string type.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### UserPoolSchemaNumberAttributeConstraints
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#UserPoolSchemaNumberAttributeConstraints">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#UserPoolSchemaNumberAttributeConstraints">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/cognito?tab=doc#UserPoolSchemaNumberAttributeConstraintsArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/cognito?tab=doc#UserPoolSchemaNumberAttributeConstraintsOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Cognito.UserPoolSchemaNumberAttributeConstraintsArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Cognito.UserPoolSchemaNumberAttributeConstraints.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Max<wbr>Value<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The maximum value of an attribute that is of the number data type.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Min<wbr>Value<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The minimum value of an attribute that is of the number data type.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Max<wbr>Value<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The maximum value of an attribute that is of the number data type.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Min<wbr>Value<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The minimum value of an attribute that is of the number data type.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">max<wbr>Value<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The maximum value of an attribute that is of the number data type.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">min<wbr>Value<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The minimum value of an attribute that is of the number data type.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">max<wbr>Value<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The maximum value of an attribute that is of the number data type.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">min<wbr>Value<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The minimum value of an attribute that is of the number data type.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### UserPoolSchemaStringAttributeConstraints
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#UserPoolSchemaStringAttributeConstraints">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#UserPoolSchemaStringAttributeConstraints">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/cognito?tab=doc#UserPoolSchemaStringAttributeConstraintsArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/cognito?tab=doc#UserPoolSchemaStringAttributeConstraintsOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Cognito.UserPoolSchemaStringAttributeConstraintsArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Cognito.UserPoolSchemaStringAttributeConstraints.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Max<wbr>Length<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The maximum length of an attribute value of the string type.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Min<wbr>Length<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The minimum length of an attribute value of the string type.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Max<wbr>Length<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The maximum length of an attribute value of the string type.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Min<wbr>Length<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The minimum length of an attribute value of the string type.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">max<wbr>Length<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The maximum length of an attribute value of the string type.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">min<wbr>Length<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The minimum length of an attribute value of the string type.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">max<wbr>Length<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The maximum length of an attribute value of the string type.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">min<wbr>Length<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The minimum length of an attribute value of the string type.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### UserPoolSmsConfiguration
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#UserPoolSmsConfiguration">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#UserPoolSmsConfiguration">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/cognito?tab=doc#UserPoolSmsConfigurationArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/cognito?tab=doc#UserPoolSmsConfigurationOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Cognito.UserPoolSmsConfigurationArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Cognito.UserPoolSmsConfiguration.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">External<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The external ID used in IAM role trust relationships. For more information about using external IDs, see [How to Use an External ID When Granting Access to Your AWS Resources to a Third Party](http://docs.aws.amazon.com/IAM/latest/UserGuide/id_roles_create_for-user_externalid.html).
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Sns<wbr>Caller<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of the Amazon SNS caller. This is usually the IAM role that you&#39;ve given Cognito permission to assume.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">External<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The external ID used in IAM role trust relationships. For more information about using external IDs, see [How to Use an External ID When Granting Access to Your AWS Resources to a Third Party](http://docs.aws.amazon.com/IAM/latest/UserGuide/id_roles_create_for-user_externalid.html).
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Sns<wbr>Caller<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of the Amazon SNS caller. This is usually the IAM role that you&#39;ve given Cognito permission to assume.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">external<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The external ID used in IAM role trust relationships. For more information about using external IDs, see [How to Use an External ID When Granting Access to Your AWS Resources to a Third Party](http://docs.aws.amazon.com/IAM/latest/UserGuide/id_roles_create_for-user_externalid.html).
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">sns<wbr>Caller<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of the Amazon SNS caller. This is usually the IAM role that you&#39;ve given Cognito permission to assume.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">external<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The external ID used in IAM role trust relationships. For more information about using external IDs, see [How to Use an External ID When Granting Access to Your AWS Resources to a Third Party](http://docs.aws.amazon.com/IAM/latest/UserGuide/id_roles_create_for-user_externalid.html).
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">sns<wbr>Caller<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ARN of the Amazon SNS caller. This is usually the IAM role that you&#39;ve given Cognito permission to assume.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### UserPoolUserPoolAddOns
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#UserPoolUserPoolAddOns">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#UserPoolUserPoolAddOns">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/cognito?tab=doc#UserPoolUserPoolAddOnsArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/cognito?tab=doc#UserPoolUserPoolAddOnsOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Cognito.UserPoolUserPoolAddOnsArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Cognito.UserPoolUserPoolAddOns.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Advanced<wbr>Security<wbr>Mode<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The mode for advanced security, must be one of `OFF`, `AUDIT` or `ENFORCED`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Advanced<wbr>Security<wbr>Mode<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The mode for advanced security, must be one of `OFF`, `AUDIT` or `ENFORCED`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">advanced<wbr>Security<wbr>Mode<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The mode for advanced security, must be one of `OFF`, `AUDIT` or `ENFORCED`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">advanced<wbr>Security<wbr>Mode<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The mode for advanced security, must be one of `OFF`, `AUDIT` or `ENFORCED`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### UserPoolVerificationMessageTemplate
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#UserPoolVerificationMessageTemplate">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#UserPoolVerificationMessageTemplate">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/cognito?tab=doc#UserPoolVerificationMessageTemplateArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/cognito?tab=doc#UserPoolVerificationMessageTemplateOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Cognito.UserPoolVerificationMessageTemplateArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Cognito.UserPoolVerificationMessageTemplate.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Default<wbr>Email<wbr>Option<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The default email option. Must be either `CONFIRM_WITH_CODE` or `CONFIRM_WITH_LINK`. Defaults to `CONFIRM_WITH_CODE`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Email<wbr>Message<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The email message template. Must contain the `{####}` placeholder. Conflicts with `email_verification_message` argument.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Email<wbr>Message<wbr>By<wbr>Link<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The email message template for sending a confirmation link to the user, it must contain the `{##Click Here##}` placeholder.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Email<wbr>Subject<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The subject line for the email message template. Conflicts with `email_verification_subject` argument.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Email<wbr>Subject<wbr>By<wbr>Link<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The subject line for the email message template for sending a confirmation link to the user.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Sms<wbr>Message<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The SMS message template. Must contain the `{####}` placeholder. Conflicts with `sms_verification_message` argument.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Default<wbr>Email<wbr>Option<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The default email option. Must be either `CONFIRM_WITH_CODE` or `CONFIRM_WITH_LINK`. Defaults to `CONFIRM_WITH_CODE`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Email<wbr>Message<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The email message template. Must contain the `{####}` placeholder. Conflicts with `email_verification_message` argument.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Email<wbr>Message<wbr>By<wbr>Link<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The email message template for sending a confirmation link to the user, it must contain the `{##Click Here##}` placeholder.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Email<wbr>Subject<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The subject line for the email message template. Conflicts with `email_verification_subject` argument.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Email<wbr>Subject<wbr>By<wbr>Link<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The subject line for the email message template for sending a confirmation link to the user.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Sms<wbr>Message<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The SMS message template. Must contain the `{####}` placeholder. Conflicts with `sms_verification_message` argument.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">default<wbr>Email<wbr>Option<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The default email option. Must be either `CONFIRM_WITH_CODE` or `CONFIRM_WITH_LINK`. Defaults to `CONFIRM_WITH_CODE`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">email<wbr>Message<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The email message template. Must contain the `{####}` placeholder. Conflicts with `email_verification_message` argument.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">email<wbr>Message<wbr>By<wbr>Link<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The email message template for sending a confirmation link to the user, it must contain the `{##Click Here##}` placeholder.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">email<wbr>Subject<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The subject line for the email message template. Conflicts with `email_verification_subject` argument.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">email<wbr>Subject<wbr>By<wbr>Link<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The subject line for the email message template for sending a confirmation link to the user.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">sms<wbr>Message<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The SMS message template. Must contain the `{####}` placeholder. Conflicts with `sms_verification_message` argument.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">default<wbr>Email<wbr>Option<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The default email option. Must be either `CONFIRM_WITH_CODE` or `CONFIRM_WITH_LINK`. Defaults to `CONFIRM_WITH_CODE`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">email<wbr>Message<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The email message template. Must contain the `{####}` placeholder. Conflicts with `email_verification_message` argument.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">email<wbr>Message<wbr>By<wbr>Link<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The email message template for sending a confirmation link to the user, it must contain the `{##Click Here##}` placeholder.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">email<wbr>Subject<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The subject line for the email message template. Conflicts with `email_verification_subject` argument.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">email<wbr>Subject<wbr>By<wbr>Link<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The subject line for the email message template for sending a confirmation link to the user.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">sms<wbr>Message<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The SMS message template. Must contain the `{####}` placeholder. Conflicts with `sms_verification_message` argument.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}








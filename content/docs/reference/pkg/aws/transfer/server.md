
---
title: "Server"
block_external_search_index: true
---

Provides a AWS Transfer Server resource.


```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const fooRole = new aws.iam.Role("foo", {
    assumeRolePolicy: `{
	"Version": "2012-10-17",
	"Statement": [
		{
		"Effect": "Allow",
		"Principal": {
			"Service": "transfer.amazonaws.com"
		},
		"Action": "sts:AssumeRole"
		}
	]
}
`,
});
const fooRolePolicy = new aws.iam.RolePolicy("foo", {
    policy: `{
	"Version": "2012-10-17",
	"Statement": [
		{
		"Sid": "AllowFullAccesstoCloudWatchLogs",
		"Effect": "Allow",
		"Action": [
			"logs:*"
		],
		"Resource": "*"
		}
	]
}
`,
    role: fooRole.id,
});
const fooServer = new aws.transfer.Server("foo", {
    identityProviderType: "SERVICE_MANAGED",
    loggingRole: fooRole.arn,
    tags: {
        ENV: "test",
        NAME: "tf-acc-test-transfer-server",
    },
});
```

> This content is derived from https://github.com/terraform-providers/terraform-provider-aws/blob/master/website/docs/r/transfer_server.html.markdown.



## Create a Server Resource

{{< chooser language "javascript,typescript,python,go,csharp" / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/transfer/#Server">Server</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/transfer/#ServerArgs">ServerArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">Server</span><span class="p">(resource_name, opts=None, </span>endpoint_details=None<span class="p">, </span>endpoint_type=None<span class="p">, </span>force_destroy=None<span class="p">, </span>host_key=None<span class="p">, </span>identity_provider_type=None<span class="p">, </span>invocation_role=None<span class="p">, </span>logging_role=None<span class="p">, </span>tags=None<span class="p">, </span>url=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewServer<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/transfer?tab=doc#ServerArgs">ServerArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/transfer?tab=doc#Server">Server</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Transfer.Server.html">Server</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Transfer.ServerArgs.html">ServerArgs</a></span>? <span class="nx">args = null<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
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
            title="Optional">Endpoint<wbr>Details<span class="property-indicator"></span>
        <span class="property-type"><a href="#serverendpointdetails">Server<wbr>Endpoint<wbr>Details<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}The virtual private cloud (VPC) endpoint settings that you want to configure for your SFTP server. Fields documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Endpoint<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The type of endpoint that you want your SFTP server connect to. If you connect to a `VPC_ENDPOINT`, your SFTP server isn&#39;t accessible over the public internet. If you want to connect your SFTP server via public internet, set `PUBLIC`.  Defaults to `PUBLIC`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Force<wbr>Destroy<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}A boolean that indicates all users associated with the server should be deleted so that the Server can be destroyed without error. The default value is `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Host<wbr>Key<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}RSA private key (e.g. as generated by the `ssh-keygen -N &#34;&#34; -f my-new-server-key` command).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Identity<wbr>Provider<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The mode of authentication enabled for this service. The default value is `SERVICE_MANAGED`, which allows you to store and access SFTP user credentials within the service. `API_GATEWAY` indicates that user authentication requires a call to an API Gateway endpoint URL provided by you to integrate an identity provider of your choice.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Invocation<wbr>Role<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of the IAM role used to authenticate the user account with an `identity_provider_type` of `API_GATEWAY`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Logging<wbr>Role<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of an IAM role that allows the service to write your SFTP users’ activity to your Amazon CloudWatch logs for monitoring and auditing purposes.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Url<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}- URL of the service endpoint used to authenticate users with an `identity_provider_type` of `API_GATEWAY`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Endpoint<wbr>Details<span class="property-indicator"></span>
        <span class="property-type"><a href="#serverendpointdetails">*Server<wbr>Endpoint<wbr>Details</a></span>
    </dt>
    <dd>{{% md %}}The virtual private cloud (VPC) endpoint settings that you want to configure for your SFTP server. Fields documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Endpoint<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The type of endpoint that you want your SFTP server connect to. If you connect to a `VPC_ENDPOINT`, your SFTP server isn&#39;t accessible over the public internet. If you want to connect your SFTP server via public internet, set `PUBLIC`.  Defaults to `PUBLIC`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Force<wbr>Destroy<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}A boolean that indicates all users associated with the server should be deleted so that the Server can be destroyed without error. The default value is `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Host<wbr>Key<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}RSA private key (e.g. as generated by the `ssh-keygen -N &#34;&#34; -f my-new-server-key` command).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Identity<wbr>Provider<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The mode of authentication enabled for this service. The default value is `SERVICE_MANAGED`, which allows you to store and access SFTP user credentials within the service. `API_GATEWAY` indicates that user authentication requires a call to an API Gateway endpoint URL provided by you to integrate an identity provider of your choice.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Invocation<wbr>Role<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of the IAM role used to authenticate the user account with an `identity_provider_type` of `API_GATEWAY`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Logging<wbr>Role<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of an IAM role that allows the service to write your SFTP users’ activity to your Amazon CloudWatch logs for monitoring and auditing purposes.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Url<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}- URL of the service endpoint used to authenticate users with an `identity_provider_type` of `API_GATEWAY`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">endpoint<wbr>Details<span class="property-indicator"></span>
        <span class="property-type"><a href="#serverendpointdetails">Server<wbr>Endpoint<wbr>Details?</a></span>
    </dt>
    <dd>{{% md %}}The virtual private cloud (VPC) endpoint settings that you want to configure for your SFTP server. Fields documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">endpoint<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The type of endpoint that you want your SFTP server connect to. If you connect to a `VPC_ENDPOINT`, your SFTP server isn&#39;t accessible over the public internet. If you want to connect your SFTP server via public internet, set `PUBLIC`.  Defaults to `PUBLIC`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">force<wbr>Destroy<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}A boolean that indicates all users associated with the server should be deleted so that the Server can be destroyed without error. The default value is `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">host<wbr>Key<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}RSA private key (e.g. as generated by the `ssh-keygen -N &#34;&#34; -f my-new-server-key` command).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">identity<wbr>Provider<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The mode of authentication enabled for this service. The default value is `SERVICE_MANAGED`, which allows you to store and access SFTP user credentials within the service. `API_GATEWAY` indicates that user authentication requires a call to an API Gateway endpoint URL provided by you to integrate an identity provider of your choice.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">invocation<wbr>Role<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of the IAM role used to authenticate the user account with an `identity_provider_type` of `API_GATEWAY`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">logging<wbr>Role<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of an IAM role that allows the service to write your SFTP users’ activity to your Amazon CloudWatch logs for monitoring and auditing purposes.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">url<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}- URL of the service endpoint used to authenticate users with an `identity_provider_type` of `API_GATEWAY`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">endpoint_<wbr>details<span class="property-indicator"></span>
        <span class="property-type"><a href="#serverendpointdetails">Dict[Server<wbr>Endpoint<wbr>Details]</a></span>
    </dt>
    <dd>{{% md %}}The virtual private cloud (VPC) endpoint settings that you want to configure for your SFTP server. Fields documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">endpoint_<wbr>type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The type of endpoint that you want your SFTP server connect to. If you connect to a `VPC_ENDPOINT`, your SFTP server isn&#39;t accessible over the public internet. If you want to connect your SFTP server via public internet, set `PUBLIC`.  Defaults to `PUBLIC`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">force_<wbr>destroy<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}A boolean that indicates all users associated with the server should be deleted so that the Server can be destroyed without error. The default value is `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">host_<wbr>key<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}RSA private key (e.g. as generated by the `ssh-keygen -N &#34;&#34; -f my-new-server-key` command).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">identity_<wbr>provider_<wbr>type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The mode of authentication enabled for this service. The default value is `SERVICE_MANAGED`, which allows you to store and access SFTP user credentials within the service. `API_GATEWAY` indicates that user authentication requires a call to an API Gateway endpoint URL provided by you to integrate an identity provider of your choice.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">invocation_<wbr>role<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of the IAM role used to authenticate the user account with an `identity_provider_type` of `API_GATEWAY`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">logging_<wbr>role<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of an IAM role that allows the service to write your SFTP users’ activity to your Amazon CloudWatch logs for monitoring and auditing purposes.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">url<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}- URL of the service endpoint used to authenticate users with an `identity_provider_type` of `API_GATEWAY`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}




## Server Output Properties

The following output properties are available:




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of Transfer Server
{{% /md %}}</dd>

    <dt class="property-"
            title="">Endpoint<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The endpoint of the Transfer Server (e.g. `s-12345678.server.transfer.REGION.amazonaws.com`)
{{% /md %}}</dd>

    <dt class="property-"
            title="">Endpoint<wbr>Details<span class="property-indicator"></span>
        <span class="property-type"><a href="#serverendpointdetails">Server<wbr>Endpoint<wbr>Details?</a></span>
    </dt>
    <dd>{{% md %}}The virtual private cloud (VPC) endpoint settings that you want to configure for your SFTP server. Fields documented below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Endpoint<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The type of endpoint that you want your SFTP server connect to. If you connect to a `VPC_ENDPOINT`, your SFTP server isn&#39;t accessible over the public internet. If you want to connect your SFTP server via public internet, set `PUBLIC`.  Defaults to `PUBLIC`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Force<wbr>Destroy<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}A boolean that indicates all users associated with the server should be deleted so that the Server can be destroyed without error. The default value is `false`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Host<wbr>Key<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}RSA private key (e.g. as generated by the `ssh-keygen -N &#34;&#34; -f my-new-server-key` command).
{{% /md %}}</dd>

    <dt class="property-"
            title="">Host<wbr>Key<wbr>Fingerprint<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}This value contains the message-digest algorithm (MD5) hash of the server&#39;s host key. This value is equivalent to the output of the `ssh-keygen -l -E md5 -f my-new-server-key` command.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Identity<wbr>Provider<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The mode of authentication enabled for this service. The default value is `SERVICE_MANAGED`, which allows you to store and access SFTP user credentials within the service. `API_GATEWAY` indicates that user authentication requires a call to an API Gateway endpoint URL provided by you to integrate an identity provider of your choice.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Invocation<wbr>Role<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of the IAM role used to authenticate the user account with an `identity_provider_type` of `API_GATEWAY`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Logging<wbr>Role<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of an IAM role that allows the service to write your SFTP users’ activity to your Amazon CloudWatch logs for monitoring and auditing purposes.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Url<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}- URL of the service endpoint used to authenticate users with an `identity_provider_type` of `API_GATEWAY`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of Transfer Server
{{% /md %}}</dd>

    <dt class="property-"
            title="">Endpoint<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The endpoint of the Transfer Server (e.g. `s-12345678.server.transfer.REGION.amazonaws.com`)
{{% /md %}}</dd>

    <dt class="property-"
            title="">Endpoint<wbr>Details<span class="property-indicator"></span>
        <span class="property-type"><a href="#serverendpointdetails">*Server<wbr>Endpoint<wbr>Details</a></span>
    </dt>
    <dd>{{% md %}}The virtual private cloud (VPC) endpoint settings that you want to configure for your SFTP server. Fields documented below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Endpoint<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The type of endpoint that you want your SFTP server connect to. If you connect to a `VPC_ENDPOINT`, your SFTP server isn&#39;t accessible over the public internet. If you want to connect your SFTP server via public internet, set `PUBLIC`.  Defaults to `PUBLIC`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Force<wbr>Destroy<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}A boolean that indicates all users associated with the server should be deleted so that the Server can be destroyed without error. The default value is `false`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Host<wbr>Key<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}RSA private key (e.g. as generated by the `ssh-keygen -N &#34;&#34; -f my-new-server-key` command).
{{% /md %}}</dd>

    <dt class="property-"
            title="">Host<wbr>Key<wbr>Fingerprint<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}This value contains the message-digest algorithm (MD5) hash of the server&#39;s host key. This value is equivalent to the output of the `ssh-keygen -l -E md5 -f my-new-server-key` command.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Identity<wbr>Provider<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The mode of authentication enabled for this service. The default value is `SERVICE_MANAGED`, which allows you to store and access SFTP user credentials within the service. `API_GATEWAY` indicates that user authentication requires a call to an API Gateway endpoint URL provided by you to integrate an identity provider of your choice.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Invocation<wbr>Role<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of the IAM role used to authenticate the user account with an `identity_provider_type` of `API_GATEWAY`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Logging<wbr>Role<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of an IAM role that allows the service to write your SFTP users’ activity to your Amazon CloudWatch logs for monitoring and auditing purposes.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Url<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}- URL of the service endpoint used to authenticate users with an `identity_provider_type` of `API_GATEWAY`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of Transfer Server
{{% /md %}}</dd>

    <dt class="property-"
            title="">endpoint<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The endpoint of the Transfer Server (e.g. `s-12345678.server.transfer.REGION.amazonaws.com`)
{{% /md %}}</dd>

    <dt class="property-"
            title="">endpoint<wbr>Details<span class="property-indicator"></span>
        <span class="property-type"><a href="#serverendpointdetails">Server<wbr>Endpoint<wbr>Details?</a></span>
    </dt>
    <dd>{{% md %}}The virtual private cloud (VPC) endpoint settings that you want to configure for your SFTP server. Fields documented below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">endpoint<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The type of endpoint that you want your SFTP server connect to. If you connect to a `VPC_ENDPOINT`, your SFTP server isn&#39;t accessible over the public internet. If you want to connect your SFTP server via public internet, set `PUBLIC`.  Defaults to `PUBLIC`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">force<wbr>Destroy<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}A boolean that indicates all users associated with the server should be deleted so that the Server can be destroyed without error. The default value is `false`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">host<wbr>Key<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}RSA private key (e.g. as generated by the `ssh-keygen -N &#34;&#34; -f my-new-server-key` command).
{{% /md %}}</dd>

    <dt class="property-"
            title="">host<wbr>Key<wbr>Fingerprint<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}This value contains the message-digest algorithm (MD5) hash of the server&#39;s host key. This value is equivalent to the output of the `ssh-keygen -l -E md5 -f my-new-server-key` command.
{{% /md %}}</dd>

    <dt class="property-"
            title="">identity<wbr>Provider<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The mode of authentication enabled for this service. The default value is `SERVICE_MANAGED`, which allows you to store and access SFTP user credentials within the service. `API_GATEWAY` indicates that user authentication requires a call to an API Gateway endpoint URL provided by you to integrate an identity provider of your choice.
{{% /md %}}</dd>

    <dt class="property-"
            title="">invocation<wbr>Role<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of the IAM role used to authenticate the user account with an `identity_provider_type` of `API_GATEWAY`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">logging<wbr>Role<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of an IAM role that allows the service to write your SFTP users’ activity to your Amazon CloudWatch logs for monitoring and auditing purposes.
{{% /md %}}</dd>

    <dt class="property-"
            title="">tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-"
            title="">url<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}- URL of the service endpoint used to authenticate users with an `identity_provider_type` of `API_GATEWAY`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of Transfer Server
{{% /md %}}</dd>

    <dt class="property-"
            title="">endpoint<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The endpoint of the Transfer Server (e.g. `s-12345678.server.transfer.REGION.amazonaws.com`)
{{% /md %}}</dd>

    <dt class="property-"
            title="">endpoint_<wbr>details<span class="property-indicator"></span>
        <span class="property-type"><a href="#serverendpointdetails">Dict[Server<wbr>Endpoint<wbr>Details]</a></span>
    </dt>
    <dd>{{% md %}}The virtual private cloud (VPC) endpoint settings that you want to configure for your SFTP server. Fields documented below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">endpoint_<wbr>type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The type of endpoint that you want your SFTP server connect to. If you connect to a `VPC_ENDPOINT`, your SFTP server isn&#39;t accessible over the public internet. If you want to connect your SFTP server via public internet, set `PUBLIC`.  Defaults to `PUBLIC`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">force_<wbr>destroy<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}A boolean that indicates all users associated with the server should be deleted so that the Server can be destroyed without error. The default value is `false`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">host_<wbr>key<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}RSA private key (e.g. as generated by the `ssh-keygen -N &#34;&#34; -f my-new-server-key` command).
{{% /md %}}</dd>

    <dt class="property-"
            title="">host_<wbr>key_<wbr>fingerprint<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}This value contains the message-digest algorithm (MD5) hash of the server&#39;s host key. This value is equivalent to the output of the `ssh-keygen -l -E md5 -f my-new-server-key` command.
{{% /md %}}</dd>

    <dt class="property-"
            title="">identity_<wbr>provider_<wbr>type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The mode of authentication enabled for this service. The default value is `SERVICE_MANAGED`, which allows you to store and access SFTP user credentials within the service. `API_GATEWAY` indicates that user authentication requires a call to an API Gateway endpoint URL provided by you to integrate an identity provider of your choice.
{{% /md %}}</dd>

    <dt class="property-"
            title="">invocation_<wbr>role<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of the IAM role used to authenticate the user account with an `identity_provider_type` of `API_GATEWAY`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">logging_<wbr>role<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of an IAM role that allows the service to write your SFTP users’ activity to your Amazon CloudWatch logs for monitoring and auditing purposes.
{{% /md %}}</dd>

    <dt class="property-"
            title="">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-"
            title="">url<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}- URL of the service endpoint used to authenticate users with an `identity_provider_type` of `API_GATEWAY`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





## Look up an Existing Server Resource

{{< chooser language "javascript,typescript,python,go,csharp  " / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">pulumi.Input&lt;pulumi.ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/transfer/#ServerState">ServerState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/transfer/#Server">Server</a></span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>arn=None<span class="p">, </span>endpoint=None<span class="p">, </span>endpoint_details=None<span class="p">, </span>endpoint_type=None<span class="p">, </span>force_destroy=None<span class="p">, </span>host_key=None<span class="p">, </span>host_key_fingerprint=None<span class="p">, </span>identity_provider_type=None<span class="p">, </span>invocation_role=None<span class="p">, </span>logging_role=None<span class="p">, </span>tags=None<span class="p">, </span>url=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetServer<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">pulumi.IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/transfer?tab=doc#ServerState">ServerState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/transfer?tab=doc#Server">Server</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Transfer.Server.html">Server</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Pulumi.Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Transfer.ServerState.html">ServerState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
{{% /choosable %}}

Get an existing Server resource's state with the given name, ID, and optional extra properties used to qualify the lookup.

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
    <dd>{{% md %}}Amazon Resource Name (ARN) of Transfer Server
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Endpoint<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The endpoint of the Transfer Server (e.g. `s-12345678.server.transfer.REGION.amazonaws.com`)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Endpoint<wbr>Details<span class="property-indicator"></span>
        <span class="property-type"><a href="#serverendpointdetails">Server<wbr>Endpoint<wbr>Details<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}The virtual private cloud (VPC) endpoint settings that you want to configure for your SFTP server. Fields documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Endpoint<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The type of endpoint that you want your SFTP server connect to. If you connect to a `VPC_ENDPOINT`, your SFTP server isn&#39;t accessible over the public internet. If you want to connect your SFTP server via public internet, set `PUBLIC`.  Defaults to `PUBLIC`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Force<wbr>Destroy<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}A boolean that indicates all users associated with the server should be deleted so that the Server can be destroyed without error. The default value is `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Host<wbr>Key<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}RSA private key (e.g. as generated by the `ssh-keygen -N &#34;&#34; -f my-new-server-key` command).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Host<wbr>Key<wbr>Fingerprint<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}This value contains the message-digest algorithm (MD5) hash of the server&#39;s host key. This value is equivalent to the output of the `ssh-keygen -l -E md5 -f my-new-server-key` command.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Identity<wbr>Provider<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The mode of authentication enabled for this service. The default value is `SERVICE_MANAGED`, which allows you to store and access SFTP user credentials within the service. `API_GATEWAY` indicates that user authentication requires a call to an API Gateway endpoint URL provided by you to integrate an identity provider of your choice.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Invocation<wbr>Role<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of the IAM role used to authenticate the user account with an `identity_provider_type` of `API_GATEWAY`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Logging<wbr>Role<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of an IAM role that allows the service to write your SFTP users’ activity to your Amazon CloudWatch logs for monitoring and auditing purposes.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Url<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}- URL of the service endpoint used to authenticate users with an `identity_provider_type` of `API_GATEWAY`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of Transfer Server
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Endpoint<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The endpoint of the Transfer Server (e.g. `s-12345678.server.transfer.REGION.amazonaws.com`)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Endpoint<wbr>Details<span class="property-indicator"></span>
        <span class="property-type"><a href="#serverendpointdetails">*Server<wbr>Endpoint<wbr>Details</a></span>
    </dt>
    <dd>{{% md %}}The virtual private cloud (VPC) endpoint settings that you want to configure for your SFTP server. Fields documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Endpoint<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The type of endpoint that you want your SFTP server connect to. If you connect to a `VPC_ENDPOINT`, your SFTP server isn&#39;t accessible over the public internet. If you want to connect your SFTP server via public internet, set `PUBLIC`.  Defaults to `PUBLIC`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Force<wbr>Destroy<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}A boolean that indicates all users associated with the server should be deleted so that the Server can be destroyed without error. The default value is `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Host<wbr>Key<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}RSA private key (e.g. as generated by the `ssh-keygen -N &#34;&#34; -f my-new-server-key` command).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Host<wbr>Key<wbr>Fingerprint<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}This value contains the message-digest algorithm (MD5) hash of the server&#39;s host key. This value is equivalent to the output of the `ssh-keygen -l -E md5 -f my-new-server-key` command.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Identity<wbr>Provider<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The mode of authentication enabled for this service. The default value is `SERVICE_MANAGED`, which allows you to store and access SFTP user credentials within the service. `API_GATEWAY` indicates that user authentication requires a call to an API Gateway endpoint URL provided by you to integrate an identity provider of your choice.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Invocation<wbr>Role<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of the IAM role used to authenticate the user account with an `identity_provider_type` of `API_GATEWAY`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Logging<wbr>Role<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of an IAM role that allows the service to write your SFTP users’ activity to your Amazon CloudWatch logs for monitoring and auditing purposes.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Url<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}- URL of the service endpoint used to authenticate users with an `identity_provider_type` of `API_GATEWAY`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of Transfer Server
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">endpoint<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The endpoint of the Transfer Server (e.g. `s-12345678.server.transfer.REGION.amazonaws.com`)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">endpoint<wbr>Details<span class="property-indicator"></span>
        <span class="property-type"><a href="#serverendpointdetails">Server<wbr>Endpoint<wbr>Details?</a></span>
    </dt>
    <dd>{{% md %}}The virtual private cloud (VPC) endpoint settings that you want to configure for your SFTP server. Fields documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">endpoint<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The type of endpoint that you want your SFTP server connect to. If you connect to a `VPC_ENDPOINT`, your SFTP server isn&#39;t accessible over the public internet. If you want to connect your SFTP server via public internet, set `PUBLIC`.  Defaults to `PUBLIC`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">force<wbr>Destroy<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}A boolean that indicates all users associated with the server should be deleted so that the Server can be destroyed without error. The default value is `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">host<wbr>Key<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}RSA private key (e.g. as generated by the `ssh-keygen -N &#34;&#34; -f my-new-server-key` command).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">host<wbr>Key<wbr>Fingerprint<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}This value contains the message-digest algorithm (MD5) hash of the server&#39;s host key. This value is equivalent to the output of the `ssh-keygen -l -E md5 -f my-new-server-key` command.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">identity<wbr>Provider<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The mode of authentication enabled for this service. The default value is `SERVICE_MANAGED`, which allows you to store and access SFTP user credentials within the service. `API_GATEWAY` indicates that user authentication requires a call to an API Gateway endpoint URL provided by you to integrate an identity provider of your choice.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">invocation<wbr>Role<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of the IAM role used to authenticate the user account with an `identity_provider_type` of `API_GATEWAY`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">logging<wbr>Role<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of an IAM role that allows the service to write your SFTP users’ activity to your Amazon CloudWatch logs for monitoring and auditing purposes.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">url<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}- URL of the service endpoint used to authenticate users with an `identity_provider_type` of `API_GATEWAY`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of Transfer Server
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">endpoint<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The endpoint of the Transfer Server (e.g. `s-12345678.server.transfer.REGION.amazonaws.com`)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">endpoint_<wbr>details<span class="property-indicator"></span>
        <span class="property-type"><a href="#serverendpointdetails">Dict[Server<wbr>Endpoint<wbr>Details]</a></span>
    </dt>
    <dd>{{% md %}}The virtual private cloud (VPC) endpoint settings that you want to configure for your SFTP server. Fields documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">endpoint_<wbr>type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The type of endpoint that you want your SFTP server connect to. If you connect to a `VPC_ENDPOINT`, your SFTP server isn&#39;t accessible over the public internet. If you want to connect your SFTP server via public internet, set `PUBLIC`.  Defaults to `PUBLIC`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">force_<wbr>destroy<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}A boolean that indicates all users associated with the server should be deleted so that the Server can be destroyed without error. The default value is `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">host_<wbr>key<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}RSA private key (e.g. as generated by the `ssh-keygen -N &#34;&#34; -f my-new-server-key` command).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">host_<wbr>key_<wbr>fingerprint<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}This value contains the message-digest algorithm (MD5) hash of the server&#39;s host key. This value is equivalent to the output of the `ssh-keygen -l -E md5 -f my-new-server-key` command.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">identity_<wbr>provider_<wbr>type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The mode of authentication enabled for this service. The default value is `SERVICE_MANAGED`, which allows you to store and access SFTP user credentials within the service. `API_GATEWAY` indicates that user authentication requires a call to an API Gateway endpoint URL provided by you to integrate an identity provider of your choice.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">invocation_<wbr>role<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of the IAM role used to authenticate the user account with an `identity_provider_type` of `API_GATEWAY`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">logging_<wbr>role<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of an IAM role that allows the service to write your SFTP users’ activity to your Amazon CloudWatch logs for monitoring and auditing purposes.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">url<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}- URL of the service endpoint used to authenticate users with an `identity_provider_type` of `API_GATEWAY`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}







## Supporting Types

#### ServerEndpointDetails
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#ServerEndpointDetails">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#ServerEndpointDetails">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/transfer?tab=doc#ServerEndpointDetailsArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/transfer?tab=doc#ServerEndpointDetailsOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Transfer.ServerEndpointDetailsArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Transfer.ServerEndpointDetails.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Vpc<wbr>Endpoint<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the VPC endpoint.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Vpc<wbr>Endpoint<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the VPC endpoint.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">vpc<wbr>Endpoint<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the VPC endpoint.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">vpc_<wbr>endpoint_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ID of the VPC endpoint.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}








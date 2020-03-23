
---
title: "Listener"
block_external_search_index: true
---

Provides a Load Balancer Listener resource.

> **Note:** `aws.alb.Listener` is known as `aws.lb.Listener`. The functionality is identical.

## Example Usage

### Forward Action

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const frontEndLoadBalancer = new aws.lb.LoadBalancer("front_end", {});
const frontEndTargetGroup = new aws.lb.TargetGroup("front_end", {});
const frontEndListener = new aws.lb.Listener("front_end", {
    certificateArn: "arn:aws:iam::187416307283:server-certificate/test_cert_rab3wuqwgja25ct3n4jdj2tzu4",
    defaultActions: [{
        targetGroupArn: frontEndTargetGroup.arn,
        type: "forward",
    }],
    loadBalancerArn: frontEndLoadBalancer.arn,
    port: 443,
    protocol: "HTTPS",
    sslPolicy: "ELBSecurityPolicy-2016-08",
});
```

### Redirect Action

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const frontEndLoadBalancer = new aws.lb.LoadBalancer("front_end", {});
const frontEndListener = new aws.lb.Listener("front_end", {
    defaultActions: [{
        redirect: {
            port: "443",
            protocol: "HTTPS",
            statusCode: "HTTP_301",
        },
        type: "redirect",
    }],
    loadBalancerArn: frontEndLoadBalancer.arn,
    port: 80,
    protocol: "HTTP",
});
```

### Fixed-response Action

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const frontEndLoadBalancer = new aws.lb.LoadBalancer("front_end", {});
const frontEndListener = new aws.lb.Listener("front_end", {
    defaultActions: [{
        fixedResponse: {
            contentType: "text/plain",
            messageBody: "Fixed response content",
            statusCode: "200",
        },
        type: "fixed-response",
    }],
    loadBalancerArn: frontEndLoadBalancer.arn,
    port: 80,
    protocol: "HTTP",
});
```

### Authenticate-cognito Action

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const frontEndLoadBalancer = new aws.lb.LoadBalancer("front_end", {});
const frontEndTargetGroup = new aws.lb.TargetGroup("front_end", {});
const pool = new aws.cognito.UserPool("pool", {});
const client = new aws.cognito.UserPoolClient("client", {});
const domain = new aws.cognito.UserPoolDomain("domain", {});
const frontEndListener = new aws.lb.Listener("front_end", {
    defaultActions: [
        {
            authenticateCognito: {
                userPoolArn: pool.arn,
                userPoolClientId: client.id,
                userPoolDomain: domain.domain,
            },
            type: "authenticate-cognito",
        },
        {
            targetGroupArn: frontEndTargetGroup.arn,
            type: "forward",
        },
    ],
    loadBalancerArn: frontEndLoadBalancer.arn,
    port: 80,
    protocol: "HTTP",
});
```

### Authenticate-oidc Action

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const frontEndLoadBalancer = new aws.lb.LoadBalancer("front_end", {});
const frontEndTargetGroup = new aws.lb.TargetGroup("front_end", {});
const frontEndListener = new aws.lb.Listener("front_end", {
    defaultActions: [
        {
            authenticateOidc: {
                authorizationEndpoint: "https://example.com/authorization_endpoint",
                clientId: "client_id",
                clientSecret: "client_secret",
                issuer: "https://example.com",
                tokenEndpoint: "https://example.com/token_endpoint",
                userInfoEndpoint: "https://example.com/user_info_endpoint",
            },
            type: "authenticate-oidc",
        },
        {
            targetGroupArn: frontEndTargetGroup.arn,
            type: "forward",
        },
    ],
    loadBalancerArn: frontEndLoadBalancer.arn,
    port: 80,
    protocol: "HTTP",
});
```

> This content is derived from https://github.com/terraform-providers/terraform-provider-aws/blob/master/website/docs/r/lb_listener.html.markdown.



## Create a Listener Resource

{{< chooser language "javascript,typescript,python,go,csharp" / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/alb/#Listener">Listener</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/alb/#ListenerArgs">ListenerArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">Listener</span><span class="p">(resource_name, opts=None, </span>certificate_arn=None<span class="p">, </span>default_actions=None<span class="p">, </span>load_balancer_arn=None<span class="p">, </span>port=None<span class="p">, </span>protocol=None<span class="p">, </span>ssl_policy=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewListener<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/alb?tab=doc#ListenerArgs">ListenerArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/alb?tab=doc#Listener">Listener</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Alb.Listener.html">Listener</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Alb.ListenerArgs.html">ListenerArgs</a></span> <span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
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
            title="Optional">Certificate<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ARN of the default SSL server certificate. Exactly one certificate is required if the protocol is HTTPS. For adding additional SSL certificates, see the [`aws.lb.ListenerCertificate` resource](https://www.terraform.io/docs/providers/aws/r/lb_listener_certificate.html).
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Default<wbr>Actions<span class="property-indicator"></span>
        <span class="property-type"><a href="#listenerdefaultaction">List&lt;Listener<wbr>Default<wbr>Action<wbr>Args&gt;</a></span>
    </dt>
    <dd>{{% md %}}An Action block. Action blocks are documented below.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Load<wbr>Balancer<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of the load balancer.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Port<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The port. Specify a value from `1` to `65535` or `#{port}`. Defaults to `#{port}`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Protocol<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The protocol. Valid values are `HTTP`, `HTTPS`, or `#{protocol}`. Defaults to `#{protocol}`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ssl<wbr>Policy<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the SSL Policy for the listener. Required if `protocol` is `HTTPS` or `TLS`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Certificate<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The ARN of the default SSL server certificate. Exactly one certificate is required if the protocol is HTTPS. For adding additional SSL certificates, see the [`aws.lb.ListenerCertificate` resource](https://www.terraform.io/docs/providers/aws/r/lb_listener_certificate.html).
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Default<wbr>Actions<span class="property-indicator"></span>
        <span class="property-type"><a href="#listenerdefaultaction">[]Listener<wbr>Default<wbr>Action</a></span>
    </dt>
    <dd>{{% md %}}An Action block. Action blocks are documented below.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Load<wbr>Balancer<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of the load balancer.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Port<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The port. Specify a value from `1` to `65535` or `#{port}`. Defaults to `#{port}`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Protocol<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The protocol. Valid values are `HTTP`, `HTTPS`, or `#{protocol}`. Defaults to `#{protocol}`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ssl<wbr>Policy<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name of the SSL Policy for the listener. Required if `protocol` is `HTTPS` or `TLS`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">certificate<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ARN of the default SSL server certificate. Exactly one certificate is required if the protocol is HTTPS. For adding additional SSL certificates, see the [`aws.lb.ListenerCertificate` resource](https://www.terraform.io/docs/providers/aws/r/lb_listener_certificate.html).
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">default<wbr>Actions<span class="property-indicator"></span>
        <span class="property-type"><a href="#listenerdefaultaction">Listener<wbr>Default<wbr>Action[]</a></span>
    </dt>
    <dd>{{% md %}}An Action block. Action blocks are documented below.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">load<wbr>Balancer<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of the load balancer.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">port<span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}The port. Specify a value from `1` to `65535` or `#{port}`. Defaults to `#{port}`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">protocol<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The protocol. Valid values are `HTTP`, `HTTPS`, or `#{protocol}`. Defaults to `#{protocol}`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ssl<wbr>Policy<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the SSL Policy for the listener. Required if `protocol` is `HTTPS` or `TLS`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">certificate_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ARN of the default SSL server certificate. Exactly one certificate is required if the protocol is HTTPS. For adding additional SSL certificates, see the [`aws.lb.ListenerCertificate` resource](https://www.terraform.io/docs/providers/aws/r/lb_listener_certificate.html).
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">default_<wbr>actions<span class="property-indicator"></span>
        <span class="property-type"><a href="#listenerdefaultaction">List[Listener<wbr>Default<wbr>Action]</a></span>
    </dt>
    <dd>{{% md %}}An Action block. Action blocks are documented below.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">load_<wbr>balancer_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ARN of the load balancer.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">port<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The port. Specify a value from `1` to `65535` or `#{port}`. Defaults to `#{port}`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">protocol<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The protocol. Valid values are `HTTP`, `HTTPS`, or `#{protocol}`. Defaults to `#{protocol}`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ssl_<wbr>policy<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the SSL Policy for the listener. Required if `protocol` is `HTTPS` or `TLS`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}




## Listener Output Properties

The following output properties are available:




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of the listener (matches `id`)
{{% /md %}}</dd>

    <dt class="property-"
            title="">Certificate<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ARN of the default SSL server certificate. Exactly one certificate is required if the protocol is HTTPS. For adding additional SSL certificates, see the [`aws.lb.ListenerCertificate` resource](https://www.terraform.io/docs/providers/aws/r/lb_listener_certificate.html).
{{% /md %}}</dd>

    <dt class="property-"
            title="">Default<wbr>Actions<span class="property-indicator"></span>
        <span class="property-type"><a href="#listenerdefaultaction">List&lt;Listener<wbr>Default<wbr>Action&gt;</a></span>
    </dt>
    <dd>{{% md %}}An Action block. Action blocks are documented below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Load<wbr>Balancer<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of the load balancer.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Port<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The port. Specify a value from `1` to `65535` or `#{port}`. Defaults to `#{port}`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Protocol<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The protocol. Valid values are `HTTP`, `HTTPS`, or `#{protocol}`. Defaults to `#{protocol}`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Ssl<wbr>Policy<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the SSL Policy for the listener. Required if `protocol` is `HTTPS` or `TLS`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of the listener (matches `id`)
{{% /md %}}</dd>

    <dt class="property-"
            title="">Certificate<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The ARN of the default SSL server certificate. Exactly one certificate is required if the protocol is HTTPS. For adding additional SSL certificates, see the [`aws.lb.ListenerCertificate` resource](https://www.terraform.io/docs/providers/aws/r/lb_listener_certificate.html).
{{% /md %}}</dd>

    <dt class="property-"
            title="">Default<wbr>Actions<span class="property-indicator"></span>
        <span class="property-type"><a href="#listenerdefaultaction">[]Listener<wbr>Default<wbr>Action</a></span>
    </dt>
    <dd>{{% md %}}An Action block. Action blocks are documented below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Load<wbr>Balancer<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of the load balancer.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Port<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The port. Specify a value from `1` to `65535` or `#{port}`. Defaults to `#{port}`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Protocol<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The protocol. Valid values are `HTTP`, `HTTPS`, or `#{protocol}`. Defaults to `#{protocol}`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Ssl<wbr>Policy<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the SSL Policy for the listener. Required if `protocol` is `HTTPS` or `TLS`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of the listener (matches `id`)
{{% /md %}}</dd>

    <dt class="property-"
            title="">certificate<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ARN of the default SSL server certificate. Exactly one certificate is required if the protocol is HTTPS. For adding additional SSL certificates, see the [`aws.lb.ListenerCertificate` resource](https://www.terraform.io/docs/providers/aws/r/lb_listener_certificate.html).
{{% /md %}}</dd>

    <dt class="property-"
            title="">default<wbr>Actions<span class="property-indicator"></span>
        <span class="property-type"><a href="#listenerdefaultaction">Listener<wbr>Default<wbr>Action[]</a></span>
    </dt>
    <dd>{{% md %}}An Action block. Action blocks are documented below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">load<wbr>Balancer<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of the load balancer.
{{% /md %}}</dd>

    <dt class="property-"
            title="">port<span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}The port. Specify a value from `1` to `65535` or `#{port}`. Defaults to `#{port}`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">protocol<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The protocol. Valid values are `HTTP`, `HTTPS`, or `#{protocol}`. Defaults to `#{protocol}`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">ssl<wbr>Policy<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the SSL Policy for the listener. Required if `protocol` is `HTTPS` or `TLS`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ARN of the listener (matches `id`)
{{% /md %}}</dd>

    <dt class="property-"
            title="">certificate_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ARN of the default SSL server certificate. Exactly one certificate is required if the protocol is HTTPS. For adding additional SSL certificates, see the [`aws.lb.ListenerCertificate` resource](https://www.terraform.io/docs/providers/aws/r/lb_listener_certificate.html).
{{% /md %}}</dd>

    <dt class="property-"
            title="">default_<wbr>actions<span class="property-indicator"></span>
        <span class="property-type"><a href="#listenerdefaultaction">List[Listener<wbr>Default<wbr>Action]</a></span>
    </dt>
    <dd>{{% md %}}An Action block. Action blocks are documented below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">load_<wbr>balancer_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ARN of the load balancer.
{{% /md %}}</dd>

    <dt class="property-"
            title="">port<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The port. Specify a value from `1` to `65535` or `#{port}`. Defaults to `#{port}`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">protocol<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The protocol. Valid values are `HTTP`, `HTTPS`, or `#{protocol}`. Defaults to `#{protocol}`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">ssl_<wbr>policy<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the SSL Policy for the listener. Required if `protocol` is `HTTPS` or `TLS`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





## Look up an Existing Listener Resource

{{< chooser language "javascript,typescript,python,go,csharp  " / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">pulumi.Input&lt;pulumi.ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/alb/#ListenerState">ListenerState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/alb/#Listener">Listener</a></span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>arn=None<span class="p">, </span>certificate_arn=None<span class="p">, </span>default_actions=None<span class="p">, </span>load_balancer_arn=None<span class="p">, </span>port=None<span class="p">, </span>protocol=None<span class="p">, </span>ssl_policy=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetListener<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">pulumi.IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/alb?tab=doc#ListenerState">ListenerState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/alb?tab=doc#Listener">Listener</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Alb.Listener.html">Listener</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Pulumi.Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Alb.ListenerState.html">ListenerState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
{{% /choosable %}}

Get an existing Listener resource's state with the given name, ID, and optional extra properties used to qualify the lookup.

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
    <dd>{{% md %}}The ARN of the listener (matches `id`)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Certificate<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ARN of the default SSL server certificate. Exactly one certificate is required if the protocol is HTTPS. For adding additional SSL certificates, see the [`aws.lb.ListenerCertificate` resource](https://www.terraform.io/docs/providers/aws/r/lb_listener_certificate.html).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Default<wbr>Actions<span class="property-indicator"></span>
        <span class="property-type"><a href="#listenerdefaultaction">List&lt;Listener<wbr>Default<wbr>Action<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}An Action block. Action blocks are documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Load<wbr>Balancer<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ARN of the load balancer.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Port<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The port. Specify a value from `1` to `65535` or `#{port}`. Defaults to `#{port}`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Protocol<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The protocol. Valid values are `HTTP`, `HTTPS`, or `#{protocol}`. Defaults to `#{protocol}`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ssl<wbr>Policy<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the SSL Policy for the listener. Required if `protocol` is `HTTPS` or `TLS`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The ARN of the listener (matches `id`)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Certificate<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The ARN of the default SSL server certificate. Exactly one certificate is required if the protocol is HTTPS. For adding additional SSL certificates, see the [`aws.lb.ListenerCertificate` resource](https://www.terraform.io/docs/providers/aws/r/lb_listener_certificate.html).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Default<wbr>Actions<span class="property-indicator"></span>
        <span class="property-type"><a href="#listenerdefaultaction">[]Listener<wbr>Default<wbr>Action</a></span>
    </dt>
    <dd>{{% md %}}An Action block. Action blocks are documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Load<wbr>Balancer<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The ARN of the load balancer.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Port<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The port. Specify a value from `1` to `65535` or `#{port}`. Defaults to `#{port}`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Protocol<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The protocol. Valid values are `HTTP`, `HTTPS`, or `#{protocol}`. Defaults to `#{protocol}`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ssl<wbr>Policy<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name of the SSL Policy for the listener. Required if `protocol` is `HTTPS` or `TLS`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ARN of the listener (matches `id`)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">certificate<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ARN of the default SSL server certificate. Exactly one certificate is required if the protocol is HTTPS. For adding additional SSL certificates, see the [`aws.lb.ListenerCertificate` resource](https://www.terraform.io/docs/providers/aws/r/lb_listener_certificate.html).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">default<wbr>Actions<span class="property-indicator"></span>
        <span class="property-type"><a href="#listenerdefaultaction">Listener<wbr>Default<wbr>Action[]?</a></span>
    </dt>
    <dd>{{% md %}}An Action block. Action blocks are documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">load<wbr>Balancer<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ARN of the load balancer.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">port<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The port. Specify a value from `1` to `65535` or `#{port}`. Defaults to `#{port}`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">protocol<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The protocol. Valid values are `HTTP`, `HTTPS`, or `#{protocol}`. Defaults to `#{protocol}`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ssl<wbr>Policy<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the SSL Policy for the listener. Required if `protocol` is `HTTPS` or `TLS`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ARN of the listener (matches `id`)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">certificate_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ARN of the default SSL server certificate. Exactly one certificate is required if the protocol is HTTPS. For adding additional SSL certificates, see the [`aws.lb.ListenerCertificate` resource](https://www.terraform.io/docs/providers/aws/r/lb_listener_certificate.html).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">default_<wbr>actions<span class="property-indicator"></span>
        <span class="property-type"><a href="#listenerdefaultaction">List[Listener<wbr>Default<wbr>Action]</a></span>
    </dt>
    <dd>{{% md %}}An Action block. Action blocks are documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">load_<wbr>balancer_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ARN of the load balancer.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">port<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The port. Specify a value from `1` to `65535` or `#{port}`. Defaults to `#{port}`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">protocol<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The protocol. Valid values are `HTTP`, `HTTPS`, or `#{protocol}`. Defaults to `#{protocol}`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ssl_<wbr>policy<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the SSL Policy for the listener. Required if `protocol` is `HTTPS` or `TLS`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}







## Supporting Types

#### ListenerDefaultAction
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#ListenerDefaultAction">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#ListenerDefaultAction">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/alb?tab=doc#ListenerDefaultActionArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/alb?tab=doc#ListenerDefaultActionOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Alb.ListenerDefaultActionArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Alb.ListenerDefaultAction.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Authenticate<wbr>Cognito<span class="property-indicator"></span>
        <span class="property-type"><a href="#listenerdefaultactionauthenticatecognito">Listener<wbr>Default<wbr>Action<wbr>Authenticate<wbr>Cognito<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Authenticate<wbr>Oidc<span class="property-indicator"></span>
        <span class="property-type"><a href="#listenerdefaultactionauthenticateoidc">Listener<wbr>Default<wbr>Action<wbr>Authenticate<wbr>Oidc<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Fixed<wbr>Response<span class="property-indicator"></span>
        <span class="property-type"><a href="#listenerdefaultactionfixedresponse">Listener<wbr>Default<wbr>Action<wbr>Fixed<wbr>Response<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}Information for creating an action that returns a custom HTTP response. Required if `type` is `fixed-response`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Order<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Redirect<span class="property-indicator"></span>
        <span class="property-type"><a href="#listenerdefaultactionredirect">Listener<wbr>Default<wbr>Action<wbr>Redirect<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}Information for creating a redirect action. Required if `type` is `redirect`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Target<wbr>Group<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ARN of the Target Group to which to route traffic. Required if `type` is `forward`.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type of routing action. Valid values are `forward`, `redirect`, `fixed-response`, `authenticate-cognito` and `authenticate-oidc`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Authenticate<wbr>Cognito<span class="property-indicator"></span>
        <span class="property-type"><a href="#listenerdefaultactionauthenticatecognito">*Listener<wbr>Default<wbr>Action<wbr>Authenticate<wbr>Cognito</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Authenticate<wbr>Oidc<span class="property-indicator"></span>
        <span class="property-type"><a href="#listenerdefaultactionauthenticateoidc">*Listener<wbr>Default<wbr>Action<wbr>Authenticate<wbr>Oidc</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Fixed<wbr>Response<span class="property-indicator"></span>
        <span class="property-type"><a href="#listenerdefaultactionfixedresponse">*Listener<wbr>Default<wbr>Action<wbr>Fixed<wbr>Response</a></span>
    </dt>
    <dd>{{% md %}}Information for creating an action that returns a custom HTTP response. Required if `type` is `fixed-response`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Order<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Redirect<span class="property-indicator"></span>
        <span class="property-type"><a href="#listenerdefaultactionredirect">*Listener<wbr>Default<wbr>Action<wbr>Redirect</a></span>
    </dt>
    <dd>{{% md %}}Information for creating a redirect action. Required if `type` is `redirect`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Target<wbr>Group<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The ARN of the Target Group to which to route traffic. Required if `type` is `forward`.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type of routing action. Valid values are `forward`, `redirect`, `fixed-response`, `authenticate-cognito` and `authenticate-oidc`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">authenticate<wbr>Cognito<span class="property-indicator"></span>
        <span class="property-type"><a href="#listenerdefaultactionauthenticatecognito">Listener<wbr>Default<wbr>Action<wbr>Authenticate<wbr>Cognito?</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">authenticate<wbr>Oidc<span class="property-indicator"></span>
        <span class="property-type"><a href="#listenerdefaultactionauthenticateoidc">Listener<wbr>Default<wbr>Action<wbr>Authenticate<wbr>Oidc?</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">fixed<wbr>Response<span class="property-indicator"></span>
        <span class="property-type"><a href="#listenerdefaultactionfixedresponse">Listener<wbr>Default<wbr>Action<wbr>Fixed<wbr>Response?</a></span>
    </dt>
    <dd>{{% md %}}Information for creating an action that returns a custom HTTP response. Required if `type` is `fixed-response`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">order<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">redirect<span class="property-indicator"></span>
        <span class="property-type"><a href="#listenerdefaultactionredirect">Listener<wbr>Default<wbr>Action<wbr>Redirect?</a></span>
    </dt>
    <dd>{{% md %}}Information for creating a redirect action. Required if `type` is `redirect`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">target<wbr>Group<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ARN of the Target Group to which to route traffic. Required if `type` is `forward`.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type of routing action. Valid values are `forward`, `redirect`, `fixed-response`, `authenticate-cognito` and `authenticate-oidc`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">authenticate<wbr>Cognito<span class="property-indicator"></span>
        <span class="property-type"><a href="#listenerdefaultactionauthenticatecognito">Dict[Listener<wbr>Default<wbr>Action<wbr>Authenticate<wbr>Cognito]</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">authenticate<wbr>Oidc<span class="property-indicator"></span>
        <span class="property-type"><a href="#listenerdefaultactionauthenticateoidc">Dict[Listener<wbr>Default<wbr>Action<wbr>Authenticate<wbr>Oidc]</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">fixed<wbr>Response<span class="property-indicator"></span>
        <span class="property-type"><a href="#listenerdefaultactionfixedresponse">Dict[Listener<wbr>Default<wbr>Action<wbr>Fixed<wbr>Response]</a></span>
    </dt>
    <dd>{{% md %}}Information for creating an action that returns a custom HTTP response. Required if `type` is `fixed-response`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">order<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">redirect<span class="property-indicator"></span>
        <span class="property-type"><a href="#listenerdefaultactionredirect">Dict[Listener<wbr>Default<wbr>Action<wbr>Redirect]</a></span>
    </dt>
    <dd>{{% md %}}Information for creating a redirect action. Required if `type` is `redirect`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">target_<wbr>group_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ARN of the Target Group to which to route traffic. Required if `type` is `forward`.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The type of routing action. Valid values are `forward`, `redirect`, `fixed-response`, `authenticate-cognito` and `authenticate-oidc`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### ListenerDefaultActionAuthenticateCognito
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#ListenerDefaultActionAuthenticateCognito">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#ListenerDefaultActionAuthenticateCognito">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/alb?tab=doc#ListenerDefaultActionAuthenticateCognitoArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/alb?tab=doc#ListenerDefaultActionAuthenticateCognitoOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Alb.ListenerDefaultActionAuthenticateCognitoArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Alb.ListenerDefaultActionAuthenticateCognito.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Authentication<wbr>Request<wbr>Extra<wbr>Params<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}The query parameters to include in the redirect request to the authorization endpoint. Max: 10.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">On<wbr>Unauthenticated<wbr>Request<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The behavior if the user is not authenticated. Valid values: `deny`, `allow` and `authenticate`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Scope<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The set of user claims to be requested from the IdP.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Session<wbr>Cookie<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the cookie used to maintain session information.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Session<wbr>Timeout<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The maximum duration of the authentication session, in seconds.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">User<wbr>Pool<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of the Cognito user pool.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">User<wbr>Pool<wbr>Client<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the Cognito user pool client.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">User<wbr>Pool<wbr>Domain<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The domain prefix or fully-qualified domain name of the Cognito user pool.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Authentication<wbr>Request<wbr>Extra<wbr>Params<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}The query parameters to include in the redirect request to the authorization endpoint. Max: 10.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">On<wbr>Unauthenticated<wbr>Request<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The behavior if the user is not authenticated. Valid values: `deny`, `allow` and `authenticate`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Scope<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The set of user claims to be requested from the IdP.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Session<wbr>Cookie<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name of the cookie used to maintain session information.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Session<wbr>Timeout<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The maximum duration of the authentication session, in seconds.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">User<wbr>Pool<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of the Cognito user pool.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">User<wbr>Pool<wbr>Client<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the Cognito user pool client.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">User<wbr>Pool<wbr>Domain<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The domain prefix or fully-qualified domain name of the Cognito user pool.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">authentication<wbr>Request<wbr>Extra<wbr>Params<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}The query parameters to include in the redirect request to the authorization endpoint. Max: 10.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">on<wbr>Unauthenticated<wbr>Request<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The behavior if the user is not authenticated. Valid values: `deny`, `allow` and `authenticate`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">scope<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The set of user claims to be requested from the IdP.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">session<wbr>Cookie<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the cookie used to maintain session information.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">session<wbr>Timeout<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The maximum duration of the authentication session, in seconds.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">user<wbr>Pool<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of the Cognito user pool.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">user<wbr>Pool<wbr>Client<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the Cognito user pool client.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">user<wbr>Pool<wbr>Domain<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The domain prefix or fully-qualified domain name of the Cognito user pool.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">authentication<wbr>Request<wbr>Extra<wbr>Params<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}The query parameters to include in the redirect request to the authorization endpoint. Max: 10.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">on<wbr>Unauthenticated<wbr>Request<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The behavior if the user is not authenticated. Valid values: `deny`, `allow` and `authenticate`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">scope<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The set of user claims to be requested from the IdP.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">session<wbr>Cookie<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the cookie used to maintain session information.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">session<wbr>Timeout<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The maximum duration of the authentication session, in seconds.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">user<wbr>Pool<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ARN of the Cognito user pool.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">user<wbr>Pool<wbr>Client<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ID of the Cognito user pool client.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">user<wbr>Pool<wbr>Domain<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The domain prefix or fully-qualified domain name of the Cognito user pool.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### ListenerDefaultActionAuthenticateOidc
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#ListenerDefaultActionAuthenticateOidc">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#ListenerDefaultActionAuthenticateOidc">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/alb?tab=doc#ListenerDefaultActionAuthenticateOidcArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/alb?tab=doc#ListenerDefaultActionAuthenticateOidcOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Alb.ListenerDefaultActionAuthenticateOidcArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Alb.ListenerDefaultActionAuthenticateOidc.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Authentication<wbr>Request<wbr>Extra<wbr>Params<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}The query parameters to include in the redirect request to the authorization endpoint. Max: 10.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Authorization<wbr>Endpoint<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The authorization endpoint of the IdP.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Client<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The OAuth 2.0 client identifier.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Client<wbr>Secret<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The OAuth 2.0 client secret.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Issuer<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The OIDC issuer identifier of the IdP.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">On<wbr>Unauthenticated<wbr>Request<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The behavior if the user is not authenticated. Valid values: `deny`, `allow` and `authenticate`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Scope<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The set of user claims to be requested from the IdP.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Session<wbr>Cookie<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the cookie used to maintain session information.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Session<wbr>Timeout<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The maximum duration of the authentication session, in seconds.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Token<wbr>Endpoint<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The token endpoint of the IdP.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">User<wbr>Info<wbr>Endpoint<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The user info endpoint of the IdP.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Authentication<wbr>Request<wbr>Extra<wbr>Params<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}The query parameters to include in the redirect request to the authorization endpoint. Max: 10.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Authorization<wbr>Endpoint<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The authorization endpoint of the IdP.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Client<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The OAuth 2.0 client identifier.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Client<wbr>Secret<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The OAuth 2.0 client secret.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Issuer<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The OIDC issuer identifier of the IdP.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">On<wbr>Unauthenticated<wbr>Request<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The behavior if the user is not authenticated. Valid values: `deny`, `allow` and `authenticate`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Scope<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The set of user claims to be requested from the IdP.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Session<wbr>Cookie<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name of the cookie used to maintain session information.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Session<wbr>Timeout<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The maximum duration of the authentication session, in seconds.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Token<wbr>Endpoint<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The token endpoint of the IdP.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">User<wbr>Info<wbr>Endpoint<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The user info endpoint of the IdP.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">authentication<wbr>Request<wbr>Extra<wbr>Params<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}The query parameters to include in the redirect request to the authorization endpoint. Max: 10.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">authorization<wbr>Endpoint<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The authorization endpoint of the IdP.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">client<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The OAuth 2.0 client identifier.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">client<wbr>Secret<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The OAuth 2.0 client secret.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">issuer<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The OIDC issuer identifier of the IdP.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">on<wbr>Unauthenticated<wbr>Request<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The behavior if the user is not authenticated. Valid values: `deny`, `allow` and `authenticate`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">scope<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The set of user claims to be requested from the IdP.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">session<wbr>Cookie<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the cookie used to maintain session information.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">session<wbr>Timeout<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The maximum duration of the authentication session, in seconds.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">token<wbr>Endpoint<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The token endpoint of the IdP.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">user<wbr>Info<wbr>Endpoint<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The user info endpoint of the IdP.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">authentication<wbr>Request<wbr>Extra<wbr>Params<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}The query parameters to include in the redirect request to the authorization endpoint. Max: 10.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">authorization<wbr>Endpoint<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The authorization endpoint of the IdP.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">client_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The OAuth 2.0 client identifier.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">client_<wbr>secret<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The OAuth 2.0 client secret.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">issuer<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The OIDC issuer identifier of the IdP.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">on<wbr>Unauthenticated<wbr>Request<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The behavior if the user is not authenticated. Valid values: `deny`, `allow` and `authenticate`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">scope<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The set of user claims to be requested from the IdP.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">session<wbr>Cookie<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the cookie used to maintain session information.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">session<wbr>Timeout<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The maximum duration of the authentication session, in seconds.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">token<wbr>Endpoint<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The token endpoint of the IdP.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">user<wbr>Info<wbr>Endpoint<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The user info endpoint of the IdP.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### ListenerDefaultActionFixedResponse
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#ListenerDefaultActionFixedResponse">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#ListenerDefaultActionFixedResponse">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/alb?tab=doc#ListenerDefaultActionFixedResponseArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/alb?tab=doc#ListenerDefaultActionFixedResponseOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Alb.ListenerDefaultActionFixedResponseArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Alb.ListenerDefaultActionFixedResponse.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Content<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The content type. Valid values are `text/plain`, `text/css`, `text/html`, `application/javascript` and `application/json`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Message<wbr>Body<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The message body.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Status<wbr>Code<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The HTTP response code. Valid values are `2XX`, `4XX`, or `5XX`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Content<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The content type. Valid values are `text/plain`, `text/css`, `text/html`, `application/javascript` and `application/json`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Message<wbr>Body<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The message body.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Status<wbr>Code<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The HTTP response code. Valid values are `2XX`, `4XX`, or `5XX`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">content<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The content type. Valid values are `text/plain`, `text/css`, `text/html`, `application/javascript` and `application/json`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">message<wbr>Body<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The message body.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">status<wbr>Code<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The HTTP response code. Valid values are `2XX`, `4XX`, or `5XX`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">content_<wbr>type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The content type. Valid values are `text/plain`, `text/css`, `text/html`, `application/javascript` and `application/json`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">message<wbr>Body<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The message body.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">status_<wbr>code<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The HTTP response code. Valid values are `2XX`, `4XX`, or `5XX`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### ListenerDefaultActionRedirect
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#ListenerDefaultActionRedirect">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#ListenerDefaultActionRedirect">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/alb?tab=doc#ListenerDefaultActionRedirectArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/alb?tab=doc#ListenerDefaultActionRedirectOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Alb.ListenerDefaultActionRedirectArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Alb.ListenerDefaultActionRedirect.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Host<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The hostname. This component is not percent-encoded. The hostname can contain `#{host}`. Defaults to `#{host}`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Path<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The absolute path, starting with the leading &#34;/&#34;. This component is not percent-encoded. The path can contain #{host}, #{path}, and #{port}. Defaults to `/#{path}`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Port<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The port. Specify a value from `1` to `65535` or `#{port}`. Defaults to `#{port}`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Protocol<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The protocol. Valid values are `HTTP`, `HTTPS`, or `#{protocol}`. Defaults to `#{protocol}`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Query<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The query parameters, URL-encoded when necessary, but not percent-encoded. Do not include the leading &#34;?&#34;. Defaults to `#{query}`.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Status<wbr>Code<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The HTTP response code. Valid values are `2XX`, `4XX`, or `5XX`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Host<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The hostname. This component is not percent-encoded. The hostname can contain `#{host}`. Defaults to `#{host}`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Path<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The absolute path, starting with the leading &#34;/&#34;. This component is not percent-encoded. The path can contain #{host}, #{path}, and #{port}. Defaults to `/#{path}`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Port<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The port. Specify a value from `1` to `65535` or `#{port}`. Defaults to `#{port}`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Protocol<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The protocol. Valid values are `HTTP`, `HTTPS`, or `#{protocol}`. Defaults to `#{protocol}`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Query<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The query parameters, URL-encoded when necessary, but not percent-encoded. Do not include the leading &#34;?&#34;. Defaults to `#{query}`.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Status<wbr>Code<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The HTTP response code. Valid values are `2XX`, `4XX`, or `5XX`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">host<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The hostname. This component is not percent-encoded. The hostname can contain `#{host}`. Defaults to `#{host}`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">path<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The absolute path, starting with the leading &#34;/&#34;. This component is not percent-encoded. The path can contain #{host}, #{path}, and #{port}. Defaults to `/#{path}`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">port<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The port. Specify a value from `1` to `65535` or `#{port}`. Defaults to `#{port}`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">protocol<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The protocol. Valid values are `HTTP`, `HTTPS`, or `#{protocol}`. Defaults to `#{protocol}`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">query<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The query parameters, URL-encoded when necessary, but not percent-encoded. Do not include the leading &#34;?&#34;. Defaults to `#{query}`.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">status<wbr>Code<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The HTTP response code. Valid values are `2XX`, `4XX`, or `5XX`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">host<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The hostname. This component is not percent-encoded. The hostname can contain `#{host}`. Defaults to `#{host}`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">path<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The absolute path, starting with the leading &#34;/&#34;. This component is not percent-encoded. The path can contain #{host}, #{path}, and #{port}. Defaults to `/#{path}`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">port<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The port. Specify a value from `1` to `65535` or `#{port}`. Defaults to `#{port}`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">protocol<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The protocol. Valid values are `HTTP`, `HTTPS`, or `#{protocol}`. Defaults to `#{protocol}`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">query<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The query parameters, URL-encoded when necessary, but not percent-encoded. Do not include the leading &#34;?&#34;. Defaults to `#{query}`.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">status_<wbr>code<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The HTTP response code. Valid values are `2XX`, `4XX`, or `5XX`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}








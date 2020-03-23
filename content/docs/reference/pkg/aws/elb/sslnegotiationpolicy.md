
---
title: "SslNegotiationPolicy"
block_external_search_index: true
---

Provides a load balancer SSL negotiation policy, which allows an ELB to control the ciphers and protocols that are supported during SSL negotiations between a client and a load balancer.

## Example Usage

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const lb = new aws.elb.LoadBalancer("lb", {
    availabilityZones: ["us-east-1a"],
    listeners: [{
        instancePort: 8000,
        instanceProtocol: "https",
        lbPort: 443,
        lbProtocol: "https",
        sslCertificateId: "arn:aws:iam::123456789012:server-certificate/certName",
    }],
});
const foo = new aws.elb.SslNegotiationPolicy("foo", {
    attributes: [
        {
            name: "Protocol-TLSv1",
            value: "false",
        },
        {
            name: "Protocol-TLSv1.1",
            value: "false",
        },
        {
            name: "Protocol-TLSv1.2",
            value: "true",
        },
        {
            name: "Server-Defined-Cipher-Order",
            value: "true",
        },
        {
            name: "ECDHE-RSA-AES128-GCM-SHA256",
            value: "true",
        },
        {
            name: "AES128-GCM-SHA256",
            value: "true",
        },
        {
            name: "EDH-RSA-DES-CBC3-SHA",
            value: "false",
        },
    ],
    lbPort: 443,
    loadBalancer: lb.id,
});
```

> This content is derived from https://github.com/terraform-providers/terraform-provider-aws/blob/master/website/docs/r/lb_ssl_negotiation_policy.html.markdown.



## Create a SslNegotiationPolicy Resource

{{< chooser language "javascript,typescript,python,go,csharp" / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/elb/#SslNegotiationPolicy">SslNegotiationPolicy</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/elb/#SslNegotiationPolicyArgs">SslNegotiationPolicyArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">SslNegotiationPolicy</span><span class="p">(resource_name, opts=None, </span>attributes=None<span class="p">, </span>lb_port=None<span class="p">, </span>load_balancer=None<span class="p">, </span>name=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewSslNegotiationPolicy<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/elb?tab=doc#SslNegotiationPolicyArgs">SslNegotiationPolicyArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/elb?tab=doc#SslNegotiationPolicy">SslNegotiationPolicy</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Elb.SslNegotiationPolicy.html">SslNegotiationPolicy</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Elb.SslNegotiationPolicyArgs.html">SslNegotiationPolicyArgs</a></span> <span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
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
            title="Optional">Attributes<span class="property-indicator"></span>
        <span class="property-type"><a href="#sslnegotiationpolicyattribute">List&lt;Ssl<wbr>Negotiation<wbr>Policy<wbr>Attribute<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}An SSL Negotiation policy attribute. Each has two properties:
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Lb<wbr>Port<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The load balancer port to which the policy
should be applied. This must be an active listener on the load
balancer.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Load<wbr>Balancer<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The load balancer to which the policy
should be attached.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the attribute
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Attributes<span class="property-indicator"></span>
        <span class="property-type"><a href="#sslnegotiationpolicyattribute">[]Ssl<wbr>Negotiation<wbr>Policy<wbr>Attribute</a></span>
    </dt>
    <dd>{{% md %}}An SSL Negotiation policy attribute. Each has two properties:
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Lb<wbr>Port<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The load balancer port to which the policy
should be applied. This must be an active listener on the load
balancer.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Load<wbr>Balancer<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The load balancer to which the policy
should be attached.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name of the attribute
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">attributes<span class="property-indicator"></span>
        <span class="property-type"><a href="#sslnegotiationpolicyattribute">Ssl<wbr>Negotiation<wbr>Policy<wbr>Attribute[]?</a></span>
    </dt>
    <dd>{{% md %}}An SSL Negotiation policy attribute. Each has two properties:
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">lb<wbr>Port<span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}The load balancer port to which the policy
should be applied. This must be an active listener on the load
balancer.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">load<wbr>Balancer<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The load balancer to which the policy
should be attached.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the attribute
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">attributes<span class="property-indicator"></span>
        <span class="property-type"><a href="#sslnegotiationpolicyattribute">List[Ssl<wbr>Negotiation<wbr>Policy<wbr>Attribute]</a></span>
    </dt>
    <dd>{{% md %}}An SSL Negotiation policy attribute. Each has two properties:
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">lb_<wbr>port<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The load balancer port to which the policy
should be applied. This must be an active listener on the load
balancer.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">load_<wbr>balancer<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The load balancer to which the policy
should be attached.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the attribute
{{% /md %}}</dd>

</dl>
{{% /choosable %}}




## SslNegotiationPolicy Output Properties

The following output properties are available:




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Attributes<span class="property-indicator"></span>
        <span class="property-type"><a href="#sslnegotiationpolicyattribute">List&lt;Ssl<wbr>Negotiation<wbr>Policy<wbr>Attribute&gt;?</a></span>
    </dt>
    <dd>{{% md %}}An SSL Negotiation policy attribute. Each has two properties:
{{% /md %}}</dd>

    <dt class="property-"
            title="">Lb<wbr>Port<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The load balancer port to which the policy
should be applied. This must be an active listener on the load
balancer.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Load<wbr>Balancer<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The load balancer to which the policy
should be attached.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the attribute
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Attributes<span class="property-indicator"></span>
        <span class="property-type"><a href="#sslnegotiationpolicyattribute">[]Ssl<wbr>Negotiation<wbr>Policy<wbr>Attribute</a></span>
    </dt>
    <dd>{{% md %}}An SSL Negotiation policy attribute. Each has two properties:
{{% /md %}}</dd>

    <dt class="property-"
            title="">Lb<wbr>Port<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The load balancer port to which the policy
should be applied. This must be an active listener on the load
balancer.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Load<wbr>Balancer<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The load balancer to which the policy
should be attached.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the attribute
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">attributes<span class="property-indicator"></span>
        <span class="property-type"><a href="#sslnegotiationpolicyattribute">Ssl<wbr>Negotiation<wbr>Policy<wbr>Attribute[]?</a></span>
    </dt>
    <dd>{{% md %}}An SSL Negotiation policy attribute. Each has two properties:
{{% /md %}}</dd>

    <dt class="property-"
            title="">lb<wbr>Port<span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}The load balancer port to which the policy
should be applied. This must be an active listener on the load
balancer.
{{% /md %}}</dd>

    <dt class="property-"
            title="">load<wbr>Balancer<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The load balancer to which the policy
should be attached.
{{% /md %}}</dd>

    <dt class="property-"
            title="">name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the attribute
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">attributes<span class="property-indicator"></span>
        <span class="property-type"><a href="#sslnegotiationpolicyattribute">List[Ssl<wbr>Negotiation<wbr>Policy<wbr>Attribute]</a></span>
    </dt>
    <dd>{{% md %}}An SSL Negotiation policy attribute. Each has two properties:
{{% /md %}}</dd>

    <dt class="property-"
            title="">lb_<wbr>port<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The load balancer port to which the policy
should be applied. This must be an active listener on the load
balancer.
{{% /md %}}</dd>

    <dt class="property-"
            title="">load_<wbr>balancer<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The load balancer to which the policy
should be attached.
{{% /md %}}</dd>

    <dt class="property-"
            title="">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the attribute
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





## Look up an Existing SslNegotiationPolicy Resource

{{< chooser language "javascript,typescript,python,go,csharp  " / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">pulumi.Input&lt;pulumi.ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/elb/#SslNegotiationPolicyState">SslNegotiationPolicyState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/elb/#SslNegotiationPolicy">SslNegotiationPolicy</a></span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>attributes=None<span class="p">, </span>lb_port=None<span class="p">, </span>load_balancer=None<span class="p">, </span>name=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetSslNegotiationPolicy<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">pulumi.IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/elb?tab=doc#SslNegotiationPolicyState">SslNegotiationPolicyState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/elb?tab=doc#SslNegotiationPolicy">SslNegotiationPolicy</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Elb.SslNegotiationPolicy.html">SslNegotiationPolicy</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Pulumi.Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Elb.SslNegotiationPolicyState.html">SslNegotiationPolicyState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
{{% /choosable %}}

Get an existing SslNegotiationPolicy resource's state with the given name, ID, and optional extra properties used to qualify the lookup.

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
            title="Optional">Attributes<span class="property-indicator"></span>
        <span class="property-type"><a href="#sslnegotiationpolicyattribute">List&lt;Ssl<wbr>Negotiation<wbr>Policy<wbr>Attribute<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}An SSL Negotiation policy attribute. Each has two properties:
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Lb<wbr>Port<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The load balancer port to which the policy
should be applied. This must be an active listener on the load
balancer.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Load<wbr>Balancer<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The load balancer to which the policy
should be attached.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the attribute
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Attributes<span class="property-indicator"></span>
        <span class="property-type"><a href="#sslnegotiationpolicyattribute">[]Ssl<wbr>Negotiation<wbr>Policy<wbr>Attribute</a></span>
    </dt>
    <dd>{{% md %}}An SSL Negotiation policy attribute. Each has two properties:
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Lb<wbr>Port<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The load balancer port to which the policy
should be applied. This must be an active listener on the load
balancer.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Load<wbr>Balancer<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The load balancer to which the policy
should be attached.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name of the attribute
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">attributes<span class="property-indicator"></span>
        <span class="property-type"><a href="#sslnegotiationpolicyattribute">Ssl<wbr>Negotiation<wbr>Policy<wbr>Attribute[]?</a></span>
    </dt>
    <dd>{{% md %}}An SSL Negotiation policy attribute. Each has two properties:
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">lb<wbr>Port<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The load balancer port to which the policy
should be applied. This must be an active listener on the load
balancer.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">load<wbr>Balancer<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The load balancer to which the policy
should be attached.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the attribute
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">attributes<span class="property-indicator"></span>
        <span class="property-type"><a href="#sslnegotiationpolicyattribute">List[Ssl<wbr>Negotiation<wbr>Policy<wbr>Attribute]</a></span>
    </dt>
    <dd>{{% md %}}An SSL Negotiation policy attribute. Each has two properties:
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">lb_<wbr>port<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The load balancer port to which the policy
should be applied. This must be an active listener on the load
balancer.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">load_<wbr>balancer<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The load balancer to which the policy
should be attached.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the attribute
{{% /md %}}</dd>

</dl>
{{% /choosable %}}







## Supporting Types

#### SslNegotiationPolicyAttribute
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#SslNegotiationPolicyAttribute">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#SslNegotiationPolicyAttribute">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/elb?tab=doc#SslNegotiationPolicyAttributeArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/elb?tab=doc#SslNegotiationPolicyAttributeOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Elb.SslNegotiationPolicyAttributeArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Elb.SslNegotiationPolicyAttribute.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the attribute
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Value<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The value of the attribute
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the attribute
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Value<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The value of the attribute
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the attribute
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">value<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The value of the attribute
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the attribute
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">value<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The value of the attribute
{{% /md %}}</dd>

</dl>
{{% /choosable %}}








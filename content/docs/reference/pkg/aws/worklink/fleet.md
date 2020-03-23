
---
title: "Fleet"
block_external_search_index: true
---

## Example Usage

Basic usage:

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const example = new aws.worklink.Fleet("example", {});
```

Network Configuration Usage:

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const example = new aws.worklink.Fleet("example", {
    network: {
        securityGroupIds: [aws_security_group_test.id],
        subnetIds: [aws_subnet_test.map(v => v.id)],
        vpcId: aws_vpc_test.id,
    },
});
```

Identity Provider Configuration Usage:

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";
import * as fs from "fs";

const test = new aws.worklink.Fleet("test", {
    identityProvider: {
        samlMetadata: fs.readFileSync("saml-metadata.xml", "utf-8"),
        type: "SAML",
    },
});
```

> This content is derived from https://github.com/terraform-providers/terraform-provider-aws/blob/master/website/docs/r/worklink_fleet.html.markdown.



## Create a Fleet Resource

{{< chooser language "javascript,typescript,python,go,csharp" / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/worklink/#Fleet">Fleet</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/worklink/#FleetArgs">FleetArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">Fleet</span><span class="p">(resource_name, opts=None, </span>audit_stream_arn=None<span class="p">, </span>device_ca_certificate=None<span class="p">, </span>display_name=None<span class="p">, </span>identity_provider=None<span class="p">, </span>name=None<span class="p">, </span>network=None<span class="p">, </span>optimize_for_end_user_location=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewFleet<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/worklink?tab=doc#FleetArgs">FleetArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/worklink?tab=doc#Fleet">Fleet</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Worklink.Fleet.html">Fleet</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Worklink.FleetArgs.html">FleetArgs</a></span>? <span class="nx">args = null<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
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
            title="Optional">Audit<wbr>Stream<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ARN of the Amazon Kinesis data stream that receives the audit events.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Device<wbr>Ca<wbr>Certificate<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The certificate chain, including intermediate certificates and the root certificate authority certificate used to issue device certificates.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Display<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the fleet.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Identity<wbr>Provider<span class="property-indicator"></span>
        <span class="property-type"><a href="#fleetidentityprovider">Fleet<wbr>Identity<wbr>Provider<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}Provide this to allow manage the identity provider configuration for the fleet. Fields documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A region-unique name for the AMI.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Network<span class="property-indicator"></span>
        <span class="property-type"><a href="#fleetnetwork">Fleet<wbr>Network<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}Provide this to allow manage the company network configuration for the fleet. Fields documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Optimize<wbr>For<wbr>End<wbr>User<wbr>Location<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}The option to optimize for better performance by routing traffic through the closest AWS Region to users, which may be outside of your home Region. Defaults to `true`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Audit<wbr>Stream<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The ARN of the Amazon Kinesis data stream that receives the audit events.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Device<wbr>Ca<wbr>Certificate<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The certificate chain, including intermediate certificates and the root certificate authority certificate used to issue device certificates.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Display<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name of the fleet.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Identity<wbr>Provider<span class="property-indicator"></span>
        <span class="property-type"><a href="#fleetidentityprovider">*Fleet<wbr>Identity<wbr>Provider</a></span>
    </dt>
    <dd>{{% md %}}Provide this to allow manage the identity provider configuration for the fleet. Fields documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}A region-unique name for the AMI.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Network<span class="property-indicator"></span>
        <span class="property-type"><a href="#fleetnetwork">*Fleet<wbr>Network</a></span>
    </dt>
    <dd>{{% md %}}Provide this to allow manage the company network configuration for the fleet. Fields documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Optimize<wbr>For<wbr>End<wbr>User<wbr>Location<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}The option to optimize for better performance by routing traffic through the closest AWS Region to users, which may be outside of your home Region. Defaults to `true`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">audit<wbr>Stream<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ARN of the Amazon Kinesis data stream that receives the audit events.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">device<wbr>Ca<wbr>Certificate<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The certificate chain, including intermediate certificates and the root certificate authority certificate used to issue device certificates.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">display<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the fleet.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">identity<wbr>Provider<span class="property-indicator"></span>
        <span class="property-type"><a href="#fleetidentityprovider">Fleet<wbr>Identity<wbr>Provider?</a></span>
    </dt>
    <dd>{{% md %}}Provide this to allow manage the identity provider configuration for the fleet. Fields documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A region-unique name for the AMI.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">network<span class="property-indicator"></span>
        <span class="property-type"><a href="#fleetnetwork">Fleet<wbr>Network?</a></span>
    </dt>
    <dd>{{% md %}}Provide this to allow manage the company network configuration for the fleet. Fields documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">optimize<wbr>For<wbr>End<wbr>User<wbr>Location<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}The option to optimize for better performance by routing traffic through the closest AWS Region to users, which may be outside of your home Region. Defaults to `true`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">audit_<wbr>stream_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ARN of the Amazon Kinesis data stream that receives the audit events.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">device_<wbr>ca_<wbr>certificate<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The certificate chain, including intermediate certificates and the root certificate authority certificate used to issue device certificates.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">display_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the fleet.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">identity_<wbr>provider<span class="property-indicator"></span>
        <span class="property-type"><a href="#fleetidentityprovider">Dict[Fleet<wbr>Identity<wbr>Provider]</a></span>
    </dt>
    <dd>{{% md %}}Provide this to allow manage the identity provider configuration for the fleet. Fields documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A region-unique name for the AMI.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">network<span class="property-indicator"></span>
        <span class="property-type"><a href="#fleetnetwork">Dict[Fleet<wbr>Network]</a></span>
    </dt>
    <dd>{{% md %}}Provide this to allow manage the company network configuration for the fleet. Fields documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">optimize_<wbr>for_<wbr>end_<wbr>user_<wbr>location<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}The option to optimize for better performance by routing traffic through the closest AWS Region to users, which may be outside of your home Region. Defaults to `true`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}




## Fleet Output Properties

The following output properties are available:




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of the created WorkLink Fleet.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Audit<wbr>Stream<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ARN of the Amazon Kinesis data stream that receives the audit events.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Company<wbr>Code<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The identifier used by users to sign in to the Amazon WorkLink app.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Created<wbr>Time<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The time that the fleet was created.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Device<wbr>Ca<wbr>Certificate<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The certificate chain, including intermediate certificates and the root certificate authority certificate used to issue device certificates.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Display<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the fleet.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Identity<wbr>Provider<span class="property-indicator"></span>
        <span class="property-type"><a href="#fleetidentityprovider">Fleet<wbr>Identity<wbr>Provider?</a></span>
    </dt>
    <dd>{{% md %}}Provide this to allow manage the identity provider configuration for the fleet. Fields documented below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Last<wbr>Updated<wbr>Time<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The time that the fleet was last updated.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}A region-unique name for the AMI.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Network<span class="property-indicator"></span>
        <span class="property-type"><a href="#fleetnetwork">Fleet<wbr>Network?</a></span>
    </dt>
    <dd>{{% md %}}Provide this to allow manage the company network configuration for the fleet. Fields documented below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Optimize<wbr>For<wbr>End<wbr>User<wbr>Location<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}The option to optimize for better performance by routing traffic through the closest AWS Region to users, which may be outside of your home Region. Defaults to `true`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of the created WorkLink Fleet.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Audit<wbr>Stream<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The ARN of the Amazon Kinesis data stream that receives the audit events.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Company<wbr>Code<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The identifier used by users to sign in to the Amazon WorkLink app.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Created<wbr>Time<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The time that the fleet was created.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Device<wbr>Ca<wbr>Certificate<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The certificate chain, including intermediate certificates and the root certificate authority certificate used to issue device certificates.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Display<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name of the fleet.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Identity<wbr>Provider<span class="property-indicator"></span>
        <span class="property-type"><a href="#fleetidentityprovider">*Fleet<wbr>Identity<wbr>Provider</a></span>
    </dt>
    <dd>{{% md %}}Provide this to allow manage the identity provider configuration for the fleet. Fields documented below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Last<wbr>Updated<wbr>Time<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The time that the fleet was last updated.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}A region-unique name for the AMI.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Network<span class="property-indicator"></span>
        <span class="property-type"><a href="#fleetnetwork">*Fleet<wbr>Network</a></span>
    </dt>
    <dd>{{% md %}}Provide this to allow manage the company network configuration for the fleet. Fields documented below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Optimize<wbr>For<wbr>End<wbr>User<wbr>Location<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}The option to optimize for better performance by routing traffic through the closest AWS Region to users, which may be outside of your home Region. Defaults to `true`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of the created WorkLink Fleet.
{{% /md %}}</dd>

    <dt class="property-"
            title="">audit<wbr>Stream<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ARN of the Amazon Kinesis data stream that receives the audit events.
{{% /md %}}</dd>

    <dt class="property-"
            title="">company<wbr>Code<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The identifier used by users to sign in to the Amazon WorkLink app.
{{% /md %}}</dd>

    <dt class="property-"
            title="">created<wbr>Time<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The time that the fleet was created.
{{% /md %}}</dd>

    <dt class="property-"
            title="">device<wbr>Ca<wbr>Certificate<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The certificate chain, including intermediate certificates and the root certificate authority certificate used to issue device certificates.
{{% /md %}}</dd>

    <dt class="property-"
            title="">display<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the fleet.
{{% /md %}}</dd>

    <dt class="property-"
            title="">identity<wbr>Provider<span class="property-indicator"></span>
        <span class="property-type"><a href="#fleetidentityprovider">Fleet<wbr>Identity<wbr>Provider?</a></span>
    </dt>
    <dd>{{% md %}}Provide this to allow manage the identity provider configuration for the fleet. Fields documented below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">last<wbr>Updated<wbr>Time<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The time that the fleet was last updated.
{{% /md %}}</dd>

    <dt class="property-"
            title="">name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}A region-unique name for the AMI.
{{% /md %}}</dd>

    <dt class="property-"
            title="">network<span class="property-indicator"></span>
        <span class="property-type"><a href="#fleetnetwork">Fleet<wbr>Network?</a></span>
    </dt>
    <dd>{{% md %}}Provide this to allow manage the company network configuration for the fleet. Fields documented below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">optimize<wbr>For<wbr>End<wbr>User<wbr>Location<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}The option to optimize for better performance by routing traffic through the closest AWS Region to users, which may be outside of your home Region. Defaults to `true`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ARN of the created WorkLink Fleet.
{{% /md %}}</dd>

    <dt class="property-"
            title="">audit_<wbr>stream_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ARN of the Amazon Kinesis data stream that receives the audit events.
{{% /md %}}</dd>

    <dt class="property-"
            title="">company_<wbr>code<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The identifier used by users to sign in to the Amazon WorkLink app.
{{% /md %}}</dd>

    <dt class="property-"
            title="">created_<wbr>time<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The time that the fleet was created.
{{% /md %}}</dd>

    <dt class="property-"
            title="">device_<wbr>ca_<wbr>certificate<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The certificate chain, including intermediate certificates and the root certificate authority certificate used to issue device certificates.
{{% /md %}}</dd>

    <dt class="property-"
            title="">display_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the fleet.
{{% /md %}}</dd>

    <dt class="property-"
            title="">identity_<wbr>provider<span class="property-indicator"></span>
        <span class="property-type"><a href="#fleetidentityprovider">Dict[Fleet<wbr>Identity<wbr>Provider]</a></span>
    </dt>
    <dd>{{% md %}}Provide this to allow manage the identity provider configuration for the fleet. Fields documented below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">last_<wbr>updated_<wbr>time<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The time that the fleet was last updated.
{{% /md %}}</dd>

    <dt class="property-"
            title="">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A region-unique name for the AMI.
{{% /md %}}</dd>

    <dt class="property-"
            title="">network<span class="property-indicator"></span>
        <span class="property-type"><a href="#fleetnetwork">Dict[Fleet<wbr>Network]</a></span>
    </dt>
    <dd>{{% md %}}Provide this to allow manage the company network configuration for the fleet. Fields documented below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">optimize_<wbr>for_<wbr>end_<wbr>user_<wbr>location<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}The option to optimize for better performance by routing traffic through the closest AWS Region to users, which may be outside of your home Region. Defaults to `true`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





## Look up an Existing Fleet Resource

{{< chooser language "javascript,typescript,python,go,csharp  " / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">pulumi.Input&lt;pulumi.ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/worklink/#FleetState">FleetState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/worklink/#Fleet">Fleet</a></span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>arn=None<span class="p">, </span>audit_stream_arn=None<span class="p">, </span>company_code=None<span class="p">, </span>created_time=None<span class="p">, </span>device_ca_certificate=None<span class="p">, </span>display_name=None<span class="p">, </span>identity_provider=None<span class="p">, </span>last_updated_time=None<span class="p">, </span>name=None<span class="p">, </span>network=None<span class="p">, </span>optimize_for_end_user_location=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetFleet<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">pulumi.IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/worklink?tab=doc#FleetState">FleetState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/worklink?tab=doc#Fleet">Fleet</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Worklink.Fleet.html">Fleet</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Pulumi.Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Worklink.FleetState.html">FleetState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
{{% /choosable %}}

Get an existing Fleet resource's state with the given name, ID, and optional extra properties used to qualify the lookup.

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
    <dd>{{% md %}}The ARN of the created WorkLink Fleet.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Audit<wbr>Stream<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ARN of the Amazon Kinesis data stream that receives the audit events.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Company<wbr>Code<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The identifier used by users to sign in to the Amazon WorkLink app.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Created<wbr>Time<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The time that the fleet was created.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Device<wbr>Ca<wbr>Certificate<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The certificate chain, including intermediate certificates and the root certificate authority certificate used to issue device certificates.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Display<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the fleet.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Identity<wbr>Provider<span class="property-indicator"></span>
        <span class="property-type"><a href="#fleetidentityprovider">Fleet<wbr>Identity<wbr>Provider<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}Provide this to allow manage the identity provider configuration for the fleet. Fields documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Last<wbr>Updated<wbr>Time<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The time that the fleet was last updated.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A region-unique name for the AMI.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Network<span class="property-indicator"></span>
        <span class="property-type"><a href="#fleetnetwork">Fleet<wbr>Network<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}Provide this to allow manage the company network configuration for the fleet. Fields documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Optimize<wbr>For<wbr>End<wbr>User<wbr>Location<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}The option to optimize for better performance by routing traffic through the closest AWS Region to users, which may be outside of your home Region. Defaults to `true`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The ARN of the created WorkLink Fleet.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Audit<wbr>Stream<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The ARN of the Amazon Kinesis data stream that receives the audit events.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Company<wbr>Code<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The identifier used by users to sign in to the Amazon WorkLink app.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Created<wbr>Time<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The time that the fleet was created.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Device<wbr>Ca<wbr>Certificate<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The certificate chain, including intermediate certificates and the root certificate authority certificate used to issue device certificates.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Display<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name of the fleet.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Identity<wbr>Provider<span class="property-indicator"></span>
        <span class="property-type"><a href="#fleetidentityprovider">*Fleet<wbr>Identity<wbr>Provider</a></span>
    </dt>
    <dd>{{% md %}}Provide this to allow manage the identity provider configuration for the fleet. Fields documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Last<wbr>Updated<wbr>Time<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The time that the fleet was last updated.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}A region-unique name for the AMI.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Network<span class="property-indicator"></span>
        <span class="property-type"><a href="#fleetnetwork">*Fleet<wbr>Network</a></span>
    </dt>
    <dd>{{% md %}}Provide this to allow manage the company network configuration for the fleet. Fields documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Optimize<wbr>For<wbr>End<wbr>User<wbr>Location<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}The option to optimize for better performance by routing traffic through the closest AWS Region to users, which may be outside of your home Region. Defaults to `true`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ARN of the created WorkLink Fleet.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">audit<wbr>Stream<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ARN of the Amazon Kinesis data stream that receives the audit events.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">company<wbr>Code<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The identifier used by users to sign in to the Amazon WorkLink app.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">created<wbr>Time<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The time that the fleet was created.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">device<wbr>Ca<wbr>Certificate<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The certificate chain, including intermediate certificates and the root certificate authority certificate used to issue device certificates.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">display<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the fleet.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">identity<wbr>Provider<span class="property-indicator"></span>
        <span class="property-type"><a href="#fleetidentityprovider">Fleet<wbr>Identity<wbr>Provider?</a></span>
    </dt>
    <dd>{{% md %}}Provide this to allow manage the identity provider configuration for the fleet. Fields documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">last<wbr>Updated<wbr>Time<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The time that the fleet was last updated.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A region-unique name for the AMI.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">network<span class="property-indicator"></span>
        <span class="property-type"><a href="#fleetnetwork">Fleet<wbr>Network?</a></span>
    </dt>
    <dd>{{% md %}}Provide this to allow manage the company network configuration for the fleet. Fields documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">optimize<wbr>For<wbr>End<wbr>User<wbr>Location<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}The option to optimize for better performance by routing traffic through the closest AWS Region to users, which may be outside of your home Region. Defaults to `true`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ARN of the created WorkLink Fleet.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">audit_<wbr>stream_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ARN of the Amazon Kinesis data stream that receives the audit events.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">company_<wbr>code<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The identifier used by users to sign in to the Amazon WorkLink app.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">created_<wbr>time<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The time that the fleet was created.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">device_<wbr>ca_<wbr>certificate<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The certificate chain, including intermediate certificates and the root certificate authority certificate used to issue device certificates.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">display_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the fleet.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">identity_<wbr>provider<span class="property-indicator"></span>
        <span class="property-type"><a href="#fleetidentityprovider">Dict[Fleet<wbr>Identity<wbr>Provider]</a></span>
    </dt>
    <dd>{{% md %}}Provide this to allow manage the identity provider configuration for the fleet. Fields documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">last_<wbr>updated_<wbr>time<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The time that the fleet was last updated.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A region-unique name for the AMI.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">network<span class="property-indicator"></span>
        <span class="property-type"><a href="#fleetnetwork">Dict[Fleet<wbr>Network]</a></span>
    </dt>
    <dd>{{% md %}}Provide this to allow manage the company network configuration for the fleet. Fields documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">optimize_<wbr>for_<wbr>end_<wbr>user_<wbr>location<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}The option to optimize for better performance by routing traffic through the closest AWS Region to users, which may be outside of your home Region. Defaults to `true`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}







## Supporting Types

#### FleetIdentityProvider
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#FleetIdentityProvider">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#FleetIdentityProvider">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/worklink?tab=doc#FleetIdentityProviderArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/worklink?tab=doc#FleetIdentityProviderOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Worklink.FleetIdentityProviderArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Worklink.FleetIdentityProvider.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Saml<wbr>Metadata<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The SAML metadata document provided by the customer’s identity provider.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type of identity provider.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Saml<wbr>Metadata<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The SAML metadata document provided by the customer’s identity provider.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type of identity provider.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">saml<wbr>Metadata<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The SAML metadata document provided by the customer’s identity provider.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type of identity provider.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">saml<wbr>Metadata<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The SAML metadata document provided by the customer’s identity provider.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The type of identity provider.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### FleetNetwork
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#FleetNetwork">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#FleetNetwork">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/worklink?tab=doc#FleetNetworkArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/worklink?tab=doc#FleetNetworkOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Worklink.FleetNetworkArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Worklink.FleetNetwork.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Security<wbr>Group<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">List<string></span>
    </dt>
    <dd>{{% md %}}A list of security group IDs associated with access to the provided subnets.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Subnet<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">List<string></span>
    </dt>
    <dd>{{% md %}}A list of subnet IDs used for X-ENI connections from Amazon WorkLink rendering containers.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Vpc<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The VPC ID with connectivity to associated websites.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Security<wbr>Group<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}A list of security group IDs associated with access to the provided subnets.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Subnet<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}A list of subnet IDs used for X-ENI connections from Amazon WorkLink rendering containers.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Vpc<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The VPC ID with connectivity to associated websites.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">security<wbr>Group<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">string[]</span>
    </dt>
    <dd>{{% md %}}A list of security group IDs associated with access to the provided subnets.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">subnet<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">string[]</span>
    </dt>
    <dd>{{% md %}}A list of subnet IDs used for X-ENI connections from Amazon WorkLink rendering containers.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">vpc<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The VPC ID with connectivity to associated websites.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">security_<wbr>group_<wbr>ids<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}A list of security group IDs associated with access to the provided subnets.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">subnet_<wbr>ids<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}A list of subnet IDs used for X-ENI connections from Amazon WorkLink rendering containers.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">vpc_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The VPC ID with connectivity to associated websites.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}








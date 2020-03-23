
---
title: "LoadBalancer"
block_external_search_index: true
---

Provides an Elastic Load Balancer resource, also known as a "Classic
Load Balancer" after the release of
[Application/Network Load Balancers](https://www.terraform.io/docs/providers/aws/r/lb.html).

> **NOTE on ELB Instances and ELB Attachments:** This provider currently
provides both a standalone ELB Attachment resource
(describing an instance attached to an ELB), and an ELB resource with
`instances` defined in-line. At this time you cannot use an ELB with in-line
instances in conjunction with a ELB Attachment resources. Doing so will cause a
conflict and will overwrite attachments.

## Example Usage

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

// Create a new load balancer
const bar = new aws.elb.LoadBalancer("bar", {
    accessLogs: {
        bucket: "foo",
        bucketPrefix: "bar",
        interval: 60,
    },
    availabilityZones: [
        "us-west-2a",
        "us-west-2b",
        "us-west-2c",
    ],
    connectionDraining: true,
    connectionDrainingTimeout: 400,
    crossZoneLoadBalancing: true,
    healthCheck: {
        healthyThreshold: 2,
        interval: 30,
        target: "HTTP:8000/",
        timeout: 3,
        unhealthyThreshold: 2,
    },
    idleTimeout: 400,
    instances: [aws_instance_foo.id],
    listeners: [
        {
            instancePort: 8000,
            instanceProtocol: "http",
            lbPort: 80,
            lbProtocol: "http",
        },
        {
            instancePort: 8000,
            instanceProtocol: "http",
            lbPort: 443,
            lbProtocol: "https",
            sslCertificateId: "arn:aws:iam::123456789012:server-certificate/certName",
        },
    ],
    tags: {
        Name: "foobar-elb",
    },
});
```

## Note on ECDSA Key Algorithm

If the ARN of the `ssl_certificate_id` that is pointed to references a
certificate that was signed by an ECDSA key, note that ELB only supports the
P256 and P384 curves.  Using a certificate signed by a key using a different
curve could produce the error `ERR_SSL_VERSION_OR_CIPHER_MISMATCH` in your
browser.

> This content is derived from https://github.com/terraform-providers/terraform-provider-aws/blob/master/website/docs/r/elb.html.markdown.



## Create a LoadBalancer Resource

{{< chooser language "javascript,typescript,python,go,csharp" / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/elb/#LoadBalancer">LoadBalancer</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/elb/#LoadBalancerArgs">LoadBalancerArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">LoadBalancer</span><span class="p">(resource_name, opts=None, </span>access_logs=None<span class="p">, </span>availability_zones=None<span class="p">, </span>connection_draining=None<span class="p">, </span>connection_draining_timeout=None<span class="p">, </span>cross_zone_load_balancing=None<span class="p">, </span>health_check=None<span class="p">, </span>idle_timeout=None<span class="p">, </span>instances=None<span class="p">, </span>internal=None<span class="p">, </span>listeners=None<span class="p">, </span>name=None<span class="p">, </span>name_prefix=None<span class="p">, </span>security_groups=None<span class="p">, </span>source_security_group=None<span class="p">, </span>subnets=None<span class="p">, </span>tags=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewLoadBalancer<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/elb?tab=doc#LoadBalancerArgs">LoadBalancerArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/elb?tab=doc#LoadBalancer">LoadBalancer</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Elb.LoadBalancer.html">LoadBalancer</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Elb.LoadBalancerArgs.html">LoadBalancerArgs</a></span> <span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
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
            title="Optional">Access<wbr>Logs<span class="property-indicator"></span>
        <span class="property-type"><a href="#loadbalanceraccesslogs">Load<wbr>Balancer<wbr>Access<wbr>Logs<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}An Access Logs block. Access Logs documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Availability<wbr>Zones<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}The AZ&#39;s to serve traffic in.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Connection<wbr>Draining<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Boolean to enable connection draining. Default: `false`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Connection<wbr>Draining<wbr>Timeout<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The time in seconds to allow for connections to drain. Default: `300`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Cross<wbr>Zone<wbr>Load<wbr>Balancing<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Enable cross-zone load balancing. Default: `true`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Health<wbr>Check<span class="property-indicator"></span>
        <span class="property-type"><a href="#loadbalancerhealthcheck">Load<wbr>Balancer<wbr>Health<wbr>Check<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}A health_check block. Health Check documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Idle<wbr>Timeout<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The time in seconds that the connection is allowed to be idle. Default: `60`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Instances<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}A list of instance ids to place in the ELB pool.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Internal<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}If true, ELB will be an internal ELB.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Listeners<span class="property-indicator"></span>
        <span class="property-type"><a href="#loadbalancerlistener">List&lt;Load<wbr>Balancer<wbr>Listener<wbr>Args&gt;</a></span>
    </dt>
    <dd>{{% md %}}A list of listener blocks. Listeners documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the ELB. By default generated by this provider.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<wbr>Prefix<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Creates a unique name beginning with the specified
prefix. Conflicts with `name`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Security<wbr>Groups<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}A list of security group IDs to assign to the ELB.
Only valid if creating an ELB within a VPC
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Source<wbr>Security<wbr>Group<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the security group that you can use as
part of your inbound rules for your load balancer&#39;s back-end application
instances. Use this for Classic or Default VPC only.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Subnets<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}A list of subnet IDs to attach to the ELB.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Access<wbr>Logs<span class="property-indicator"></span>
        <span class="property-type"><a href="#loadbalanceraccesslogs">*Load<wbr>Balancer<wbr>Access<wbr>Logs</a></span>
    </dt>
    <dd>{{% md %}}An Access Logs block. Access Logs documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Availability<wbr>Zones<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}The AZ&#39;s to serve traffic in.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Connection<wbr>Draining<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Boolean to enable connection draining. Default: `false`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Connection<wbr>Draining<wbr>Timeout<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The time in seconds to allow for connections to drain. Default: `300`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Cross<wbr>Zone<wbr>Load<wbr>Balancing<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Enable cross-zone load balancing. Default: `true`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Health<wbr>Check<span class="property-indicator"></span>
        <span class="property-type"><a href="#loadbalancerhealthcheck">*Load<wbr>Balancer<wbr>Health<wbr>Check</a></span>
    </dt>
    <dd>{{% md %}}A health_check block. Health Check documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Idle<wbr>Timeout<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The time in seconds that the connection is allowed to be idle. Default: `60`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Instances<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}A list of instance ids to place in the ELB pool.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Internal<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}If true, ELB will be an internal ELB.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Listeners<span class="property-indicator"></span>
        <span class="property-type"><a href="#loadbalancerlistener">[]Load<wbr>Balancer<wbr>Listener</a></span>
    </dt>
    <dd>{{% md %}}A list of listener blocks. Listeners documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name of the ELB. By default generated by this provider.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<wbr>Prefix<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Creates a unique name beginning with the specified
prefix. Conflicts with `name`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Security<wbr>Groups<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}A list of security group IDs to assign to the ELB.
Only valid if creating an ELB within a VPC
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Source<wbr>Security<wbr>Group<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name of the security group that you can use as
part of your inbound rules for your load balancer&#39;s back-end application
instances. Use this for Classic or Default VPC only.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Subnets<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}A list of subnet IDs to attach to the ELB.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">access<wbr>Logs<span class="property-indicator"></span>
        <span class="property-type"><a href="#loadbalanceraccesslogs">Load<wbr>Balancer<wbr>Access<wbr>Logs?</a></span>
    </dt>
    <dd>{{% md %}}An Access Logs block. Access Logs documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">availability<wbr>Zones<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}The AZ&#39;s to serve traffic in.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">connection<wbr>Draining<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Boolean to enable connection draining. Default: `false`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">connection<wbr>Draining<wbr>Timeout<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The time in seconds to allow for connections to drain. Default: `300`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">cross<wbr>Zone<wbr>Load<wbr>Balancing<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Enable cross-zone load balancing. Default: `true`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">health<wbr>Check<span class="property-indicator"></span>
        <span class="property-type"><a href="#loadbalancerhealthcheck">Load<wbr>Balancer<wbr>Health<wbr>Check?</a></span>
    </dt>
    <dd>{{% md %}}A health_check block. Health Check documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">idle<wbr>Timeout<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The time in seconds that the connection is allowed to be idle. Default: `60`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">instances<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}A list of instance ids to place in the ELB pool.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">internal<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}If true, ELB will be an internal ELB.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">listeners<span class="property-indicator"></span>
        <span class="property-type"><a href="#loadbalancerlistener">Load<wbr>Balancer<wbr>Listener[]</a></span>
    </dt>
    <dd>{{% md %}}A list of listener blocks. Listeners documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the ELB. By default generated by this provider.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<wbr>Prefix<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Creates a unique name beginning with the specified
prefix. Conflicts with `name`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">security<wbr>Groups<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}A list of security group IDs to assign to the ELB.
Only valid if creating an ELB within a VPC
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">source<wbr>Security<wbr>Group<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the security group that you can use as
part of your inbound rules for your load balancer&#39;s back-end application
instances. Use this for Classic or Default VPC only.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">subnets<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}A list of subnet IDs to attach to the ELB.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">access_<wbr>logs<span class="property-indicator"></span>
        <span class="property-type"><a href="#loadbalanceraccesslogs">Dict[Load<wbr>Balancer<wbr>Access<wbr>Logs]</a></span>
    </dt>
    <dd>{{% md %}}An Access Logs block. Access Logs documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">availability_<wbr>zones<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}The AZ&#39;s to serve traffic in.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">connection_<wbr>draining<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Boolean to enable connection draining. Default: `false`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">connection_<wbr>draining_<wbr>timeout<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The time in seconds to allow for connections to drain. Default: `300`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">cross_<wbr>zone_<wbr>load_<wbr>balancing<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Enable cross-zone load balancing. Default: `true`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">health_<wbr>check<span class="property-indicator"></span>
        <span class="property-type"><a href="#loadbalancerhealthcheck">Dict[Load<wbr>Balancer<wbr>Health<wbr>Check]</a></span>
    </dt>
    <dd>{{% md %}}A health_check block. Health Check documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">idle_<wbr>timeout<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The time in seconds that the connection is allowed to be idle. Default: `60`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">instances<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}A list of instance ids to place in the ELB pool.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">internal<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}If true, ELB will be an internal ELB.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">listeners<span class="property-indicator"></span>
        <span class="property-type"><a href="#loadbalancerlistener">List[Load<wbr>Balancer<wbr>Listener]</a></span>
    </dt>
    <dd>{{% md %}}A list of listener blocks. Listeners documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the ELB. By default generated by this provider.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name_<wbr>prefix<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Creates a unique name beginning with the specified
prefix. Conflicts with `name`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">security_<wbr>groups<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}A list of security group IDs to assign to the ELB.
Only valid if creating an ELB within a VPC
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">source_<wbr>security_<wbr>group<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the security group that you can use as
part of your inbound rules for your load balancer&#39;s back-end application
instances. Use this for Classic or Default VPC only.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">subnets<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}A list of subnet IDs to attach to the ELB.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}




## LoadBalancer Output Properties

The following output properties are available:




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Access<wbr>Logs<span class="property-indicator"></span>
        <span class="property-type"><a href="#loadbalanceraccesslogs">Load<wbr>Balancer<wbr>Access<wbr>Logs?</a></span>
    </dt>
    <dd>{{% md %}}An Access Logs block. Access Logs documented below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of the ELB
{{% /md %}}</dd>

    <dt class="property-"
            title="">Availability<wbr>Zones<span class="property-indicator"></span>
        <span class="property-type">List<string></span>
    </dt>
    <dd>{{% md %}}The AZ&#39;s to serve traffic in.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Connection<wbr>Draining<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Boolean to enable connection draining. Default: `false`
{{% /md %}}</dd>

    <dt class="property-"
            title="">Connection<wbr>Draining<wbr>Timeout<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The time in seconds to allow for connections to drain. Default: `300`
{{% /md %}}</dd>

    <dt class="property-"
            title="">Cross<wbr>Zone<wbr>Load<wbr>Balancing<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Enable cross-zone load balancing. Default: `true`
{{% /md %}}</dd>

    <dt class="property-"
            title="">Dns<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The DNS name of the ELB
{{% /md %}}</dd>

    <dt class="property-"
            title="">Health<wbr>Check<span class="property-indicator"></span>
        <span class="property-type"><a href="#loadbalancerhealthcheck">Load<wbr>Balancer<wbr>Health<wbr>Check</a></span>
    </dt>
    <dd>{{% md %}}A health_check block. Health Check documented below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Idle<wbr>Timeout<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The time in seconds that the connection is allowed to be idle. Default: `60`
{{% /md %}}</dd>

    <dt class="property-"
            title="">Instances<span class="property-indicator"></span>
        <span class="property-type">List<string></span>
    </dt>
    <dd>{{% md %}}A list of instance ids to place in the ELB pool.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Internal<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}If true, ELB will be an internal ELB.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Listeners<span class="property-indicator"></span>
        <span class="property-type"><a href="#loadbalancerlistener">List&lt;Load<wbr>Balancer<wbr>Listener&gt;</a></span>
    </dt>
    <dd>{{% md %}}A list of listener blocks. Listeners documented below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the ELB. By default generated by this provider.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Name<wbr>Prefix<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Creates a unique name beginning with the specified
prefix. Conflicts with `name`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Security<wbr>Groups<span class="property-indicator"></span>
        <span class="property-type">List<string></span>
    </dt>
    <dd>{{% md %}}A list of security group IDs to assign to the ELB.
Only valid if creating an ELB within a VPC
{{% /md %}}</dd>

    <dt class="property-"
            title="">Source<wbr>Security<wbr>Group<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the security group that you can use as
part of your inbound rules for your load balancer&#39;s back-end application
instances. Use this for Classic or Default VPC only.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Source<wbr>Security<wbr>Group<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the security group that you can use as
part of your inbound rules for your load balancer&#39;s back-end application
instances. Only available on ELBs launched in a VPC.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Subnets<span class="property-indicator"></span>
        <span class="property-type">List<string></span>
    </dt>
    <dd>{{% md %}}A list of subnet IDs to attach to the ELB.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Zone<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The canonical hosted zone ID of the ELB (to be used in a Route 53 Alias record)
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Access<wbr>Logs<span class="property-indicator"></span>
        <span class="property-type"><a href="#loadbalanceraccesslogs">*Load<wbr>Balancer<wbr>Access<wbr>Logs</a></span>
    </dt>
    <dd>{{% md %}}An Access Logs block. Access Logs documented below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of the ELB
{{% /md %}}</dd>

    <dt class="property-"
            title="">Availability<wbr>Zones<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}The AZ&#39;s to serve traffic in.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Connection<wbr>Draining<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Boolean to enable connection draining. Default: `false`
{{% /md %}}</dd>

    <dt class="property-"
            title="">Connection<wbr>Draining<wbr>Timeout<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The time in seconds to allow for connections to drain. Default: `300`
{{% /md %}}</dd>

    <dt class="property-"
            title="">Cross<wbr>Zone<wbr>Load<wbr>Balancing<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Enable cross-zone load balancing. Default: `true`
{{% /md %}}</dd>

    <dt class="property-"
            title="">Dns<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The DNS name of the ELB
{{% /md %}}</dd>

    <dt class="property-"
            title="">Health<wbr>Check<span class="property-indicator"></span>
        <span class="property-type"><a href="#loadbalancerhealthcheck">Load<wbr>Balancer<wbr>Health<wbr>Check</a></span>
    </dt>
    <dd>{{% md %}}A health_check block. Health Check documented below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Idle<wbr>Timeout<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The time in seconds that the connection is allowed to be idle. Default: `60`
{{% /md %}}</dd>

    <dt class="property-"
            title="">Instances<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}A list of instance ids to place in the ELB pool.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Internal<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}If true, ELB will be an internal ELB.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Listeners<span class="property-indicator"></span>
        <span class="property-type"><a href="#loadbalancerlistener">[]Load<wbr>Balancer<wbr>Listener</a></span>
    </dt>
    <dd>{{% md %}}A list of listener blocks. Listeners documented below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the ELB. By default generated by this provider.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Name<wbr>Prefix<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Creates a unique name beginning with the specified
prefix. Conflicts with `name`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Security<wbr>Groups<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}A list of security group IDs to assign to the ELB.
Only valid if creating an ELB within a VPC
{{% /md %}}</dd>

    <dt class="property-"
            title="">Source<wbr>Security<wbr>Group<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the security group that you can use as
part of your inbound rules for your load balancer&#39;s back-end application
instances. Use this for Classic or Default VPC only.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Source<wbr>Security<wbr>Group<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the security group that you can use as
part of your inbound rules for your load balancer&#39;s back-end application
instances. Only available on ELBs launched in a VPC.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Subnets<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}A list of subnet IDs to attach to the ELB.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Zone<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The canonical hosted zone ID of the ELB (to be used in a Route 53 Alias record)
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">access<wbr>Logs<span class="property-indicator"></span>
        <span class="property-type"><a href="#loadbalanceraccesslogs">Load<wbr>Balancer<wbr>Access<wbr>Logs?</a></span>
    </dt>
    <dd>{{% md %}}An Access Logs block. Access Logs documented below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of the ELB
{{% /md %}}</dd>

    <dt class="property-"
            title="">availability<wbr>Zones<span class="property-indicator"></span>
        <span class="property-type">string[]</span>
    </dt>
    <dd>{{% md %}}The AZ&#39;s to serve traffic in.
{{% /md %}}</dd>

    <dt class="property-"
            title="">connection<wbr>Draining<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Boolean to enable connection draining. Default: `false`
{{% /md %}}</dd>

    <dt class="property-"
            title="">connection<wbr>Draining<wbr>Timeout<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The time in seconds to allow for connections to drain. Default: `300`
{{% /md %}}</dd>

    <dt class="property-"
            title="">cross<wbr>Zone<wbr>Load<wbr>Balancing<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Enable cross-zone load balancing. Default: `true`
{{% /md %}}</dd>

    <dt class="property-"
            title="">dns<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The DNS name of the ELB
{{% /md %}}</dd>

    <dt class="property-"
            title="">health<wbr>Check<span class="property-indicator"></span>
        <span class="property-type"><a href="#loadbalancerhealthcheck">Load<wbr>Balancer<wbr>Health<wbr>Check</a></span>
    </dt>
    <dd>{{% md %}}A health_check block. Health Check documented below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">idle<wbr>Timeout<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The time in seconds that the connection is allowed to be idle. Default: `60`
{{% /md %}}</dd>

    <dt class="property-"
            title="">instances<span class="property-indicator"></span>
        <span class="property-type">string[]</span>
    </dt>
    <dd>{{% md %}}A list of instance ids to place in the ELB pool.
{{% /md %}}</dd>

    <dt class="property-"
            title="">internal<span class="property-indicator"></span>
        <span class="property-type">boolean</span>
    </dt>
    <dd>{{% md %}}If true, ELB will be an internal ELB.
{{% /md %}}</dd>

    <dt class="property-"
            title="">listeners<span class="property-indicator"></span>
        <span class="property-type"><a href="#loadbalancerlistener">Load<wbr>Balancer<wbr>Listener[]</a></span>
    </dt>
    <dd>{{% md %}}A list of listener blocks. Listeners documented below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the ELB. By default generated by this provider.
{{% /md %}}</dd>

    <dt class="property-"
            title="">name<wbr>Prefix<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Creates a unique name beginning with the specified
prefix. Conflicts with `name`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">security<wbr>Groups<span class="property-indicator"></span>
        <span class="property-type">string[]</span>
    </dt>
    <dd>{{% md %}}A list of security group IDs to assign to the ELB.
Only valid if creating an ELB within a VPC
{{% /md %}}</dd>

    <dt class="property-"
            title="">source<wbr>Security<wbr>Group<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the security group that you can use as
part of your inbound rules for your load balancer&#39;s back-end application
instances. Use this for Classic or Default VPC only.
{{% /md %}}</dd>

    <dt class="property-"
            title="">source<wbr>Security<wbr>Group<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the security group that you can use as
part of your inbound rules for your load balancer&#39;s back-end application
instances. Only available on ELBs launched in a VPC.
{{% /md %}}</dd>

    <dt class="property-"
            title="">subnets<span class="property-indicator"></span>
        <span class="property-type">string[]</span>
    </dt>
    <dd>{{% md %}}A list of subnet IDs to attach to the ELB.
{{% /md %}}</dd>

    <dt class="property-"
            title="">tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-"
            title="">zone<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The canonical hosted zone ID of the ELB (to be used in a Route 53 Alias record)
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">access_<wbr>logs<span class="property-indicator"></span>
        <span class="property-type"><a href="#loadbalanceraccesslogs">Dict[Load<wbr>Balancer<wbr>Access<wbr>Logs]</a></span>
    </dt>
    <dd>{{% md %}}An Access Logs block. Access Logs documented below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ARN of the ELB
{{% /md %}}</dd>

    <dt class="property-"
            title="">availability_<wbr>zones<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}The AZ&#39;s to serve traffic in.
{{% /md %}}</dd>

    <dt class="property-"
            title="">connection_<wbr>draining<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Boolean to enable connection draining. Default: `false`
{{% /md %}}</dd>

    <dt class="property-"
            title="">connection_<wbr>draining_<wbr>timeout<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The time in seconds to allow for connections to drain. Default: `300`
{{% /md %}}</dd>

    <dt class="property-"
            title="">cross_<wbr>zone_<wbr>load_<wbr>balancing<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Enable cross-zone load balancing. Default: `true`
{{% /md %}}</dd>

    <dt class="property-"
            title="">dns_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The DNS name of the ELB
{{% /md %}}</dd>

    <dt class="property-"
            title="">health_<wbr>check<span class="property-indicator"></span>
        <span class="property-type"><a href="#loadbalancerhealthcheck">Dict[Load<wbr>Balancer<wbr>Health<wbr>Check]</a></span>
    </dt>
    <dd>{{% md %}}A health_check block. Health Check documented below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">idle_<wbr>timeout<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The time in seconds that the connection is allowed to be idle. Default: `60`
{{% /md %}}</dd>

    <dt class="property-"
            title="">instances<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}A list of instance ids to place in the ELB pool.
{{% /md %}}</dd>

    <dt class="property-"
            title="">internal<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}If true, ELB will be an internal ELB.
{{% /md %}}</dd>

    <dt class="property-"
            title="">listeners<span class="property-indicator"></span>
        <span class="property-type"><a href="#loadbalancerlistener">List[Load<wbr>Balancer<wbr>Listener]</a></span>
    </dt>
    <dd>{{% md %}}A list of listener blocks. Listeners documented below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the ELB. By default generated by this provider.
{{% /md %}}</dd>

    <dt class="property-"
            title="">name_<wbr>prefix<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Creates a unique name beginning with the specified
prefix. Conflicts with `name`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">security_<wbr>groups<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}A list of security group IDs to assign to the ELB.
Only valid if creating an ELB within a VPC
{{% /md %}}</dd>

    <dt class="property-"
            title="">source_<wbr>security_<wbr>group<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the security group that you can use as
part of your inbound rules for your load balancer&#39;s back-end application
instances. Use this for Classic or Default VPC only.
{{% /md %}}</dd>

    <dt class="property-"
            title="">source_<wbr>security_<wbr>group_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ID of the security group that you can use as
part of your inbound rules for your load balancer&#39;s back-end application
instances. Only available on ELBs launched in a VPC.
{{% /md %}}</dd>

    <dt class="property-"
            title="">subnets<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}A list of subnet IDs to attach to the ELB.
{{% /md %}}</dd>

    <dt class="property-"
            title="">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-"
            title="">zone_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The canonical hosted zone ID of the ELB (to be used in a Route 53 Alias record)
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





## Look up an Existing LoadBalancer Resource

{{< chooser language "javascript,typescript,python,go,csharp  " / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">pulumi.Input&lt;pulumi.ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/elb/#LoadBalancerState">LoadBalancerState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/elb/#LoadBalancer">LoadBalancer</a></span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>access_logs=None<span class="p">, </span>arn=None<span class="p">, </span>availability_zones=None<span class="p">, </span>connection_draining=None<span class="p">, </span>connection_draining_timeout=None<span class="p">, </span>cross_zone_load_balancing=None<span class="p">, </span>dns_name=None<span class="p">, </span>health_check=None<span class="p">, </span>idle_timeout=None<span class="p">, </span>instances=None<span class="p">, </span>internal=None<span class="p">, </span>listeners=None<span class="p">, </span>name=None<span class="p">, </span>name_prefix=None<span class="p">, </span>security_groups=None<span class="p">, </span>source_security_group=None<span class="p">, </span>source_security_group_id=None<span class="p">, </span>subnets=None<span class="p">, </span>tags=None<span class="p">, </span>zone_id=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetLoadBalancer<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">pulumi.IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/elb?tab=doc#LoadBalancerState">LoadBalancerState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/elb?tab=doc#LoadBalancer">LoadBalancer</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Elb.LoadBalancer.html">LoadBalancer</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Pulumi.Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Elb.LoadBalancerState.html">LoadBalancerState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
{{% /choosable %}}

Get an existing LoadBalancer resource's state with the given name, ID, and optional extra properties used to qualify the lookup.

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
            title="Optional">Access<wbr>Logs<span class="property-indicator"></span>
        <span class="property-type"><a href="#loadbalanceraccesslogs">Load<wbr>Balancer<wbr>Access<wbr>Logs<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}An Access Logs block. Access Logs documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ARN of the ELB
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Availability<wbr>Zones<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}The AZ&#39;s to serve traffic in.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Connection<wbr>Draining<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Boolean to enable connection draining. Default: `false`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Connection<wbr>Draining<wbr>Timeout<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The time in seconds to allow for connections to drain. Default: `300`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Cross<wbr>Zone<wbr>Load<wbr>Balancing<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Enable cross-zone load balancing. Default: `true`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Dns<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The DNS name of the ELB
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Health<wbr>Check<span class="property-indicator"></span>
        <span class="property-type"><a href="#loadbalancerhealthcheck">Load<wbr>Balancer<wbr>Health<wbr>Check<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}A health_check block. Health Check documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Idle<wbr>Timeout<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The time in seconds that the connection is allowed to be idle. Default: `60`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Instances<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}A list of instance ids to place in the ELB pool.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Internal<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}If true, ELB will be an internal ELB.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Listeners<span class="property-indicator"></span>
        <span class="property-type"><a href="#loadbalancerlistener">List&lt;Load<wbr>Balancer<wbr>Listener<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}A list of listener blocks. Listeners documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the ELB. By default generated by this provider.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<wbr>Prefix<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Creates a unique name beginning with the specified
prefix. Conflicts with `name`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Security<wbr>Groups<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}A list of security group IDs to assign to the ELB.
Only valid if creating an ELB within a VPC
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Source<wbr>Security<wbr>Group<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the security group that you can use as
part of your inbound rules for your load balancer&#39;s back-end application
instances. Use this for Classic or Default VPC only.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Source<wbr>Security<wbr>Group<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ID of the security group that you can use as
part of your inbound rules for your load balancer&#39;s back-end application
instances. Only available on ELBs launched in a VPC.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Subnets<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}A list of subnet IDs to attach to the ELB.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Zone<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The canonical hosted zone ID of the ELB (to be used in a Route 53 Alias record)
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Access<wbr>Logs<span class="property-indicator"></span>
        <span class="property-type"><a href="#loadbalanceraccesslogs">*Load<wbr>Balancer<wbr>Access<wbr>Logs</a></span>
    </dt>
    <dd>{{% md %}}An Access Logs block. Access Logs documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The ARN of the ELB
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Availability<wbr>Zones<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}The AZ&#39;s to serve traffic in.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Connection<wbr>Draining<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Boolean to enable connection draining. Default: `false`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Connection<wbr>Draining<wbr>Timeout<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The time in seconds to allow for connections to drain. Default: `300`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Cross<wbr>Zone<wbr>Load<wbr>Balancing<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Enable cross-zone load balancing. Default: `true`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Dns<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The DNS name of the ELB
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Health<wbr>Check<span class="property-indicator"></span>
        <span class="property-type"><a href="#loadbalancerhealthcheck">*Load<wbr>Balancer<wbr>Health<wbr>Check</a></span>
    </dt>
    <dd>{{% md %}}A health_check block. Health Check documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Idle<wbr>Timeout<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The time in seconds that the connection is allowed to be idle. Default: `60`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Instances<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}A list of instance ids to place in the ELB pool.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Internal<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}If true, ELB will be an internal ELB.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Listeners<span class="property-indicator"></span>
        <span class="property-type"><a href="#loadbalancerlistener">[]Load<wbr>Balancer<wbr>Listener</a></span>
    </dt>
    <dd>{{% md %}}A list of listener blocks. Listeners documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name of the ELB. By default generated by this provider.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<wbr>Prefix<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Creates a unique name beginning with the specified
prefix. Conflicts with `name`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Security<wbr>Groups<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}A list of security group IDs to assign to the ELB.
Only valid if creating an ELB within a VPC
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Source<wbr>Security<wbr>Group<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name of the security group that you can use as
part of your inbound rules for your load balancer&#39;s back-end application
instances. Use this for Classic or Default VPC only.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Source<wbr>Security<wbr>Group<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The ID of the security group that you can use as
part of your inbound rules for your load balancer&#39;s back-end application
instances. Only available on ELBs launched in a VPC.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Subnets<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}A list of subnet IDs to attach to the ELB.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Zone<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The canonical hosted zone ID of the ELB (to be used in a Route 53 Alias record)
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">access<wbr>Logs<span class="property-indicator"></span>
        <span class="property-type"><a href="#loadbalanceraccesslogs">Load<wbr>Balancer<wbr>Access<wbr>Logs?</a></span>
    </dt>
    <dd>{{% md %}}An Access Logs block. Access Logs documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ARN of the ELB
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">availability<wbr>Zones<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}The AZ&#39;s to serve traffic in.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">connection<wbr>Draining<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Boolean to enable connection draining. Default: `false`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">connection<wbr>Draining<wbr>Timeout<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The time in seconds to allow for connections to drain. Default: `300`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">cross<wbr>Zone<wbr>Load<wbr>Balancing<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Enable cross-zone load balancing. Default: `true`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">dns<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The DNS name of the ELB
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">health<wbr>Check<span class="property-indicator"></span>
        <span class="property-type"><a href="#loadbalancerhealthcheck">Load<wbr>Balancer<wbr>Health<wbr>Check?</a></span>
    </dt>
    <dd>{{% md %}}A health_check block. Health Check documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">idle<wbr>Timeout<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The time in seconds that the connection is allowed to be idle. Default: `60`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">instances<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}A list of instance ids to place in the ELB pool.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">internal<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}If true, ELB will be an internal ELB.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">listeners<span class="property-indicator"></span>
        <span class="property-type"><a href="#loadbalancerlistener">Load<wbr>Balancer<wbr>Listener[]?</a></span>
    </dt>
    <dd>{{% md %}}A list of listener blocks. Listeners documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the ELB. By default generated by this provider.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<wbr>Prefix<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Creates a unique name beginning with the specified
prefix. Conflicts with `name`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">security<wbr>Groups<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}A list of security group IDs to assign to the ELB.
Only valid if creating an ELB within a VPC
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">source<wbr>Security<wbr>Group<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the security group that you can use as
part of your inbound rules for your load balancer&#39;s back-end application
instances. Use this for Classic or Default VPC only.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">source<wbr>Security<wbr>Group<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ID of the security group that you can use as
part of your inbound rules for your load balancer&#39;s back-end application
instances. Only available on ELBs launched in a VPC.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">subnets<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}A list of subnet IDs to attach to the ELB.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">zone<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The canonical hosted zone ID of the ELB (to be used in a Route 53 Alias record)
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">access_<wbr>logs<span class="property-indicator"></span>
        <span class="property-type"><a href="#loadbalanceraccesslogs">Dict[Load<wbr>Balancer<wbr>Access<wbr>Logs]</a></span>
    </dt>
    <dd>{{% md %}}An Access Logs block. Access Logs documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ARN of the ELB
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">availability_<wbr>zones<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}The AZ&#39;s to serve traffic in.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">connection_<wbr>draining<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Boolean to enable connection draining. Default: `false`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">connection_<wbr>draining_<wbr>timeout<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The time in seconds to allow for connections to drain. Default: `300`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">cross_<wbr>zone_<wbr>load_<wbr>balancing<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Enable cross-zone load balancing. Default: `true`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">dns_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The DNS name of the ELB
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">health_<wbr>check<span class="property-indicator"></span>
        <span class="property-type"><a href="#loadbalancerhealthcheck">Dict[Load<wbr>Balancer<wbr>Health<wbr>Check]</a></span>
    </dt>
    <dd>{{% md %}}A health_check block. Health Check documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">idle_<wbr>timeout<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The time in seconds that the connection is allowed to be idle. Default: `60`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">instances<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}A list of instance ids to place in the ELB pool.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">internal<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}If true, ELB will be an internal ELB.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">listeners<span class="property-indicator"></span>
        <span class="property-type"><a href="#loadbalancerlistener">List[Load<wbr>Balancer<wbr>Listener]</a></span>
    </dt>
    <dd>{{% md %}}A list of listener blocks. Listeners documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the ELB. By default generated by this provider.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name_<wbr>prefix<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Creates a unique name beginning with the specified
prefix. Conflicts with `name`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">security_<wbr>groups<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}A list of security group IDs to assign to the ELB.
Only valid if creating an ELB within a VPC
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">source_<wbr>security_<wbr>group<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the security group that you can use as
part of your inbound rules for your load balancer&#39;s back-end application
instances. Use this for Classic or Default VPC only.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">source_<wbr>security_<wbr>group_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ID of the security group that you can use as
part of your inbound rules for your load balancer&#39;s back-end application
instances. Only available on ELBs launched in a VPC.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">subnets<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}A list of subnet IDs to attach to the ELB.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">zone_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The canonical hosted zone ID of the ELB (to be used in a Route 53 Alias record)
{{% /md %}}</dd>

</dl>
{{% /choosable %}}







## Supporting Types

#### LoadBalancerAccessLogs
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#LoadBalancerAccessLogs">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#LoadBalancerAccessLogs">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/elb?tab=doc#LoadBalancerAccessLogsArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/elb?tab=doc#LoadBalancerAccessLogsOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Elb.LoadBalancerAccessLogsArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Elb.LoadBalancerAccessLogs.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Bucket<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The S3 bucket name to store the logs in.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Bucket<wbr>Prefix<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The S3 bucket prefix. Logs are stored in the root if not configured.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Enabled<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Boolean to enable / disable `access_logs`. Default is `true`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Interval<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The interval between checks.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Bucket<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The S3 bucket name to store the logs in.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Bucket<wbr>Prefix<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The S3 bucket prefix. Logs are stored in the root if not configured.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Enabled<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Boolean to enable / disable `access_logs`. Default is `true`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Interval<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The interval between checks.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">bucket<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The S3 bucket name to store the logs in.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">bucket<wbr>Prefix<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The S3 bucket prefix. Logs are stored in the root if not configured.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">enabled<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Boolean to enable / disable `access_logs`. Default is `true`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">interval<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The interval between checks.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">bucket<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The S3 bucket name to store the logs in.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">bucket_<wbr>prefix<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The S3 bucket prefix. Logs are stored in the root if not configured.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">enabled<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Boolean to enable / disable `access_logs`. Default is `true`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">interval<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The interval between checks.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### LoadBalancerHealthCheck
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#LoadBalancerHealthCheck">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#LoadBalancerHealthCheck">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/elb?tab=doc#LoadBalancerHealthCheckArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/elb?tab=doc#LoadBalancerHealthCheckOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Elb.LoadBalancerHealthCheckArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Elb.LoadBalancerHealthCheck.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Healthy<wbr>Threshold<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The number of checks before the instance is declared healthy.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Interval<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The interval between checks.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Target<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The target of the check. Valid pattern is &#34;${PROTOCOL}:${PORT}${PATH}&#34;, where PROTOCOL
values are:
* `HTTP`, `HTTPS` - PORT and PATH are required
* `TCP`, `SSL` - PORT is required, PATH is not supported
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Timeout<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The length of time before the check times out.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Unhealthy<wbr>Threshold<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The number of checks before the instance is declared unhealthy.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Healthy<wbr>Threshold<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The number of checks before the instance is declared healthy.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Interval<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The interval between checks.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Target<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The target of the check. Valid pattern is &#34;${PROTOCOL}:${PORT}${PATH}&#34;, where PROTOCOL
values are:
* `HTTP`, `HTTPS` - PORT and PATH are required
* `TCP`, `SSL` - PORT is required, PATH is not supported
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Timeout<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The length of time before the check times out.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Unhealthy<wbr>Threshold<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The number of checks before the instance is declared unhealthy.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">healthy<wbr>Threshold<span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}The number of checks before the instance is declared healthy.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">interval<span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}The interval between checks.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">target<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The target of the check. Valid pattern is &#34;${PROTOCOL}:${PORT}${PATH}&#34;, where PROTOCOL
values are:
* `HTTP`, `HTTPS` - PORT and PATH are required
* `TCP`, `SSL` - PORT is required, PATH is not supported
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">timeout<span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}The length of time before the check times out.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">unhealthy<wbr>Threshold<span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}The number of checks before the instance is declared unhealthy.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">healthy<wbr>Threshold<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The number of checks before the instance is declared healthy.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">interval<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The interval between checks.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">target<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The target of the check. Valid pattern is &#34;${PROTOCOL}:${PORT}${PATH}&#34;, where PROTOCOL
values are:
* `HTTP`, `HTTPS` - PORT and PATH are required
* `TCP`, `SSL` - PORT is required, PATH is not supported
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">timeout<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The length of time before the check times out.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">unhealthy<wbr>Threshold<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The number of checks before the instance is declared unhealthy.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### LoadBalancerListener
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#LoadBalancerListener">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#LoadBalancerListener">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/elb?tab=doc#LoadBalancerListenerArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/elb?tab=doc#LoadBalancerListenerOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Elb.LoadBalancerListenerArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Elb.LoadBalancerListener.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Instance<wbr>Port<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The port on the instance to route to
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Instance<wbr>Protocol<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The protocol to use to the instance. Valid
values are `HTTP`, `HTTPS`, `TCP`, or `SSL`
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Lb<wbr>Port<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The port to listen on for the load balancer
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Lb<wbr>Protocol<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The protocol to listen on. Valid values are `HTTP`,
`HTTPS`, `TCP`, or `SSL`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ssl<wbr>Certificate<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ARN of an SSL certificate you have
uploaded to AWS IAM. **Note ECDSA-specific restrictions below.  Only valid when `lb_protocol` is either HTTPS or SSL**
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Instance<wbr>Port<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The port on the instance to route to
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Instance<wbr>Protocol<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The protocol to use to the instance. Valid
values are `HTTP`, `HTTPS`, `TCP`, or `SSL`
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Lb<wbr>Port<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The port to listen on for the load balancer
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Lb<wbr>Protocol<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The protocol to listen on. Valid values are `HTTP`,
`HTTPS`, `TCP`, or `SSL`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ssl<wbr>Certificate<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The ARN of an SSL certificate you have
uploaded to AWS IAM. **Note ECDSA-specific restrictions below.  Only valid when `lb_protocol` is either HTTPS or SSL**
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">instance<wbr>Port<span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}The port on the instance to route to
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">instance<wbr>Protocol<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The protocol to use to the instance. Valid
values are `HTTP`, `HTTPS`, `TCP`, or `SSL`
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">lb<wbr>Port<span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}The port to listen on for the load balancer
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">lb<wbr>Protocol<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The protocol to listen on. Valid values are `HTTP`,
`HTTPS`, `TCP`, or `SSL`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ssl<wbr>Certificate<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ARN of an SSL certificate you have
uploaded to AWS IAM. **Note ECDSA-specific restrictions below.  Only valid when `lb_protocol` is either HTTPS or SSL**
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">instance_<wbr>port<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The port on the instance to route to
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">instance<wbr>Protocol<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The protocol to use to the instance. Valid
values are `HTTP`, `HTTPS`, `TCP`, or `SSL`
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">lb_<wbr>port<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The port to listen on for the load balancer
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">lb<wbr>Protocol<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The protocol to listen on. Valid values are `HTTP`,
`HTTPS`, `TCP`, or `SSL`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ssl<wbr>Certificate<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ARN of an SSL certificate you have
uploaded to AWS IAM. **Note ECDSA-specific restrictions below.  Only valid when `lb_protocol` is either HTTPS or SSL**
{{% /md %}}</dd>

</dl>
{{% /choosable %}}









---
title: "LoadBalancer"
block_external_search_index: true
---

Provides a Load Balancer resource.

> **Note:** `aws.alb.LoadBalancer` is known as `aws.lb.LoadBalancer`. The functionality is identical.

## Example Usage

### Application Load Balancer

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const test = new aws.lb.LoadBalancer("test", {
    accessLogs: {
        bucket: aws_s3_bucket_lb_logs.bucket,
        enabled: true,
        prefix: "test-lb",
    },
    enableDeletionProtection: true,
    internal: false,
    loadBalancerType: "application",
    securityGroups: [aws_security_group_lb_sg.id],
    subnets: [aws_subnet_public.map(v => v.id)],
    tags: {
        Environment: "production",
    },
});
```

### Network Load Balancer

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const test = new aws.lb.LoadBalancer("test", {
    enableDeletionProtection: true,
    internal: false,
    loadBalancerType: "network",
    subnets: [aws_subnet_public.map(v => v.id)],
    tags: {
        Environment: "production",
    },
});
```

### Specifying Elastic IPs

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const example = new aws.lb.LoadBalancer("example", {
    loadBalancerType: "network",
    subnetMappings: [
        {
            allocationId: aws_eip_example1.id,
            subnetId: aws_subnet_example1.id,
        },
        {
            allocationId: aws_eip_example2.id,
            subnetId: aws_subnet_example2.id,
        },
    ],
});
```

> This content is derived from https://github.com/terraform-providers/terraform-provider-aws/blob/master/website/docs/r/lb.html.markdown.



## Create a LoadBalancer Resource

{{< chooser language "javascript,typescript,python,go,csharp" / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/elasticloadbalancingv2/#LoadBalancer">LoadBalancer</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/elasticloadbalancingv2/#LoadBalancerArgs">LoadBalancerArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">LoadBalancer</span><span class="p">(resource_name, opts=None, </span>access_logs=None<span class="p">, </span>enable_cross_zone_load_balancing=None<span class="p">, </span>enable_deletion_protection=None<span class="p">, </span>enable_http2=None<span class="p">, </span>idle_timeout=None<span class="p">, </span>internal=None<span class="p">, </span>ip_address_type=None<span class="p">, </span>load_balancer_type=None<span class="p">, </span>name=None<span class="p">, </span>name_prefix=None<span class="p">, </span>security_groups=None<span class="p">, </span>subnet_mappings=None<span class="p">, </span>subnets=None<span class="p">, </span>tags=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewLoadBalancer<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/elasticloadbalancingv2?tab=doc#LoadBalancerArgs">LoadBalancerArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/elasticloadbalancingv2?tab=doc#LoadBalancer">LoadBalancer</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Elasticloadbalancingv2.LoadBalancer.html">LoadBalancer</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Elasticloadbalancingv2.LoadBalancerArgs.html">LoadBalancerArgs</a></span>? <span class="nx">args = null<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
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
            title="Optional">Enable<wbr>Cross<wbr>Zone<wbr>Load<wbr>Balancing<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}If true, cross-zone load balancing of the load balancer will be enabled.
This is a `network` load balancer feature. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Enable<wbr>Deletion<wbr>Protection<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}If true, deletion of the load balancer will be disabled via
the AWS API. This will prevent this provider from deleting the load balancer. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Enable<wbr>Http2<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Indicates whether HTTP/2 is enabled in `application` load balancers. Defaults to `true`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Idle<wbr>Timeout<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The time in seconds that the connection is allowed to be idle. Only valid for Load Balancers of type `application`. Default: 60.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Internal<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}If true, the LB will be internal.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ip<wbr>Address<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The type of IP addresses used by the subnets for your load balancer. The possible values are `ipv4` and `dualstack`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Load<wbr>Balancer<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The type of load balancer to create. Possible values are `application` or `network`. The default value is `application`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the LB. This name must be unique within your AWS account, can have a maximum of 32 characters,
must contain only alphanumeric characters or hyphens, and must not begin or end with a hyphen. If not specified,
this provider will autogenerate a name beginning with `tf-lb`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<wbr>Prefix<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Creates a unique name beginning with the specified prefix. Conflicts with `name`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Security<wbr>Groups<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}A list of security group IDs to assign to the LB. Only valid for Load Balancers of type `application`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Subnet<wbr>Mappings<span class="property-indicator"></span>
        <span class="property-type"><a href="#loadbalancersubnetmapping">List&lt;Load<wbr>Balancer<wbr>Subnet<wbr>Mapping<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}A subnet mapping block as documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Subnets<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}A list of subnet IDs to attach to the LB. Subnets
cannot be updated for Load Balancers of type `network`. Changing this value
for load balancers of type `network` will force a recreation of the resource.
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
            title="Optional">Enable<wbr>Cross<wbr>Zone<wbr>Load<wbr>Balancing<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}If true, cross-zone load balancing of the load balancer will be enabled.
This is a `network` load balancer feature. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Enable<wbr>Deletion<wbr>Protection<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}If true, deletion of the load balancer will be disabled via
the AWS API. This will prevent this provider from deleting the load balancer. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Enable<wbr>Http2<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Indicates whether HTTP/2 is enabled in `application` load balancers. Defaults to `true`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Idle<wbr>Timeout<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The time in seconds that the connection is allowed to be idle. Only valid for Load Balancers of type `application`. Default: 60.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Internal<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}If true, the LB will be internal.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ip<wbr>Address<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The type of IP addresses used by the subnets for your load balancer. The possible values are `ipv4` and `dualstack`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Load<wbr>Balancer<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The type of load balancer to create. Possible values are `application` or `network`. The default value is `application`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name of the LB. This name must be unique within your AWS account, can have a maximum of 32 characters,
must contain only alphanumeric characters or hyphens, and must not begin or end with a hyphen. If not specified,
this provider will autogenerate a name beginning with `tf-lb`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<wbr>Prefix<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Creates a unique name beginning with the specified prefix. Conflicts with `name`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Security<wbr>Groups<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}A list of security group IDs to assign to the LB. Only valid for Load Balancers of type `application`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Subnet<wbr>Mappings<span class="property-indicator"></span>
        <span class="property-type"><a href="#loadbalancersubnetmapping">[]Load<wbr>Balancer<wbr>Subnet<wbr>Mapping</a></span>
    </dt>
    <dd>{{% md %}}A subnet mapping block as documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Subnets<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}A list of subnet IDs to attach to the LB. Subnets
cannot be updated for Load Balancers of type `network`. Changing this value
for load balancers of type `network` will force a recreation of the resource.
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
            title="Optional">enable<wbr>Cross<wbr>Zone<wbr>Load<wbr>Balancing<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}If true, cross-zone load balancing of the load balancer will be enabled.
This is a `network` load balancer feature. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">enable<wbr>Deletion<wbr>Protection<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}If true, deletion of the load balancer will be disabled via
the AWS API. This will prevent this provider from deleting the load balancer. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">enable<wbr>Http2<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Indicates whether HTTP/2 is enabled in `application` load balancers. Defaults to `true`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">idle<wbr>Timeout<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The time in seconds that the connection is allowed to be idle. Only valid for Load Balancers of type `application`. Default: 60.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">internal<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}If true, the LB will be internal.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ip<wbr>Address<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The type of IP addresses used by the subnets for your load balancer. The possible values are `ipv4` and `dualstack`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">load<wbr>Balancer<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The type of load balancer to create. Possible values are `application` or `network`. The default value is `application`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the LB. This name must be unique within your AWS account, can have a maximum of 32 characters,
must contain only alphanumeric characters or hyphens, and must not begin or end with a hyphen. If not specified,
this provider will autogenerate a name beginning with `tf-lb`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<wbr>Prefix<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Creates a unique name beginning with the specified prefix. Conflicts with `name`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">security<wbr>Groups<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}A list of security group IDs to assign to the LB. Only valid for Load Balancers of type `application`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">subnet<wbr>Mappings<span class="property-indicator"></span>
        <span class="property-type"><a href="#loadbalancersubnetmapping">Load<wbr>Balancer<wbr>Subnet<wbr>Mapping[]?</a></span>
    </dt>
    <dd>{{% md %}}A subnet mapping block as documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">subnets<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}A list of subnet IDs to attach to the LB. Subnets
cannot be updated for Load Balancers of type `network`. Changing this value
for load balancers of type `network` will force a recreation of the resource.
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
            title="Optional">enable_<wbr>cross_<wbr>zone_<wbr>load_<wbr>balancing<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}If true, cross-zone load balancing of the load balancer will be enabled.
This is a `network` load balancer feature. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">enable_<wbr>deletion_<wbr>protection<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}If true, deletion of the load balancer will be disabled via
the AWS API. This will prevent this provider from deleting the load balancer. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">enable_<wbr>http2<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Indicates whether HTTP/2 is enabled in `application` load balancers. Defaults to `true`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">idle_<wbr>timeout<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The time in seconds that the connection is allowed to be idle. Only valid for Load Balancers of type `application`. Default: 60.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">internal<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}If true, the LB will be internal.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ip_<wbr>address_<wbr>type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The type of IP addresses used by the subnets for your load balancer. The possible values are `ipv4` and `dualstack`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">load_<wbr>balancer_<wbr>type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The type of load balancer to create. Possible values are `application` or `network`. The default value is `application`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the LB. This name must be unique within your AWS account, can have a maximum of 32 characters,
must contain only alphanumeric characters or hyphens, and must not begin or end with a hyphen. If not specified,
this provider will autogenerate a name beginning with `tf-lb`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name_<wbr>prefix<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Creates a unique name beginning with the specified prefix. Conflicts with `name`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">security_<wbr>groups<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}A list of security group IDs to assign to the LB. Only valid for Load Balancers of type `application`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">subnet_<wbr>mappings<span class="property-indicator"></span>
        <span class="property-type"><a href="#loadbalancersubnetmapping">List[Load<wbr>Balancer<wbr>Subnet<wbr>Mapping]</a></span>
    </dt>
    <dd>{{% md %}}A subnet mapping block as documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">subnets<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}A list of subnet IDs to attach to the LB. Subnets
cannot be updated for Load Balancers of type `network`. Changing this value
for load balancers of type `network` will force a recreation of the resource.
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
    <dd>{{% md %}}The ARN of the load balancer (matches `id`).
{{% /md %}}</dd>

    <dt class="property-"
            title="">Arn<wbr>Suffix<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN suffix for use with CloudWatch Metrics.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Dns<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The DNS name of the load balancer.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Enable<wbr>Cross<wbr>Zone<wbr>Load<wbr>Balancing<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}If true, cross-zone load balancing of the load balancer will be enabled.
This is a `network` load balancer feature. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Enable<wbr>Deletion<wbr>Protection<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}If true, deletion of the load balancer will be disabled via
the AWS API. This will prevent this provider from deleting the load balancer. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Enable<wbr>Http2<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Indicates whether HTTP/2 is enabled in `application` load balancers. Defaults to `true`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Idle<wbr>Timeout<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The time in seconds that the connection is allowed to be idle. Only valid for Load Balancers of type `application`. Default: 60.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Internal<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}If true, the LB will be internal.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Ip<wbr>Address<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type of IP addresses used by the subnets for your load balancer. The possible values are `ipv4` and `dualstack`
{{% /md %}}</dd>

    <dt class="property-"
            title="">Load<wbr>Balancer<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The type of load balancer to create. Possible values are `application` or `network`. The default value is `application`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the LB. This name must be unique within your AWS account, can have a maximum of 32 characters,
must contain only alphanumeric characters or hyphens, and must not begin or end with a hyphen. If not specified,
this provider will autogenerate a name beginning with `tf-lb`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Name<wbr>Prefix<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Creates a unique name beginning with the specified prefix. Conflicts with `name`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Security<wbr>Groups<span class="property-indicator"></span>
        <span class="property-type">List<string></span>
    </dt>
    <dd>{{% md %}}A list of security group IDs to assign to the LB. Only valid for Load Balancers of type `application`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Subnet<wbr>Mappings<span class="property-indicator"></span>
        <span class="property-type"><a href="#loadbalancersubnetmapping">List&lt;Load<wbr>Balancer<wbr>Subnet<wbr>Mapping&gt;</a></span>
    </dt>
    <dd>{{% md %}}A subnet mapping block as documented below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Subnets<span class="property-indicator"></span>
        <span class="property-type">List<string></span>
    </dt>
    <dd>{{% md %}}A list of subnet IDs to attach to the LB. Subnets
cannot be updated for Load Balancers of type `network`. Changing this value
for load balancers of type `network` will force a recreation of the resource.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Vpc<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">Zone<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The canonical hosted zone ID of the load balancer (to be used in a Route 53 Alias record).
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
    <dd>{{% md %}}The ARN of the load balancer (matches `id`).
{{% /md %}}</dd>

    <dt class="property-"
            title="">Arn<wbr>Suffix<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN suffix for use with CloudWatch Metrics.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Dns<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The DNS name of the load balancer.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Enable<wbr>Cross<wbr>Zone<wbr>Load<wbr>Balancing<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}If true, cross-zone load balancing of the load balancer will be enabled.
This is a `network` load balancer feature. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Enable<wbr>Deletion<wbr>Protection<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}If true, deletion of the load balancer will be disabled via
the AWS API. This will prevent this provider from deleting the load balancer. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Enable<wbr>Http2<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Indicates whether HTTP/2 is enabled in `application` load balancers. Defaults to `true`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Idle<wbr>Timeout<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The time in seconds that the connection is allowed to be idle. Only valid for Load Balancers of type `application`. Default: 60.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Internal<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}If true, the LB will be internal.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Ip<wbr>Address<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type of IP addresses used by the subnets for your load balancer. The possible values are `ipv4` and `dualstack`
{{% /md %}}</dd>

    <dt class="property-"
            title="">Load<wbr>Balancer<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The type of load balancer to create. Possible values are `application` or `network`. The default value is `application`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the LB. This name must be unique within your AWS account, can have a maximum of 32 characters,
must contain only alphanumeric characters or hyphens, and must not begin or end with a hyphen. If not specified,
this provider will autogenerate a name beginning with `tf-lb`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Name<wbr>Prefix<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Creates a unique name beginning with the specified prefix. Conflicts with `name`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Security<wbr>Groups<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}A list of security group IDs to assign to the LB. Only valid for Load Balancers of type `application`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Subnet<wbr>Mappings<span class="property-indicator"></span>
        <span class="property-type"><a href="#loadbalancersubnetmapping">[]Load<wbr>Balancer<wbr>Subnet<wbr>Mapping</a></span>
    </dt>
    <dd>{{% md %}}A subnet mapping block as documented below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Subnets<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}A list of subnet IDs to attach to the LB. Subnets
cannot be updated for Load Balancers of type `network`. Changing this value
for load balancers of type `network` will force a recreation of the resource.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Vpc<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">Zone<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The canonical hosted zone ID of the load balancer (to be used in a Route 53 Alias record).
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
    <dd>{{% md %}}The ARN of the load balancer (matches `id`).
{{% /md %}}</dd>

    <dt class="property-"
            title="">arn<wbr>Suffix<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN suffix for use with CloudWatch Metrics.
{{% /md %}}</dd>

    <dt class="property-"
            title="">dns<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The DNS name of the load balancer.
{{% /md %}}</dd>

    <dt class="property-"
            title="">enable<wbr>Cross<wbr>Zone<wbr>Load<wbr>Balancing<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}If true, cross-zone load balancing of the load balancer will be enabled.
This is a `network` load balancer feature. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">enable<wbr>Deletion<wbr>Protection<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}If true, deletion of the load balancer will be disabled via
the AWS API. This will prevent this provider from deleting the load balancer. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">enable<wbr>Http2<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Indicates whether HTTP/2 is enabled in `application` load balancers. Defaults to `true`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">idle<wbr>Timeout<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The time in seconds that the connection is allowed to be idle. Only valid for Load Balancers of type `application`. Default: 60.
{{% /md %}}</dd>

    <dt class="property-"
            title="">internal<span class="property-indicator"></span>
        <span class="property-type">boolean</span>
    </dt>
    <dd>{{% md %}}If true, the LB will be internal.
{{% /md %}}</dd>

    <dt class="property-"
            title="">ip<wbr>Address<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type of IP addresses used by the subnets for your load balancer. The possible values are `ipv4` and `dualstack`
{{% /md %}}</dd>

    <dt class="property-"
            title="">load<wbr>Balancer<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The type of load balancer to create. Possible values are `application` or `network`. The default value is `application`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the LB. This name must be unique within your AWS account, can have a maximum of 32 characters,
must contain only alphanumeric characters or hyphens, and must not begin or end with a hyphen. If not specified,
this provider will autogenerate a name beginning with `tf-lb`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">name<wbr>Prefix<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Creates a unique name beginning with the specified prefix. Conflicts with `name`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">security<wbr>Groups<span class="property-indicator"></span>
        <span class="property-type">string[]</span>
    </dt>
    <dd>{{% md %}}A list of security group IDs to assign to the LB. Only valid for Load Balancers of type `application`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">subnet<wbr>Mappings<span class="property-indicator"></span>
        <span class="property-type"><a href="#loadbalancersubnetmapping">Load<wbr>Balancer<wbr>Subnet<wbr>Mapping[]</a></span>
    </dt>
    <dd>{{% md %}}A subnet mapping block as documented below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">subnets<span class="property-indicator"></span>
        <span class="property-type">string[]</span>
    </dt>
    <dd>{{% md %}}A list of subnet IDs to attach to the LB. Subnets
cannot be updated for Load Balancers of type `network`. Changing this value
for load balancers of type `network` will force a recreation of the resource.
{{% /md %}}</dd>

    <dt class="property-"
            title="">tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-"
            title="">vpc<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">zone<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The canonical hosted zone ID of the load balancer (to be used in a Route 53 Alias record).
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
    <dd>{{% md %}}The ARN of the load balancer (matches `id`).
{{% /md %}}</dd>

    <dt class="property-"
            title="">arn_<wbr>suffix<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ARN suffix for use with CloudWatch Metrics.
{{% /md %}}</dd>

    <dt class="property-"
            title="">dns_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The DNS name of the load balancer.
{{% /md %}}</dd>

    <dt class="property-"
            title="">enable_<wbr>cross_<wbr>zone_<wbr>load_<wbr>balancing<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}If true, cross-zone load balancing of the load balancer will be enabled.
This is a `network` load balancer feature. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">enable_<wbr>deletion_<wbr>protection<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}If true, deletion of the load balancer will be disabled via
the AWS API. This will prevent this provider from deleting the load balancer. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">enable_<wbr>http2<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Indicates whether HTTP/2 is enabled in `application` load balancers. Defaults to `true`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">idle_<wbr>timeout<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The time in seconds that the connection is allowed to be idle. Only valid for Load Balancers of type `application`. Default: 60.
{{% /md %}}</dd>

    <dt class="property-"
            title="">internal<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}If true, the LB will be internal.
{{% /md %}}</dd>

    <dt class="property-"
            title="">ip_<wbr>address_<wbr>type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The type of IP addresses used by the subnets for your load balancer. The possible values are `ipv4` and `dualstack`
{{% /md %}}</dd>

    <dt class="property-"
            title="">load_<wbr>balancer_<wbr>type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The type of load balancer to create. Possible values are `application` or `network`. The default value is `application`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the LB. This name must be unique within your AWS account, can have a maximum of 32 characters,
must contain only alphanumeric characters or hyphens, and must not begin or end with a hyphen. If not specified,
this provider will autogenerate a name beginning with `tf-lb`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">name_<wbr>prefix<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Creates a unique name beginning with the specified prefix. Conflicts with `name`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">security_<wbr>groups<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}A list of security group IDs to assign to the LB. Only valid for Load Balancers of type `application`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">subnet_<wbr>mappings<span class="property-indicator"></span>
        <span class="property-type"><a href="#loadbalancersubnetmapping">List[Load<wbr>Balancer<wbr>Subnet<wbr>Mapping]</a></span>
    </dt>
    <dd>{{% md %}}A subnet mapping block as documented below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">subnets<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}A list of subnet IDs to attach to the LB. Subnets
cannot be updated for Load Balancers of type `network`. Changing this value
for load balancers of type `network` will force a recreation of the resource.
{{% /md %}}</dd>

    <dt class="property-"
            title="">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-"
            title="">vpc_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">zone_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The canonical hosted zone ID of the load balancer (to be used in a Route 53 Alias record).
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





## Look up an Existing LoadBalancer Resource

{{< chooser language "javascript,typescript,python,go,csharp  " / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">pulumi.Input&lt;pulumi.ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/elasticloadbalancingv2/#LoadBalancerState">LoadBalancerState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/elasticloadbalancingv2/#LoadBalancer">LoadBalancer</a></span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>access_logs=None<span class="p">, </span>arn=None<span class="p">, </span>arn_suffix=None<span class="p">, </span>dns_name=None<span class="p">, </span>enable_cross_zone_load_balancing=None<span class="p">, </span>enable_deletion_protection=None<span class="p">, </span>enable_http2=None<span class="p">, </span>idle_timeout=None<span class="p">, </span>internal=None<span class="p">, </span>ip_address_type=None<span class="p">, </span>load_balancer_type=None<span class="p">, </span>name=None<span class="p">, </span>name_prefix=None<span class="p">, </span>security_groups=None<span class="p">, </span>subnet_mappings=None<span class="p">, </span>subnets=None<span class="p">, </span>tags=None<span class="p">, </span>vpc_id=None<span class="p">, </span>zone_id=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetLoadBalancer<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">pulumi.IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/elasticloadbalancingv2?tab=doc#LoadBalancerState">LoadBalancerState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/elasticloadbalancingv2?tab=doc#LoadBalancer">LoadBalancer</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Elasticloadbalancingv2.LoadBalancer.html">LoadBalancer</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Pulumi.Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Elasticloadbalancingv2.LoadBalancerState.html">LoadBalancerState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
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
    <dd>{{% md %}}The ARN of the load balancer (matches `id`).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Arn<wbr>Suffix<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ARN suffix for use with CloudWatch Metrics.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Dns<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The DNS name of the load balancer.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Enable<wbr>Cross<wbr>Zone<wbr>Load<wbr>Balancing<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}If true, cross-zone load balancing of the load balancer will be enabled.
This is a `network` load balancer feature. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Enable<wbr>Deletion<wbr>Protection<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}If true, deletion of the load balancer will be disabled via
the AWS API. This will prevent this provider from deleting the load balancer. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Enable<wbr>Http2<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Indicates whether HTTP/2 is enabled in `application` load balancers. Defaults to `true`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Idle<wbr>Timeout<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The time in seconds that the connection is allowed to be idle. Only valid for Load Balancers of type `application`. Default: 60.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Internal<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}If true, the LB will be internal.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ip<wbr>Address<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The type of IP addresses used by the subnets for your load balancer. The possible values are `ipv4` and `dualstack`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Load<wbr>Balancer<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The type of load balancer to create. Possible values are `application` or `network`. The default value is `application`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the LB. This name must be unique within your AWS account, can have a maximum of 32 characters,
must contain only alphanumeric characters or hyphens, and must not begin or end with a hyphen. If not specified,
this provider will autogenerate a name beginning with `tf-lb`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<wbr>Prefix<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Creates a unique name beginning with the specified prefix. Conflicts with `name`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Security<wbr>Groups<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}A list of security group IDs to assign to the LB. Only valid for Load Balancers of type `application`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Subnet<wbr>Mappings<span class="property-indicator"></span>
        <span class="property-type"><a href="#loadbalancersubnetmapping">List&lt;Load<wbr>Balancer<wbr>Subnet<wbr>Mapping<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}A subnet mapping block as documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Subnets<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}A list of subnet IDs to attach to the LB. Subnets
cannot be updated for Load Balancers of type `network`. Changing this value
for load balancers of type `network` will force a recreation of the resource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Vpc<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Zone<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The canonical hosted zone ID of the load balancer (to be used in a Route 53 Alias record).
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
    <dd>{{% md %}}The ARN of the load balancer (matches `id`).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Arn<wbr>Suffix<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The ARN suffix for use with CloudWatch Metrics.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Dns<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The DNS name of the load balancer.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Enable<wbr>Cross<wbr>Zone<wbr>Load<wbr>Balancing<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}If true, cross-zone load balancing of the load balancer will be enabled.
This is a `network` load balancer feature. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Enable<wbr>Deletion<wbr>Protection<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}If true, deletion of the load balancer will be disabled via
the AWS API. This will prevent this provider from deleting the load balancer. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Enable<wbr>Http2<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Indicates whether HTTP/2 is enabled in `application` load balancers. Defaults to `true`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Idle<wbr>Timeout<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The time in seconds that the connection is allowed to be idle. Only valid for Load Balancers of type `application`. Default: 60.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Internal<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}If true, the LB will be internal.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ip<wbr>Address<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The type of IP addresses used by the subnets for your load balancer. The possible values are `ipv4` and `dualstack`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Load<wbr>Balancer<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The type of load balancer to create. Possible values are `application` or `network`. The default value is `application`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name of the LB. This name must be unique within your AWS account, can have a maximum of 32 characters,
must contain only alphanumeric characters or hyphens, and must not begin or end with a hyphen. If not specified,
this provider will autogenerate a name beginning with `tf-lb`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<wbr>Prefix<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Creates a unique name beginning with the specified prefix. Conflicts with `name`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Security<wbr>Groups<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}A list of security group IDs to assign to the LB. Only valid for Load Balancers of type `application`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Subnet<wbr>Mappings<span class="property-indicator"></span>
        <span class="property-type"><a href="#loadbalancersubnetmapping">[]Load<wbr>Balancer<wbr>Subnet<wbr>Mapping</a></span>
    </dt>
    <dd>{{% md %}}A subnet mapping block as documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Subnets<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}A list of subnet IDs to attach to the LB. Subnets
cannot be updated for Load Balancers of type `network`. Changing this value
for load balancers of type `network` will force a recreation of the resource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Vpc<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Zone<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The canonical hosted zone ID of the load balancer (to be used in a Route 53 Alias record).
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
    <dd>{{% md %}}The ARN of the load balancer (matches `id`).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">arn<wbr>Suffix<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ARN suffix for use with CloudWatch Metrics.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">dns<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The DNS name of the load balancer.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">enable<wbr>Cross<wbr>Zone<wbr>Load<wbr>Balancing<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}If true, cross-zone load balancing of the load balancer will be enabled.
This is a `network` load balancer feature. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">enable<wbr>Deletion<wbr>Protection<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}If true, deletion of the load balancer will be disabled via
the AWS API. This will prevent this provider from deleting the load balancer. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">enable<wbr>Http2<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Indicates whether HTTP/2 is enabled in `application` load balancers. Defaults to `true`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">idle<wbr>Timeout<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The time in seconds that the connection is allowed to be idle. Only valid for Load Balancers of type `application`. Default: 60.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">internal<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}If true, the LB will be internal.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ip<wbr>Address<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The type of IP addresses used by the subnets for your load balancer. The possible values are `ipv4` and `dualstack`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">load<wbr>Balancer<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The type of load balancer to create. Possible values are `application` or `network`. The default value is `application`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the LB. This name must be unique within your AWS account, can have a maximum of 32 characters,
must contain only alphanumeric characters or hyphens, and must not begin or end with a hyphen. If not specified,
this provider will autogenerate a name beginning with `tf-lb`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<wbr>Prefix<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Creates a unique name beginning with the specified prefix. Conflicts with `name`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">security<wbr>Groups<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}A list of security group IDs to assign to the LB. Only valid for Load Balancers of type `application`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">subnet<wbr>Mappings<span class="property-indicator"></span>
        <span class="property-type"><a href="#loadbalancersubnetmapping">Load<wbr>Balancer<wbr>Subnet<wbr>Mapping[]?</a></span>
    </dt>
    <dd>{{% md %}}A subnet mapping block as documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">subnets<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}A list of subnet IDs to attach to the LB. Subnets
cannot be updated for Load Balancers of type `network`. Changing this value
for load balancers of type `network` will force a recreation of the resource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">vpc<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">zone<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The canonical hosted zone ID of the load balancer (to be used in a Route 53 Alias record).
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
    <dd>{{% md %}}The ARN of the load balancer (matches `id`).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">arn_<wbr>suffix<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ARN suffix for use with CloudWatch Metrics.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">dns_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The DNS name of the load balancer.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">enable_<wbr>cross_<wbr>zone_<wbr>load_<wbr>balancing<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}If true, cross-zone load balancing of the load balancer will be enabled.
This is a `network` load balancer feature. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">enable_<wbr>deletion_<wbr>protection<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}If true, deletion of the load balancer will be disabled via
the AWS API. This will prevent this provider from deleting the load balancer. Defaults to `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">enable_<wbr>http2<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Indicates whether HTTP/2 is enabled in `application` load balancers. Defaults to `true`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">idle_<wbr>timeout<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The time in seconds that the connection is allowed to be idle. Only valid for Load Balancers of type `application`. Default: 60.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">internal<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}If true, the LB will be internal.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ip_<wbr>address_<wbr>type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The type of IP addresses used by the subnets for your load balancer. The possible values are `ipv4` and `dualstack`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">load_<wbr>balancer_<wbr>type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The type of load balancer to create. Possible values are `application` or `network`. The default value is `application`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the LB. This name must be unique within your AWS account, can have a maximum of 32 characters,
must contain only alphanumeric characters or hyphens, and must not begin or end with a hyphen. If not specified,
this provider will autogenerate a name beginning with `tf-lb`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name_<wbr>prefix<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Creates a unique name beginning with the specified prefix. Conflicts with `name`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">security_<wbr>groups<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}A list of security group IDs to assign to the LB. Only valid for Load Balancers of type `application`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">subnet_<wbr>mappings<span class="property-indicator"></span>
        <span class="property-type"><a href="#loadbalancersubnetmapping">List[Load<wbr>Balancer<wbr>Subnet<wbr>Mapping]</a></span>
    </dt>
    <dd>{{% md %}}A subnet mapping block as documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">subnets<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}A list of subnet IDs to attach to the LB. Subnets
cannot be updated for Load Balancers of type `network`. Changing this value
for load balancers of type `network` will force a recreation of the resource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">vpc_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">zone_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The canonical hosted zone ID of the load balancer (to be used in a Route 53 Alias record).
{{% /md %}}</dd>

</dl>
{{% /choosable %}}







## Supporting Types

#### LoadBalancerAccessLogs
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#LoadBalancerAccessLogs">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#LoadBalancerAccessLogs">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/elasticloadbalancingv2?tab=doc#LoadBalancerAccessLogsArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/elasticloadbalancingv2?tab=doc#LoadBalancerAccessLogsOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Elasticloadbalancingv2.LoadBalancerAccessLogsArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Elasticloadbalancingv2.LoadBalancerAccessLogs.html">output</a> API doc for this type.
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
            title="Optional">Enabled<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Boolean to enable / disable `access_logs`. Defaults to `false`, even when `bucket` is specified.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Prefix<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The S3 bucket prefix. Logs are stored in the root if not configured.
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
            title="Optional">Enabled<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Boolean to enable / disable `access_logs`. Defaults to `false`, even when `bucket` is specified.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Prefix<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The S3 bucket prefix. Logs are stored in the root if not configured.
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
            title="Optional">enabled<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Boolean to enable / disable `access_logs`. Defaults to `false`, even when `bucket` is specified.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">prefix<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The S3 bucket prefix. Logs are stored in the root if not configured.
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
            title="Optional">enabled<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Boolean to enable / disable `access_logs`. Defaults to `false`, even when `bucket` is specified.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">prefix<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The S3 bucket prefix. Logs are stored in the root if not configured.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### LoadBalancerSubnetMapping
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#LoadBalancerSubnetMapping">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#LoadBalancerSubnetMapping">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/elasticloadbalancingv2?tab=doc#LoadBalancerSubnetMappingArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/elasticloadbalancingv2?tab=doc#LoadBalancerSubnetMappingOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Elasticloadbalancingv2.LoadBalancerSubnetMappingArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Elasticloadbalancingv2.LoadBalancerSubnetMapping.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Allocation<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The allocation ID of the Elastic IP address.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Subnet<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The id of the subnet of which to attach to the load balancer. You can specify only one subnet per Availability Zone.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Allocation<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The allocation ID of the Elastic IP address.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Subnet<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The id of the subnet of which to attach to the load balancer. You can specify only one subnet per Availability Zone.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">allocation<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The allocation ID of the Elastic IP address.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">subnet<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The id of the subnet of which to attach to the load balancer. You can specify only one subnet per Availability Zone.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">allocation_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The allocation ID of the Elastic IP address.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">subnet_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The id of the subnet of which to attach to the load balancer. You can specify only one subnet per Availability Zone.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}








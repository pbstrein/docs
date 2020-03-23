
---
title: "TargetGroup"
block_external_search_index: true
---

Provides a Target Group resource for use with Load Balancer resources.

> **Note:** `aws.alb.TargetGroup` is known as `aws.lb.TargetGroup`. The functionality is identical.

## Example Usage

### Instance Target Group

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const main = new aws.ec2.Vpc("main", {
    cidrBlock: "10.0.0.0/16",
});
const test = new aws.lb.TargetGroup("test", {
    port: 80,
    protocol: "HTTP",
    vpcId: main.id,
});
```

### IP Target Group

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const main = new aws.ec2.Vpc("main", {
    cidrBlock: "10.0.0.0/16",
});
const ip_example = new aws.lb.TargetGroup("ip-example", {
    port: 80,
    protocol: "HTTP",
    targetType: "ip",
    vpcId: main.id,
});
```

### Lambda Target Group

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const lambda_example = new aws.lb.TargetGroup("lambda-example", {
    targetType: "lambda",
});
```

> This content is derived from https://github.com/terraform-providers/terraform-provider-aws/blob/master/website/docs/r/lb_target_group.html.markdown.



## Create a TargetGroup Resource

{{< chooser language "javascript,typescript,python,go,csharp" / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/applicationloadbalancing/#TargetGroup">TargetGroup</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/applicationloadbalancing/#TargetGroupArgs">TargetGroupArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">TargetGroup</span><span class="p">(resource_name, opts=None, </span>deregistration_delay=None<span class="p">, </span>health_check=None<span class="p">, </span>lambda_multi_value_headers_enabled=None<span class="p">, </span>load_balancing_algorithm_type=None<span class="p">, </span>name=None<span class="p">, </span>name_prefix=None<span class="p">, </span>port=None<span class="p">, </span>protocol=None<span class="p">, </span>proxy_protocol_v2=None<span class="p">, </span>slow_start=None<span class="p">, </span>stickiness=None<span class="p">, </span>tags=None<span class="p">, </span>target_type=None<span class="p">, </span>vpc_id=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewTargetGroup<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/applicationloadbalancing?tab=doc#TargetGroupArgs">TargetGroupArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/applicationloadbalancing?tab=doc#TargetGroup">TargetGroup</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Applicationloadbalancing.TargetGroup.html">TargetGroup</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Applicationloadbalancing.TargetGroupArgs.html">TargetGroupArgs</a></span>? <span class="nx">args = null<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
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
            title="Optional">Deregistration<wbr>Delay<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The amount time for Elastic Load Balancing to wait before changing the state of a deregistering target from draining to unused. The range is 0-3600 seconds. The default value is 300 seconds.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Health<wbr>Check<span class="property-indicator"></span>
        <span class="property-type"><a href="#targetgrouphealthcheck">Target<wbr>Group<wbr>Health<wbr>Check<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}A Health Check block. Health Check blocks are documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Lambda<wbr>Multi<wbr>Value<wbr>Headers<wbr>Enabled<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Boolean whether the request and response headers exchanged between the load balancer and the Lambda function include arrays of values or strings. Only applies when `target_type` is `lambda`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Load<wbr>Balancing<wbr>Algorithm<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Determines how the load balancer selects targets when routing requests. Only applicable for Application Load Balancer Target Groups. The value is `round_robin` or `least_outstanding_requests`. The default is `round_robin`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the target group. If omitted, this provider will assign a random, unique name.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<wbr>Prefix<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Creates a unique name beginning with the specified prefix. Conflicts with `name`. Cannot be longer than 6 characters.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Port<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The port to use to connect with the target. Valid values are either ports 1-65535, or `traffic-port`. Defaults to `traffic-port`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Protocol<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The protocol to use to connect with the target. Defaults to `HTTP`. Not applicable when `target_type` is `lambda`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Proxy<wbr>Protocol<wbr>V2<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Boolean to enable / disable support for proxy protocol v2 on Network Load Balancers. See [doc](https://docs.aws.amazon.com/elasticloadbalancing/latest/network/load-balancer-target-groups.html#proxy-protocol) for more information.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Slow<wbr>Start<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The amount time for targets to warm up before the load balancer sends them a full share of requests. The range is 30-900 seconds or 0 to disable. The default value is 0 seconds.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Stickiness<span class="property-indicator"></span>
        <span class="property-type"><a href="#targetgroupstickiness">Target<wbr>Group<wbr>Stickiness<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}A Stickiness block. Stickiness blocks are documented below. `stickiness` is only valid if used with Load Balancers of type `Application`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Target<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The type of target that you must specify when registering targets with this target group.
The possible values are `instance` (targets are specified by instance ID) or `ip` (targets are specified by IP address) or `lambda` (targets are specified by lambda arn).
The default is `instance`. Note that you can&#39;t specify targets for a target group using both instance IDs and IP addresses.
If the target type is `ip`, specify IP addresses from the subnets of the virtual private cloud (VPC) for the target group,
the RFC 1918 range (10.0.0.0/8, 172.16.0.0/12, and 192.168.0.0/16), and the RFC 6598 range (100.64.0.0/10).
You can&#39;t specify publicly routable IP addresses.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Vpc<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The identifier of the VPC in which to create the target group. Required when `target_type` is `instance` or `ip`. Does not apply when `target_type` is `lambda`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Deregistration<wbr>Delay<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The amount time for Elastic Load Balancing to wait before changing the state of a deregistering target from draining to unused. The range is 0-3600 seconds. The default value is 300 seconds.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Health<wbr>Check<span class="property-indicator"></span>
        <span class="property-type"><a href="#targetgrouphealthcheck">*Target<wbr>Group<wbr>Health<wbr>Check</a></span>
    </dt>
    <dd>{{% md %}}A Health Check block. Health Check blocks are documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Lambda<wbr>Multi<wbr>Value<wbr>Headers<wbr>Enabled<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Boolean whether the request and response headers exchanged between the load balancer and the Lambda function include arrays of values or strings. Only applies when `target_type` is `lambda`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Load<wbr>Balancing<wbr>Algorithm<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Determines how the load balancer selects targets when routing requests. Only applicable for Application Load Balancer Target Groups. The value is `round_robin` or `least_outstanding_requests`. The default is `round_robin`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name of the target group. If omitted, this provider will assign a random, unique name.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<wbr>Prefix<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Creates a unique name beginning with the specified prefix. Conflicts with `name`. Cannot be longer than 6 characters.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Port<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The port to use to connect with the target. Valid values are either ports 1-65535, or `traffic-port`. Defaults to `traffic-port`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Protocol<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The protocol to use to connect with the target. Defaults to `HTTP`. Not applicable when `target_type` is `lambda`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Proxy<wbr>Protocol<wbr>V2<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Boolean to enable / disable support for proxy protocol v2 on Network Load Balancers. See [doc](https://docs.aws.amazon.com/elasticloadbalancing/latest/network/load-balancer-target-groups.html#proxy-protocol) for more information.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Slow<wbr>Start<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The amount time for targets to warm up before the load balancer sends them a full share of requests. The range is 30-900 seconds or 0 to disable. The default value is 0 seconds.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Stickiness<span class="property-indicator"></span>
        <span class="property-type"><a href="#targetgroupstickiness">*Target<wbr>Group<wbr>Stickiness</a></span>
    </dt>
    <dd>{{% md %}}A Stickiness block. Stickiness blocks are documented below. `stickiness` is only valid if used with Load Balancers of type `Application`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Target<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The type of target that you must specify when registering targets with this target group.
The possible values are `instance` (targets are specified by instance ID) or `ip` (targets are specified by IP address) or `lambda` (targets are specified by lambda arn).
The default is `instance`. Note that you can&#39;t specify targets for a target group using both instance IDs and IP addresses.
If the target type is `ip`, specify IP addresses from the subnets of the virtual private cloud (VPC) for the target group,
the RFC 1918 range (10.0.0.0/8, 172.16.0.0/12, and 192.168.0.0/16), and the RFC 6598 range (100.64.0.0/10).
You can&#39;t specify publicly routable IP addresses.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Vpc<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The identifier of the VPC in which to create the target group. Required when `target_type` is `instance` or `ip`. Does not apply when `target_type` is `lambda`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">deregistration<wbr>Delay<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The amount time for Elastic Load Balancing to wait before changing the state of a deregistering target from draining to unused. The range is 0-3600 seconds. The default value is 300 seconds.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">health<wbr>Check<span class="property-indicator"></span>
        <span class="property-type"><a href="#targetgrouphealthcheck">Target<wbr>Group<wbr>Health<wbr>Check?</a></span>
    </dt>
    <dd>{{% md %}}A Health Check block. Health Check blocks are documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">lambda<wbr>Multi<wbr>Value<wbr>Headers<wbr>Enabled<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Boolean whether the request and response headers exchanged between the load balancer and the Lambda function include arrays of values or strings. Only applies when `target_type` is `lambda`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">load<wbr>Balancing<wbr>Algorithm<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Determines how the load balancer selects targets when routing requests. Only applicable for Application Load Balancer Target Groups. The value is `round_robin` or `least_outstanding_requests`. The default is `round_robin`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the target group. If omitted, this provider will assign a random, unique name.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<wbr>Prefix<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Creates a unique name beginning with the specified prefix. Conflicts with `name`. Cannot be longer than 6 characters.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">port<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The port to use to connect with the target. Valid values are either ports 1-65535, or `traffic-port`. Defaults to `traffic-port`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">protocol<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The protocol to use to connect with the target. Defaults to `HTTP`. Not applicable when `target_type` is `lambda`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">proxy<wbr>Protocol<wbr>V2<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Boolean to enable / disable support for proxy protocol v2 on Network Load Balancers. See [doc](https://docs.aws.amazon.com/elasticloadbalancing/latest/network/load-balancer-target-groups.html#proxy-protocol) for more information.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">slow<wbr>Start<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The amount time for targets to warm up before the load balancer sends them a full share of requests. The range is 30-900 seconds or 0 to disable. The default value is 0 seconds.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">stickiness<span class="property-indicator"></span>
        <span class="property-type"><a href="#targetgroupstickiness">Target<wbr>Group<wbr>Stickiness?</a></span>
    </dt>
    <dd>{{% md %}}A Stickiness block. Stickiness blocks are documented below. `stickiness` is only valid if used with Load Balancers of type `Application`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">target<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The type of target that you must specify when registering targets with this target group.
The possible values are `instance` (targets are specified by instance ID) or `ip` (targets are specified by IP address) or `lambda` (targets are specified by lambda arn).
The default is `instance`. Note that you can&#39;t specify targets for a target group using both instance IDs and IP addresses.
If the target type is `ip`, specify IP addresses from the subnets of the virtual private cloud (VPC) for the target group,
the RFC 1918 range (10.0.0.0/8, 172.16.0.0/12, and 192.168.0.0/16), and the RFC 6598 range (100.64.0.0/10).
You can&#39;t specify publicly routable IP addresses.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">vpc<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The identifier of the VPC in which to create the target group. Required when `target_type` is `instance` or `ip`. Does not apply when `target_type` is `lambda`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">deregistration_<wbr>delay<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The amount time for Elastic Load Balancing to wait before changing the state of a deregistering target from draining to unused. The range is 0-3600 seconds. The default value is 300 seconds.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">health_<wbr>check<span class="property-indicator"></span>
        <span class="property-type"><a href="#targetgrouphealthcheck">Dict[Target<wbr>Group<wbr>Health<wbr>Check]</a></span>
    </dt>
    <dd>{{% md %}}A Health Check block. Health Check blocks are documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">lambda_<wbr>multi_<wbr>value_<wbr>headers_<wbr>enabled<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Boolean whether the request and response headers exchanged between the load balancer and the Lambda function include arrays of values or strings. Only applies when `target_type` is `lambda`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">load_<wbr>balancing_<wbr>algorithm_<wbr>type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Determines how the load balancer selects targets when routing requests. Only applicable for Application Load Balancer Target Groups. The value is `round_robin` or `least_outstanding_requests`. The default is `round_robin`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the target group. If omitted, this provider will assign a random, unique name.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name_<wbr>prefix<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Creates a unique name beginning with the specified prefix. Conflicts with `name`. Cannot be longer than 6 characters.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">port<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The port to use to connect with the target. Valid values are either ports 1-65535, or `traffic-port`. Defaults to `traffic-port`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">protocol<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The protocol to use to connect with the target. Defaults to `HTTP`. Not applicable when `target_type` is `lambda`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">proxy_<wbr>protocol_<wbr>v2<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Boolean to enable / disable support for proxy protocol v2 on Network Load Balancers. See [doc](https://docs.aws.amazon.com/elasticloadbalancing/latest/network/load-balancer-target-groups.html#proxy-protocol) for more information.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">slow_<wbr>start<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The amount time for targets to warm up before the load balancer sends them a full share of requests. The range is 30-900 seconds or 0 to disable. The default value is 0 seconds.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">stickiness<span class="property-indicator"></span>
        <span class="property-type"><a href="#targetgroupstickiness">Dict[Target<wbr>Group<wbr>Stickiness]</a></span>
    </dt>
    <dd>{{% md %}}A Stickiness block. Stickiness blocks are documented below. `stickiness` is only valid if used with Load Balancers of type `Application`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">target_<wbr>type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The type of target that you must specify when registering targets with this target group.
The possible values are `instance` (targets are specified by instance ID) or `ip` (targets are specified by IP address) or `lambda` (targets are specified by lambda arn).
The default is `instance`. Note that you can&#39;t specify targets for a target group using both instance IDs and IP addresses.
If the target type is `ip`, specify IP addresses from the subnets of the virtual private cloud (VPC) for the target group,
the RFC 1918 range (10.0.0.0/8, 172.16.0.0/12, and 192.168.0.0/16), and the RFC 6598 range (100.64.0.0/10).
You can&#39;t specify publicly routable IP addresses.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">vpc_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The identifier of the VPC in which to create the target group. Required when `target_type` is `instance` or `ip`. Does not apply when `target_type` is `lambda`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}




## TargetGroup Output Properties

The following output properties are available:




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of the Target Group (matches `id`)
{{% /md %}}</dd>

    <dt class="property-"
            title="">Arn<wbr>Suffix<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN suffix for use with CloudWatch Metrics.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Deregistration<wbr>Delay<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The amount time for Elastic Load Balancing to wait before changing the state of a deregistering target from draining to unused. The range is 0-3600 seconds. The default value is 300 seconds.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Health<wbr>Check<span class="property-indicator"></span>
        <span class="property-type"><a href="#targetgrouphealthcheck">Target<wbr>Group<wbr>Health<wbr>Check</a></span>
    </dt>
    <dd>{{% md %}}A Health Check block. Health Check blocks are documented below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Lambda<wbr>Multi<wbr>Value<wbr>Headers<wbr>Enabled<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Boolean whether the request and response headers exchanged between the load balancer and the Lambda function include arrays of values or strings. Only applies when `target_type` is `lambda`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Load<wbr>Balancing<wbr>Algorithm<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Determines how the load balancer selects targets when routing requests. Only applicable for Application Load Balancer Target Groups. The value is `round_robin` or `least_outstanding_requests`. The default is `round_robin`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the target group. If omitted, this provider will assign a random, unique name.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Name<wbr>Prefix<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Creates a unique name beginning with the specified prefix. Conflicts with `name`. Cannot be longer than 6 characters.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Port<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The port to use to connect with the target. Valid values are either ports 1-65535, or `traffic-port`. Defaults to `traffic-port`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Protocol<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The protocol to use to connect with the target. Defaults to `HTTP`. Not applicable when `target_type` is `lambda`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Proxy<wbr>Protocol<wbr>V2<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Boolean to enable / disable support for proxy protocol v2 on Network Load Balancers. See [doc](https://docs.aws.amazon.com/elasticloadbalancing/latest/network/load-balancer-target-groups.html#proxy-protocol) for more information.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Slow<wbr>Start<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The amount time for targets to warm up before the load balancer sends them a full share of requests. The range is 30-900 seconds or 0 to disable. The default value is 0 seconds.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Stickiness<span class="property-indicator"></span>
        <span class="property-type"><a href="#targetgroupstickiness">Target<wbr>Group<wbr>Stickiness</a></span>
    </dt>
    <dd>{{% md %}}A Stickiness block. Stickiness blocks are documented below. `stickiness` is only valid if used with Load Balancers of type `Application`
{{% /md %}}</dd>

    <dt class="property-"
            title="">Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Target<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The type of target that you must specify when registering targets with this target group.
The possible values are `instance` (targets are specified by instance ID) or `ip` (targets are specified by IP address) or `lambda` (targets are specified by lambda arn).
The default is `instance`. Note that you can&#39;t specify targets for a target group using both instance IDs and IP addresses.
If the target type is `ip`, specify IP addresses from the subnets of the virtual private cloud (VPC) for the target group,
the RFC 1918 range (10.0.0.0/8, 172.16.0.0/12, and 192.168.0.0/16), and the RFC 6598 range (100.64.0.0/10).
You can&#39;t specify publicly routable IP addresses.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Vpc<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The identifier of the VPC in which to create the target group. Required when `target_type` is `instance` or `ip`. Does not apply when `target_type` is `lambda`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of the Target Group (matches `id`)
{{% /md %}}</dd>

    <dt class="property-"
            title="">Arn<wbr>Suffix<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN suffix for use with CloudWatch Metrics.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Deregistration<wbr>Delay<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The amount time for Elastic Load Balancing to wait before changing the state of a deregistering target from draining to unused. The range is 0-3600 seconds. The default value is 300 seconds.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Health<wbr>Check<span class="property-indicator"></span>
        <span class="property-type"><a href="#targetgrouphealthcheck">Target<wbr>Group<wbr>Health<wbr>Check</a></span>
    </dt>
    <dd>{{% md %}}A Health Check block. Health Check blocks are documented below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Lambda<wbr>Multi<wbr>Value<wbr>Headers<wbr>Enabled<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Boolean whether the request and response headers exchanged between the load balancer and the Lambda function include arrays of values or strings. Only applies when `target_type` is `lambda`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Load<wbr>Balancing<wbr>Algorithm<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Determines how the load balancer selects targets when routing requests. Only applicable for Application Load Balancer Target Groups. The value is `round_robin` or `least_outstanding_requests`. The default is `round_robin`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the target group. If omitted, this provider will assign a random, unique name.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Name<wbr>Prefix<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Creates a unique name beginning with the specified prefix. Conflicts with `name`. Cannot be longer than 6 characters.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Port<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The port to use to connect with the target. Valid values are either ports 1-65535, or `traffic-port`. Defaults to `traffic-port`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Protocol<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The protocol to use to connect with the target. Defaults to `HTTP`. Not applicable when `target_type` is `lambda`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Proxy<wbr>Protocol<wbr>V2<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Boolean to enable / disable support for proxy protocol v2 on Network Load Balancers. See [doc](https://docs.aws.amazon.com/elasticloadbalancing/latest/network/load-balancer-target-groups.html#proxy-protocol) for more information.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Slow<wbr>Start<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The amount time for targets to warm up before the load balancer sends them a full share of requests. The range is 30-900 seconds or 0 to disable. The default value is 0 seconds.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Stickiness<span class="property-indicator"></span>
        <span class="property-type"><a href="#targetgroupstickiness">Target<wbr>Group<wbr>Stickiness</a></span>
    </dt>
    <dd>{{% md %}}A Stickiness block. Stickiness blocks are documented below. `stickiness` is only valid if used with Load Balancers of type `Application`
{{% /md %}}</dd>

    <dt class="property-"
            title="">Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Target<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The type of target that you must specify when registering targets with this target group.
The possible values are `instance` (targets are specified by instance ID) or `ip` (targets are specified by IP address) or `lambda` (targets are specified by lambda arn).
The default is `instance`. Note that you can&#39;t specify targets for a target group using both instance IDs and IP addresses.
If the target type is `ip`, specify IP addresses from the subnets of the virtual private cloud (VPC) for the target group,
the RFC 1918 range (10.0.0.0/8, 172.16.0.0/12, and 192.168.0.0/16), and the RFC 6598 range (100.64.0.0/10).
You can&#39;t specify publicly routable IP addresses.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Vpc<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The identifier of the VPC in which to create the target group. Required when `target_type` is `instance` or `ip`. Does not apply when `target_type` is `lambda`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of the Target Group (matches `id`)
{{% /md %}}</dd>

    <dt class="property-"
            title="">arn<wbr>Suffix<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN suffix for use with CloudWatch Metrics.
{{% /md %}}</dd>

    <dt class="property-"
            title="">deregistration<wbr>Delay<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The amount time for Elastic Load Balancing to wait before changing the state of a deregistering target from draining to unused. The range is 0-3600 seconds. The default value is 300 seconds.
{{% /md %}}</dd>

    <dt class="property-"
            title="">health<wbr>Check<span class="property-indicator"></span>
        <span class="property-type"><a href="#targetgrouphealthcheck">Target<wbr>Group<wbr>Health<wbr>Check</a></span>
    </dt>
    <dd>{{% md %}}A Health Check block. Health Check blocks are documented below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">lambda<wbr>Multi<wbr>Value<wbr>Headers<wbr>Enabled<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Boolean whether the request and response headers exchanged between the load balancer and the Lambda function include arrays of values or strings. Only applies when `target_type` is `lambda`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">load<wbr>Balancing<wbr>Algorithm<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Determines how the load balancer selects targets when routing requests. Only applicable for Application Load Balancer Target Groups. The value is `round_robin` or `least_outstanding_requests`. The default is `round_robin`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the target group. If omitted, this provider will assign a random, unique name.
{{% /md %}}</dd>

    <dt class="property-"
            title="">name<wbr>Prefix<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Creates a unique name beginning with the specified prefix. Conflicts with `name`. Cannot be longer than 6 characters.
{{% /md %}}</dd>

    <dt class="property-"
            title="">port<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The port to use to connect with the target. Valid values are either ports 1-65535, or `traffic-port`. Defaults to `traffic-port`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">protocol<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The protocol to use to connect with the target. Defaults to `HTTP`. Not applicable when `target_type` is `lambda`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">proxy<wbr>Protocol<wbr>V2<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Boolean to enable / disable support for proxy protocol v2 on Network Load Balancers. See [doc](https://docs.aws.amazon.com/elasticloadbalancing/latest/network/load-balancer-target-groups.html#proxy-protocol) for more information.
{{% /md %}}</dd>

    <dt class="property-"
            title="">slow<wbr>Start<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The amount time for targets to warm up before the load balancer sends them a full share of requests. The range is 30-900 seconds or 0 to disable. The default value is 0 seconds.
{{% /md %}}</dd>

    <dt class="property-"
            title="">stickiness<span class="property-indicator"></span>
        <span class="property-type"><a href="#targetgroupstickiness">Target<wbr>Group<wbr>Stickiness</a></span>
    </dt>
    <dd>{{% md %}}A Stickiness block. Stickiness blocks are documented below. `stickiness` is only valid if used with Load Balancers of type `Application`
{{% /md %}}</dd>

    <dt class="property-"
            title="">tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-"
            title="">target<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The type of target that you must specify when registering targets with this target group.
The possible values are `instance` (targets are specified by instance ID) or `ip` (targets are specified by IP address) or `lambda` (targets are specified by lambda arn).
The default is `instance`. Note that you can&#39;t specify targets for a target group using both instance IDs and IP addresses.
If the target type is `ip`, specify IP addresses from the subnets of the virtual private cloud (VPC) for the target group,
the RFC 1918 range (10.0.0.0/8, 172.16.0.0/12, and 192.168.0.0/16), and the RFC 6598 range (100.64.0.0/10).
You can&#39;t specify publicly routable IP addresses.
{{% /md %}}</dd>

    <dt class="property-"
            title="">vpc<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The identifier of the VPC in which to create the target group. Required when `target_type` is `instance` or `ip`. Does not apply when `target_type` is `lambda`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ARN of the Target Group (matches `id`)
{{% /md %}}</dd>

    <dt class="property-"
            title="">arn_<wbr>suffix<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ARN suffix for use with CloudWatch Metrics.
{{% /md %}}</dd>

    <dt class="property-"
            title="">deregistration_<wbr>delay<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The amount time for Elastic Load Balancing to wait before changing the state of a deregistering target from draining to unused. The range is 0-3600 seconds. The default value is 300 seconds.
{{% /md %}}</dd>

    <dt class="property-"
            title="">health_<wbr>check<span class="property-indicator"></span>
        <span class="property-type"><a href="#targetgrouphealthcheck">Dict[Target<wbr>Group<wbr>Health<wbr>Check]</a></span>
    </dt>
    <dd>{{% md %}}A Health Check block. Health Check blocks are documented below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">lambda_<wbr>multi_<wbr>value_<wbr>headers_<wbr>enabled<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Boolean whether the request and response headers exchanged between the load balancer and the Lambda function include arrays of values or strings. Only applies when `target_type` is `lambda`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">load_<wbr>balancing_<wbr>algorithm_<wbr>type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Determines how the load balancer selects targets when routing requests. Only applicable for Application Load Balancer Target Groups. The value is `round_robin` or `least_outstanding_requests`. The default is `round_robin`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the target group. If omitted, this provider will assign a random, unique name.
{{% /md %}}</dd>

    <dt class="property-"
            title="">name_<wbr>prefix<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Creates a unique name beginning with the specified prefix. Conflicts with `name`. Cannot be longer than 6 characters.
{{% /md %}}</dd>

    <dt class="property-"
            title="">port<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The port to use to connect with the target. Valid values are either ports 1-65535, or `traffic-port`. Defaults to `traffic-port`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">protocol<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The protocol to use to connect with the target. Defaults to `HTTP`. Not applicable when `target_type` is `lambda`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">proxy_<wbr>protocol_<wbr>v2<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Boolean to enable / disable support for proxy protocol v2 on Network Load Balancers. See [doc](https://docs.aws.amazon.com/elasticloadbalancing/latest/network/load-balancer-target-groups.html#proxy-protocol) for more information.
{{% /md %}}</dd>

    <dt class="property-"
            title="">slow_<wbr>start<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The amount time for targets to warm up before the load balancer sends them a full share of requests. The range is 30-900 seconds or 0 to disable. The default value is 0 seconds.
{{% /md %}}</dd>

    <dt class="property-"
            title="">stickiness<span class="property-indicator"></span>
        <span class="property-type"><a href="#targetgroupstickiness">Dict[Target<wbr>Group<wbr>Stickiness]</a></span>
    </dt>
    <dd>{{% md %}}A Stickiness block. Stickiness blocks are documented below. `stickiness` is only valid if used with Load Balancers of type `Application`
{{% /md %}}</dd>

    <dt class="property-"
            title="">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-"
            title="">target_<wbr>type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The type of target that you must specify when registering targets with this target group.
The possible values are `instance` (targets are specified by instance ID) or `ip` (targets are specified by IP address) or `lambda` (targets are specified by lambda arn).
The default is `instance`. Note that you can&#39;t specify targets for a target group using both instance IDs and IP addresses.
If the target type is `ip`, specify IP addresses from the subnets of the virtual private cloud (VPC) for the target group,
the RFC 1918 range (10.0.0.0/8, 172.16.0.0/12, and 192.168.0.0/16), and the RFC 6598 range (100.64.0.0/10).
You can&#39;t specify publicly routable IP addresses.
{{% /md %}}</dd>

    <dt class="property-"
            title="">vpc_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The identifier of the VPC in which to create the target group. Required when `target_type` is `instance` or `ip`. Does not apply when `target_type` is `lambda`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





## Look up an Existing TargetGroup Resource

{{< chooser language "javascript,typescript,python,go,csharp  " / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">pulumi.Input&lt;pulumi.ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/applicationloadbalancing/#TargetGroupState">TargetGroupState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/applicationloadbalancing/#TargetGroup">TargetGroup</a></span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>arn=None<span class="p">, </span>arn_suffix=None<span class="p">, </span>deregistration_delay=None<span class="p">, </span>health_check=None<span class="p">, </span>lambda_multi_value_headers_enabled=None<span class="p">, </span>load_balancing_algorithm_type=None<span class="p">, </span>name=None<span class="p">, </span>name_prefix=None<span class="p">, </span>port=None<span class="p">, </span>protocol=None<span class="p">, </span>proxy_protocol_v2=None<span class="p">, </span>slow_start=None<span class="p">, </span>stickiness=None<span class="p">, </span>tags=None<span class="p">, </span>target_type=None<span class="p">, </span>vpc_id=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetTargetGroup<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">pulumi.IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/applicationloadbalancing?tab=doc#TargetGroupState">TargetGroupState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/applicationloadbalancing?tab=doc#TargetGroup">TargetGroup</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Applicationloadbalancing.TargetGroup.html">TargetGroup</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Pulumi.Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Applicationloadbalancing.TargetGroupState.html">TargetGroupState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
{{% /choosable %}}

Get an existing TargetGroup resource's state with the given name, ID, and optional extra properties used to qualify the lookup.

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
    <dd>{{% md %}}The ARN of the Target Group (matches `id`)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Arn<wbr>Suffix<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ARN suffix for use with CloudWatch Metrics.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Deregistration<wbr>Delay<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The amount time for Elastic Load Balancing to wait before changing the state of a deregistering target from draining to unused. The range is 0-3600 seconds. The default value is 300 seconds.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Health<wbr>Check<span class="property-indicator"></span>
        <span class="property-type"><a href="#targetgrouphealthcheck">Target<wbr>Group<wbr>Health<wbr>Check<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}A Health Check block. Health Check blocks are documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Lambda<wbr>Multi<wbr>Value<wbr>Headers<wbr>Enabled<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Boolean whether the request and response headers exchanged between the load balancer and the Lambda function include arrays of values or strings. Only applies when `target_type` is `lambda`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Load<wbr>Balancing<wbr>Algorithm<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Determines how the load balancer selects targets when routing requests. Only applicable for Application Load Balancer Target Groups. The value is `round_robin` or `least_outstanding_requests`. The default is `round_robin`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the target group. If omitted, this provider will assign a random, unique name.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<wbr>Prefix<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Creates a unique name beginning with the specified prefix. Conflicts with `name`. Cannot be longer than 6 characters.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Port<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The port to use to connect with the target. Valid values are either ports 1-65535, or `traffic-port`. Defaults to `traffic-port`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Protocol<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The protocol to use to connect with the target. Defaults to `HTTP`. Not applicable when `target_type` is `lambda`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Proxy<wbr>Protocol<wbr>V2<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Boolean to enable / disable support for proxy protocol v2 on Network Load Balancers. See [doc](https://docs.aws.amazon.com/elasticloadbalancing/latest/network/load-balancer-target-groups.html#proxy-protocol) for more information.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Slow<wbr>Start<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The amount time for targets to warm up before the load balancer sends them a full share of requests. The range is 30-900 seconds or 0 to disable. The default value is 0 seconds.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Stickiness<span class="property-indicator"></span>
        <span class="property-type"><a href="#targetgroupstickiness">Target<wbr>Group<wbr>Stickiness<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}A Stickiness block. Stickiness blocks are documented below. `stickiness` is only valid if used with Load Balancers of type `Application`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Target<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The type of target that you must specify when registering targets with this target group.
The possible values are `instance` (targets are specified by instance ID) or `ip` (targets are specified by IP address) or `lambda` (targets are specified by lambda arn).
The default is `instance`. Note that you can&#39;t specify targets for a target group using both instance IDs and IP addresses.
If the target type is `ip`, specify IP addresses from the subnets of the virtual private cloud (VPC) for the target group,
the RFC 1918 range (10.0.0.0/8, 172.16.0.0/12, and 192.168.0.0/16), and the RFC 6598 range (100.64.0.0/10).
You can&#39;t specify publicly routable IP addresses.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Vpc<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The identifier of the VPC in which to create the target group. Required when `target_type` is `instance` or `ip`. Does not apply when `target_type` is `lambda`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The ARN of the Target Group (matches `id`)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Arn<wbr>Suffix<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The ARN suffix for use with CloudWatch Metrics.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Deregistration<wbr>Delay<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The amount time for Elastic Load Balancing to wait before changing the state of a deregistering target from draining to unused. The range is 0-3600 seconds. The default value is 300 seconds.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Health<wbr>Check<span class="property-indicator"></span>
        <span class="property-type"><a href="#targetgrouphealthcheck">*Target<wbr>Group<wbr>Health<wbr>Check</a></span>
    </dt>
    <dd>{{% md %}}A Health Check block. Health Check blocks are documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Lambda<wbr>Multi<wbr>Value<wbr>Headers<wbr>Enabled<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Boolean whether the request and response headers exchanged between the load balancer and the Lambda function include arrays of values or strings. Only applies when `target_type` is `lambda`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Load<wbr>Balancing<wbr>Algorithm<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Determines how the load balancer selects targets when routing requests. Only applicable for Application Load Balancer Target Groups. The value is `round_robin` or `least_outstanding_requests`. The default is `round_robin`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name of the target group. If omitted, this provider will assign a random, unique name.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<wbr>Prefix<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Creates a unique name beginning with the specified prefix. Conflicts with `name`. Cannot be longer than 6 characters.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Port<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The port to use to connect with the target. Valid values are either ports 1-65535, or `traffic-port`. Defaults to `traffic-port`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Protocol<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The protocol to use to connect with the target. Defaults to `HTTP`. Not applicable when `target_type` is `lambda`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Proxy<wbr>Protocol<wbr>V2<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Boolean to enable / disable support for proxy protocol v2 on Network Load Balancers. See [doc](https://docs.aws.amazon.com/elasticloadbalancing/latest/network/load-balancer-target-groups.html#proxy-protocol) for more information.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Slow<wbr>Start<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The amount time for targets to warm up before the load balancer sends them a full share of requests. The range is 30-900 seconds or 0 to disable. The default value is 0 seconds.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Stickiness<span class="property-indicator"></span>
        <span class="property-type"><a href="#targetgroupstickiness">*Target<wbr>Group<wbr>Stickiness</a></span>
    </dt>
    <dd>{{% md %}}A Stickiness block. Stickiness blocks are documented below. `stickiness` is only valid if used with Load Balancers of type `Application`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Target<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The type of target that you must specify when registering targets with this target group.
The possible values are `instance` (targets are specified by instance ID) or `ip` (targets are specified by IP address) or `lambda` (targets are specified by lambda arn).
The default is `instance`. Note that you can&#39;t specify targets for a target group using both instance IDs and IP addresses.
If the target type is `ip`, specify IP addresses from the subnets of the virtual private cloud (VPC) for the target group,
the RFC 1918 range (10.0.0.0/8, 172.16.0.0/12, and 192.168.0.0/16), and the RFC 6598 range (100.64.0.0/10).
You can&#39;t specify publicly routable IP addresses.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Vpc<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The identifier of the VPC in which to create the target group. Required when `target_type` is `instance` or `ip`. Does not apply when `target_type` is `lambda`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ARN of the Target Group (matches `id`)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">arn<wbr>Suffix<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ARN suffix for use with CloudWatch Metrics.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">deregistration<wbr>Delay<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The amount time for Elastic Load Balancing to wait before changing the state of a deregistering target from draining to unused. The range is 0-3600 seconds. The default value is 300 seconds.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">health<wbr>Check<span class="property-indicator"></span>
        <span class="property-type"><a href="#targetgrouphealthcheck">Target<wbr>Group<wbr>Health<wbr>Check?</a></span>
    </dt>
    <dd>{{% md %}}A Health Check block. Health Check blocks are documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">lambda<wbr>Multi<wbr>Value<wbr>Headers<wbr>Enabled<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Boolean whether the request and response headers exchanged between the load balancer and the Lambda function include arrays of values or strings. Only applies when `target_type` is `lambda`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">load<wbr>Balancing<wbr>Algorithm<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Determines how the load balancer selects targets when routing requests. Only applicable for Application Load Balancer Target Groups. The value is `round_robin` or `least_outstanding_requests`. The default is `round_robin`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the target group. If omitted, this provider will assign a random, unique name.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<wbr>Prefix<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Creates a unique name beginning with the specified prefix. Conflicts with `name`. Cannot be longer than 6 characters.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">port<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The port to use to connect with the target. Valid values are either ports 1-65535, or `traffic-port`. Defaults to `traffic-port`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">protocol<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The protocol to use to connect with the target. Defaults to `HTTP`. Not applicable when `target_type` is `lambda`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">proxy<wbr>Protocol<wbr>V2<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Boolean to enable / disable support for proxy protocol v2 on Network Load Balancers. See [doc](https://docs.aws.amazon.com/elasticloadbalancing/latest/network/load-balancer-target-groups.html#proxy-protocol) for more information.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">slow<wbr>Start<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The amount time for targets to warm up before the load balancer sends them a full share of requests. The range is 30-900 seconds or 0 to disable. The default value is 0 seconds.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">stickiness<span class="property-indicator"></span>
        <span class="property-type"><a href="#targetgroupstickiness">Target<wbr>Group<wbr>Stickiness?</a></span>
    </dt>
    <dd>{{% md %}}A Stickiness block. Stickiness blocks are documented below. `stickiness` is only valid if used with Load Balancers of type `Application`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">target<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The type of target that you must specify when registering targets with this target group.
The possible values are `instance` (targets are specified by instance ID) or `ip` (targets are specified by IP address) or `lambda` (targets are specified by lambda arn).
The default is `instance`. Note that you can&#39;t specify targets for a target group using both instance IDs and IP addresses.
If the target type is `ip`, specify IP addresses from the subnets of the virtual private cloud (VPC) for the target group,
the RFC 1918 range (10.0.0.0/8, 172.16.0.0/12, and 192.168.0.0/16), and the RFC 6598 range (100.64.0.0/10).
You can&#39;t specify publicly routable IP addresses.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">vpc<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The identifier of the VPC in which to create the target group. Required when `target_type` is `instance` or `ip`. Does not apply when `target_type` is `lambda`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ARN of the Target Group (matches `id`)
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">arn_<wbr>suffix<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ARN suffix for use with CloudWatch Metrics.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">deregistration_<wbr>delay<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The amount time for Elastic Load Balancing to wait before changing the state of a deregistering target from draining to unused. The range is 0-3600 seconds. The default value is 300 seconds.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">health_<wbr>check<span class="property-indicator"></span>
        <span class="property-type"><a href="#targetgrouphealthcheck">Dict[Target<wbr>Group<wbr>Health<wbr>Check]</a></span>
    </dt>
    <dd>{{% md %}}A Health Check block. Health Check blocks are documented below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">lambda_<wbr>multi_<wbr>value_<wbr>headers_<wbr>enabled<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Boolean whether the request and response headers exchanged between the load balancer and the Lambda function include arrays of values or strings. Only applies when `target_type` is `lambda`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">load_<wbr>balancing_<wbr>algorithm_<wbr>type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Determines how the load balancer selects targets when routing requests. Only applicable for Application Load Balancer Target Groups. The value is `round_robin` or `least_outstanding_requests`. The default is `round_robin`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the target group. If omitted, this provider will assign a random, unique name.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name_<wbr>prefix<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Creates a unique name beginning with the specified prefix. Conflicts with `name`. Cannot be longer than 6 characters.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">port<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The port to use to connect with the target. Valid values are either ports 1-65535, or `traffic-port`. Defaults to `traffic-port`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">protocol<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The protocol to use to connect with the target. Defaults to `HTTP`. Not applicable when `target_type` is `lambda`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">proxy_<wbr>protocol_<wbr>v2<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Boolean to enable / disable support for proxy protocol v2 on Network Load Balancers. See [doc](https://docs.aws.amazon.com/elasticloadbalancing/latest/network/load-balancer-target-groups.html#proxy-protocol) for more information.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">slow_<wbr>start<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The amount time for targets to warm up before the load balancer sends them a full share of requests. The range is 30-900 seconds or 0 to disable. The default value is 0 seconds.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">stickiness<span class="property-indicator"></span>
        <span class="property-type"><a href="#targetgroupstickiness">Dict[Target<wbr>Group<wbr>Stickiness]</a></span>
    </dt>
    <dd>{{% md %}}A Stickiness block. Stickiness blocks are documented below. `stickiness` is only valid if used with Load Balancers of type `Application`
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">target_<wbr>type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The type of target that you must specify when registering targets with this target group.
The possible values are `instance` (targets are specified by instance ID) or `ip` (targets are specified by IP address) or `lambda` (targets are specified by lambda arn).
The default is `instance`. Note that you can&#39;t specify targets for a target group using both instance IDs and IP addresses.
If the target type is `ip`, specify IP addresses from the subnets of the virtual private cloud (VPC) for the target group,
the RFC 1918 range (10.0.0.0/8, 172.16.0.0/12, and 192.168.0.0/16), and the RFC 6598 range (100.64.0.0/10).
You can&#39;t specify publicly routable IP addresses.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">vpc_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The identifier of the VPC in which to create the target group. Required when `target_type` is `instance` or `ip`. Does not apply when `target_type` is `lambda`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}







## Supporting Types

#### TargetGroupHealthCheck
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#TargetGroupHealthCheck">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#TargetGroupHealthCheck">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/applicationloadbalancing?tab=doc#TargetGroupHealthCheckArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/applicationloadbalancing?tab=doc#TargetGroupHealthCheckOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Applicationloadbalancing.TargetGroupHealthCheckArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Applicationloadbalancing.TargetGroupHealthCheck.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Enabled<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Indicates whether  health checks are enabled. Defaults to true.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Healthy<wbr>Threshold<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The number of consecutive health checks successes required before considering an unhealthy target healthy. Defaults to 3.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Interval<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The approximate amount of time, in seconds, between health checks of an individual target. Minimum value 5 seconds, Maximum value 300 seconds. For `lambda` target groups, it needs to be greater as the `timeout` of the underlying `lambda`. Default 30 seconds.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Matcher<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Path<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The destination for the health check request. Applies to Application Load Balancers only (HTTP/HTTPS), not Network Load Balancers (TCP).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Port<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The port to use to connect with the target. Valid values are either ports 1-65535, or `traffic-port`. Defaults to `traffic-port`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Protocol<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The protocol to use to connect with the target. Defaults to `HTTP`. Not applicable when `target_type` is `lambda`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Timeout<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The amount of time, in seconds, during which no response means a failed health check. For Application Load Balancers, the range is 2 to 120 seconds, and the default is 5 seconds for the `instance` target type and 30 seconds for the `lambda` target type. For Network Load Balancers, you cannot set a custom value, and the default is 10 seconds for TCP and HTTPS health checks and 6 seconds for HTTP health checks.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Unhealthy<wbr>Threshold<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The number of consecutive health check failures required before considering the target unhealthy . For Network Load Balancers, this value must be the same as the `healthy_threshold`. Defaults to 3.
* `matcher` (Required for HTTP/HTTPS ALB) The HTTP codes to use when checking for a successful response from a target. You can specify multiple values (for example, &#34;200,202&#34;) or a range of values (for example, &#34;200-299&#34;). Applies to Application Load Balancers only (HTTP/HTTPS), not Network Load Balancers (TCP).
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Enabled<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Indicates whether  health checks are enabled. Defaults to true.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Healthy<wbr>Threshold<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The number of consecutive health checks successes required before considering an unhealthy target healthy. Defaults to 3.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Interval<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The approximate amount of time, in seconds, between health checks of an individual target. Minimum value 5 seconds, Maximum value 300 seconds. For `lambda` target groups, it needs to be greater as the `timeout` of the underlying `lambda`. Default 30 seconds.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Matcher<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Path<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The destination for the health check request. Applies to Application Load Balancers only (HTTP/HTTPS), not Network Load Balancers (TCP).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Port<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The port to use to connect with the target. Valid values are either ports 1-65535, or `traffic-port`. Defaults to `traffic-port`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Protocol<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The protocol to use to connect with the target. Defaults to `HTTP`. Not applicable when `target_type` is `lambda`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Timeout<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The amount of time, in seconds, during which no response means a failed health check. For Application Load Balancers, the range is 2 to 120 seconds, and the default is 5 seconds for the `instance` target type and 30 seconds for the `lambda` target type. For Network Load Balancers, you cannot set a custom value, and the default is 10 seconds for TCP and HTTPS health checks and 6 seconds for HTTP health checks.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Unhealthy<wbr>Threshold<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The number of consecutive health check failures required before considering the target unhealthy . For Network Load Balancers, this value must be the same as the `healthy_threshold`. Defaults to 3.
* `matcher` (Required for HTTP/HTTPS ALB) The HTTP codes to use when checking for a successful response from a target. You can specify multiple values (for example, &#34;200,202&#34;) or a range of values (for example, &#34;200-299&#34;). Applies to Application Load Balancers only (HTTP/HTTPS), not Network Load Balancers (TCP).
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">enabled<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Indicates whether  health checks are enabled. Defaults to true.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">healthy<wbr>Threshold<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The number of consecutive health checks successes required before considering an unhealthy target healthy. Defaults to 3.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">interval<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The approximate amount of time, in seconds, between health checks of an individual target. Minimum value 5 seconds, Maximum value 300 seconds. For `lambda` target groups, it needs to be greater as the `timeout` of the underlying `lambda`. Default 30 seconds.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">matcher<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">path<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The destination for the health check request. Applies to Application Load Balancers only (HTTP/HTTPS), not Network Load Balancers (TCP).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">port<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The port to use to connect with the target. Valid values are either ports 1-65535, or `traffic-port`. Defaults to `traffic-port`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">protocol<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The protocol to use to connect with the target. Defaults to `HTTP`. Not applicable when `target_type` is `lambda`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">timeout<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The amount of time, in seconds, during which no response means a failed health check. For Application Load Balancers, the range is 2 to 120 seconds, and the default is 5 seconds for the `instance` target type and 30 seconds for the `lambda` target type. For Network Load Balancers, you cannot set a custom value, and the default is 10 seconds for TCP and HTTPS health checks and 6 seconds for HTTP health checks.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">unhealthy<wbr>Threshold<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The number of consecutive health check failures required before considering the target unhealthy . For Network Load Balancers, this value must be the same as the `healthy_threshold`. Defaults to 3.
* `matcher` (Required for HTTP/HTTPS ALB) The HTTP codes to use when checking for a successful response from a target. You can specify multiple values (for example, &#34;200,202&#34;) or a range of values (for example, &#34;200-299&#34;). Applies to Application Load Balancers only (HTTP/HTTPS), not Network Load Balancers (TCP).
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">enabled<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Indicates whether  health checks are enabled. Defaults to true.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">healthy<wbr>Threshold<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The number of consecutive health checks successes required before considering an unhealthy target healthy. Defaults to 3.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">interval<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The approximate amount of time, in seconds, between health checks of an individual target. Minimum value 5 seconds, Maximum value 300 seconds. For `lambda` target groups, it needs to be greater as the `timeout` of the underlying `lambda`. Default 30 seconds.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">matcher<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">path<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The destination for the health check request. Applies to Application Load Balancers only (HTTP/HTTPS), not Network Load Balancers (TCP).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">port<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The port to use to connect with the target. Valid values are either ports 1-65535, or `traffic-port`. Defaults to `traffic-port`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">protocol<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The protocol to use to connect with the target. Defaults to `HTTP`. Not applicable when `target_type` is `lambda`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">timeout<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The amount of time, in seconds, during which no response means a failed health check. For Application Load Balancers, the range is 2 to 120 seconds, and the default is 5 seconds for the `instance` target type and 30 seconds for the `lambda` target type. For Network Load Balancers, you cannot set a custom value, and the default is 10 seconds for TCP and HTTPS health checks and 6 seconds for HTTP health checks.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">unhealthy<wbr>Threshold<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The number of consecutive health check failures required before considering the target unhealthy . For Network Load Balancers, this value must be the same as the `healthy_threshold`. Defaults to 3.
* `matcher` (Required for HTTP/HTTPS ALB) The HTTP codes to use when checking for a successful response from a target. You can specify multiple values (for example, &#34;200,202&#34;) or a range of values (for example, &#34;200-299&#34;). Applies to Application Load Balancers only (HTTP/HTTPS), not Network Load Balancers (TCP).
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### TargetGroupStickiness
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#TargetGroupStickiness">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#TargetGroupStickiness">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/applicationloadbalancing?tab=doc#TargetGroupStickinessArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/applicationloadbalancing?tab=doc#TargetGroupStickinessOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Applicationloadbalancing.TargetGroupStickinessArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Applicationloadbalancing.TargetGroupStickiness.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Cookie<wbr>Duration<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The time period, in seconds, during which requests from a client should be routed to the same target. After this time period expires, the load balancer-generated cookie is considered stale. The range is 1 second to 1 week (604800 seconds). The default value is 1 day (86400 seconds).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Enabled<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Indicates whether  health checks are enabled. Defaults to true.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type of sticky sessions. The only current possible value is `lb_cookie`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Cookie<wbr>Duration<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The time period, in seconds, during which requests from a client should be routed to the same target. After this time period expires, the load balancer-generated cookie is considered stale. The range is 1 second to 1 week (604800 seconds). The default value is 1 day (86400 seconds).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Enabled<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Indicates whether  health checks are enabled. Defaults to true.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type of sticky sessions. The only current possible value is `lb_cookie`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">cookie<wbr>Duration<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The time period, in seconds, during which requests from a client should be routed to the same target. After this time period expires, the load balancer-generated cookie is considered stale. The range is 1 second to 1 week (604800 seconds). The default value is 1 day (86400 seconds).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">enabled<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Indicates whether  health checks are enabled. Defaults to true.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type of sticky sessions. The only current possible value is `lb_cookie`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">cookie<wbr>Duration<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The time period, in seconds, during which requests from a client should be routed to the same target. After this time period expires, the load balancer-generated cookie is considered stale. The range is 1 second to 1 week (604800 seconds). The default value is 1 day (86400 seconds).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">enabled<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Indicates whether  health checks are enabled. Defaults to true.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The type of sticky sessions. The only current possible value is `lb_cookie`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}








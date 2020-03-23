
---
title: "SpotFleetRequest"
block_external_search_index: true
---

Provides an EC2 Spot Fleet Request resource. This allows a fleet of Spot
instances to be requested on the Spot market.

## Example Usage

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

// Request a Spot fleet
const cheapCompute = new aws.ec2.SpotFleetRequest("cheap_compute", {
    allocationStrategy: "diversified",
    iamFleetRole: "arn:aws:iam::12345678:role/spot-fleet",
    launchSpecifications: [
        {
            ami: "ami-1234",
            iamInstanceProfileArn: aws_iam_instance_profile_example.arn,
            instanceType: "m4.10xlarge",
            placementTenancy: "dedicated",
            spotPrice: "2.793",
        },
        {
            ami: "ami-5678",
            availabilityZone: "us-west-1a",
            iamInstanceProfileArn: aws_iam_instance_profile_example.arn,
            instanceType: "m4.4xlarge",
            keyName: "my-key",
            rootBlockDevices: [{
                volumeSize: 300,
                volumeType: "gp2",
            }],
            spotPrice: "1.117",
            subnetId: "subnet-1234",
            tags: {
                Name: "spot-fleet-example",
            },
            weightedCapacity: "35",
        },
    ],
    spotPrice: "0.03",
    targetCapacity: 6,
    validUntil: "2019-11-04T20:44:20Z",
});
```

> **NOTE:** This provider does not support the functionality where multiple `subnet_id` or `availability_zone` parameters can be specified in the same
launch configuration block. If you want to specify multiple values, then separate launch configuration blocks should be used:

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const foo = new aws.ec2.SpotFleetRequest("foo", {
    iamFleetRole: "arn:aws:iam::12345678:role/spot-fleet",
    launchSpecifications: [
        {
            ami: "ami-d06a90b0",
            availabilityZone: "us-west-2a",
            instanceType: "m1.small",
            keyName: "my-key",
        },
        {
            ami: "ami-d06a90b0",
            availabilityZone: "us-west-2a",
            instanceType: "m5.large",
            keyName: "my-key",
        },
    ],
    spotPrice: "0.005",
    targetCapacity: 2,
    validUntil: "2019-11-04T20:44:20Z",
});
```

> This content is derived from https://github.com/terraform-providers/terraform-provider-aws/blob/master/website/docs/r/spot_fleet_request.html.markdown.



## Create a SpotFleetRequest Resource

{{< chooser language "javascript,typescript,python,go,csharp" / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/ec2/#SpotFleetRequest">SpotFleetRequest</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/ec2/#SpotFleetRequestArgs">SpotFleetRequestArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">SpotFleetRequest</span><span class="p">(resource_name, opts=None, </span>allocation_strategy=None<span class="p">, </span>excess_capacity_termination_policy=None<span class="p">, </span>fleet_type=None<span class="p">, </span>iam_fleet_role=None<span class="p">, </span>instance_interruption_behaviour=None<span class="p">, </span>instance_pools_to_use_count=None<span class="p">, </span>launch_specifications=None<span class="p">, </span>load_balancers=None<span class="p">, </span>replace_unhealthy_instances=None<span class="p">, </span>spot_price=None<span class="p">, </span>target_capacity=None<span class="p">, </span>target_group_arns=None<span class="p">, </span>terminate_instances_with_expiration=None<span class="p">, </span>valid_from=None<span class="p">, </span>valid_until=None<span class="p">, </span>wait_for_fulfillment=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewSpotFleetRequest<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ec2?tab=doc#SpotFleetRequestArgs">SpotFleetRequestArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ec2?tab=doc#SpotFleetRequest">SpotFleetRequest</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ec2.SpotFleetRequest.html">SpotFleetRequest</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ec2.SpotFleetRequestArgs.html">SpotFleetRequestArgs</a></span> <span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
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
            title="Optional">Allocation<wbr>Strategy<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Indicates how to allocate the target capacity across
the Spot pools specified by the Spot fleet request. The default is
`lowestPrice`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Excess<wbr>Capacity<wbr>Termination<wbr>Policy<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Indicates whether running Spot
instances should be terminated if the target capacity of the Spot fleet
request is decreased below the current size of the Spot fleet.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Fleet<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The type of fleet request. Indicates whether the Spot Fleet only requests the target
capacity or also attempts to maintain it. Default is `maintain`.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Iam<wbr>Fleet<wbr>Role<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Grants the Spot fleet permission to terminate
Spot instances on your behalf when you cancel its Spot fleet request using
CancelSpotFleetRequests or when the Spot fleet request expires, if you set
terminateInstancesWithExpiration.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Instance<wbr>Interruption<wbr>Behaviour<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Indicates whether a Spot
instance stops or terminates when it is interrupted. Default is
`terminate`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Instance<wbr>Pools<wbr>To<wbr>Use<wbr>Count<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}
The number of Spot pools across which to allocate your target Spot capacity.
Valid only when `allocation_strategy` is set to `lowestPrice`. Spot Fleet selects
the cheapest Spot pools and evenly allocates your target Spot capacity across
the number of Spot pools that you specify.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Launch<wbr>Specifications<span class="property-indicator"></span>
        <span class="property-type"><a href="#spotfleetrequestlaunchspecification">List&lt;Spot<wbr>Fleet<wbr>Request<wbr>Launch<wbr>Specification<wbr>Args&gt;</a></span>
    </dt>
    <dd>{{% md %}}Used to define the launch configuration of the
spot-fleet request. Can be specified multiple times to define different bids
across different markets and instance types.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Load<wbr>Balancers<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}A list of elastic load balancer names to add to the Spot fleet.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Replace<wbr>Unhealthy<wbr>Instances<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Indicates whether Spot fleet should replace unhealthy instances. Default `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Spot<wbr>Price<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The maximum bid price per unit hour.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Target<wbr>Capacity<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The number of units to request. You can choose to set the
target capacity in terms of instances or a performance characteristic that is
important to your application workload, such as vCPUs, memory, or I/O.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Target<wbr>Group<wbr>Arns<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}A list of `aws.alb.TargetGroup` ARNs, for use with Application Load Balancing.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Terminate<wbr>Instances<wbr>With<wbr>Expiration<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Indicates whether running Spot
instances should be terminated when the Spot fleet request expires.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Valid<wbr>From<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The start date and time of the request, in UTC [RFC3339](https://tools.ietf.org/html/rfc3339#section-5.8) format(for example, YYYY-MM-DDTHH:MM:SSZ). The default is to start fulfilling the request immediately.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Valid<wbr>Until<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The end date and time of the request, in UTC [RFC3339](https://tools.ietf.org/html/rfc3339#section-5.8) format(for example, YYYY-MM-DDTHH:MM:SSZ). At this point, no new Spot instance requests are placed or enabled to fulfill the request. Defaults to 24 hours.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Wait<wbr>For<wbr>Fulfillment<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}If set, this provider will
wait for the Spot Request to be fulfilled, and will throw an error if the
timeout of 10m is reached.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Allocation<wbr>Strategy<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Indicates how to allocate the target capacity across
the Spot pools specified by the Spot fleet request. The default is
`lowestPrice`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Excess<wbr>Capacity<wbr>Termination<wbr>Policy<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Indicates whether running Spot
instances should be terminated if the target capacity of the Spot fleet
request is decreased below the current size of the Spot fleet.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Fleet<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The type of fleet request. Indicates whether the Spot Fleet only requests the target
capacity or also attempts to maintain it. Default is `maintain`.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Iam<wbr>Fleet<wbr>Role<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Grants the Spot fleet permission to terminate
Spot instances on your behalf when you cancel its Spot fleet request using
CancelSpotFleetRequests or when the Spot fleet request expires, if you set
terminateInstancesWithExpiration.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Instance<wbr>Interruption<wbr>Behaviour<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Indicates whether a Spot
instance stops or terminates when it is interrupted. Default is
`terminate`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Instance<wbr>Pools<wbr>To<wbr>Use<wbr>Count<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}
The number of Spot pools across which to allocate your target Spot capacity.
Valid only when `allocation_strategy` is set to `lowestPrice`. Spot Fleet selects
the cheapest Spot pools and evenly allocates your target Spot capacity across
the number of Spot pools that you specify.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Launch<wbr>Specifications<span class="property-indicator"></span>
        <span class="property-type"><a href="#spotfleetrequestlaunchspecification">[]Spot<wbr>Fleet<wbr>Request<wbr>Launch<wbr>Specification</a></span>
    </dt>
    <dd>{{% md %}}Used to define the launch configuration of the
spot-fleet request. Can be specified multiple times to define different bids
across different markets and instance types.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Load<wbr>Balancers<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}A list of elastic load balancer names to add to the Spot fleet.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Replace<wbr>Unhealthy<wbr>Instances<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Indicates whether Spot fleet should replace unhealthy instances. Default `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Spot<wbr>Price<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The maximum bid price per unit hour.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Target<wbr>Capacity<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The number of units to request. You can choose to set the
target capacity in terms of instances or a performance characteristic that is
important to your application workload, such as vCPUs, memory, or I/O.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Target<wbr>Group<wbr>Arns<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}A list of `aws.alb.TargetGroup` ARNs, for use with Application Load Balancing.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Terminate<wbr>Instances<wbr>With<wbr>Expiration<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Indicates whether running Spot
instances should be terminated when the Spot fleet request expires.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Valid<wbr>From<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The start date and time of the request, in UTC [RFC3339](https://tools.ietf.org/html/rfc3339#section-5.8) format(for example, YYYY-MM-DDTHH:MM:SSZ). The default is to start fulfilling the request immediately.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Valid<wbr>Until<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The end date and time of the request, in UTC [RFC3339](https://tools.ietf.org/html/rfc3339#section-5.8) format(for example, YYYY-MM-DDTHH:MM:SSZ). At this point, no new Spot instance requests are placed or enabled to fulfill the request. Defaults to 24 hours.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Wait<wbr>For<wbr>Fulfillment<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}If set, this provider will
wait for the Spot Request to be fulfilled, and will throw an error if the
timeout of 10m is reached.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">allocation<wbr>Strategy<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Indicates how to allocate the target capacity across
the Spot pools specified by the Spot fleet request. The default is
`lowestPrice`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">excess<wbr>Capacity<wbr>Termination<wbr>Policy<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Indicates whether running Spot
instances should be terminated if the target capacity of the Spot fleet
request is decreased below the current size of the Spot fleet.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">fleet<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The type of fleet request. Indicates whether the Spot Fleet only requests the target
capacity or also attempts to maintain it. Default is `maintain`.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">iam<wbr>Fleet<wbr>Role<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Grants the Spot fleet permission to terminate
Spot instances on your behalf when you cancel its Spot fleet request using
CancelSpotFleetRequests or when the Spot fleet request expires, if you set
terminateInstancesWithExpiration.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">instance<wbr>Interruption<wbr>Behaviour<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Indicates whether a Spot
instance stops or terminates when it is interrupted. Default is
`terminate`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">instance<wbr>Pools<wbr>To<wbr>Use<wbr>Count<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}
The number of Spot pools across which to allocate your target Spot capacity.
Valid only when `allocation_strategy` is set to `lowestPrice`. Spot Fleet selects
the cheapest Spot pools and evenly allocates your target Spot capacity across
the number of Spot pools that you specify.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">launch<wbr>Specifications<span class="property-indicator"></span>
        <span class="property-type"><a href="#spotfleetrequestlaunchspecification">Spot<wbr>Fleet<wbr>Request<wbr>Launch<wbr>Specification[]</a></span>
    </dt>
    <dd>{{% md %}}Used to define the launch configuration of the
spot-fleet request. Can be specified multiple times to define different bids
across different markets and instance types.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">load<wbr>Balancers<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}A list of elastic load balancer names to add to the Spot fleet.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">replace<wbr>Unhealthy<wbr>Instances<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Indicates whether Spot fleet should replace unhealthy instances. Default `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">spot<wbr>Price<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The maximum bid price per unit hour.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">target<wbr>Capacity<span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}The number of units to request. You can choose to set the
target capacity in terms of instances or a performance characteristic that is
important to your application workload, such as vCPUs, memory, or I/O.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">target<wbr>Group<wbr>Arns<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}A list of `aws.alb.TargetGroup` ARNs, for use with Application Load Balancing.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">terminate<wbr>Instances<wbr>With<wbr>Expiration<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Indicates whether running Spot
instances should be terminated when the Spot fleet request expires.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">valid<wbr>From<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The start date and time of the request, in UTC [RFC3339](https://tools.ietf.org/html/rfc3339#section-5.8) format(for example, YYYY-MM-DDTHH:MM:SSZ). The default is to start fulfilling the request immediately.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">valid<wbr>Until<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The end date and time of the request, in UTC [RFC3339](https://tools.ietf.org/html/rfc3339#section-5.8) format(for example, YYYY-MM-DDTHH:MM:SSZ). At this point, no new Spot instance requests are placed or enabled to fulfill the request. Defaults to 24 hours.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">wait<wbr>For<wbr>Fulfillment<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}If set, this provider will
wait for the Spot Request to be fulfilled, and will throw an error if the
timeout of 10m is reached.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">allocation_<wbr>strategy<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Indicates how to allocate the target capacity across
the Spot pools specified by the Spot fleet request. The default is
`lowestPrice`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">excess_<wbr>capacity_<wbr>termination_<wbr>policy<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Indicates whether running Spot
instances should be terminated if the target capacity of the Spot fleet
request is decreased below the current size of the Spot fleet.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">fleet_<wbr>type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The type of fleet request. Indicates whether the Spot Fleet only requests the target
capacity or also attempts to maintain it. Default is `maintain`.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">iam_<wbr>fleet_<wbr>role<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Grants the Spot fleet permission to terminate
Spot instances on your behalf when you cancel its Spot fleet request using
CancelSpotFleetRequests or when the Spot fleet request expires, if you set
terminateInstancesWithExpiration.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">instance_<wbr>interruption_<wbr>behaviour<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Indicates whether a Spot
instance stops or terminates when it is interrupted. Default is
`terminate`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">instance_<wbr>pools_<wbr>to_<wbr>use_<wbr>count<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}
The number of Spot pools across which to allocate your target Spot capacity.
Valid only when `allocation_strategy` is set to `lowestPrice`. Spot Fleet selects
the cheapest Spot pools and evenly allocates your target Spot capacity across
the number of Spot pools that you specify.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">launch_<wbr>specifications<span class="property-indicator"></span>
        <span class="property-type"><a href="#spotfleetrequestlaunchspecification">List[Spot<wbr>Fleet<wbr>Request<wbr>Launch<wbr>Specification]</a></span>
    </dt>
    <dd>{{% md %}}Used to define the launch configuration of the
spot-fleet request. Can be specified multiple times to define different bids
across different markets and instance types.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">load_<wbr>balancers<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}A list of elastic load balancer names to add to the Spot fleet.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">replace_<wbr>unhealthy_<wbr>instances<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Indicates whether Spot fleet should replace unhealthy instances. Default `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">spot_<wbr>price<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The maximum bid price per unit hour.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">target_<wbr>capacity<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The number of units to request. You can choose to set the
target capacity in terms of instances or a performance characteristic that is
important to your application workload, such as vCPUs, memory, or I/O.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">target_<wbr>group_<wbr>arns<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}A list of `aws.alb.TargetGroup` ARNs, for use with Application Load Balancing.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">terminate_<wbr>instances_<wbr>with_<wbr>expiration<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Indicates whether running Spot
instances should be terminated when the Spot fleet request expires.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">valid_<wbr>from<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The start date and time of the request, in UTC [RFC3339](https://tools.ietf.org/html/rfc3339#section-5.8) format(for example, YYYY-MM-DDTHH:MM:SSZ). The default is to start fulfilling the request immediately.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">valid_<wbr>until<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The end date and time of the request, in UTC [RFC3339](https://tools.ietf.org/html/rfc3339#section-5.8) format(for example, YYYY-MM-DDTHH:MM:SSZ). At this point, no new Spot instance requests are placed or enabled to fulfill the request. Defaults to 24 hours.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">wait_<wbr>for_<wbr>fulfillment<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}If set, this provider will
wait for the Spot Request to be fulfilled, and will throw an error if the
timeout of 10m is reached.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}




## SpotFleetRequest Output Properties

The following output properties are available:




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Allocation<wbr>Strategy<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Indicates how to allocate the target capacity across
the Spot pools specified by the Spot fleet request. The default is
`lowestPrice`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Client<wbr>Token<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">Excess<wbr>Capacity<wbr>Termination<wbr>Policy<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Indicates whether running Spot
instances should be terminated if the target capacity of the Spot fleet
request is decreased below the current size of the Spot fleet.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Fleet<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The type of fleet request. Indicates whether the Spot Fleet only requests the target
capacity or also attempts to maintain it. Default is `maintain`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Iam<wbr>Fleet<wbr>Role<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Grants the Spot fleet permission to terminate
Spot instances on your behalf when you cancel its Spot fleet request using
CancelSpotFleetRequests or when the Spot fleet request expires, if you set
terminateInstancesWithExpiration.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Instance<wbr>Interruption<wbr>Behaviour<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Indicates whether a Spot
instance stops or terminates when it is interrupted. Default is
`terminate`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Instance<wbr>Pools<wbr>To<wbr>Use<wbr>Count<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}
The number of Spot pools across which to allocate your target Spot capacity.
Valid only when `allocation_strategy` is set to `lowestPrice`. Spot Fleet selects
the cheapest Spot pools and evenly allocates your target Spot capacity across
the number of Spot pools that you specify.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Launch<wbr>Specifications<span class="property-indicator"></span>
        <span class="property-type"><a href="#spotfleetrequestlaunchspecification">List&lt;Spot<wbr>Fleet<wbr>Request<wbr>Launch<wbr>Specification&gt;</a></span>
    </dt>
    <dd>{{% md %}}Used to define the launch configuration of the
spot-fleet request. Can be specified multiple times to define different bids
across different markets and instance types.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Load<wbr>Balancers<span class="property-indicator"></span>
        <span class="property-type">List<string></span>
    </dt>
    <dd>{{% md %}}A list of elastic load balancer names to add to the Spot fleet.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Replace<wbr>Unhealthy<wbr>Instances<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Indicates whether Spot fleet should replace unhealthy instances. Default `false`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Spot<wbr>Price<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The maximum bid price per unit hour.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Spot<wbr>Request<wbr>State<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The state of the Spot fleet request.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Target<wbr>Capacity<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The number of units to request. You can choose to set the
target capacity in terms of instances or a performance characteristic that is
important to your application workload, such as vCPUs, memory, or I/O.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Target<wbr>Group<wbr>Arns<span class="property-indicator"></span>
        <span class="property-type">List<string></span>
    </dt>
    <dd>{{% md %}}A list of `aws.alb.TargetGroup` ARNs, for use with Application Load Balancing.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Terminate<wbr>Instances<wbr>With<wbr>Expiration<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Indicates whether running Spot
instances should be terminated when the Spot fleet request expires.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Valid<wbr>From<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The start date and time of the request, in UTC [RFC3339](https://tools.ietf.org/html/rfc3339#section-5.8) format(for example, YYYY-MM-DDTHH:MM:SSZ). The default is to start fulfilling the request immediately.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Valid<wbr>Until<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The end date and time of the request, in UTC [RFC3339](https://tools.ietf.org/html/rfc3339#section-5.8) format(for example, YYYY-MM-DDTHH:MM:SSZ). At this point, no new Spot instance requests are placed or enabled to fulfill the request. Defaults to 24 hours.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Wait<wbr>For<wbr>Fulfillment<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}If set, this provider will
wait for the Spot Request to be fulfilled, and will throw an error if the
timeout of 10m is reached.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Allocation<wbr>Strategy<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Indicates how to allocate the target capacity across
the Spot pools specified by the Spot fleet request. The default is
`lowestPrice`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Client<wbr>Token<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">Excess<wbr>Capacity<wbr>Termination<wbr>Policy<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Indicates whether running Spot
instances should be terminated if the target capacity of the Spot fleet
request is decreased below the current size of the Spot fleet.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Fleet<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The type of fleet request. Indicates whether the Spot Fleet only requests the target
capacity or also attempts to maintain it. Default is `maintain`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Iam<wbr>Fleet<wbr>Role<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Grants the Spot fleet permission to terminate
Spot instances on your behalf when you cancel its Spot fleet request using
CancelSpotFleetRequests or when the Spot fleet request expires, if you set
terminateInstancesWithExpiration.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Instance<wbr>Interruption<wbr>Behaviour<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Indicates whether a Spot
instance stops or terminates when it is interrupted. Default is
`terminate`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Instance<wbr>Pools<wbr>To<wbr>Use<wbr>Count<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}
The number of Spot pools across which to allocate your target Spot capacity.
Valid only when `allocation_strategy` is set to `lowestPrice`. Spot Fleet selects
the cheapest Spot pools and evenly allocates your target Spot capacity across
the number of Spot pools that you specify.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Launch<wbr>Specifications<span class="property-indicator"></span>
        <span class="property-type"><a href="#spotfleetrequestlaunchspecification">[]Spot<wbr>Fleet<wbr>Request<wbr>Launch<wbr>Specification</a></span>
    </dt>
    <dd>{{% md %}}Used to define the launch configuration of the
spot-fleet request. Can be specified multiple times to define different bids
across different markets and instance types.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Load<wbr>Balancers<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}A list of elastic load balancer names to add to the Spot fleet.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Replace<wbr>Unhealthy<wbr>Instances<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Indicates whether Spot fleet should replace unhealthy instances. Default `false`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Spot<wbr>Price<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The maximum bid price per unit hour.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Spot<wbr>Request<wbr>State<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The state of the Spot fleet request.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Target<wbr>Capacity<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The number of units to request. You can choose to set the
target capacity in terms of instances or a performance characteristic that is
important to your application workload, such as vCPUs, memory, or I/O.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Target<wbr>Group<wbr>Arns<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}A list of `aws.alb.TargetGroup` ARNs, for use with Application Load Balancing.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Terminate<wbr>Instances<wbr>With<wbr>Expiration<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Indicates whether running Spot
instances should be terminated when the Spot fleet request expires.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Valid<wbr>From<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The start date and time of the request, in UTC [RFC3339](https://tools.ietf.org/html/rfc3339#section-5.8) format(for example, YYYY-MM-DDTHH:MM:SSZ). The default is to start fulfilling the request immediately.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Valid<wbr>Until<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The end date and time of the request, in UTC [RFC3339](https://tools.ietf.org/html/rfc3339#section-5.8) format(for example, YYYY-MM-DDTHH:MM:SSZ). At this point, no new Spot instance requests are placed or enabled to fulfill the request. Defaults to 24 hours.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Wait<wbr>For<wbr>Fulfillment<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}If set, this provider will
wait for the Spot Request to be fulfilled, and will throw an error if the
timeout of 10m is reached.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">allocation<wbr>Strategy<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Indicates how to allocate the target capacity across
the Spot pools specified by the Spot fleet request. The default is
`lowestPrice`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">client<wbr>Token<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">excess<wbr>Capacity<wbr>Termination<wbr>Policy<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Indicates whether running Spot
instances should be terminated if the target capacity of the Spot fleet
request is decreased below the current size of the Spot fleet.
{{% /md %}}</dd>

    <dt class="property-"
            title="">fleet<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The type of fleet request. Indicates whether the Spot Fleet only requests the target
capacity or also attempts to maintain it. Default is `maintain`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">iam<wbr>Fleet<wbr>Role<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Grants the Spot fleet permission to terminate
Spot instances on your behalf when you cancel its Spot fleet request using
CancelSpotFleetRequests or when the Spot fleet request expires, if you set
terminateInstancesWithExpiration.
{{% /md %}}</dd>

    <dt class="property-"
            title="">instance<wbr>Interruption<wbr>Behaviour<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Indicates whether a Spot
instance stops or terminates when it is interrupted. Default is
`terminate`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">instance<wbr>Pools<wbr>To<wbr>Use<wbr>Count<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}
The number of Spot pools across which to allocate your target Spot capacity.
Valid only when `allocation_strategy` is set to `lowestPrice`. Spot Fleet selects
the cheapest Spot pools and evenly allocates your target Spot capacity across
the number of Spot pools that you specify.
{{% /md %}}</dd>

    <dt class="property-"
            title="">launch<wbr>Specifications<span class="property-indicator"></span>
        <span class="property-type"><a href="#spotfleetrequestlaunchspecification">Spot<wbr>Fleet<wbr>Request<wbr>Launch<wbr>Specification[]</a></span>
    </dt>
    <dd>{{% md %}}Used to define the launch configuration of the
spot-fleet request. Can be specified multiple times to define different bids
across different markets and instance types.
{{% /md %}}</dd>

    <dt class="property-"
            title="">load<wbr>Balancers<span class="property-indicator"></span>
        <span class="property-type">string[]</span>
    </dt>
    <dd>{{% md %}}A list of elastic load balancer names to add to the Spot fleet.
{{% /md %}}</dd>

    <dt class="property-"
            title="">replace<wbr>Unhealthy<wbr>Instances<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Indicates whether Spot fleet should replace unhealthy instances. Default `false`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">spot<wbr>Price<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The maximum bid price per unit hour.
{{% /md %}}</dd>

    <dt class="property-"
            title="">spot<wbr>Request<wbr>State<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The state of the Spot fleet request.
{{% /md %}}</dd>

    <dt class="property-"
            title="">target<wbr>Capacity<span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}The number of units to request. You can choose to set the
target capacity in terms of instances or a performance characteristic that is
important to your application workload, such as vCPUs, memory, or I/O.
{{% /md %}}</dd>

    <dt class="property-"
            title="">target<wbr>Group<wbr>Arns<span class="property-indicator"></span>
        <span class="property-type">string[]</span>
    </dt>
    <dd>{{% md %}}A list of `aws.alb.TargetGroup` ARNs, for use with Application Load Balancing.
{{% /md %}}</dd>

    <dt class="property-"
            title="">terminate<wbr>Instances<wbr>With<wbr>Expiration<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Indicates whether running Spot
instances should be terminated when the Spot fleet request expires.
{{% /md %}}</dd>

    <dt class="property-"
            title="">valid<wbr>From<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The start date and time of the request, in UTC [RFC3339](https://tools.ietf.org/html/rfc3339#section-5.8) format(for example, YYYY-MM-DDTHH:MM:SSZ). The default is to start fulfilling the request immediately.
{{% /md %}}</dd>

    <dt class="property-"
            title="">valid<wbr>Until<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The end date and time of the request, in UTC [RFC3339](https://tools.ietf.org/html/rfc3339#section-5.8) format(for example, YYYY-MM-DDTHH:MM:SSZ). At this point, no new Spot instance requests are placed or enabled to fulfill the request. Defaults to 24 hours.
{{% /md %}}</dd>

    <dt class="property-"
            title="">wait<wbr>For<wbr>Fulfillment<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}If set, this provider will
wait for the Spot Request to be fulfilled, and will throw an error if the
timeout of 10m is reached.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">allocation_<wbr>strategy<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Indicates how to allocate the target capacity across
the Spot pools specified by the Spot fleet request. The default is
`lowestPrice`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">client_<wbr>token<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">excess_<wbr>capacity_<wbr>termination_<wbr>policy<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Indicates whether running Spot
instances should be terminated if the target capacity of the Spot fleet
request is decreased below the current size of the Spot fleet.
{{% /md %}}</dd>

    <dt class="property-"
            title="">fleet_<wbr>type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The type of fleet request. Indicates whether the Spot Fleet only requests the target
capacity or also attempts to maintain it. Default is `maintain`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">iam_<wbr>fleet_<wbr>role<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Grants the Spot fleet permission to terminate
Spot instances on your behalf when you cancel its Spot fleet request using
CancelSpotFleetRequests or when the Spot fleet request expires, if you set
terminateInstancesWithExpiration.
{{% /md %}}</dd>

    <dt class="property-"
            title="">instance_<wbr>interruption_<wbr>behaviour<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Indicates whether a Spot
instance stops or terminates when it is interrupted. Default is
`terminate`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">instance_<wbr>pools_<wbr>to_<wbr>use_<wbr>count<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}
The number of Spot pools across which to allocate your target Spot capacity.
Valid only when `allocation_strategy` is set to `lowestPrice`. Spot Fleet selects
the cheapest Spot pools and evenly allocates your target Spot capacity across
the number of Spot pools that you specify.
{{% /md %}}</dd>

    <dt class="property-"
            title="">launch_<wbr>specifications<span class="property-indicator"></span>
        <span class="property-type"><a href="#spotfleetrequestlaunchspecification">List[Spot<wbr>Fleet<wbr>Request<wbr>Launch<wbr>Specification]</a></span>
    </dt>
    <dd>{{% md %}}Used to define the launch configuration of the
spot-fleet request. Can be specified multiple times to define different bids
across different markets and instance types.
{{% /md %}}</dd>

    <dt class="property-"
            title="">load_<wbr>balancers<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}A list of elastic load balancer names to add to the Spot fleet.
{{% /md %}}</dd>

    <dt class="property-"
            title="">replace_<wbr>unhealthy_<wbr>instances<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Indicates whether Spot fleet should replace unhealthy instances. Default `false`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">spot_<wbr>price<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The maximum bid price per unit hour.
{{% /md %}}</dd>

    <dt class="property-"
            title="">spot_<wbr>request_<wbr>state<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The state of the Spot fleet request.
{{% /md %}}</dd>

    <dt class="property-"
            title="">target_<wbr>capacity<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The number of units to request. You can choose to set the
target capacity in terms of instances or a performance characteristic that is
important to your application workload, such as vCPUs, memory, or I/O.
{{% /md %}}</dd>

    <dt class="property-"
            title="">target_<wbr>group_<wbr>arns<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}A list of `aws.alb.TargetGroup` ARNs, for use with Application Load Balancing.
{{% /md %}}</dd>

    <dt class="property-"
            title="">terminate_<wbr>instances_<wbr>with_<wbr>expiration<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Indicates whether running Spot
instances should be terminated when the Spot fleet request expires.
{{% /md %}}</dd>

    <dt class="property-"
            title="">valid_<wbr>from<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The start date and time of the request, in UTC [RFC3339](https://tools.ietf.org/html/rfc3339#section-5.8) format(for example, YYYY-MM-DDTHH:MM:SSZ). The default is to start fulfilling the request immediately.
{{% /md %}}</dd>

    <dt class="property-"
            title="">valid_<wbr>until<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The end date and time of the request, in UTC [RFC3339](https://tools.ietf.org/html/rfc3339#section-5.8) format(for example, YYYY-MM-DDTHH:MM:SSZ). At this point, no new Spot instance requests are placed or enabled to fulfill the request. Defaults to 24 hours.
{{% /md %}}</dd>

    <dt class="property-"
            title="">wait_<wbr>for_<wbr>fulfillment<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}If set, this provider will
wait for the Spot Request to be fulfilled, and will throw an error if the
timeout of 10m is reached.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





## Look up an Existing SpotFleetRequest Resource

{{< chooser language "javascript,typescript,python,go,csharp  " / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">pulumi.Input&lt;pulumi.ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/ec2/#SpotFleetRequestState">SpotFleetRequestState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/ec2/#SpotFleetRequest">SpotFleetRequest</a></span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>allocation_strategy=None<span class="p">, </span>client_token=None<span class="p">, </span>excess_capacity_termination_policy=None<span class="p">, </span>fleet_type=None<span class="p">, </span>iam_fleet_role=None<span class="p">, </span>instance_interruption_behaviour=None<span class="p">, </span>instance_pools_to_use_count=None<span class="p">, </span>launch_specifications=None<span class="p">, </span>load_balancers=None<span class="p">, </span>replace_unhealthy_instances=None<span class="p">, </span>spot_price=None<span class="p">, </span>spot_request_state=None<span class="p">, </span>target_capacity=None<span class="p">, </span>target_group_arns=None<span class="p">, </span>terminate_instances_with_expiration=None<span class="p">, </span>valid_from=None<span class="p">, </span>valid_until=None<span class="p">, </span>wait_for_fulfillment=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetSpotFleetRequest<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">pulumi.IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ec2?tab=doc#SpotFleetRequestState">SpotFleetRequestState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ec2?tab=doc#SpotFleetRequest">SpotFleetRequest</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ec2.SpotFleetRequest.html">SpotFleetRequest</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Pulumi.Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ec2.SpotFleetRequestState.html">SpotFleetRequestState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
{{% /choosable %}}

Get an existing SpotFleetRequest resource's state with the given name, ID, and optional extra properties used to qualify the lookup.

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
            title="Optional">Allocation<wbr>Strategy<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Indicates how to allocate the target capacity across
the Spot pools specified by the Spot fleet request. The default is
`lowestPrice`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Client<wbr>Token<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Excess<wbr>Capacity<wbr>Termination<wbr>Policy<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Indicates whether running Spot
instances should be terminated if the target capacity of the Spot fleet
request is decreased below the current size of the Spot fleet.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Fleet<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The type of fleet request. Indicates whether the Spot Fleet only requests the target
capacity or also attempts to maintain it. Default is `maintain`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Iam<wbr>Fleet<wbr>Role<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Grants the Spot fleet permission to terminate
Spot instances on your behalf when you cancel its Spot fleet request using
CancelSpotFleetRequests or when the Spot fleet request expires, if you set
terminateInstancesWithExpiration.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Instance<wbr>Interruption<wbr>Behaviour<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Indicates whether a Spot
instance stops or terminates when it is interrupted. Default is
`terminate`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Instance<wbr>Pools<wbr>To<wbr>Use<wbr>Count<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}
The number of Spot pools across which to allocate your target Spot capacity.
Valid only when `allocation_strategy` is set to `lowestPrice`. Spot Fleet selects
the cheapest Spot pools and evenly allocates your target Spot capacity across
the number of Spot pools that you specify.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Launch<wbr>Specifications<span class="property-indicator"></span>
        <span class="property-type"><a href="#spotfleetrequestlaunchspecification">List&lt;Spot<wbr>Fleet<wbr>Request<wbr>Launch<wbr>Specification<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}Used to define the launch configuration of the
spot-fleet request. Can be specified multiple times to define different bids
across different markets and instance types.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Load<wbr>Balancers<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}A list of elastic load balancer names to add to the Spot fleet.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Replace<wbr>Unhealthy<wbr>Instances<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Indicates whether Spot fleet should replace unhealthy instances. Default `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Spot<wbr>Price<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The maximum bid price per unit hour.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Spot<wbr>Request<wbr>State<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The state of the Spot fleet request.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Target<wbr>Capacity<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The number of units to request. You can choose to set the
target capacity in terms of instances or a performance characteristic that is
important to your application workload, such as vCPUs, memory, or I/O.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Target<wbr>Group<wbr>Arns<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}A list of `aws.alb.TargetGroup` ARNs, for use with Application Load Balancing.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Terminate<wbr>Instances<wbr>With<wbr>Expiration<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Indicates whether running Spot
instances should be terminated when the Spot fleet request expires.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Valid<wbr>From<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The start date and time of the request, in UTC [RFC3339](https://tools.ietf.org/html/rfc3339#section-5.8) format(for example, YYYY-MM-DDTHH:MM:SSZ). The default is to start fulfilling the request immediately.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Valid<wbr>Until<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The end date and time of the request, in UTC [RFC3339](https://tools.ietf.org/html/rfc3339#section-5.8) format(for example, YYYY-MM-DDTHH:MM:SSZ). At this point, no new Spot instance requests are placed or enabled to fulfill the request. Defaults to 24 hours.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Wait<wbr>For<wbr>Fulfillment<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}If set, this provider will
wait for the Spot Request to be fulfilled, and will throw an error if the
timeout of 10m is reached.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Allocation<wbr>Strategy<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Indicates how to allocate the target capacity across
the Spot pools specified by the Spot fleet request. The default is
`lowestPrice`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Client<wbr>Token<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Excess<wbr>Capacity<wbr>Termination<wbr>Policy<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Indicates whether running Spot
instances should be terminated if the target capacity of the Spot fleet
request is decreased below the current size of the Spot fleet.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Fleet<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The type of fleet request. Indicates whether the Spot Fleet only requests the target
capacity or also attempts to maintain it. Default is `maintain`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Iam<wbr>Fleet<wbr>Role<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Grants the Spot fleet permission to terminate
Spot instances on your behalf when you cancel its Spot fleet request using
CancelSpotFleetRequests or when the Spot fleet request expires, if you set
terminateInstancesWithExpiration.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Instance<wbr>Interruption<wbr>Behaviour<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Indicates whether a Spot
instance stops or terminates when it is interrupted. Default is
`terminate`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Instance<wbr>Pools<wbr>To<wbr>Use<wbr>Count<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}
The number of Spot pools across which to allocate your target Spot capacity.
Valid only when `allocation_strategy` is set to `lowestPrice`. Spot Fleet selects
the cheapest Spot pools and evenly allocates your target Spot capacity across
the number of Spot pools that you specify.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Launch<wbr>Specifications<span class="property-indicator"></span>
        <span class="property-type"><a href="#spotfleetrequestlaunchspecification">[]Spot<wbr>Fleet<wbr>Request<wbr>Launch<wbr>Specification</a></span>
    </dt>
    <dd>{{% md %}}Used to define the launch configuration of the
spot-fleet request. Can be specified multiple times to define different bids
across different markets and instance types.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Load<wbr>Balancers<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}A list of elastic load balancer names to add to the Spot fleet.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Replace<wbr>Unhealthy<wbr>Instances<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Indicates whether Spot fleet should replace unhealthy instances. Default `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Spot<wbr>Price<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The maximum bid price per unit hour.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Spot<wbr>Request<wbr>State<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The state of the Spot fleet request.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Target<wbr>Capacity<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The number of units to request. You can choose to set the
target capacity in terms of instances or a performance characteristic that is
important to your application workload, such as vCPUs, memory, or I/O.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Target<wbr>Group<wbr>Arns<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}A list of `aws.alb.TargetGroup` ARNs, for use with Application Load Balancing.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Terminate<wbr>Instances<wbr>With<wbr>Expiration<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Indicates whether running Spot
instances should be terminated when the Spot fleet request expires.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Valid<wbr>From<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The start date and time of the request, in UTC [RFC3339](https://tools.ietf.org/html/rfc3339#section-5.8) format(for example, YYYY-MM-DDTHH:MM:SSZ). The default is to start fulfilling the request immediately.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Valid<wbr>Until<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The end date and time of the request, in UTC [RFC3339](https://tools.ietf.org/html/rfc3339#section-5.8) format(for example, YYYY-MM-DDTHH:MM:SSZ). At this point, no new Spot instance requests are placed or enabled to fulfill the request. Defaults to 24 hours.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Wait<wbr>For<wbr>Fulfillment<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}If set, this provider will
wait for the Spot Request to be fulfilled, and will throw an error if the
timeout of 10m is reached.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">allocation<wbr>Strategy<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Indicates how to allocate the target capacity across
the Spot pools specified by the Spot fleet request. The default is
`lowestPrice`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">client<wbr>Token<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">excess<wbr>Capacity<wbr>Termination<wbr>Policy<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Indicates whether running Spot
instances should be terminated if the target capacity of the Spot fleet
request is decreased below the current size of the Spot fleet.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">fleet<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The type of fleet request. Indicates whether the Spot Fleet only requests the target
capacity or also attempts to maintain it. Default is `maintain`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">iam<wbr>Fleet<wbr>Role<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Grants the Spot fleet permission to terminate
Spot instances on your behalf when you cancel its Spot fleet request using
CancelSpotFleetRequests or when the Spot fleet request expires, if you set
terminateInstancesWithExpiration.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">instance<wbr>Interruption<wbr>Behaviour<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Indicates whether a Spot
instance stops or terminates when it is interrupted. Default is
`terminate`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">instance<wbr>Pools<wbr>To<wbr>Use<wbr>Count<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}
The number of Spot pools across which to allocate your target Spot capacity.
Valid only when `allocation_strategy` is set to `lowestPrice`. Spot Fleet selects
the cheapest Spot pools and evenly allocates your target Spot capacity across
the number of Spot pools that you specify.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">launch<wbr>Specifications<span class="property-indicator"></span>
        <span class="property-type"><a href="#spotfleetrequestlaunchspecification">Spot<wbr>Fleet<wbr>Request<wbr>Launch<wbr>Specification[]?</a></span>
    </dt>
    <dd>{{% md %}}Used to define the launch configuration of the
spot-fleet request. Can be specified multiple times to define different bids
across different markets and instance types.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">load<wbr>Balancers<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}A list of elastic load balancer names to add to the Spot fleet.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">replace<wbr>Unhealthy<wbr>Instances<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Indicates whether Spot fleet should replace unhealthy instances. Default `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">spot<wbr>Price<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The maximum bid price per unit hour.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">spot<wbr>Request<wbr>State<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The state of the Spot fleet request.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">target<wbr>Capacity<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The number of units to request. You can choose to set the
target capacity in terms of instances or a performance characteristic that is
important to your application workload, such as vCPUs, memory, or I/O.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">target<wbr>Group<wbr>Arns<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}A list of `aws.alb.TargetGroup` ARNs, for use with Application Load Balancing.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">terminate<wbr>Instances<wbr>With<wbr>Expiration<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Indicates whether running Spot
instances should be terminated when the Spot fleet request expires.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">valid<wbr>From<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The start date and time of the request, in UTC [RFC3339](https://tools.ietf.org/html/rfc3339#section-5.8) format(for example, YYYY-MM-DDTHH:MM:SSZ). The default is to start fulfilling the request immediately.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">valid<wbr>Until<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The end date and time of the request, in UTC [RFC3339](https://tools.ietf.org/html/rfc3339#section-5.8) format(for example, YYYY-MM-DDTHH:MM:SSZ). At this point, no new Spot instance requests are placed or enabled to fulfill the request. Defaults to 24 hours.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">wait<wbr>For<wbr>Fulfillment<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}If set, this provider will
wait for the Spot Request to be fulfilled, and will throw an error if the
timeout of 10m is reached.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">allocation_<wbr>strategy<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Indicates how to allocate the target capacity across
the Spot pools specified by the Spot fleet request. The default is
`lowestPrice`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">client_<wbr>token<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">excess_<wbr>capacity_<wbr>termination_<wbr>policy<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Indicates whether running Spot
instances should be terminated if the target capacity of the Spot fleet
request is decreased below the current size of the Spot fleet.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">fleet_<wbr>type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The type of fleet request. Indicates whether the Spot Fleet only requests the target
capacity or also attempts to maintain it. Default is `maintain`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">iam_<wbr>fleet_<wbr>role<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Grants the Spot fleet permission to terminate
Spot instances on your behalf when you cancel its Spot fleet request using
CancelSpotFleetRequests or when the Spot fleet request expires, if you set
terminateInstancesWithExpiration.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">instance_<wbr>interruption_<wbr>behaviour<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Indicates whether a Spot
instance stops or terminates when it is interrupted. Default is
`terminate`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">instance_<wbr>pools_<wbr>to_<wbr>use_<wbr>count<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}
The number of Spot pools across which to allocate your target Spot capacity.
Valid only when `allocation_strategy` is set to `lowestPrice`. Spot Fleet selects
the cheapest Spot pools and evenly allocates your target Spot capacity across
the number of Spot pools that you specify.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">launch_<wbr>specifications<span class="property-indicator"></span>
        <span class="property-type"><a href="#spotfleetrequestlaunchspecification">List[Spot<wbr>Fleet<wbr>Request<wbr>Launch<wbr>Specification]</a></span>
    </dt>
    <dd>{{% md %}}Used to define the launch configuration of the
spot-fleet request. Can be specified multiple times to define different bids
across different markets and instance types.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">load_<wbr>balancers<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}A list of elastic load balancer names to add to the Spot fleet.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">replace_<wbr>unhealthy_<wbr>instances<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Indicates whether Spot fleet should replace unhealthy instances. Default `false`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">spot_<wbr>price<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The maximum bid price per unit hour.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">spot_<wbr>request_<wbr>state<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The state of the Spot fleet request.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">target_<wbr>capacity<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The number of units to request. You can choose to set the
target capacity in terms of instances or a performance characteristic that is
important to your application workload, such as vCPUs, memory, or I/O.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">target_<wbr>group_<wbr>arns<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}A list of `aws.alb.TargetGroup` ARNs, for use with Application Load Balancing.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">terminate_<wbr>instances_<wbr>with_<wbr>expiration<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Indicates whether running Spot
instances should be terminated when the Spot fleet request expires.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">valid_<wbr>from<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The start date and time of the request, in UTC [RFC3339](https://tools.ietf.org/html/rfc3339#section-5.8) format(for example, YYYY-MM-DDTHH:MM:SSZ). The default is to start fulfilling the request immediately.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">valid_<wbr>until<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The end date and time of the request, in UTC [RFC3339](https://tools.ietf.org/html/rfc3339#section-5.8) format(for example, YYYY-MM-DDTHH:MM:SSZ). At this point, no new Spot instance requests are placed or enabled to fulfill the request. Defaults to 24 hours.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">wait_<wbr>for_<wbr>fulfillment<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}If set, this provider will
wait for the Spot Request to be fulfilled, and will throw an error if the
timeout of 10m is reached.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}







## Supporting Types

#### SpotFleetRequestLaunchSpecification
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#SpotFleetRequestLaunchSpecification">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#SpotFleetRequestLaunchSpecification">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ec2?tab=doc#SpotFleetRequestLaunchSpecificationArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ec2?tab=doc#SpotFleetRequestLaunchSpecificationOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ec2.SpotFleetRequestLaunchSpecificationArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ec2.SpotFleetRequestLaunchSpecification.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Ami<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Associate<wbr>Public<wbr>Ip<wbr>Address<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Availability<wbr>Zone<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ebs<wbr>Block<wbr>Devices<span class="property-indicator"></span>
        <span class="property-type"><a href="#spotfleetrequestlaunchspecificationebsblockdevice">List&lt;Spot<wbr>Fleet<wbr>Request<wbr>Launch<wbr>Specification<wbr>Ebs<wbr>Block<wbr>Device<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ebs<wbr>Optimized<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ephemeral<wbr>Block<wbr>Devices<span class="property-indicator"></span>
        <span class="property-type"><a href="#spotfleetrequestlaunchspecificationephemeralblockdevice">List&lt;Spot<wbr>Fleet<wbr>Request<wbr>Launch<wbr>Specification<wbr>Ephemeral<wbr>Block<wbr>Device<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Iam<wbr>Instance<wbr>Profile<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Iam<wbr>Instance<wbr>Profile<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Instance<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Key<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Monitoring<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Placement<wbr>Group<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Placement<wbr>Tenancy<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Root<wbr>Block<wbr>Devices<span class="property-indicator"></span>
        <span class="property-type"><a href="#spotfleetrequestlaunchspecificationrootblockdevice">List&lt;Spot<wbr>Fleet<wbr>Request<wbr>Launch<wbr>Specification<wbr>Root<wbr>Block<wbr>Device<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Spot<wbr>Price<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The maximum bid price per unit hour.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Subnet<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">User<wbr>Data<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Vpc<wbr>Security<wbr>Group<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Weighted<wbr>Capacity<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Ami<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Associate<wbr>Public<wbr>Ip<wbr>Address<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Availability<wbr>Zone<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ebs<wbr>Block<wbr>Devices<span class="property-indicator"></span>
        <span class="property-type"><a href="#spotfleetrequestlaunchspecificationebsblockdevice">[]Spot<wbr>Fleet<wbr>Request<wbr>Launch<wbr>Specification<wbr>Ebs<wbr>Block<wbr>Device</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ebs<wbr>Optimized<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ephemeral<wbr>Block<wbr>Devices<span class="property-indicator"></span>
        <span class="property-type"><a href="#spotfleetrequestlaunchspecificationephemeralblockdevice">[]Spot<wbr>Fleet<wbr>Request<wbr>Launch<wbr>Specification<wbr>Ephemeral<wbr>Block<wbr>Device</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Iam<wbr>Instance<wbr>Profile<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Iam<wbr>Instance<wbr>Profile<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Instance<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Key<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Monitoring<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Placement<wbr>Group<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Placement<wbr>Tenancy<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Root<wbr>Block<wbr>Devices<span class="property-indicator"></span>
        <span class="property-type"><a href="#spotfleetrequestlaunchspecificationrootblockdevice">[]Spot<wbr>Fleet<wbr>Request<wbr>Launch<wbr>Specification<wbr>Root<wbr>Block<wbr>Device</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Spot<wbr>Price<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The maximum bid price per unit hour.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Subnet<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">User<wbr>Data<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Vpc<wbr>Security<wbr>Group<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Weighted<wbr>Capacity<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">ami<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">associate<wbr>Public<wbr>Ip<wbr>Address<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">availability<wbr>Zone<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ebs<wbr>Block<wbr>Devices<span class="property-indicator"></span>
        <span class="property-type"><a href="#spotfleetrequestlaunchspecificationebsblockdevice">Spot<wbr>Fleet<wbr>Request<wbr>Launch<wbr>Specification<wbr>Ebs<wbr>Block<wbr>Device[]?</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ebs<wbr>Optimized<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ephemeral<wbr>Block<wbr>Devices<span class="property-indicator"></span>
        <span class="property-type"><a href="#spotfleetrequestlaunchspecificationephemeralblockdevice">Spot<wbr>Fleet<wbr>Request<wbr>Launch<wbr>Specification<wbr>Ephemeral<wbr>Block<wbr>Device[]?</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">iam<wbr>Instance<wbr>Profile<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">iam<wbr>Instance<wbr>Profile<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">instance<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">key<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">monitoring<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">placement<wbr>Group<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">placement<wbr>Tenancy<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">root<wbr>Block<wbr>Devices<span class="property-indicator"></span>
        <span class="property-type"><a href="#spotfleetrequestlaunchspecificationrootblockdevice">Spot<wbr>Fleet<wbr>Request<wbr>Launch<wbr>Specification<wbr>Root<wbr>Block<wbr>Device[]?</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">spot<wbr>Price<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The maximum bid price per unit hour.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">subnet<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">user<wbr>Data<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">vpc<wbr>Security<wbr>Group<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">weighted<wbr>Capacity<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">ami<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">associate_<wbr>public_<wbr>ip_<wbr>address<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">availability_<wbr>zone<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ebs_<wbr>block_<wbr>devices<span class="property-indicator"></span>
        <span class="property-type"><a href="#spotfleetrequestlaunchspecificationebsblockdevice">List[Spot<wbr>Fleet<wbr>Request<wbr>Launch<wbr>Specification<wbr>Ebs<wbr>Block<wbr>Device]</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ebs_<wbr>optimized<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ephemeral_<wbr>block_<wbr>devices<span class="property-indicator"></span>
        <span class="property-type"><a href="#spotfleetrequestlaunchspecificationephemeralblockdevice">List[Spot<wbr>Fleet<wbr>Request<wbr>Launch<wbr>Specification<wbr>Ephemeral<wbr>Block<wbr>Device]</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">iam_<wbr>instance_<wbr>profile<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">iam<wbr>Instance<wbr>Profile<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">instance_<wbr>type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">key_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">monitoring<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">placement_<wbr>group<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">placement_<wbr>tenancy<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">root_<wbr>block_<wbr>devices<span class="property-indicator"></span>
        <span class="property-type"><a href="#spotfleetrequestlaunchspecificationrootblockdevice">List[Spot<wbr>Fleet<wbr>Request<wbr>Launch<wbr>Specification<wbr>Root<wbr>Block<wbr>Device]</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">spot_<wbr>price<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The maximum bid price per unit hour.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">subnet_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}A mapping of tags to assign to the resource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">user_<wbr>data<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">vpc_<wbr>security_<wbr>group_<wbr>ids<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">weighted<wbr>Capacity<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### SpotFleetRequestLaunchSpecificationEbsBlockDevice
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#SpotFleetRequestLaunchSpecificationEbsBlockDevice">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#SpotFleetRequestLaunchSpecificationEbsBlockDevice">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ec2?tab=doc#SpotFleetRequestLaunchSpecificationEbsBlockDeviceArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ec2?tab=doc#SpotFleetRequestLaunchSpecificationEbsBlockDeviceOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ec2.SpotFleetRequestLaunchSpecificationEbsBlockDeviceArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ec2.SpotFleetRequestLaunchSpecificationEbsBlockDevice.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Delete<wbr>On<wbr>Termination<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Device<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Encrypted<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Iops<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Kms<wbr>Key<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Snapshot<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Volume<wbr>Size<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Volume<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Delete<wbr>On<wbr>Termination<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Device<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Encrypted<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Iops<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Kms<wbr>Key<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Snapshot<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Volume<wbr>Size<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Volume<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">delete<wbr>On<wbr>Termination<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">device<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">encrypted<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">iops<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">kms<wbr>Key<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">snapshot<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">volume<wbr>Size<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">volume<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">delete<wbr>On<wbr>Termination<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">device_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">encrypted<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">iops<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">kms_<wbr>key_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">snapshot_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">volume_<wbr>size<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">volume<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### SpotFleetRequestLaunchSpecificationEphemeralBlockDevice
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#SpotFleetRequestLaunchSpecificationEphemeralBlockDevice">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#SpotFleetRequestLaunchSpecificationEphemeralBlockDevice">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ec2?tab=doc#SpotFleetRequestLaunchSpecificationEphemeralBlockDeviceArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ec2?tab=doc#SpotFleetRequestLaunchSpecificationEphemeralBlockDeviceOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ec2.SpotFleetRequestLaunchSpecificationEphemeralBlockDeviceArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ec2.SpotFleetRequestLaunchSpecificationEphemeralBlockDevice.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Device<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Virtual<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Device<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Virtual<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">device<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">virtual<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">device_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">virtual<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### SpotFleetRequestLaunchSpecificationRootBlockDevice
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#SpotFleetRequestLaunchSpecificationRootBlockDevice">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#SpotFleetRequestLaunchSpecificationRootBlockDevice">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ec2?tab=doc#SpotFleetRequestLaunchSpecificationRootBlockDeviceArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/ec2?tab=doc#SpotFleetRequestLaunchSpecificationRootBlockDeviceOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ec2.SpotFleetRequestLaunchSpecificationRootBlockDeviceArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Ec2.SpotFleetRequestLaunchSpecificationRootBlockDevice.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Delete<wbr>On<wbr>Termination<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Encrypted<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Iops<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Kms<wbr>Key<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Volume<wbr>Size<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Volume<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Delete<wbr>On<wbr>Termination<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Encrypted<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Iops<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Kms<wbr>Key<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Volume<wbr>Size<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Volume<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">delete<wbr>On<wbr>Termination<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">encrypted<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">iops<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">kms<wbr>Key<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">volume<wbr>Size<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">volume<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">delete<wbr>On<wbr>Termination<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">encrypted<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">iops<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">kms_<wbr>key_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">volume_<wbr>size<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">volume<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}








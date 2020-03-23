
---
title: "ComputeEnvironment"
block_external_search_index: true
---

Creates a AWS Batch compute environment. Compute environments contain the Amazon ECS container instances that are used to run containerized batch jobs.

For information about AWS Batch, see [What is AWS Batch?][1] .
For information about compute environment, see [Compute Environments][2] .

> **Note:** To prevent a race condition during environment deletion, make sure to set `depends_on` to the related `aws.iam.RolePolicyAttachment`;
otherwise, the policy may be destroyed too soon and the compute environment will then get stuck in the `DELETING` state, see [Troubleshooting AWS Batch][3] .

## Example Usage

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const ecsInstanceRoleRole = new aws.iam.Role("ecs_instance_role", {
    assumeRolePolicy: `{
    "Version": "2012-10-17",
    "Statement": [
	{
	    "Action": "sts:AssumeRole",
	    "Effect": "Allow",
	    "Principal": {
		"Service": "ec2.amazonaws.com"
	    }
	}
    ]
}
`,
});
const ecsInstanceRoleRolePolicyAttachment = new aws.iam.RolePolicyAttachment("ecs_instance_role", {
    policyArn: "arn:aws:iam::aws:policy/service-role/AmazonEC2ContainerServiceforEC2Role",
    role: ecsInstanceRoleRole.name,
});
const ecsInstanceRoleInstanceProfile = new aws.iam.InstanceProfile("ecs_instance_role", {
    role: ecsInstanceRoleRole.name,
});
const awsBatchServiceRoleRole = new aws.iam.Role("aws_batch_service_role", {
    assumeRolePolicy: `{
    "Version": "2012-10-17",
    "Statement": [
	{
	    "Action": "sts:AssumeRole",
	    "Effect": "Allow",
	    "Principal": {
		"Service": "batch.amazonaws.com"
	    }
	}
    ]
}
`,
});
const awsBatchServiceRoleRolePolicyAttachment = new aws.iam.RolePolicyAttachment("aws_batch_service_role", {
    policyArn: "arn:aws:iam::aws:policy/service-role/AWSBatchServiceRole",
    role: awsBatchServiceRoleRole.name,
});
const sampleSecurityGroup = new aws.ec2.SecurityGroup("sample", {
    egress: [{
        cidrBlocks: ["0.0.0.0/0"],
        fromPort: 0,
        protocol: "-1",
        toPort: 0,
    }],
});
const sampleVpc = new aws.ec2.Vpc("sample", {
    cidrBlock: "10.1.0.0/16",
});
const sampleSubnet = new aws.ec2.Subnet("sample", {
    cidrBlock: "10.1.1.0/24",
    vpcId: sampleVpc.id,
});
const sampleComputeEnvironment = new aws.batch.ComputeEnvironment("sample", {
    computeEnvironmentName: "sample",
    computeResources: {
        instanceRole: ecsInstanceRoleInstanceProfile.arn,
        instanceTypes: ["c4.large"],
        maxVcpus: 16,
        minVcpus: 0,
        securityGroupIds: [sampleSecurityGroup.id],
        subnets: [sampleSubnet.id],
        type: "EC2",
    },
    serviceRole: awsBatchServiceRoleRole.arn,
    type: "MANAGED",
}, {dependsOn: [awsBatchServiceRoleRolePolicyAttachment]});
```

> This content is derived from https://github.com/terraform-providers/terraform-provider-aws/blob/master/website/docs/r/batch_compute_environment.html.markdown.



## Create a ComputeEnvironment Resource

{{< chooser language "javascript,typescript,python,go,csharp" / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/batch/#ComputeEnvironment">ComputeEnvironment</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/batch/#ComputeEnvironmentArgs">ComputeEnvironmentArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">ComputeEnvironment</span><span class="p">(resource_name, opts=None, </span>compute_environment_name=None<span class="p">, </span>compute_environment_name_prefix=None<span class="p">, </span>compute_resources=None<span class="p">, </span>service_role=None<span class="p">, </span>state=None<span class="p">, </span>type=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewComputeEnvironment<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/batch?tab=doc#ComputeEnvironmentArgs">ComputeEnvironmentArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/batch?tab=doc#ComputeEnvironment">ComputeEnvironment</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Batch.ComputeEnvironment.html">ComputeEnvironment</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Batch.ComputeEnvironmentArgs.html">ComputeEnvironmentArgs</a></span> <span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
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
            title="Optional">Compute<wbr>Environment<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Compute<wbr>Environment<wbr>Name<wbr>Prefix<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Creates a unique compute environment name beginning with the specified prefix. Conflicts with `compute_environment_name`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Compute<wbr>Resources<span class="property-indicator"></span>
        <span class="property-type"><a href="#computeenvironmentcomputeresources">Compute<wbr>Environment<wbr>Compute<wbr>Resources<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}Details of the compute resources managed by the compute environment. This parameter is required for managed compute environments. See details below.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Service<wbr>Role<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The full Amazon Resource Name (ARN) of the IAM role that allows AWS Batch to make calls to other AWS services on your behalf.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">State<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The state of the compute environment. If the state is `ENABLED`, then the compute environment accepts jobs from a queue and can scale out automatically based on queues. Valid items are `ENABLED` or `DISABLED`. Defaults to `ENABLED`.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type of compute environment. Valid items are `EC2` or `SPOT`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Compute<wbr>Environment<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Compute<wbr>Environment<wbr>Name<wbr>Prefix<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Creates a unique compute environment name beginning with the specified prefix. Conflicts with `compute_environment_name`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Compute<wbr>Resources<span class="property-indicator"></span>
        <span class="property-type"><a href="#computeenvironmentcomputeresources">*Compute<wbr>Environment<wbr>Compute<wbr>Resources</a></span>
    </dt>
    <dd>{{% md %}}Details of the compute resources managed by the compute environment. This parameter is required for managed compute environments. See details below.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Service<wbr>Role<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The full Amazon Resource Name (ARN) of the IAM role that allows AWS Batch to make calls to other AWS services on your behalf.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">State<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The state of the compute environment. If the state is `ENABLED`, then the compute environment accepts jobs from a queue and can scale out automatically based on queues. Valid items are `ENABLED` or `DISABLED`. Defaults to `ENABLED`.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type of compute environment. Valid items are `EC2` or `SPOT`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">compute<wbr>Environment<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">compute<wbr>Environment<wbr>Name<wbr>Prefix<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Creates a unique compute environment name beginning with the specified prefix. Conflicts with `compute_environment_name`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">compute<wbr>Resources<span class="property-indicator"></span>
        <span class="property-type"><a href="#computeenvironmentcomputeresources">Compute<wbr>Environment<wbr>Compute<wbr>Resources?</a></span>
    </dt>
    <dd>{{% md %}}Details of the compute resources managed by the compute environment. This parameter is required for managed compute environments. See details below.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">service<wbr>Role<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The full Amazon Resource Name (ARN) of the IAM role that allows AWS Batch to make calls to other AWS services on your behalf.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">state<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The state of the compute environment. If the state is `ENABLED`, then the compute environment accepts jobs from a queue and can scale out automatically based on queues. Valid items are `ENABLED` or `DISABLED`. Defaults to `ENABLED`.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type of compute environment. Valid items are `EC2` or `SPOT`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">compute_<wbr>environment_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">compute_<wbr>environment_<wbr>name_<wbr>prefix<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Creates a unique compute environment name beginning with the specified prefix. Conflicts with `compute_environment_name`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">compute_<wbr>resources<span class="property-indicator"></span>
        <span class="property-type"><a href="#computeenvironmentcomputeresources">Dict[Compute<wbr>Environment<wbr>Compute<wbr>Resources]</a></span>
    </dt>
    <dd>{{% md %}}Details of the compute resources managed by the compute environment. This parameter is required for managed compute environments. See details below.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">service_<wbr>role<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The full Amazon Resource Name (ARN) of the IAM role that allows AWS Batch to make calls to other AWS services on your behalf.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">state<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The state of the compute environment. If the state is `ENABLED`, then the compute environment accepts jobs from a queue and can scale out automatically based on queues. Valid items are `ENABLED` or `DISABLED`. Defaults to `ENABLED`.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The type of compute environment. Valid items are `EC2` or `SPOT`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}




## ComputeEnvironment Output Properties

The following output properties are available:




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Amazon Resource Name (ARN) of the compute environment.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Compute<wbr>Environment<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">Compute<wbr>Environment<wbr>Name<wbr>Prefix<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Creates a unique compute environment name beginning with the specified prefix. Conflicts with `compute_environment_name`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Compute<wbr>Resources<span class="property-indicator"></span>
        <span class="property-type"><a href="#computeenvironmentcomputeresources">Compute<wbr>Environment<wbr>Compute<wbr>Resources?</a></span>
    </dt>
    <dd>{{% md %}}Details of the compute resources managed by the compute environment. This parameter is required for managed compute environments. See details below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Ecs<wbr>Cluster<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Amazon Resource Name (ARN) of the underlying Amazon ECS cluster used by the compute environment.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Service<wbr>Role<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The full Amazon Resource Name (ARN) of the IAM role that allows AWS Batch to make calls to other AWS services on your behalf.
{{% /md %}}</dd>

    <dt class="property-"
            title="">State<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The state of the compute environment. If the state is `ENABLED`, then the compute environment accepts jobs from a queue and can scale out automatically based on queues. Valid items are `ENABLED` or `DISABLED`. Defaults to `ENABLED`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Status<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The current status of the compute environment (for example, CREATING or VALID).
{{% /md %}}</dd>

    <dt class="property-"
            title="">Status<wbr>Reason<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}A short, human-readable string to provide additional details about the current status of the compute environment.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type of compute environment. Valid items are `EC2` or `SPOT`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Amazon Resource Name (ARN) of the compute environment.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Compute<wbr>Environment<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">Compute<wbr>Environment<wbr>Name<wbr>Prefix<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Creates a unique compute environment name beginning with the specified prefix. Conflicts with `compute_environment_name`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Compute<wbr>Resources<span class="property-indicator"></span>
        <span class="property-type"><a href="#computeenvironmentcomputeresources">*Compute<wbr>Environment<wbr>Compute<wbr>Resources</a></span>
    </dt>
    <dd>{{% md %}}Details of the compute resources managed by the compute environment. This parameter is required for managed compute environments. See details below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Ecs<wbr>Cluster<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Amazon Resource Name (ARN) of the underlying Amazon ECS cluster used by the compute environment.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Service<wbr>Role<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The full Amazon Resource Name (ARN) of the IAM role that allows AWS Batch to make calls to other AWS services on your behalf.
{{% /md %}}</dd>

    <dt class="property-"
            title="">State<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The state of the compute environment. If the state is `ENABLED`, then the compute environment accepts jobs from a queue and can scale out automatically based on queues. Valid items are `ENABLED` or `DISABLED`. Defaults to `ENABLED`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Status<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The current status of the compute environment (for example, CREATING or VALID).
{{% /md %}}</dd>

    <dt class="property-"
            title="">Status<wbr>Reason<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}A short, human-readable string to provide additional details about the current status of the compute environment.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type of compute environment. Valid items are `EC2` or `SPOT`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Amazon Resource Name (ARN) of the compute environment.
{{% /md %}}</dd>

    <dt class="property-"
            title="">compute<wbr>Environment<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">compute<wbr>Environment<wbr>Name<wbr>Prefix<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Creates a unique compute environment name beginning with the specified prefix. Conflicts with `compute_environment_name`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">compute<wbr>Resources<span class="property-indicator"></span>
        <span class="property-type"><a href="#computeenvironmentcomputeresources">Compute<wbr>Environment<wbr>Compute<wbr>Resources?</a></span>
    </dt>
    <dd>{{% md %}}Details of the compute resources managed by the compute environment. This parameter is required for managed compute environments. See details below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">ecs<wbr>Cluster<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Amazon Resource Name (ARN) of the underlying Amazon ECS cluster used by the compute environment.
{{% /md %}}</dd>

    <dt class="property-"
            title="">service<wbr>Role<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The full Amazon Resource Name (ARN) of the IAM role that allows AWS Batch to make calls to other AWS services on your behalf.
{{% /md %}}</dd>

    <dt class="property-"
            title="">state<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The state of the compute environment. If the state is `ENABLED`, then the compute environment accepts jobs from a queue and can scale out automatically based on queues. Valid items are `ENABLED` or `DISABLED`. Defaults to `ENABLED`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">status<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The current status of the compute environment (for example, CREATING or VALID).
{{% /md %}}</dd>

    <dt class="property-"
            title="">status<wbr>Reason<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}A short, human-readable string to provide additional details about the current status of the compute environment.
{{% /md %}}</dd>

    <dt class="property-"
            title="">type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type of compute environment. Valid items are `EC2` or `SPOT`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The Amazon Resource Name (ARN) of the compute environment.
{{% /md %}}</dd>

    <dt class="property-"
            title="">compute_<wbr>environment_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">compute_<wbr>environment_<wbr>name_<wbr>prefix<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Creates a unique compute environment name beginning with the specified prefix. Conflicts with `compute_environment_name`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">compute_<wbr>resources<span class="property-indicator"></span>
        <span class="property-type"><a href="#computeenvironmentcomputeresources">Dict[Compute<wbr>Environment<wbr>Compute<wbr>Resources]</a></span>
    </dt>
    <dd>{{% md %}}Details of the compute resources managed by the compute environment. This parameter is required for managed compute environments. See details below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">ecs_<wbr>cluster_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The Amazon Resource Name (ARN) of the underlying Amazon ECS cluster used by the compute environment.
{{% /md %}}</dd>

    <dt class="property-"
            title="">service_<wbr>role<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The full Amazon Resource Name (ARN) of the IAM role that allows AWS Batch to make calls to other AWS services on your behalf.
{{% /md %}}</dd>

    <dt class="property-"
            title="">state<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The state of the compute environment. If the state is `ENABLED`, then the compute environment accepts jobs from a queue and can scale out automatically based on queues. Valid items are `ENABLED` or `DISABLED`. Defaults to `ENABLED`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">status<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The current status of the compute environment (for example, CREATING or VALID).
{{% /md %}}</dd>

    <dt class="property-"
            title="">status_<wbr>reason<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A short, human-readable string to provide additional details about the current status of the compute environment.
{{% /md %}}</dd>

    <dt class="property-"
            title="">type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The type of compute environment. Valid items are `EC2` or `SPOT`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





## Look up an Existing ComputeEnvironment Resource

{{< chooser language "javascript,typescript,python,go,csharp  " / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">pulumi.Input&lt;pulumi.ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/batch/#ComputeEnvironmentState">ComputeEnvironmentState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/batch/#ComputeEnvironment">ComputeEnvironment</a></span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>arn=None<span class="p">, </span>compute_environment_name=None<span class="p">, </span>compute_environment_name_prefix=None<span class="p">, </span>compute_resources=None<span class="p">, </span>ecs_cluster_arn=None<span class="p">, </span>service_role=None<span class="p">, </span>state=None<span class="p">, </span>status=None<span class="p">, </span>status_reason=None<span class="p">, </span>type=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetComputeEnvironment<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">pulumi.IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/batch?tab=doc#ComputeEnvironmentState">ComputeEnvironmentState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/batch?tab=doc#ComputeEnvironment">ComputeEnvironment</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Batch.ComputeEnvironment.html">ComputeEnvironment</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Pulumi.Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Batch.ComputeEnvironmentState.html">ComputeEnvironmentState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
{{% /choosable %}}

Get an existing ComputeEnvironment resource's state with the given name, ID, and optional extra properties used to qualify the lookup.

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
    <dd>{{% md %}}The Amazon Resource Name (ARN) of the compute environment.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Compute<wbr>Environment<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Compute<wbr>Environment<wbr>Name<wbr>Prefix<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Creates a unique compute environment name beginning with the specified prefix. Conflicts with `compute_environment_name`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Compute<wbr>Resources<span class="property-indicator"></span>
        <span class="property-type"><a href="#computeenvironmentcomputeresources">Compute<wbr>Environment<wbr>Compute<wbr>Resources<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}Details of the compute resources managed by the compute environment. This parameter is required for managed compute environments. See details below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ecs<wbr>Cluster<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The Amazon Resource Name (ARN) of the underlying Amazon ECS cluster used by the compute environment.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Service<wbr>Role<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The full Amazon Resource Name (ARN) of the IAM role that allows AWS Batch to make calls to other AWS services on your behalf.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">State<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The state of the compute environment. If the state is `ENABLED`, then the compute environment accepts jobs from a queue and can scale out automatically based on queues. Valid items are `ENABLED` or `DISABLED`. Defaults to `ENABLED`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Status<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The current status of the compute environment (for example, CREATING or VALID).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Status<wbr>Reason<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A short, human-readable string to provide additional details about the current status of the compute environment.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The type of compute environment. Valid items are `EC2` or `SPOT`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The Amazon Resource Name (ARN) of the compute environment.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Compute<wbr>Environment<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Compute<wbr>Environment<wbr>Name<wbr>Prefix<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Creates a unique compute environment name beginning with the specified prefix. Conflicts with `compute_environment_name`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Compute<wbr>Resources<span class="property-indicator"></span>
        <span class="property-type"><a href="#computeenvironmentcomputeresources">*Compute<wbr>Environment<wbr>Compute<wbr>Resources</a></span>
    </dt>
    <dd>{{% md %}}Details of the compute resources managed by the compute environment. This parameter is required for managed compute environments. See details below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ecs<wbr>Cluster<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The Amazon Resource Name (ARN) of the underlying Amazon ECS cluster used by the compute environment.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Service<wbr>Role<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The full Amazon Resource Name (ARN) of the IAM role that allows AWS Batch to make calls to other AWS services on your behalf.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">State<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The state of the compute environment. If the state is `ENABLED`, then the compute environment accepts jobs from a queue and can scale out automatically based on queues. Valid items are `ENABLED` or `DISABLED`. Defaults to `ENABLED`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Status<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The current status of the compute environment (for example, CREATING or VALID).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Status<wbr>Reason<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}A short, human-readable string to provide additional details about the current status of the compute environment.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Type<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The type of compute environment. Valid items are `EC2` or `SPOT`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The Amazon Resource Name (ARN) of the compute environment.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">compute<wbr>Environment<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">compute<wbr>Environment<wbr>Name<wbr>Prefix<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Creates a unique compute environment name beginning with the specified prefix. Conflicts with `compute_environment_name`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">compute<wbr>Resources<span class="property-indicator"></span>
        <span class="property-type"><a href="#computeenvironmentcomputeresources">Compute<wbr>Environment<wbr>Compute<wbr>Resources?</a></span>
    </dt>
    <dd>{{% md %}}Details of the compute resources managed by the compute environment. This parameter is required for managed compute environments. See details below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ecs<wbr>Cluster<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The Amazon Resource Name (ARN) of the underlying Amazon ECS cluster used by the compute environment.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">service<wbr>Role<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The full Amazon Resource Name (ARN) of the IAM role that allows AWS Batch to make calls to other AWS services on your behalf.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">state<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The state of the compute environment. If the state is `ENABLED`, then the compute environment accepts jobs from a queue and can scale out automatically based on queues. Valid items are `ENABLED` or `DISABLED`. Defaults to `ENABLED`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">status<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The current status of the compute environment (for example, CREATING or VALID).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">status<wbr>Reason<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A short, human-readable string to provide additional details about the current status of the compute environment.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The type of compute environment. Valid items are `EC2` or `SPOT`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The Amazon Resource Name (ARN) of the compute environment.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">compute_<wbr>environment_<wbr>name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">compute_<wbr>environment_<wbr>name_<wbr>prefix<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Creates a unique compute environment name beginning with the specified prefix. Conflicts with `compute_environment_name`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">compute_<wbr>resources<span class="property-indicator"></span>
        <span class="property-type"><a href="#computeenvironmentcomputeresources">Dict[Compute<wbr>Environment<wbr>Compute<wbr>Resources]</a></span>
    </dt>
    <dd>{{% md %}}Details of the compute resources managed by the compute environment. This parameter is required for managed compute environments. See details below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ecs_<wbr>cluster_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The Amazon Resource Name (ARN) of the underlying Amazon ECS cluster used by the compute environment.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">service_<wbr>role<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The full Amazon Resource Name (ARN) of the IAM role that allows AWS Batch to make calls to other AWS services on your behalf.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">state<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The state of the compute environment. If the state is `ENABLED`, then the compute environment accepts jobs from a queue and can scale out automatically based on queues. Valid items are `ENABLED` or `DISABLED`. Defaults to `ENABLED`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">status<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The current status of the compute environment (for example, CREATING or VALID).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">status_<wbr>reason<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A short, human-readable string to provide additional details about the current status of the compute environment.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The type of compute environment. Valid items are `EC2` or `SPOT`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}







## Supporting Types

#### ComputeEnvironmentComputeResources
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#ComputeEnvironmentComputeResources">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#ComputeEnvironmentComputeResources">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/batch?tab=doc#ComputeEnvironmentComputeResourcesArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/batch?tab=doc#ComputeEnvironmentComputeResourcesOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Batch.ComputeEnvironmentComputeResourcesArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Batch.ComputeEnvironmentComputeResources.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Allocation<wbr>Strategy<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The allocation strategy to use for the compute resource in case not enough instances of the best fitting instance type can be allocated. Valid items are `BEST_FIT_PROGRESSIVE`, `SPOT_CAPACITY_OPTIMIZED` or `BEST_FIT`. Defaults to `BEST_FIT`. See [AWS docs](https://docs.aws.amazon.com/batch/latest/userguide/allocation-strategies.html) for details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Bid<wbr>Percentage<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}Integer of minimum percentage that a Spot Instance price must be when compared with the On-Demand price for that instance type before instances are launched. For example, if your bid percentage is 20% (`20`), then the Spot price must be below 20% of the current On-Demand price for that EC2 instance. This parameter is required for SPOT compute environments.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Desired<wbr>Vcpus<span class="property-indicator"></span>
        <span class="property-type">int?</span>
    </dt>
    <dd>{{% md %}}The desired number of EC2 vCPUS in the compute environment.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ec2Key<wbr>Pair<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The EC2 key pair that is used for instances launched in the compute environment.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Image<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The Amazon Machine Image (AMI) ID used for instances launched in the compute environment.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Instance<wbr>Role<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Amazon ECS instance role applied to Amazon EC2 instances in a compute environment.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Instance<wbr>Types<span class="property-indicator"></span>
        <span class="property-type">List<string></span>
    </dt>
    <dd>{{% md %}}A list of instance types that may be launched.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Launch<wbr>Template<span class="property-indicator"></span>
        <span class="property-type"><a href="#computeenvironmentcomputeresourceslaunchtemplate">Compute<wbr>Environment<wbr>Compute<wbr>Resources<wbr>Launch<wbr>Template<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}The launch template to use for your compute resources. See details below.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Max<wbr>Vcpus<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The maximum number of EC2 vCPUs that an environment can reach.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Min<wbr>Vcpus<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The minimum number of EC2 vCPUs that an environment should maintain.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Security<wbr>Group<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">List<string></span>
    </dt>
    <dd>{{% md %}}A list of EC2 security group that are associated with instances launched in the compute environment.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Spot<wbr>Iam<wbr>Fleet<wbr>Role<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The Amazon Resource Name (ARN) of the Amazon EC2 Spot Fleet IAM role applied to a SPOT compute environment. This parameter is required for SPOT compute environments.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Subnets<span class="property-indicator"></span>
        <span class="property-type">List<string></span>
    </dt>
    <dd>{{% md %}}A list of VPC subnets into which the compute resources are launched.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}Key-value pair tags to be applied to resources that are launched in the compute environment.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type of compute environment. Valid items are `EC2` or `SPOT`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Allocation<wbr>Strategy<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The allocation strategy to use for the compute resource in case not enough instances of the best fitting instance type can be allocated. Valid items are `BEST_FIT_PROGRESSIVE`, `SPOT_CAPACITY_OPTIMIZED` or `BEST_FIT`. Defaults to `BEST_FIT`. See [AWS docs](https://docs.aws.amazon.com/batch/latest/userguide/allocation-strategies.html) for details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Bid<wbr>Percentage<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}Integer of minimum percentage that a Spot Instance price must be when compared with the On-Demand price for that instance type before instances are launched. For example, if your bid percentage is 20% (`20`), then the Spot price must be below 20% of the current On-Demand price for that EC2 instance. This parameter is required for SPOT compute environments.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Desired<wbr>Vcpus<span class="property-indicator"></span>
        <span class="property-type">*int</span>
    </dt>
    <dd>{{% md %}}The desired number of EC2 vCPUS in the compute environment.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Ec2Key<wbr>Pair<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The EC2 key pair that is used for instances launched in the compute environment.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Image<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The Amazon Machine Image (AMI) ID used for instances launched in the compute environment.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Instance<wbr>Role<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Amazon ECS instance role applied to Amazon EC2 instances in a compute environment.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Instance<wbr>Types<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}A list of instance types that may be launched.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Launch<wbr>Template<span class="property-indicator"></span>
        <span class="property-type"><a href="#computeenvironmentcomputeresourceslaunchtemplate">*Compute<wbr>Environment<wbr>Compute<wbr>Resources<wbr>Launch<wbr>Template</a></span>
    </dt>
    <dd>{{% md %}}The launch template to use for your compute resources. See details below.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Max<wbr>Vcpus<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The maximum number of EC2 vCPUs that an environment can reach.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Min<wbr>Vcpus<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}The minimum number of EC2 vCPUs that an environment should maintain.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Security<wbr>Group<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}A list of EC2 security group that are associated with instances launched in the compute environment.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Spot<wbr>Iam<wbr>Fleet<wbr>Role<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The Amazon Resource Name (ARN) of the Amazon EC2 Spot Fleet IAM role applied to a SPOT compute environment. This parameter is required for SPOT compute environments.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Subnets<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}A list of VPC subnets into which the compute resources are launched.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}Key-value pair tags to be applied to resources that are launched in the compute environment.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type of compute environment. Valid items are `EC2` or `SPOT`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">allocation<wbr>Strategy<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The allocation strategy to use for the compute resource in case not enough instances of the best fitting instance type can be allocated. Valid items are `BEST_FIT_PROGRESSIVE`, `SPOT_CAPACITY_OPTIMIZED` or `BEST_FIT`. Defaults to `BEST_FIT`. See [AWS docs](https://docs.aws.amazon.com/batch/latest/userguide/allocation-strategies.html) for details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">bid<wbr>Percentage<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}Integer of minimum percentage that a Spot Instance price must be when compared with the On-Demand price for that instance type before instances are launched. For example, if your bid percentage is 20% (`20`), then the Spot price must be below 20% of the current On-Demand price for that EC2 instance. This parameter is required for SPOT compute environments.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">desired<wbr>Vcpus<span class="property-indicator"></span>
        <span class="property-type">number?</span>
    </dt>
    <dd>{{% md %}}The desired number of EC2 vCPUS in the compute environment.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ec2Key<wbr>Pair<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The EC2 key pair that is used for instances launched in the compute environment.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">image<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The Amazon Machine Image (AMI) ID used for instances launched in the compute environment.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">instance<wbr>Role<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Amazon ECS instance role applied to Amazon EC2 instances in a compute environment.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">instance<wbr>Types<span class="property-indicator"></span>
        <span class="property-type">string[]</span>
    </dt>
    <dd>{{% md %}}A list of instance types that may be launched.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">launch<wbr>Template<span class="property-indicator"></span>
        <span class="property-type"><a href="#computeenvironmentcomputeresourceslaunchtemplate">Compute<wbr>Environment<wbr>Compute<wbr>Resources<wbr>Launch<wbr>Template?</a></span>
    </dt>
    <dd>{{% md %}}The launch template to use for your compute resources. See details below.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">max<wbr>Vcpus<span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}The maximum number of EC2 vCPUs that an environment can reach.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">min<wbr>Vcpus<span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}The minimum number of EC2 vCPUs that an environment should maintain.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">security<wbr>Group<wbr>Ids<span class="property-indicator"></span>
        <span class="property-type">string[]</span>
    </dt>
    <dd>{{% md %}}A list of EC2 security group that are associated with instances launched in the compute environment.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">spot<wbr>Iam<wbr>Fleet<wbr>Role<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The Amazon Resource Name (ARN) of the Amazon EC2 Spot Fleet IAM role applied to a SPOT compute environment. This parameter is required for SPOT compute environments.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">subnets<span class="property-indicator"></span>
        <span class="property-type">string[]</span>
    </dt>
    <dd>{{% md %}}A list of VPC subnets into which the compute resources are launched.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}Key-value pair tags to be applied to resources that are launched in the compute environment.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type of compute environment. Valid items are `EC2` or `SPOT`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">allocation_<wbr>strategy<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The allocation strategy to use for the compute resource in case not enough instances of the best fitting instance type can be allocated. Valid items are `BEST_FIT_PROGRESSIVE`, `SPOT_CAPACITY_OPTIMIZED` or `BEST_FIT`. Defaults to `BEST_FIT`. See [AWS docs](https://docs.aws.amazon.com/batch/latest/userguide/allocation-strategies.html) for details.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">bid<wbr>Percentage<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}Integer of minimum percentage that a Spot Instance price must be when compared with the On-Demand price for that instance type before instances are launched. For example, if your bid percentage is 20% (`20`), then the Spot price must be below 20% of the current On-Demand price for that EC2 instance. This parameter is required for SPOT compute environments.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">desired<wbr>Vcpus<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The desired number of EC2 vCPUS in the compute environment.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">ec2Key<wbr>Pair<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The EC2 key pair that is used for instances launched in the compute environment.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">image_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The Amazon Machine Image (AMI) ID used for instances launched in the compute environment.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">instance<wbr>Role<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The Amazon ECS instance role applied to Amazon EC2 instances in a compute environment.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">instance_<wbr>types<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}A list of instance types that may be launched.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">launch_<wbr>template<span class="property-indicator"></span>
        <span class="property-type"><a href="#computeenvironmentcomputeresourceslaunchtemplate">Dict[Compute<wbr>Environment<wbr>Compute<wbr>Resources<wbr>Launch<wbr>Template]</a></span>
    </dt>
    <dd>{{% md %}}The launch template to use for your compute resources. See details below.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">max<wbr>Vcpus<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The maximum number of EC2 vCPUs that an environment can reach.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">min<wbr>Vcpus<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}The minimum number of EC2 vCPUs that an environment should maintain.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">security_<wbr>group_<wbr>ids<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}A list of EC2 security group that are associated with instances launched in the compute environment.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">spot<wbr>Iam<wbr>Fleet<wbr>Role<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The Amazon Resource Name (ARN) of the Amazon EC2 Spot Fleet IAM role applied to a SPOT compute environment. This parameter is required for SPOT compute environments.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">subnets<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}A list of VPC subnets into which the compute resources are launched.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}Key-value pair tags to be applied to resources that are launched in the compute environment.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The type of compute environment. Valid items are `EC2` or `SPOT`.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### ComputeEnvironmentComputeResourcesLaunchTemplate
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#ComputeEnvironmentComputeResourcesLaunchTemplate">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#ComputeEnvironmentComputeResourcesLaunchTemplate">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/batch?tab=doc#ComputeEnvironmentComputeResourcesLaunchTemplateArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/batch?tab=doc#ComputeEnvironmentComputeResourcesLaunchTemplateOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Batch.ComputeEnvironmentComputeResourcesLaunchTemplateArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Batch.ComputeEnvironmentComputeResourcesLaunchTemplate.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Launch<wbr>Template<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}ID of the launch template. You must specify either the launch template ID or launch template name in the request, but not both.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Launch<wbr>Template<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Name of the launch template.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Version<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The version number of the launch template. Default: The default version of the launch template.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Launch<wbr>Template<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}ID of the launch template. You must specify either the launch template ID or launch template name in the request, but not both.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Launch<wbr>Template<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Name of the launch template.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Version<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The version number of the launch template. Default: The default version of the launch template.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">launch<wbr>Template<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}ID of the launch template. You must specify either the launch template ID or launch template name in the request, but not both.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">launch<wbr>Template<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Name of the launch template.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">version<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The version number of the launch template. Default: The default version of the launch template.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">launch<wbr>Template<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}ID of the launch template. You must specify either the launch template ID or launch template name in the request, but not both.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">launch<wbr>Template<wbr>Name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Name of the launch template.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">version<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The version number of the launch template. Default: The default version of the launch template.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}








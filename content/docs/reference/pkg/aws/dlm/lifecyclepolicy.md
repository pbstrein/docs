
---
title: "LifecyclePolicy"
block_external_search_index: true
---

Provides a [Data Lifecycle Manager (DLM) lifecycle policy](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/snapshot-lifecycle.html) for managing snapshots.

## Example Usage

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const dlmLifecycleRole = new aws.iam.Role("dlm_lifecycle_role", {
    assumeRolePolicy: `{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Action": "sts:AssumeRole",
      "Principal": {
        "Service": "dlm.amazonaws.com"
      },
      "Effect": "Allow",
      "Sid": ""
    }
  ]
}
`,
});
const dlmLifecycle = new aws.iam.RolePolicy("dlm_lifecycle", {
    policy: `{
   "Version": "2012-10-17",
   "Statement": [
      {
         "Effect": "Allow",
         "Action": [
            "ec2:CreateSnapshot",
            "ec2:DeleteSnapshot",
            "ec2:DescribeVolumes",
            "ec2:DescribeSnapshots"
         ],
         "Resource": "*"
      },
      {
         "Effect": "Allow",
         "Action": [
            "ec2:CreateTags"
         ],
         "Resource": "arn:aws:ec2:*::snapshot/*"
      }
   ]
}
`,
    role: dlmLifecycleRole.id,
});
const example = new aws.dlm.LifecyclePolicy("example", {
    description: "example DLM lifecycle policy",
    executionRoleArn: dlmLifecycleRole.arn,
    policyDetails: {
        resourceTypes: ["VOLUME"],
        schedules: [{
            copyTags: false,
            createRule: {
                interval: 24,
                intervalUnit: "HOURS",
                times: "23:45",
            },
            name: "2 weeks of daily snapshots",
            retainRule: {
                count: 14,
            },
            tagsToAdd: {
                SnapshotCreator: "DLM",
            },
        }],
        targetTags: {
            Snapshot: "true",
        },
    },
    state: "ENABLED",
});
```

> This content is derived from https://github.com/terraform-providers/terraform-provider-aws/blob/master/website/docs/r/dlm_lifecycle_policy.markdown.



## Create a LifecyclePolicy Resource

{{< chooser language "javascript,typescript,python,go,csharp" / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/dlm/#LifecyclePolicy">LifecyclePolicy</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/dlm/#LifecyclePolicyArgs">LifecyclePolicyArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">LifecyclePolicy</span><span class="p">(resource_name, opts=None, </span>description=None<span class="p">, </span>execution_role_arn=None<span class="p">, </span>policy_details=None<span class="p">, </span>state=None<span class="p">, </span>tags=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewLifecyclePolicy<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/dlm?tab=doc#LifecyclePolicyArgs">LifecyclePolicyArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/dlm?tab=doc#LifecyclePolicy">LifecyclePolicy</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Dlm.LifecyclePolicy.html">LifecyclePolicy</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Dlm.LifecyclePolicyArgs.html">LifecyclePolicyArgs</a></span> <span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
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

    <dt class="property-required"
            title="Required">Description<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}A description for the DLM lifecycle policy.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Execution<wbr>Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of an IAM role that is able to be assumed by the DLM service.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Policy<wbr>Details<span class="property-indicator"></span>
        <span class="property-type"><a href="#lifecyclepolicypolicydetails">Lifecycle<wbr>Policy<wbr>Policy<wbr>Details<wbr>Args</a></span>
    </dt>
    <dd>{{% md %}}See the `policy_details` configuration block. Max of 1.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">State<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Whether the lifecycle policy should be enabled or disabled. `ENABLED` or `DISABLED` are valid values. Defaults to `ENABLED`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}Key-value mapping of resource tags.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Description<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}A description for the DLM lifecycle policy.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Execution<wbr>Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of an IAM role that is able to be assumed by the DLM service.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Policy<wbr>Details<span class="property-indicator"></span>
        <span class="property-type"><a href="#lifecyclepolicypolicydetails">Lifecycle<wbr>Policy<wbr>Policy<wbr>Details</a></span>
    </dt>
    <dd>{{% md %}}See the `policy_details` configuration block. Max of 1.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">State<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Whether the lifecycle policy should be enabled or disabled. `ENABLED` or `DISABLED` are valid values. Defaults to `ENABLED`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}Key-value mapping of resource tags.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">description<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}A description for the DLM lifecycle policy.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">execution<wbr>Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of an IAM role that is able to be assumed by the DLM service.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">policy<wbr>Details<span class="property-indicator"></span>
        <span class="property-type"><a href="#lifecyclepolicypolicydetails">Lifecycle<wbr>Policy<wbr>Policy<wbr>Details</a></span>
    </dt>
    <dd>{{% md %}}See the `policy_details` configuration block. Max of 1.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">state<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Whether the lifecycle policy should be enabled or disabled. `ENABLED` or `DISABLED` are valid values. Defaults to `ENABLED`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}Key-value mapping of resource tags.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">description<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A description for the DLM lifecycle policy.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">execution_<wbr>role_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ARN of an IAM role that is able to be assumed by the DLM service.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">policy_<wbr>details<span class="property-indicator"></span>
        <span class="property-type"><a href="#lifecyclepolicypolicydetails">Dict[Lifecycle<wbr>Policy<wbr>Policy<wbr>Details]</a></span>
    </dt>
    <dd>{{% md %}}See the `policy_details` configuration block. Max of 1.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">state<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Whether the lifecycle policy should be enabled or disabled. `ENABLED` or `DISABLED` are valid values. Defaults to `ENABLED`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}Key-value mapping of resource tags.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}




## LifecyclePolicy Output Properties

The following output properties are available:




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of the DLM Lifecycle Policy.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Description<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}A description for the DLM lifecycle policy.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Execution<wbr>Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of an IAM role that is able to be assumed by the DLM service.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Policy<wbr>Details<span class="property-indicator"></span>
        <span class="property-type"><a href="#lifecyclepolicypolicydetails">Lifecycle<wbr>Policy<wbr>Policy<wbr>Details</a></span>
    </dt>
    <dd>{{% md %}}See the `policy_details` configuration block. Max of 1.
{{% /md %}}</dd>

    <dt class="property-"
            title="">State<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Whether the lifecycle policy should be enabled or disabled. `ENABLED` or `DISABLED` are valid values. Defaults to `ENABLED`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}Key-value mapping of resource tags.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of the DLM Lifecycle Policy.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Description<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}A description for the DLM lifecycle policy.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Execution<wbr>Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of an IAM role that is able to be assumed by the DLM service.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Policy<wbr>Details<span class="property-indicator"></span>
        <span class="property-type"><a href="#lifecyclepolicypolicydetails">Lifecycle<wbr>Policy<wbr>Policy<wbr>Details</a></span>
    </dt>
    <dd>{{% md %}}See the `policy_details` configuration block. Max of 1.
{{% /md %}}</dd>

    <dt class="property-"
            title="">State<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Whether the lifecycle policy should be enabled or disabled. `ENABLED` or `DISABLED` are valid values. Defaults to `ENABLED`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}Key-value mapping of resource tags.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of the DLM Lifecycle Policy.
{{% /md %}}</dd>

    <dt class="property-"
            title="">description<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}A description for the DLM lifecycle policy.
{{% /md %}}</dd>

    <dt class="property-"
            title="">execution<wbr>Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ARN of an IAM role that is able to be assumed by the DLM service.
{{% /md %}}</dd>

    <dt class="property-"
            title="">policy<wbr>Details<span class="property-indicator"></span>
        <span class="property-type"><a href="#lifecyclepolicypolicydetails">Lifecycle<wbr>Policy<wbr>Policy<wbr>Details</a></span>
    </dt>
    <dd>{{% md %}}See the `policy_details` configuration block. Max of 1.
{{% /md %}}</dd>

    <dt class="property-"
            title="">state<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Whether the lifecycle policy should be enabled or disabled. `ENABLED` or `DISABLED` are valid values. Defaults to `ENABLED`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}Key-value mapping of resource tags.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of the DLM Lifecycle Policy.
{{% /md %}}</dd>

    <dt class="property-"
            title="">description<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A description for the DLM lifecycle policy.
{{% /md %}}</dd>

    <dt class="property-"
            title="">execution_<wbr>role_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ARN of an IAM role that is able to be assumed by the DLM service.
{{% /md %}}</dd>

    <dt class="property-"
            title="">policy_<wbr>details<span class="property-indicator"></span>
        <span class="property-type"><a href="#lifecyclepolicypolicydetails">Dict[Lifecycle<wbr>Policy<wbr>Policy<wbr>Details]</a></span>
    </dt>
    <dd>{{% md %}}See the `policy_details` configuration block. Max of 1.
{{% /md %}}</dd>

    <dt class="property-"
            title="">state<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Whether the lifecycle policy should be enabled or disabled. `ENABLED` or `DISABLED` are valid values. Defaults to `ENABLED`.
{{% /md %}}</dd>

    <dt class="property-"
            title="">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}Key-value mapping of resource tags.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





## Look up an Existing LifecyclePolicy Resource

{{< chooser language "javascript,typescript,python,go,csharp  " / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">pulumi.Input&lt;pulumi.ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/dlm/#LifecyclePolicyState">LifecyclePolicyState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/dlm/#LifecyclePolicy">LifecyclePolicy</a></span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>arn=None<span class="p">, </span>description=None<span class="p">, </span>execution_role_arn=None<span class="p">, </span>policy_details=None<span class="p">, </span>state=None<span class="p">, </span>tags=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetLifecyclePolicy<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">pulumi.IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/dlm?tab=doc#LifecyclePolicyState">LifecyclePolicyState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/dlm?tab=doc#LifecyclePolicy">LifecyclePolicy</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Dlm.LifecyclePolicy.html">LifecyclePolicy</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Pulumi.Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Dlm.LifecyclePolicyState.html">LifecyclePolicyState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
{{% /choosable %}}

Get an existing LifecyclePolicy resource's state with the given name, ID, and optional extra properties used to qualify the lookup.

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
    <dd>{{% md %}}Amazon Resource Name (ARN) of the DLM Lifecycle Policy.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Description<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A description for the DLM lifecycle policy.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Execution<wbr>Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ARN of an IAM role that is able to be assumed by the DLM service.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Policy<wbr>Details<span class="property-indicator"></span>
        <span class="property-type"><a href="#lifecyclepolicypolicydetails">Lifecycle<wbr>Policy<wbr>Policy<wbr>Details<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}See the `policy_details` configuration block. Max of 1.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">State<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Whether the lifecycle policy should be enabled or disabled. `ENABLED` or `DISABLED` are valid values. Defaults to `ENABLED`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}Key-value mapping of resource tags.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of the DLM Lifecycle Policy.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Description<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}A description for the DLM lifecycle policy.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Execution<wbr>Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The ARN of an IAM role that is able to be assumed by the DLM service.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Policy<wbr>Details<span class="property-indicator"></span>
        <span class="property-type"><a href="#lifecyclepolicypolicydetails">*Lifecycle<wbr>Policy<wbr>Policy<wbr>Details</a></span>
    </dt>
    <dd>{{% md %}}See the `policy_details` configuration block. Max of 1.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">State<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Whether the lifecycle policy should be enabled or disabled. `ENABLED` or `DISABLED` are valid values. Defaults to `ENABLED`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}Key-value mapping of resource tags.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of the DLM Lifecycle Policy.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">description<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A description for the DLM lifecycle policy.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">execution<wbr>Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ARN of an IAM role that is able to be assumed by the DLM service.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">policy<wbr>Details<span class="property-indicator"></span>
        <span class="property-type"><a href="#lifecyclepolicypolicydetails">Lifecycle<wbr>Policy<wbr>Policy<wbr>Details?</a></span>
    </dt>
    <dd>{{% md %}}See the `policy_details` configuration block. Max of 1.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">state<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Whether the lifecycle policy should be enabled or disabled. `ENABLED` or `DISABLED` are valid values. Defaults to `ENABLED`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}Key-value mapping of resource tags.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Amazon Resource Name (ARN) of the DLM Lifecycle Policy.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">description<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A description for the DLM lifecycle policy.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">execution_<wbr>role_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ARN of an IAM role that is able to be assumed by the DLM service.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">policy_<wbr>details<span class="property-indicator"></span>
        <span class="property-type"><a href="#lifecyclepolicypolicydetails">Dict[Lifecycle<wbr>Policy<wbr>Policy<wbr>Details]</a></span>
    </dt>
    <dd>{{% md %}}See the `policy_details` configuration block. Max of 1.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">state<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Whether the lifecycle policy should be enabled or disabled. `ENABLED` or `DISABLED` are valid values. Defaults to `ENABLED`.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}Key-value mapping of resource tags.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}







## Supporting Types

#### LifecyclePolicyPolicyDetails
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#LifecyclePolicyPolicyDetails">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#LifecyclePolicyPolicyDetails">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/dlm?tab=doc#LifecyclePolicyPolicyDetailsArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/dlm?tab=doc#LifecyclePolicyPolicyDetailsOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Dlm.LifecyclePolicyPolicyDetailsArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Dlm.LifecyclePolicyPolicyDetails.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Resource<wbr>Types<span class="property-indicator"></span>
        <span class="property-type">List<string></span>
    </dt>
    <dd>{{% md %}}A list of resource types that should be targeted by the lifecycle policy. `VOLUME` is currently the only allowed value.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Schedules<span class="property-indicator"></span>
        <span class="property-type"><a href="#lifecyclepolicypolicydetailsschedule">List&lt;Lifecycle<wbr>Policy<wbr>Policy<wbr>Details<wbr>Schedule<wbr>Args&gt;</a></span>
    </dt>
    <dd>{{% md %}}See the `schedule` configuration block.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Target<wbr>Tags<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object></span>
    </dt>
    <dd>{{% md %}}A mapping of tag keys and their values. Any resources that match the `resource_types` and are tagged with _any_ of these tags will be targeted.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Resource<wbr>Types<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}A list of resource types that should be targeted by the lifecycle policy. `VOLUME` is currently the only allowed value.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Schedules<span class="property-indicator"></span>
        <span class="property-type"><a href="#lifecyclepolicypolicydetailsschedule">[]Lifecycle<wbr>Policy<wbr>Policy<wbr>Details<wbr>Schedule</a></span>
    </dt>
    <dd>{{% md %}}See the `schedule` configuration block.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Target<wbr>Tags<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}A mapping of tag keys and their values. Any resources that match the `resource_types` and are tagged with _any_ of these tags will be targeted.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">resource<wbr>Types<span class="property-indicator"></span>
        <span class="property-type">string[]</span>
    </dt>
    <dd>{{% md %}}A list of resource types that should be targeted by the lifecycle policy. `VOLUME` is currently the only allowed value.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">schedules<span class="property-indicator"></span>
        <span class="property-type"><a href="#lifecyclepolicypolicydetailsschedule">Lifecycle<wbr>Policy<wbr>Policy<wbr>Details<wbr>Schedule[]</a></span>
    </dt>
    <dd>{{% md %}}See the `schedule` configuration block.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">target<wbr>Tags<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}</span>
    </dt>
    <dd>{{% md %}}A mapping of tag keys and their values. Any resources that match the `resource_types` and are tagged with _any_ of these tags will be targeted.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">resource<wbr>Types<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}A list of resource types that should be targeted by the lifecycle policy. `VOLUME` is currently the only allowed value.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">schedules<span class="property-indicator"></span>
        <span class="property-type"><a href="#lifecyclepolicypolicydetailsschedule">List[Lifecycle<wbr>Policy<wbr>Policy<wbr>Details<wbr>Schedule]</a></span>
    </dt>
    <dd>{{% md %}}See the `schedule` configuration block.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">target<wbr>Tags<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}A mapping of tag keys and their values. Any resources that match the `resource_types` and are tagged with _any_ of these tags will be targeted.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### LifecyclePolicyPolicyDetailsSchedule
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#LifecyclePolicyPolicyDetailsSchedule">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#LifecyclePolicyPolicyDetailsSchedule">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/dlm?tab=doc#LifecyclePolicyPolicyDetailsScheduleArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/dlm?tab=doc#LifecyclePolicyPolicyDetailsScheduleOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Dlm.LifecyclePolicyPolicyDetailsScheduleArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Dlm.LifecyclePolicyPolicyDetailsSchedule.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Copy<wbr>Tags<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Copy all user-defined tags on a source volume to snapshots of the volume created by this policy.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Create<wbr>Rule<span class="property-indicator"></span>
        <span class="property-type"><a href="#lifecyclepolicypolicydetailsschedulecreaterule">Lifecycle<wbr>Policy<wbr>Policy<wbr>Details<wbr>Schedule<wbr>Create<wbr>Rule<wbr>Args</a></span>
    </dt>
    <dd>{{% md %}}See the `create_rule` block. Max of 1 per schedule.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}A name for the schedule.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Retain<wbr>Rule<span class="property-indicator"></span>
        <span class="property-type"><a href="#lifecyclepolicypolicydetailsscheduleretainrule">Lifecycle<wbr>Policy<wbr>Policy<wbr>Details<wbr>Schedule<wbr>Retain<wbr>Rule<wbr>Args</a></span>
    </dt>
    <dd>{{% md %}}See the `retain_rule` block. Max of 1 per schedule.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<wbr>To<wbr>Add<span class="property-indicator"></span>
        <span class="property-type">Dictionary<string, object>?</span>
    </dt>
    <dd>{{% md %}}A mapping of tag keys and their values. DLM lifecycle policies will already tag the snapshot with the tags on the volume. This configuration adds extra tags on top of these.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Copy<wbr>Tags<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Copy all user-defined tags on a source volume to snapshots of the volume created by this policy.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Create<wbr>Rule<span class="property-indicator"></span>
        <span class="property-type"><a href="#lifecyclepolicypolicydetailsschedulecreaterule">Lifecycle<wbr>Policy<wbr>Policy<wbr>Details<wbr>Schedule<wbr>Create<wbr>Rule</a></span>
    </dt>
    <dd>{{% md %}}See the `create_rule` block. Max of 1 per schedule.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}A name for the schedule.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Retain<wbr>Rule<span class="property-indicator"></span>
        <span class="property-type"><a href="#lifecyclepolicypolicydetailsscheduleretainrule">Lifecycle<wbr>Policy<wbr>Policy<wbr>Details<wbr>Schedule<wbr>Retain<wbr>Rule</a></span>
    </dt>
    <dd>{{% md %}}See the `retain_rule` block. Max of 1 per schedule.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Tags<wbr>To<wbr>Add<span class="property-indicator"></span>
        <span class="property-type">map[string]interface{}</span>
    </dt>
    <dd>{{% md %}}A mapping of tag keys and their values. DLM lifecycle policies will already tag the snapshot with the tags on the volume. This configuration adds extra tags on top of these.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">copy<wbr>Tags<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Copy all user-defined tags on a source volume to snapshots of the volume created by this policy.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">create<wbr>Rule<span class="property-indicator"></span>
        <span class="property-type"><a href="#lifecyclepolicypolicydetailsschedulecreaterule">Lifecycle<wbr>Policy<wbr>Policy<wbr>Details<wbr>Schedule<wbr>Create<wbr>Rule</a></span>
    </dt>
    <dd>{{% md %}}See the `create_rule` block. Max of 1 per schedule.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}A name for the schedule.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">retain<wbr>Rule<span class="property-indicator"></span>
        <span class="property-type"><a href="#lifecyclepolicypolicydetailsscheduleretainrule">Lifecycle<wbr>Policy<wbr>Policy<wbr>Details<wbr>Schedule<wbr>Retain<wbr>Rule</a></span>
    </dt>
    <dd>{{% md %}}See the `retain_rule` block. Max of 1 per schedule.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<wbr>To<wbr>Add<span class="property-indicator"></span>
        <span class="property-type">{[key: string]: any}?</span>
    </dt>
    <dd>{{% md %}}A mapping of tag keys and their values. DLM lifecycle policies will already tag the snapshot with the tags on the volume. This configuration adds extra tags on top of these.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">copy<wbr>Tags<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Copy all user-defined tags on a source volume to snapshots of the volume created by this policy.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">create<wbr>Rule<span class="property-indicator"></span>
        <span class="property-type"><a href="#lifecyclepolicypolicydetailsschedulecreaterule">Dict[Lifecycle<wbr>Policy<wbr>Policy<wbr>Details<wbr>Schedule<wbr>Create<wbr>Rule]</a></span>
    </dt>
    <dd>{{% md %}}See the `create_rule` block. Max of 1 per schedule.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A name for the schedule.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">retain<wbr>Rule<span class="property-indicator"></span>
        <span class="property-type"><a href="#lifecyclepolicypolicydetailsscheduleretainrule">Dict[Lifecycle<wbr>Policy<wbr>Policy<wbr>Details<wbr>Schedule<wbr>Retain<wbr>Rule]</a></span>
    </dt>
    <dd>{{% md %}}See the `retain_rule` block. Max of 1 per schedule.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">tags<wbr>To<wbr>Add<span class="property-indicator"></span>
        <span class="property-type">Dict[str, Any]</span>
    </dt>
    <dd>{{% md %}}A mapping of tag keys and their values. DLM lifecycle policies will already tag the snapshot with the tags on the volume. This configuration adds extra tags on top of these.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### LifecyclePolicyPolicyDetailsScheduleCreateRule
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#LifecyclePolicyPolicyDetailsScheduleCreateRule">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#LifecyclePolicyPolicyDetailsScheduleCreateRule">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/dlm?tab=doc#LifecyclePolicyPolicyDetailsScheduleCreateRuleArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/dlm?tab=doc#LifecyclePolicyPolicyDetailsScheduleCreateRuleOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Dlm.LifecyclePolicyPolicyDetailsScheduleCreateRuleArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Dlm.LifecyclePolicyPolicyDetailsScheduleCreateRule.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Interval<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}How often this lifecycle policy should be evaluated. `2`,`3`,`4`,`6`,`8`,`12` or `24` are valid values.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Interval<wbr>Unit<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The unit for how often the lifecycle policy should be evaluated. `HOURS` is currently the only allowed value and also the default value.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Times<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A list of times in 24 hour clock format that sets when the lifecycle policy should be evaluated. Max of 1.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Interval<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}How often this lifecycle policy should be evaluated. `2`,`3`,`4`,`6`,`8`,`12` or `24` are valid values.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Interval<wbr>Unit<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The unit for how often the lifecycle policy should be evaluated. `HOURS` is currently the only allowed value and also the default value.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Times<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}A list of times in 24 hour clock format that sets when the lifecycle policy should be evaluated. Max of 1.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">interval<span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}How often this lifecycle policy should be evaluated. `2`,`3`,`4`,`6`,`8`,`12` or `24` are valid values.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">interval<wbr>Unit<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The unit for how often the lifecycle policy should be evaluated. `HOURS` is currently the only allowed value and also the default value.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">times<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A list of times in 24 hour clock format that sets when the lifecycle policy should be evaluated. Max of 1.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">interval<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}How often this lifecycle policy should be evaluated. `2`,`3`,`4`,`6`,`8`,`12` or `24` are valid values.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">interval<wbr>Unit<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The unit for how often the lifecycle policy should be evaluated. `HOURS` is currently the only allowed value and also the default value.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">times<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A list of times in 24 hour clock format that sets when the lifecycle policy should be evaluated. Max of 1.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### LifecyclePolicyPolicyDetailsScheduleRetainRule
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#LifecyclePolicyPolicyDetailsScheduleRetainRule">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#LifecyclePolicyPolicyDetailsScheduleRetainRule">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/dlm?tab=doc#LifecyclePolicyPolicyDetailsScheduleRetainRuleArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/dlm?tab=doc#LifecyclePolicyPolicyDetailsScheduleRetainRuleOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Dlm.LifecyclePolicyPolicyDetailsScheduleRetainRuleArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Dlm.LifecyclePolicyPolicyDetailsScheduleRetainRule.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Count<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}How many snapshots to keep. Must be an integer between 1 and 1000.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Count<span class="property-indicator"></span>
        <span class="property-type">int</span>
    </dt>
    <dd>{{% md %}}How many snapshots to keep. Must be an integer between 1 and 1000.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">count<span class="property-indicator"></span>
        <span class="property-type">number</span>
    </dt>
    <dd>{{% md %}}How many snapshots to keep. Must be an integer between 1 and 1000.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">count<span class="property-indicator"></span>
        <span class="property-type">float</span>
    </dt>
    <dd>{{% md %}}How many snapshots to keep. Must be an integer between 1 and 1000.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}








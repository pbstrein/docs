
---
title: "GetOrganization"
block_external_search_index: true
---

Get information about the organization that the user's account belongs to

## Example Usage

### SNS topic that can be interacted by the organization only

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const example = aws.organizations.getOrganization();
const snsTopic = new aws.sns.Topic("sns_topic", {});
const snsTopicPolicyPolicyDocument = snsTopic.arn.apply(arn => aws.iam.getPolicyDocument({
    statements: [{
        actions: [
            "SNS:Subscribe",
            "SNS:Publish",
        ],
        conditions: [{
            test: "StringEquals",
            values: [example],
            variable: "aws:PrincipalOrgID",
        }],
        effect: "Allow",
        principals: [{
            identifiers: ["*"],
            type: "AWS",
        }],
        resources: [arn],
    }],
}));
const snsTopicPolicyTopicPolicy = new aws.sns.TopicPolicy("sns_topic_policy", {
    arn: snsTopic.arn,
    policy: snsTopicPolicyPolicyDocument.json,
});
```

> This content is derived from https://github.com/terraform-providers/terraform-provider-aws/blob/master/website/docs/d/organizations_organization.html.markdown.





## Using GetOrganization

{{< chooser language "typescript,python,go,csharp" >}}

{{% choosable language typescript %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">function </span>getOrganization<span class="p">(</span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#InvokeOptions">pulumi.InvokeOptions</a></span><span class="p">): Promise&lt;<span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/organizations/#GetOrganizationResult">GetOrganizationResult</a></span>></span></code></pre></div>
{{% /choosable %}}" }}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">function </span> get_organization(</span>opts=None<span class="p">)</span></code></pre></div>
{{% /choosable %}}" }}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>LookupOrganization<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#InvokeOption">pulumi.InvokeOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/organizations?tab=doc#LookupOrganizationResult">LookupOrganizationResult</a></span>, error)</span></code></pre></div>
{{% /choosable %}}" }}

{{% choosable language csharp %}}
<div class="highlight">
<pre class="chroma">
<code class="language-csharp" data-lang="csharp"><span class="k">public static class </span><span class="nx">GetOrganization </span><span class="p">{</span>
    <span class="k">public static </span>Task&lt;<span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Organizations.GetOrganizationResult.html">GetOrganizationResult</a></span>> <span class="p">InvokeAsync(</span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/InvokeOptions.html">InvokeOptions</a></span>? <span class="nx">opts = null<span class="p">)</span>
<span class="p">}</span></code></pre>
</div>
{{% /choosable %}}" }}




## GetOrganization Result

The following output properties are available:




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Accounts<span class="property-indicator"></span>
        <span class="property-type"><a href="#getorganizationaccount">List&lt;Get<wbr>Organization<wbr>Account&gt;</a></span>
    </dt>
    <dd>{{% md %}}List of organization accounts including the master account. For a list excluding the master account, see the `non_master_accounts` attribute. All elements have these attributes:
{{% /md %}}</dd>

    <dt class="property-"
            title="">Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}ARN of the root
{{% /md %}}</dd>

    <dt class="property-"
            title="">Aws<wbr>Service<wbr>Access<wbr>Principals<span class="property-indicator"></span>
        <span class="property-type">List<string></span>
    </dt>
    <dd>{{% md %}}A list of AWS service principal names that have integration enabled with your organization. Organization must have `feature_set` set to `ALL`. For additional information, see the [AWS Organizations User Guide](https://docs.aws.amazon.com/organizations/latest/userguide/orgs_integrate_services.html).
{{% /md %}}</dd>

    <dt class="property-"
            title="">Enabled<wbr>Policy<wbr>Types<span class="property-indicator"></span>
        <span class="property-type">List<string></span>
    </dt>
    <dd>{{% md %}}A list of Organizations policy types that are enabled in the Organization Root. Organization must have `feature_set` set to `ALL`. For additional information about valid policy types (e.g. `SERVICE_CONTROL_POLICY`), see the [AWS Organizations API Reference](https://docs.aws.amazon.com/organizations/latest/APIReference/API_EnablePolicyType.html).
{{% /md %}}</dd>

    <dt class="property-"
            title="">Feature<wbr>Set<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The FeatureSet of the organization.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}id is the provider-assigned unique ID for this managed resource.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Master<wbr>Account<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Amazon Resource Name (ARN) of the account that is designated as the master account for the organization.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Master<wbr>Account<wbr>Email<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The email address that is associated with the AWS account that is designated as the master account for the organization.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Master<wbr>Account<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The unique identifier (ID) of the master account of an organization.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Non<wbr>Master<wbr>Accounts<span class="property-indicator"></span>
        <span class="property-type"><a href="#getorganizationnonmasteraccount">List&lt;Get<wbr>Organization<wbr>Non<wbr>Master<wbr>Account&gt;</a></span>
    </dt>
    <dd>{{% md %}}List of organization accounts excluding the master account. For a list including the master account, see the `accounts` attribute. All elements have these attributes:
{{% /md %}}</dd>

    <dt class="property-"
            title="">Roots<span class="property-indicator"></span>
        <span class="property-type"><a href="#getorganizationroot">List&lt;Get<wbr>Organization<wbr>Root&gt;</a></span>
    </dt>
    <dd>{{% md %}}List of organization roots. All elements have these attributes:
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Accounts<span class="property-indicator"></span>
        <span class="property-type"><a href="#getorganizationaccount">[]Get<wbr>Organization<wbr>Account</a></span>
    </dt>
    <dd>{{% md %}}List of organization accounts including the master account. For a list excluding the master account, see the `non_master_accounts` attribute. All elements have these attributes:
{{% /md %}}</dd>

    <dt class="property-"
            title="">Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}ARN of the root
{{% /md %}}</dd>

    <dt class="property-"
            title="">Aws<wbr>Service<wbr>Access<wbr>Principals<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}A list of AWS service principal names that have integration enabled with your organization. Organization must have `feature_set` set to `ALL`. For additional information, see the [AWS Organizations User Guide](https://docs.aws.amazon.com/organizations/latest/userguide/orgs_integrate_services.html).
{{% /md %}}</dd>

    <dt class="property-"
            title="">Enabled<wbr>Policy<wbr>Types<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}A list of Organizations policy types that are enabled in the Organization Root. Organization must have `feature_set` set to `ALL`. For additional information about valid policy types (e.g. `SERVICE_CONTROL_POLICY`), see the [AWS Organizations API Reference](https://docs.aws.amazon.com/organizations/latest/APIReference/API_EnablePolicyType.html).
{{% /md %}}</dd>

    <dt class="property-"
            title="">Feature<wbr>Set<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The FeatureSet of the organization.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}id is the provider-assigned unique ID for this managed resource.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Master<wbr>Account<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Amazon Resource Name (ARN) of the account that is designated as the master account for the organization.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Master<wbr>Account<wbr>Email<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The email address that is associated with the AWS account that is designated as the master account for the organization.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Master<wbr>Account<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The unique identifier (ID) of the master account of an organization.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Non<wbr>Master<wbr>Accounts<span class="property-indicator"></span>
        <span class="property-type"><a href="#getorganizationnonmasteraccount">[]Get<wbr>Organization<wbr>Non<wbr>Master<wbr>Account</a></span>
    </dt>
    <dd>{{% md %}}List of organization accounts excluding the master account. For a list including the master account, see the `accounts` attribute. All elements have these attributes:
{{% /md %}}</dd>

    <dt class="property-"
            title="">Roots<span class="property-indicator"></span>
        <span class="property-type"><a href="#getorganizationroot">[]Get<wbr>Organization<wbr>Root</a></span>
    </dt>
    <dd>{{% md %}}List of organization roots. All elements have these attributes:
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">accounts<span class="property-indicator"></span>
        <span class="property-type"><a href="#getorganizationaccount">Get<wbr>Organization<wbr>Account[]</a></span>
    </dt>
    <dd>{{% md %}}List of organization accounts including the master account. For a list excluding the master account, see the `non_master_accounts` attribute. All elements have these attributes:
{{% /md %}}</dd>

    <dt class="property-"
            title="">arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}ARN of the root
{{% /md %}}</dd>

    <dt class="property-"
            title="">aws<wbr>Service<wbr>Access<wbr>Principals<span class="property-indicator"></span>
        <span class="property-type">string[]</span>
    </dt>
    <dd>{{% md %}}A list of AWS service principal names that have integration enabled with your organization. Organization must have `feature_set` set to `ALL`. For additional information, see the [AWS Organizations User Guide](https://docs.aws.amazon.com/organizations/latest/userguide/orgs_integrate_services.html).
{{% /md %}}</dd>

    <dt class="property-"
            title="">enabled<wbr>Policy<wbr>Types<span class="property-indicator"></span>
        <span class="property-type">string[]</span>
    </dt>
    <dd>{{% md %}}A list of Organizations policy types that are enabled in the Organization Root. Organization must have `feature_set` set to `ALL`. For additional information about valid policy types (e.g. `SERVICE_CONTROL_POLICY`), see the [AWS Organizations API Reference](https://docs.aws.amazon.com/organizations/latest/APIReference/API_EnablePolicyType.html).
{{% /md %}}</dd>

    <dt class="property-"
            title="">feature<wbr>Set<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The FeatureSet of the organization.
{{% /md %}}</dd>

    <dt class="property-"
            title="">id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}id is the provider-assigned unique ID for this managed resource.
{{% /md %}}</dd>

    <dt class="property-"
            title="">master<wbr>Account<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The Amazon Resource Name (ARN) of the account that is designated as the master account for the organization.
{{% /md %}}</dd>

    <dt class="property-"
            title="">master<wbr>Account<wbr>Email<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The email address that is associated with the AWS account that is designated as the master account for the organization.
{{% /md %}}</dd>

    <dt class="property-"
            title="">master<wbr>Account<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The unique identifier (ID) of the master account of an organization.
{{% /md %}}</dd>

    <dt class="property-"
            title="">non<wbr>Master<wbr>Accounts<span class="property-indicator"></span>
        <span class="property-type"><a href="#getorganizationnonmasteraccount">Get<wbr>Organization<wbr>Non<wbr>Master<wbr>Account[]</a></span>
    </dt>
    <dd>{{% md %}}List of organization accounts excluding the master account. For a list including the master account, see the `accounts` attribute. All elements have these attributes:
{{% /md %}}</dd>

    <dt class="property-"
            title="">roots<span class="property-indicator"></span>
        <span class="property-type"><a href="#getorganizationroot">Get<wbr>Organization<wbr>Root[]</a></span>
    </dt>
    <dd>{{% md %}}List of organization roots. All elements have these attributes:
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">accounts<span class="property-indicator"></span>
        <span class="property-type"><a href="#getorganizationaccount">List[Get<wbr>Organization<wbr>Account]</a></span>
    </dt>
    <dd>{{% md %}}List of organization accounts including the master account. For a list excluding the master account, see the `non_master_accounts` attribute. All elements have these attributes:
{{% /md %}}</dd>

    <dt class="property-"
            title="">arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}ARN of the root
{{% /md %}}</dd>

    <dt class="property-"
            title="">aws_<wbr>service_<wbr>access_<wbr>principals<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}A list of AWS service principal names that have integration enabled with your organization. Organization must have `feature_set` set to `ALL`. For additional information, see the [AWS Organizations User Guide](https://docs.aws.amazon.com/organizations/latest/userguide/orgs_integrate_services.html).
{{% /md %}}</dd>

    <dt class="property-"
            title="">enabled_<wbr>policy_<wbr>types<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}A list of Organizations policy types that are enabled in the Organization Root. Organization must have `feature_set` set to `ALL`. For additional information about valid policy types (e.g. `SERVICE_CONTROL_POLICY`), see the [AWS Organizations API Reference](https://docs.aws.amazon.com/organizations/latest/APIReference/API_EnablePolicyType.html).
{{% /md %}}</dd>

    <dt class="property-"
            title="">feature_<wbr>set<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The FeatureSet of the organization.
{{% /md %}}</dd>

    <dt class="property-"
            title="">id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}id is the provider-assigned unique ID for this managed resource.
{{% /md %}}</dd>

    <dt class="property-"
            title="">master_<wbr>account_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The Amazon Resource Name (ARN) of the account that is designated as the master account for the organization.
{{% /md %}}</dd>

    <dt class="property-"
            title="">master_<wbr>account_<wbr>email<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The email address that is associated with the AWS account that is designated as the master account for the organization.
{{% /md %}}</dd>

    <dt class="property-"
            title="">master_<wbr>account_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The unique identifier (ID) of the master account of an organization.
{{% /md %}}</dd>

    <dt class="property-"
            title="">non_<wbr>master_<wbr>accounts<span class="property-indicator"></span>
        <span class="property-type"><a href="#getorganizationnonmasteraccount">List[Get<wbr>Organization<wbr>Non<wbr>Master<wbr>Account]</a></span>
    </dt>
    <dd>{{% md %}}List of organization accounts excluding the master account. For a list including the master account, see the `accounts` attribute. All elements have these attributes:
{{% /md %}}</dd>

    <dt class="property-"
            title="">roots<span class="property-indicator"></span>
        <span class="property-type"><a href="#getorganizationroot">List[Get<wbr>Organization<wbr>Root]</a></span>
    </dt>
    <dd>{{% md %}}List of organization roots. All elements have these attributes:
{{% /md %}}</dd>

</dl>
{{% /choosable %}}








## Supporting Types

#### GetOrganizationAccount
{{% lang nodejs %}}
> See the   <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#GetOrganizationAccount">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the   <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/organizations?tab=doc#GetOrganizationAccount">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the   <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Organizations.GetOrganizationAccount.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}ARN of the root
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Email<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Email of the account
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Identifier of the root
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the policy type
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Status<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The status of the policy type as it relates to the associated root
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}ARN of the root
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Email<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Email of the account
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Identifier of the root
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the policy type
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Status<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The status of the policy type as it relates to the associated root
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}ARN of the root
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">email<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Email of the account
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Identifier of the root
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the policy type
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">status<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The status of the policy type as it relates to the associated root
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}ARN of the root
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">email<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Email of the account
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Identifier of the root
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the policy type
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">status<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The status of the policy type as it relates to the associated root
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### GetOrganizationNonMasterAccount
{{% lang nodejs %}}
> See the   <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#GetOrganizationNonMasterAccount">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the   <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/organizations?tab=doc#GetOrganizationNonMasterAccount">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the   <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Organizations.GetOrganizationNonMasterAccount.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}ARN of the root
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Email<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Email of the account
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Identifier of the root
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the policy type
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Status<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The status of the policy type as it relates to the associated root
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}ARN of the root
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Email<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Email of the account
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Identifier of the root
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the policy type
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Status<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The status of the policy type as it relates to the associated root
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}ARN of the root
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">email<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Email of the account
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Identifier of the root
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the policy type
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">status<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The status of the policy type as it relates to the associated root
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}ARN of the root
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">email<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Email of the account
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Identifier of the root
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the policy type
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">status<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The status of the policy type as it relates to the associated root
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### GetOrganizationRoot
{{% lang nodejs %}}
> See the   <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#GetOrganizationRoot">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the   <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/organizations?tab=doc#GetOrganizationRoot">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the   <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Organizations.GetOrganizationRoot.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}ARN of the root
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Identifier of the root
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the policy type
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Policy<wbr>Types<span class="property-indicator"></span>
        <span class="property-type"><a href="#getorganizationrootpolicytype">List&lt;Get<wbr>Organization<wbr>Root<wbr>Policy<wbr>Type<wbr>Args&gt;</a></span>
    </dt>
    <dd>{{% md %}}List of policy types enabled for this root. All elements have these attributes:
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}ARN of the root
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Identifier of the root
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the policy type
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Policy<wbr>Types<span class="property-indicator"></span>
        <span class="property-type"><a href="#getorganizationrootpolicytype">[]Get<wbr>Organization<wbr>Root<wbr>Policy<wbr>Type</a></span>
    </dt>
    <dd>{{% md %}}List of policy types enabled for this root. All elements have these attributes:
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}ARN of the root
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Identifier of the root
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the policy type
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">policy<wbr>Types<span class="property-indicator"></span>
        <span class="property-type"><a href="#getorganizationrootpolicytype">Get<wbr>Organization<wbr>Root<wbr>Policy<wbr>Type[]</a></span>
    </dt>
    <dd>{{% md %}}List of policy types enabled for this root. All elements have these attributes:
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}ARN of the root
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Identifier of the root
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the policy type
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">policy<wbr>Types<span class="property-indicator"></span>
        <span class="property-type"><a href="#getorganizationrootpolicytype">List[Get<wbr>Organization<wbr>Root<wbr>Policy<wbr>Type]</a></span>
    </dt>
    <dd>{{% md %}}List of policy types enabled for this root. All elements have these attributes:
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### GetOrganizationRootPolicyType
{{% lang nodejs %}}
> See the   <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#GetOrganizationRootPolicyType">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the   <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/organizations?tab=doc#GetOrganizationRootPolicyType">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the   <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Organizations.GetOrganizationRootPolicyType.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Status<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The status of the policy type as it relates to the associated root
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Status<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The status of the policy type as it relates to the associated root
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">status<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The status of the policy type as it relates to the associated root
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">status<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The status of the policy type as it relates to the associated root
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}








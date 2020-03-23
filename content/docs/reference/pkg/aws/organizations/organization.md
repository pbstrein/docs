
---
title: "Organization"
block_external_search_index: true
---

Provides a resource to create an organization.

## Example Usage

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const org = new aws.organizations.Organization("org", {
    awsServiceAccessPrincipals: [
        "cloudtrail.amazonaws.com",
        "config.amazonaws.com",
    ],
    featureSet: "ALL",
});
```

> This content is derived from https://github.com/terraform-providers/terraform-provider-aws/blob/master/website/docs/r/organizations_organization.html.markdown.



## Create a Organization Resource

{{< chooser language "javascript,typescript,python,go,csharp" / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/organizations/#Organization">Organization</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/organizations/#OrganizationArgs">OrganizationArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">Organization</span><span class="p">(resource_name, opts=None, </span>aws_service_access_principals=None<span class="p">, </span>enabled_policy_types=None<span class="p">, </span>feature_set=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewOrganization<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/organizations?tab=doc#OrganizationArgs">OrganizationArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/organizations?tab=doc#Organization">Organization</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Organizations.Organization.html">Organization</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Organizations.OrganizationArgs.html">OrganizationArgs</a></span>? <span class="nx">args = null<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
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
            title="Optional">Aws<wbr>Service<wbr>Access<wbr>Principals<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}List of AWS service principal names for which you want to enable integration with your organization. This is typically in the form of a URL, such as service-abbreviation.amazonaws.com. Organization must have `feature_set` set to `ALL`. For additional information, see the [AWS Organizations User Guide](https://docs.aws.amazon.com/organizations/latest/userguide/orgs_integrate_services.html).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Enabled<wbr>Policy<wbr>Types<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}List of Organizations policy types to enable in the Organization Root. Organization must have `feature_set` set to `ALL`. For additional information about valid policy types (e.g. `SERVICE_CONTROL_POLICY` and `TAG_POLICY`), see the [AWS Organizations API Reference](https://docs.aws.amazon.com/organizations/latest/APIReference/API_EnablePolicyType.html).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Feature<wbr>Set<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Specify &#34;ALL&#34; (default) or &#34;CONSOLIDATED_BILLING&#34;.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Aws<wbr>Service<wbr>Access<wbr>Principals<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}List of AWS service principal names for which you want to enable integration with your organization. This is typically in the form of a URL, such as service-abbreviation.amazonaws.com. Organization must have `feature_set` set to `ALL`. For additional information, see the [AWS Organizations User Guide](https://docs.aws.amazon.com/organizations/latest/userguide/orgs_integrate_services.html).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Enabled<wbr>Policy<wbr>Types<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}List of Organizations policy types to enable in the Organization Root. Organization must have `feature_set` set to `ALL`. For additional information about valid policy types (e.g. `SERVICE_CONTROL_POLICY` and `TAG_POLICY`), see the [AWS Organizations API Reference](https://docs.aws.amazon.com/organizations/latest/APIReference/API_EnablePolicyType.html).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Feature<wbr>Set<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Specify &#34;ALL&#34; (default) or &#34;CONSOLIDATED_BILLING&#34;.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">aws<wbr>Service<wbr>Access<wbr>Principals<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}List of AWS service principal names for which you want to enable integration with your organization. This is typically in the form of a URL, such as service-abbreviation.amazonaws.com. Organization must have `feature_set` set to `ALL`. For additional information, see the [AWS Organizations User Guide](https://docs.aws.amazon.com/organizations/latest/userguide/orgs_integrate_services.html).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">enabled<wbr>Policy<wbr>Types<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}List of Organizations policy types to enable in the Organization Root. Organization must have `feature_set` set to `ALL`. For additional information about valid policy types (e.g. `SERVICE_CONTROL_POLICY` and `TAG_POLICY`), see the [AWS Organizations API Reference](https://docs.aws.amazon.com/organizations/latest/APIReference/API_EnablePolicyType.html).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">feature<wbr>Set<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Specify &#34;ALL&#34; (default) or &#34;CONSOLIDATED_BILLING&#34;.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">aws_<wbr>service_<wbr>access_<wbr>principals<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}List of AWS service principal names for which you want to enable integration with your organization. This is typically in the form of a URL, such as service-abbreviation.amazonaws.com. Organization must have `feature_set` set to `ALL`. For additional information, see the [AWS Organizations User Guide](https://docs.aws.amazon.com/organizations/latest/userguide/orgs_integrate_services.html).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">enabled_<wbr>policy_<wbr>types<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}List of Organizations policy types to enable in the Organization Root. Organization must have `feature_set` set to `ALL`. For additional information about valid policy types (e.g. `SERVICE_CONTROL_POLICY` and `TAG_POLICY`), see the [AWS Organizations API Reference](https://docs.aws.amazon.com/organizations/latest/APIReference/API_EnablePolicyType.html).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">feature_<wbr>set<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Specify &#34;ALL&#34; (default) or &#34;CONSOLIDATED_BILLING&#34;.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}




## Organization Output Properties

The following output properties are available:




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Accounts<span class="property-indicator"></span>
        <span class="property-type"><a href="#organizationaccount">List&lt;Organization<wbr>Account&gt;</a></span>
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
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}List of AWS service principal names for which you want to enable integration with your organization. This is typically in the form of a URL, such as service-abbreviation.amazonaws.com. Organization must have `feature_set` set to `ALL`. For additional information, see the [AWS Organizations User Guide](https://docs.aws.amazon.com/organizations/latest/userguide/orgs_integrate_services.html).
{{% /md %}}</dd>

    <dt class="property-"
            title="">Enabled<wbr>Policy<wbr>Types<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}List of Organizations policy types to enable in the Organization Root. Organization must have `feature_set` set to `ALL`. For additional information about valid policy types (e.g. `SERVICE_CONTROL_POLICY` and `TAG_POLICY`), see the [AWS Organizations API Reference](https://docs.aws.amazon.com/organizations/latest/APIReference/API_EnablePolicyType.html).
{{% /md %}}</dd>

    <dt class="property-"
            title="">Feature<wbr>Set<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Specify &#34;ALL&#34; (default) or &#34;CONSOLIDATED_BILLING&#34;.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Master<wbr>Account<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}ARN of the master account
{{% /md %}}</dd>

    <dt class="property-"
            title="">Master<wbr>Account<wbr>Email<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Email address of the master account
{{% /md %}}</dd>

    <dt class="property-"
            title="">Master<wbr>Account<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Identifier of the master account
{{% /md %}}</dd>

    <dt class="property-"
            title="">Non<wbr>Master<wbr>Accounts<span class="property-indicator"></span>
        <span class="property-type"><a href="#organizationnonmasteraccount">List&lt;Organization<wbr>Non<wbr>Master<wbr>Account&gt;</a></span>
    </dt>
    <dd>{{% md %}}List of organization accounts excluding the master account. For a list including the master account, see the `accounts` attribute. All elements have these attributes:
{{% /md %}}</dd>

    <dt class="property-"
            title="">Roots<span class="property-indicator"></span>
        <span class="property-type"><a href="#organizationroot">List&lt;Organization<wbr>Root&gt;</a></span>
    </dt>
    <dd>{{% md %}}List of organization roots. All elements have these attributes:
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Accounts<span class="property-indicator"></span>
        <span class="property-type"><a href="#organizationaccount">[]Organization<wbr>Account</a></span>
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
    <dd>{{% md %}}List of AWS service principal names for which you want to enable integration with your organization. This is typically in the form of a URL, such as service-abbreviation.amazonaws.com. Organization must have `feature_set` set to `ALL`. For additional information, see the [AWS Organizations User Guide](https://docs.aws.amazon.com/organizations/latest/userguide/orgs_integrate_services.html).
{{% /md %}}</dd>

    <dt class="property-"
            title="">Enabled<wbr>Policy<wbr>Types<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}List of Organizations policy types to enable in the Organization Root. Organization must have `feature_set` set to `ALL`. For additional information about valid policy types (e.g. `SERVICE_CONTROL_POLICY` and `TAG_POLICY`), see the [AWS Organizations API Reference](https://docs.aws.amazon.com/organizations/latest/APIReference/API_EnablePolicyType.html).
{{% /md %}}</dd>

    <dt class="property-"
            title="">Feature<wbr>Set<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Specify &#34;ALL&#34; (default) or &#34;CONSOLIDATED_BILLING&#34;.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Master<wbr>Account<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}ARN of the master account
{{% /md %}}</dd>

    <dt class="property-"
            title="">Master<wbr>Account<wbr>Email<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Email address of the master account
{{% /md %}}</dd>

    <dt class="property-"
            title="">Master<wbr>Account<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Identifier of the master account
{{% /md %}}</dd>

    <dt class="property-"
            title="">Non<wbr>Master<wbr>Accounts<span class="property-indicator"></span>
        <span class="property-type"><a href="#organizationnonmasteraccount">[]Organization<wbr>Non<wbr>Master<wbr>Account</a></span>
    </dt>
    <dd>{{% md %}}List of organization accounts excluding the master account. For a list including the master account, see the `accounts` attribute. All elements have these attributes:
{{% /md %}}</dd>

    <dt class="property-"
            title="">Roots<span class="property-indicator"></span>
        <span class="property-type"><a href="#organizationroot">[]Organization<wbr>Root</a></span>
    </dt>
    <dd>{{% md %}}List of organization roots. All elements have these attributes:
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">accounts<span class="property-indicator"></span>
        <span class="property-type"><a href="#organizationaccount">Organization<wbr>Account[]</a></span>
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
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}List of AWS service principal names for which you want to enable integration with your organization. This is typically in the form of a URL, such as service-abbreviation.amazonaws.com. Organization must have `feature_set` set to `ALL`. For additional information, see the [AWS Organizations User Guide](https://docs.aws.amazon.com/organizations/latest/userguide/orgs_integrate_services.html).
{{% /md %}}</dd>

    <dt class="property-"
            title="">enabled<wbr>Policy<wbr>Types<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}List of Organizations policy types to enable in the Organization Root. Organization must have `feature_set` set to `ALL`. For additional information about valid policy types (e.g. `SERVICE_CONTROL_POLICY` and `TAG_POLICY`), see the [AWS Organizations API Reference](https://docs.aws.amazon.com/organizations/latest/APIReference/API_EnablePolicyType.html).
{{% /md %}}</dd>

    <dt class="property-"
            title="">feature<wbr>Set<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Specify &#34;ALL&#34; (default) or &#34;CONSOLIDATED_BILLING&#34;.
{{% /md %}}</dd>

    <dt class="property-"
            title="">master<wbr>Account<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}ARN of the master account
{{% /md %}}</dd>

    <dt class="property-"
            title="">master<wbr>Account<wbr>Email<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Email address of the master account
{{% /md %}}</dd>

    <dt class="property-"
            title="">master<wbr>Account<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Identifier of the master account
{{% /md %}}</dd>

    <dt class="property-"
            title="">non<wbr>Master<wbr>Accounts<span class="property-indicator"></span>
        <span class="property-type"><a href="#organizationnonmasteraccount">Organization<wbr>Non<wbr>Master<wbr>Account[]</a></span>
    </dt>
    <dd>{{% md %}}List of organization accounts excluding the master account. For a list including the master account, see the `accounts` attribute. All elements have these attributes:
{{% /md %}}</dd>

    <dt class="property-"
            title="">roots<span class="property-indicator"></span>
        <span class="property-type"><a href="#organizationroot">Organization<wbr>Root[]</a></span>
    </dt>
    <dd>{{% md %}}List of organization roots. All elements have these attributes:
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">accounts<span class="property-indicator"></span>
        <span class="property-type"><a href="#organizationaccount">List[Organization<wbr>Account]</a></span>
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
    <dd>{{% md %}}List of AWS service principal names for which you want to enable integration with your organization. This is typically in the form of a URL, such as service-abbreviation.amazonaws.com. Organization must have `feature_set` set to `ALL`. For additional information, see the [AWS Organizations User Guide](https://docs.aws.amazon.com/organizations/latest/userguide/orgs_integrate_services.html).
{{% /md %}}</dd>

    <dt class="property-"
            title="">enabled_<wbr>policy_<wbr>types<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}List of Organizations policy types to enable in the Organization Root. Organization must have `feature_set` set to `ALL`. For additional information about valid policy types (e.g. `SERVICE_CONTROL_POLICY` and `TAG_POLICY`), see the [AWS Organizations API Reference](https://docs.aws.amazon.com/organizations/latest/APIReference/API_EnablePolicyType.html).
{{% /md %}}</dd>

    <dt class="property-"
            title="">feature_<wbr>set<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Specify &#34;ALL&#34; (default) or &#34;CONSOLIDATED_BILLING&#34;.
{{% /md %}}</dd>

    <dt class="property-"
            title="">master_<wbr>account_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}ARN of the master account
{{% /md %}}</dd>

    <dt class="property-"
            title="">master_<wbr>account_<wbr>email<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Email address of the master account
{{% /md %}}</dd>

    <dt class="property-"
            title="">master_<wbr>account_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Identifier of the master account
{{% /md %}}</dd>

    <dt class="property-"
            title="">non_<wbr>master_<wbr>accounts<span class="property-indicator"></span>
        <span class="property-type"><a href="#organizationnonmasteraccount">List[Organization<wbr>Non<wbr>Master<wbr>Account]</a></span>
    </dt>
    <dd>{{% md %}}List of organization accounts excluding the master account. For a list including the master account, see the `accounts` attribute. All elements have these attributes:
{{% /md %}}</dd>

    <dt class="property-"
            title="">roots<span class="property-indicator"></span>
        <span class="property-type"><a href="#organizationroot">List[Organization<wbr>Root]</a></span>
    </dt>
    <dd>{{% md %}}List of organization roots. All elements have these attributes:
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





## Look up an Existing Organization Resource

{{< chooser language "javascript,typescript,python,go,csharp  " / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">pulumi.Input&lt;pulumi.ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/organizations/#OrganizationState">OrganizationState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/organizations/#Organization">Organization</a></span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>accounts=None<span class="p">, </span>arn=None<span class="p">, </span>aws_service_access_principals=None<span class="p">, </span>enabled_policy_types=None<span class="p">, </span>feature_set=None<span class="p">, </span>master_account_arn=None<span class="p">, </span>master_account_email=None<span class="p">, </span>master_account_id=None<span class="p">, </span>non_master_accounts=None<span class="p">, </span>roots=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetOrganization<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">pulumi.IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/organizations?tab=doc#OrganizationState">OrganizationState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/organizations?tab=doc#Organization">Organization</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Organizations.Organization.html">Organization</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Pulumi.Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Organizations.OrganizationState.html">OrganizationState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
{{% /choosable %}}

Get an existing Organization resource's state with the given name, ID, and optional extra properties used to qualify the lookup.

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
            title="Optional">Accounts<span class="property-indicator"></span>
        <span class="property-type"><a href="#organizationaccount">List&lt;Organization<wbr>Account<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}List of organization accounts including the master account. For a list excluding the master account, see the `non_master_accounts` attribute. All elements have these attributes:
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}ARN of the root
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Aws<wbr>Service<wbr>Access<wbr>Principals<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}List of AWS service principal names for which you want to enable integration with your organization. This is typically in the form of a URL, such as service-abbreviation.amazonaws.com. Organization must have `feature_set` set to `ALL`. For additional information, see the [AWS Organizations User Guide](https://docs.aws.amazon.com/organizations/latest/userguide/orgs_integrate_services.html).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Enabled<wbr>Policy<wbr>Types<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}List of Organizations policy types to enable in the Organization Root. Organization must have `feature_set` set to `ALL`. For additional information about valid policy types (e.g. `SERVICE_CONTROL_POLICY` and `TAG_POLICY`), see the [AWS Organizations API Reference](https://docs.aws.amazon.com/organizations/latest/APIReference/API_EnablePolicyType.html).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Feature<wbr>Set<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Specify &#34;ALL&#34; (default) or &#34;CONSOLIDATED_BILLING&#34;.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Master<wbr>Account<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}ARN of the master account
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Master<wbr>Account<wbr>Email<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Email address of the master account
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Master<wbr>Account<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Identifier of the master account
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Non<wbr>Master<wbr>Accounts<span class="property-indicator"></span>
        <span class="property-type"><a href="#organizationnonmasteraccount">List&lt;Organization<wbr>Non<wbr>Master<wbr>Account<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}List of organization accounts excluding the master account. For a list including the master account, see the `accounts` attribute. All elements have these attributes:
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Roots<span class="property-indicator"></span>
        <span class="property-type"><a href="#organizationroot">List&lt;Organization<wbr>Root<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}List of organization roots. All elements have these attributes:
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Accounts<span class="property-indicator"></span>
        <span class="property-type"><a href="#organizationaccount">[]Organization<wbr>Account</a></span>
    </dt>
    <dd>{{% md %}}List of organization accounts including the master account. For a list excluding the master account, see the `non_master_accounts` attribute. All elements have these attributes:
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}ARN of the root
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Aws<wbr>Service<wbr>Access<wbr>Principals<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}List of AWS service principal names for which you want to enable integration with your organization. This is typically in the form of a URL, such as service-abbreviation.amazonaws.com. Organization must have `feature_set` set to `ALL`. For additional information, see the [AWS Organizations User Guide](https://docs.aws.amazon.com/organizations/latest/userguide/orgs_integrate_services.html).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Enabled<wbr>Policy<wbr>Types<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}List of Organizations policy types to enable in the Organization Root. Organization must have `feature_set` set to `ALL`. For additional information about valid policy types (e.g. `SERVICE_CONTROL_POLICY` and `TAG_POLICY`), see the [AWS Organizations API Reference](https://docs.aws.amazon.com/organizations/latest/APIReference/API_EnablePolicyType.html).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Feature<wbr>Set<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Specify &#34;ALL&#34; (default) or &#34;CONSOLIDATED_BILLING&#34;.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Master<wbr>Account<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}ARN of the master account
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Master<wbr>Account<wbr>Email<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Email address of the master account
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Master<wbr>Account<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Identifier of the master account
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Non<wbr>Master<wbr>Accounts<span class="property-indicator"></span>
        <span class="property-type"><a href="#organizationnonmasteraccount">[]Organization<wbr>Non<wbr>Master<wbr>Account</a></span>
    </dt>
    <dd>{{% md %}}List of organization accounts excluding the master account. For a list including the master account, see the `accounts` attribute. All elements have these attributes:
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Roots<span class="property-indicator"></span>
        <span class="property-type"><a href="#organizationroot">[]Organization<wbr>Root</a></span>
    </dt>
    <dd>{{% md %}}List of organization roots. All elements have these attributes:
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">accounts<span class="property-indicator"></span>
        <span class="property-type"><a href="#organizationaccount">Organization<wbr>Account[]?</a></span>
    </dt>
    <dd>{{% md %}}List of organization accounts including the master account. For a list excluding the master account, see the `non_master_accounts` attribute. All elements have these attributes:
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}ARN of the root
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">aws<wbr>Service<wbr>Access<wbr>Principals<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}List of AWS service principal names for which you want to enable integration with your organization. This is typically in the form of a URL, such as service-abbreviation.amazonaws.com. Organization must have `feature_set` set to `ALL`. For additional information, see the [AWS Organizations User Guide](https://docs.aws.amazon.com/organizations/latest/userguide/orgs_integrate_services.html).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">enabled<wbr>Policy<wbr>Types<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}List of Organizations policy types to enable in the Organization Root. Organization must have `feature_set` set to `ALL`. For additional information about valid policy types (e.g. `SERVICE_CONTROL_POLICY` and `TAG_POLICY`), see the [AWS Organizations API Reference](https://docs.aws.amazon.com/organizations/latest/APIReference/API_EnablePolicyType.html).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">feature<wbr>Set<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Specify &#34;ALL&#34; (default) or &#34;CONSOLIDATED_BILLING&#34;.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">master<wbr>Account<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}ARN of the master account
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">master<wbr>Account<wbr>Email<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Email address of the master account
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">master<wbr>Account<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Identifier of the master account
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">non<wbr>Master<wbr>Accounts<span class="property-indicator"></span>
        <span class="property-type"><a href="#organizationnonmasteraccount">Organization<wbr>Non<wbr>Master<wbr>Account[]?</a></span>
    </dt>
    <dd>{{% md %}}List of organization accounts excluding the master account. For a list including the master account, see the `accounts` attribute. All elements have these attributes:
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">roots<span class="property-indicator"></span>
        <span class="property-type"><a href="#organizationroot">Organization<wbr>Root[]?</a></span>
    </dt>
    <dd>{{% md %}}List of organization roots. All elements have these attributes:
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">accounts<span class="property-indicator"></span>
        <span class="property-type"><a href="#organizationaccount">List[Organization<wbr>Account]</a></span>
    </dt>
    <dd>{{% md %}}List of organization accounts including the master account. For a list excluding the master account, see the `non_master_accounts` attribute. All elements have these attributes:
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}ARN of the root
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">aws_<wbr>service_<wbr>access_<wbr>principals<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}List of AWS service principal names for which you want to enable integration with your organization. This is typically in the form of a URL, such as service-abbreviation.amazonaws.com. Organization must have `feature_set` set to `ALL`. For additional information, see the [AWS Organizations User Guide](https://docs.aws.amazon.com/organizations/latest/userguide/orgs_integrate_services.html).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">enabled_<wbr>policy_<wbr>types<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}List of Organizations policy types to enable in the Organization Root. Organization must have `feature_set` set to `ALL`. For additional information about valid policy types (e.g. `SERVICE_CONTROL_POLICY` and `TAG_POLICY`), see the [AWS Organizations API Reference](https://docs.aws.amazon.com/organizations/latest/APIReference/API_EnablePolicyType.html).
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">feature_<wbr>set<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Specify &#34;ALL&#34; (default) or &#34;CONSOLIDATED_BILLING&#34;.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">master_<wbr>account_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}ARN of the master account
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">master_<wbr>account_<wbr>email<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Email address of the master account
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">master_<wbr>account_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Identifier of the master account
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">non_<wbr>master_<wbr>accounts<span class="property-indicator"></span>
        <span class="property-type"><a href="#organizationnonmasteraccount">List[Organization<wbr>Non<wbr>Master<wbr>Account]</a></span>
    </dt>
    <dd>{{% md %}}List of organization accounts excluding the master account. For a list including the master account, see the `accounts` attribute. All elements have these attributes:
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">roots<span class="property-indicator"></span>
        <span class="property-type"><a href="#organizationroot">List[Organization<wbr>Root]</a></span>
    </dt>
    <dd>{{% md %}}List of organization roots. All elements have these attributes:
{{% /md %}}</dd>

</dl>
{{% /choosable %}}







## Supporting Types

#### OrganizationAccount
{{% lang nodejs %}}
> See the   <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#OrganizationAccount">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the   <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/organizations?tab=doc#OrganizationAccountOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the   <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Organizations.OrganizationAccount.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}ARN of the root
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Email<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Email of the account
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Identifier of the root
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the policy type
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Status<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The status of the policy type as it relates to the associated root
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}ARN of the root
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Email<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Email of the account
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Identifier of the root
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name of the policy type
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Status<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The status of the policy type as it relates to the associated root
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}ARN of the root
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">email<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Email of the account
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Identifier of the root
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the policy type
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">status<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The status of the policy type as it relates to the associated root
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}ARN of the root
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">email<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Email of the account
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Identifier of the root
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the policy type
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">status<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The status of the policy type as it relates to the associated root
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### OrganizationNonMasterAccount
{{% lang nodejs %}}
> See the   <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#OrganizationNonMasterAccount">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the   <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/organizations?tab=doc#OrganizationNonMasterAccountOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the   <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Organizations.OrganizationNonMasterAccount.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}ARN of the root
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Email<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Email of the account
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Identifier of the root
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the policy type
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Status<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The status of the policy type as it relates to the associated root
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}ARN of the root
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Email<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Email of the account
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Identifier of the root
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name of the policy type
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Status<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The status of the policy type as it relates to the associated root
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}ARN of the root
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">email<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Email of the account
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Identifier of the root
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the policy type
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">status<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The status of the policy type as it relates to the associated root
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}ARN of the root
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">email<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Email of the account
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Identifier of the root
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the policy type
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">status<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The status of the policy type as it relates to the associated root
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### OrganizationRoot
{{% lang nodejs %}}
> See the   <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#OrganizationRoot">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the   <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/organizations?tab=doc#OrganizationRootOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the   <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Organizations.OrganizationRoot.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}ARN of the root
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Identifier of the root
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the policy type
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Policy<wbr>Types<span class="property-indicator"></span>
        <span class="property-type"><a href="#organizationrootpolicytype">List&lt;Organization<wbr>Root<wbr>Policy<wbr>Type<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}List of policy types enabled for this root. All elements have these attributes:
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Arn<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}ARN of the root
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Identifier of the root
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name of the policy type
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Policy<wbr>Types<span class="property-indicator"></span>
        <span class="property-type"><a href="#organizationrootpolicytype">[]Organization<wbr>Root<wbr>Policy<wbr>Type</a></span>
    </dt>
    <dd>{{% md %}}List of policy types enabled for this root. All elements have these attributes:
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">arn<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}ARN of the root
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Identifier of the root
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the policy type
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">policy<wbr>Types<span class="property-indicator"></span>
        <span class="property-type"><a href="#organizationrootpolicytype">Organization<wbr>Root<wbr>Policy<wbr>Type[]?</a></span>
    </dt>
    <dd>{{% md %}}List of policy types enabled for this root. All elements have these attributes:
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}ARN of the root
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Identifier of the root
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the policy type
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">policy<wbr>Types<span class="property-indicator"></span>
        <span class="property-type"><a href="#organizationrootpolicytype">List[Organization<wbr>Root<wbr>Policy<wbr>Type]</a></span>
    </dt>
    <dd>{{% md %}}List of policy types enabled for this root. All elements have these attributes:
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### OrganizationRootPolicyType
{{% lang nodejs %}}
> See the   <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#OrganizationRootPolicyType">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the   <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/organizations?tab=doc#OrganizationRootPolicyTypeOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the   <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Organizations.OrganizationRootPolicyType.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Status<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The status of the policy type as it relates to the associated root
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Status<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The status of the policy type as it relates to the associated root
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Type<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">status<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The status of the policy type as it relates to the associated root
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">type<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">status<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The status of the policy type as it relates to the associated root
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}









---
title: "IdentityPoolRoleAttachment"
block_external_search_index: true
---

Provides an AWS Cognito Identity Pool Roles Attachment.

## Example Usage

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const mainIdentityPool = new aws.cognito.IdentityPool("main", {
    allowUnauthenticatedIdentities: false,
    identityPoolName: "identity pool",
    supportedLoginProviders: {
        "graph.facebook.com": "7346241598935555",
    },
});
const authenticatedRole = new aws.iam.Role("authenticated", {
    assumeRolePolicy: pulumi.interpolate`{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Principal": {
        "Federated": "cognito-identity.amazonaws.com"
      },
      "Action": "sts:AssumeRoleWithWebIdentity",
      "Condition": {
        "StringEquals": {
          "cognito-identity.amazonaws.com:aud": "${mainIdentityPool.id}"
        },
        "ForAnyValue:StringLike": {
          "cognito-identity.amazonaws.com:amr": "authenticated"
        }
      }
    }
  ]
}
`,
});
const authenticatedRolePolicy = new aws.iam.RolePolicy("authenticated", {
    policy: `{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Action": [
        "mobileanalytics:PutEvents",
        "cognito-sync:*",
        "cognito-identity:*"
      ],
      "Resource": [
        "*"
      ]
    }
  ]
}
`,
    role: authenticatedRole.id,
});
const mainIdentityPoolRoleAttachment = new aws.cognito.IdentityPoolRoleAttachment("main", {
    identityPoolId: mainIdentityPool.id,
    roleMappings: [{
        ambiguousRoleResolution: "AuthenticatedRole",
        identityProvider: "graph.facebook.com",
        mappingRules: [{
            claim: "isAdmin",
            matchType: "Equals",
            roleArn: authenticatedRole.arn,
            value: "paid",
        }],
        type: "Rules",
    }],
    roles: {
        authenticated: authenticatedRole.arn,
    },
});
```

> This content is derived from https://github.com/terraform-providers/terraform-provider-aws/blob/master/website/docs/r/cognito_identity_pool_roles_attachment.markdown.



## Create a IdentityPoolRoleAttachment Resource

{{< chooser language "javascript,typescript,python,go,csharp" / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/cognito/#IdentityPoolRoleAttachment">IdentityPoolRoleAttachment</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/cognito/#IdentityPoolRoleAttachmentArgs">IdentityPoolRoleAttachmentArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">IdentityPoolRoleAttachment</span><span class="p">(resource_name, opts=None, </span>identity_pool_id=None<span class="p">, </span>role_mappings=None<span class="p">, </span>roles=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewIdentityPoolRoleAttachment<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/cognito?tab=doc#IdentityPoolRoleAttachmentArgs">IdentityPoolRoleAttachmentArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/cognito?tab=doc#IdentityPoolRoleAttachment">IdentityPoolRoleAttachment</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Cognito.IdentityPoolRoleAttachment.html">IdentityPoolRoleAttachment</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Cognito.IdentityPoolRoleAttachmentArgs.html">IdentityPoolRoleAttachmentArgs</a></span> <span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
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
            title="Required">Identity<wbr>Pool<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}An identity pool ID in the format REGION:GUID.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Role<wbr>Mappings<span class="property-indicator"></span>
        <span class="property-type"><a href="#identitypoolroleattachmentrolemapping">List&lt;Identity<wbr>Pool<wbr>Role<wbr>Attachment<wbr>Role<wbr>Mapping<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}A List of Role Mapping.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Roles<span class="property-indicator"></span>
        <span class="property-type"><a href="#identitypoolroleattachmentroles">Identity<wbr>Pool<wbr>Role<wbr>Attachment<wbr>Roles<wbr>Args</a></span>
    </dt>
    <dd>{{% md %}}The map of roles associated with this pool. For a given role, the key will be either &#34;authenticated&#34; or &#34;unauthenticated&#34; and the value will be the Role ARN.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Identity<wbr>Pool<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}An identity pool ID in the format REGION:GUID.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Role<wbr>Mappings<span class="property-indicator"></span>
        <span class="property-type"><a href="#identitypoolroleattachmentrolemapping">[]Identity<wbr>Pool<wbr>Role<wbr>Attachment<wbr>Role<wbr>Mapping</a></span>
    </dt>
    <dd>{{% md %}}A List of Role Mapping.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Roles<span class="property-indicator"></span>
        <span class="property-type"><a href="#identitypoolroleattachmentroles">Identity<wbr>Pool<wbr>Role<wbr>Attachment<wbr>Roles</a></span>
    </dt>
    <dd>{{% md %}}The map of roles associated with this pool. For a given role, the key will be either &#34;authenticated&#34; or &#34;unauthenticated&#34; and the value will be the Role ARN.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">identity<wbr>Pool<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}An identity pool ID in the format REGION:GUID.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">role<wbr>Mappings<span class="property-indicator"></span>
        <span class="property-type"><a href="#identitypoolroleattachmentrolemapping">Identity<wbr>Pool<wbr>Role<wbr>Attachment<wbr>Role<wbr>Mapping[]?</a></span>
    </dt>
    <dd>{{% md %}}A List of Role Mapping.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">roles<span class="property-indicator"></span>
        <span class="property-type"><a href="#identitypoolroleattachmentroles">Identity<wbr>Pool<wbr>Role<wbr>Attachment<wbr>Roles</a></span>
    </dt>
    <dd>{{% md %}}The map of roles associated with this pool. For a given role, the key will be either &#34;authenticated&#34; or &#34;unauthenticated&#34; and the value will be the Role ARN.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">identity_<wbr>pool_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}An identity pool ID in the format REGION:GUID.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">role_<wbr>mappings<span class="property-indicator"></span>
        <span class="property-type"><a href="#identitypoolroleattachmentrolemapping">List[Identity<wbr>Pool<wbr>Role<wbr>Attachment<wbr>Role<wbr>Mapping]</a></span>
    </dt>
    <dd>{{% md %}}A List of Role Mapping.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">roles<span class="property-indicator"></span>
        <span class="property-type"><a href="#identitypoolroleattachmentroles">Dict[Identity<wbr>Pool<wbr>Role<wbr>Attachment<wbr>Roles]</a></span>
    </dt>
    <dd>{{% md %}}The map of roles associated with this pool. For a given role, the key will be either &#34;authenticated&#34; or &#34;unauthenticated&#34; and the value will be the Role ARN.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}




## IdentityPoolRoleAttachment Output Properties

The following output properties are available:




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Identity<wbr>Pool<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}An identity pool ID in the format REGION:GUID.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Role<wbr>Mappings<span class="property-indicator"></span>
        <span class="property-type"><a href="#identitypoolroleattachmentrolemapping">List&lt;Identity<wbr>Pool<wbr>Role<wbr>Attachment<wbr>Role<wbr>Mapping&gt;?</a></span>
    </dt>
    <dd>{{% md %}}A List of Role Mapping.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Roles<span class="property-indicator"></span>
        <span class="property-type"><a href="#identitypoolroleattachmentroles">Identity<wbr>Pool<wbr>Role<wbr>Attachment<wbr>Roles</a></span>
    </dt>
    <dd>{{% md %}}The map of roles associated with this pool. For a given role, the key will be either &#34;authenticated&#34; or &#34;unauthenticated&#34; and the value will be the Role ARN.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Identity<wbr>Pool<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}An identity pool ID in the format REGION:GUID.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Role<wbr>Mappings<span class="property-indicator"></span>
        <span class="property-type"><a href="#identitypoolroleattachmentrolemapping">[]Identity<wbr>Pool<wbr>Role<wbr>Attachment<wbr>Role<wbr>Mapping</a></span>
    </dt>
    <dd>{{% md %}}A List of Role Mapping.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Roles<span class="property-indicator"></span>
        <span class="property-type"><a href="#identitypoolroleattachmentroles">Identity<wbr>Pool<wbr>Role<wbr>Attachment<wbr>Roles</a></span>
    </dt>
    <dd>{{% md %}}The map of roles associated with this pool. For a given role, the key will be either &#34;authenticated&#34; or &#34;unauthenticated&#34; and the value will be the Role ARN.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">identity<wbr>Pool<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}An identity pool ID in the format REGION:GUID.
{{% /md %}}</dd>

    <dt class="property-"
            title="">role<wbr>Mappings<span class="property-indicator"></span>
        <span class="property-type"><a href="#identitypoolroleattachmentrolemapping">Identity<wbr>Pool<wbr>Role<wbr>Attachment<wbr>Role<wbr>Mapping[]?</a></span>
    </dt>
    <dd>{{% md %}}A List of Role Mapping.
{{% /md %}}</dd>

    <dt class="property-"
            title="">roles<span class="property-indicator"></span>
        <span class="property-type"><a href="#identitypoolroleattachmentroles">Identity<wbr>Pool<wbr>Role<wbr>Attachment<wbr>Roles</a></span>
    </dt>
    <dd>{{% md %}}The map of roles associated with this pool. For a given role, the key will be either &#34;authenticated&#34; or &#34;unauthenticated&#34; and the value will be the Role ARN.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">identity_<wbr>pool_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}An identity pool ID in the format REGION:GUID.
{{% /md %}}</dd>

    <dt class="property-"
            title="">role_<wbr>mappings<span class="property-indicator"></span>
        <span class="property-type"><a href="#identitypoolroleattachmentrolemapping">List[Identity<wbr>Pool<wbr>Role<wbr>Attachment<wbr>Role<wbr>Mapping]</a></span>
    </dt>
    <dd>{{% md %}}A List of Role Mapping.
{{% /md %}}</dd>

    <dt class="property-"
            title="">roles<span class="property-indicator"></span>
        <span class="property-type"><a href="#identitypoolroleattachmentroles">Dict[Identity<wbr>Pool<wbr>Role<wbr>Attachment<wbr>Roles]</a></span>
    </dt>
    <dd>{{% md %}}The map of roles associated with this pool. For a given role, the key will be either &#34;authenticated&#34; or &#34;unauthenticated&#34; and the value will be the Role ARN.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





## Look up an Existing IdentityPoolRoleAttachment Resource

{{< chooser language "javascript,typescript,python,go,csharp  " / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">pulumi.Input&lt;pulumi.ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/cognito/#IdentityPoolRoleAttachmentState">IdentityPoolRoleAttachmentState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/cognito/#IdentityPoolRoleAttachment">IdentityPoolRoleAttachment</a></span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>identity_pool_id=None<span class="p">, </span>role_mappings=None<span class="p">, </span>roles=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetIdentityPoolRoleAttachment<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">pulumi.IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/cognito?tab=doc#IdentityPoolRoleAttachmentState">IdentityPoolRoleAttachmentState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/cognito?tab=doc#IdentityPoolRoleAttachment">IdentityPoolRoleAttachment</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Cognito.IdentityPoolRoleAttachment.html">IdentityPoolRoleAttachment</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Pulumi.Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Cognito.IdentityPoolRoleAttachmentState.html">IdentityPoolRoleAttachmentState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
{{% /choosable %}}

Get an existing IdentityPoolRoleAttachment resource's state with the given name, ID, and optional extra properties used to qualify the lookup.

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
            title="Optional">Identity<wbr>Pool<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}An identity pool ID in the format REGION:GUID.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Role<wbr>Mappings<span class="property-indicator"></span>
        <span class="property-type"><a href="#identitypoolroleattachmentrolemapping">List&lt;Identity<wbr>Pool<wbr>Role<wbr>Attachment<wbr>Role<wbr>Mapping<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}A List of Role Mapping.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Roles<span class="property-indicator"></span>
        <span class="property-type"><a href="#identitypoolroleattachmentroles">Identity<wbr>Pool<wbr>Role<wbr>Attachment<wbr>Roles<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}The map of roles associated with this pool. For a given role, the key will be either &#34;authenticated&#34; or &#34;unauthenticated&#34; and the value will be the Role ARN.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Identity<wbr>Pool<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}An identity pool ID in the format REGION:GUID.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Role<wbr>Mappings<span class="property-indicator"></span>
        <span class="property-type"><a href="#identitypoolroleattachmentrolemapping">[]Identity<wbr>Pool<wbr>Role<wbr>Attachment<wbr>Role<wbr>Mapping</a></span>
    </dt>
    <dd>{{% md %}}A List of Role Mapping.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Roles<span class="property-indicator"></span>
        <span class="property-type"><a href="#identitypoolroleattachmentroles">*Identity<wbr>Pool<wbr>Role<wbr>Attachment<wbr>Roles</a></span>
    </dt>
    <dd>{{% md %}}The map of roles associated with this pool. For a given role, the key will be either &#34;authenticated&#34; or &#34;unauthenticated&#34; and the value will be the Role ARN.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">identity<wbr>Pool<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}An identity pool ID in the format REGION:GUID.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">role<wbr>Mappings<span class="property-indicator"></span>
        <span class="property-type"><a href="#identitypoolroleattachmentrolemapping">Identity<wbr>Pool<wbr>Role<wbr>Attachment<wbr>Role<wbr>Mapping[]?</a></span>
    </dt>
    <dd>{{% md %}}A List of Role Mapping.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">roles<span class="property-indicator"></span>
        <span class="property-type"><a href="#identitypoolroleattachmentroles">Identity<wbr>Pool<wbr>Role<wbr>Attachment<wbr>Roles?</a></span>
    </dt>
    <dd>{{% md %}}The map of roles associated with this pool. For a given role, the key will be either &#34;authenticated&#34; or &#34;unauthenticated&#34; and the value will be the Role ARN.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">identity_<wbr>pool_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}An identity pool ID in the format REGION:GUID.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">role_<wbr>mappings<span class="property-indicator"></span>
        <span class="property-type"><a href="#identitypoolroleattachmentrolemapping">List[Identity<wbr>Pool<wbr>Role<wbr>Attachment<wbr>Role<wbr>Mapping]</a></span>
    </dt>
    <dd>{{% md %}}A List of Role Mapping.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">roles<span class="property-indicator"></span>
        <span class="property-type"><a href="#identitypoolroleattachmentroles">Dict[Identity<wbr>Pool<wbr>Role<wbr>Attachment<wbr>Roles]</a></span>
    </dt>
    <dd>{{% md %}}The map of roles associated with this pool. For a given role, the key will be either &#34;authenticated&#34; or &#34;unauthenticated&#34; and the value will be the Role ARN.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}







## Supporting Types

#### IdentityPoolRoleAttachmentRoleMapping
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#IdentityPoolRoleAttachmentRoleMapping">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#IdentityPoolRoleAttachmentRoleMapping">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/cognito?tab=doc#IdentityPoolRoleAttachmentRoleMappingArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/cognito?tab=doc#IdentityPoolRoleAttachmentRoleMappingOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Cognito.IdentityPoolRoleAttachmentRoleMappingArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Cognito.IdentityPoolRoleAttachmentRoleMapping.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Ambiguous<wbr>Role<wbr>Resolution<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Specifies the action to be taken if either no rules match the claim value for the Rules type, or there is no cognito:preferred_role claim and there are multiple cognito:roles matches for the Token type. `Required` if you specify Token or Rules as the Type.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Identity<wbr>Provider<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}A string identifying the identity provider, for example, &#34;graph.facebook.com&#34; or &#34;cognito-idp.us-east-1.amazonaws.com/us-east-1_abcdefghi:app_client_id&#34;.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Mapping<wbr>Rules<span class="property-indicator"></span>
        <span class="property-type"><a href="#identitypoolroleattachmentrolemappingmappingrule">List&lt;Identity<wbr>Pool<wbr>Role<wbr>Attachment<wbr>Role<wbr>Mapping<wbr>Mapping<wbr>Rule<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}The Rules Configuration to be used for mapping users to roles. You can specify up to 25 rules per identity provider. Rules are evaluated in order. The first one to match specifies the role.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The role mapping type.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Ambiguous<wbr>Role<wbr>Resolution<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Specifies the action to be taken if either no rules match the claim value for the Rules type, or there is no cognito:preferred_role claim and there are multiple cognito:roles matches for the Token type. `Required` if you specify Token or Rules as the Type.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Identity<wbr>Provider<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}A string identifying the identity provider, for example, &#34;graph.facebook.com&#34; or &#34;cognito-idp.us-east-1.amazonaws.com/us-east-1_abcdefghi:app_client_id&#34;.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Mapping<wbr>Rules<span class="property-indicator"></span>
        <span class="property-type"><a href="#identitypoolroleattachmentrolemappingmappingrule">[]Identity<wbr>Pool<wbr>Role<wbr>Attachment<wbr>Role<wbr>Mapping<wbr>Mapping<wbr>Rule</a></span>
    </dt>
    <dd>{{% md %}}The Rules Configuration to be used for mapping users to roles. You can specify up to 25 rules per identity provider. Rules are evaluated in order. The first one to match specifies the role.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The role mapping type.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">ambiguous<wbr>Role<wbr>Resolution<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Specifies the action to be taken if either no rules match the claim value for the Rules type, or there is no cognito:preferred_role claim and there are multiple cognito:roles matches for the Token type. `Required` if you specify Token or Rules as the Type.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">identity<wbr>Provider<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}A string identifying the identity provider, for example, &#34;graph.facebook.com&#34; or &#34;cognito-idp.us-east-1.amazonaws.com/us-east-1_abcdefghi:app_client_id&#34;.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">mapping<wbr>Rules<span class="property-indicator"></span>
        <span class="property-type"><a href="#identitypoolroleattachmentrolemappingmappingrule">Identity<wbr>Pool<wbr>Role<wbr>Attachment<wbr>Role<wbr>Mapping<wbr>Mapping<wbr>Rule[]?</a></span>
    </dt>
    <dd>{{% md %}}The Rules Configuration to be used for mapping users to roles. You can specify up to 25 rules per identity provider. Rules are evaluated in order. The first one to match specifies the role.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The role mapping type.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">ambiguous<wbr>Role<wbr>Resolution<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Specifies the action to be taken if either no rules match the claim value for the Rules type, or there is no cognito:preferred_role claim and there are multiple cognito:roles matches for the Token type. `Required` if you specify Token or Rules as the Type.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">identity_<wbr>provider<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A string identifying the identity provider, for example, &#34;graph.facebook.com&#34; or &#34;cognito-idp.us-east-1.amazonaws.com/us-east-1_abcdefghi:app_client_id&#34;.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">mapping<wbr>Rules<span class="property-indicator"></span>
        <span class="property-type"><a href="#identitypoolroleattachmentrolemappingmappingrule">List[Identity<wbr>Pool<wbr>Role<wbr>Attachment<wbr>Role<wbr>Mapping<wbr>Mapping<wbr>Rule]</a></span>
    </dt>
    <dd>{{% md %}}The Rules Configuration to be used for mapping users to roles. You can specify up to 25 rules per identity provider. Rules are evaluated in order. The first one to match specifies the role.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The role mapping type.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### IdentityPoolRoleAttachmentRoleMappingMappingRule
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#IdentityPoolRoleAttachmentRoleMappingMappingRule">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#IdentityPoolRoleAttachmentRoleMappingMappingRule">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/cognito?tab=doc#IdentityPoolRoleAttachmentRoleMappingMappingRuleArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/cognito?tab=doc#IdentityPoolRoleAttachmentRoleMappingMappingRuleOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Cognito.IdentityPoolRoleAttachmentRoleMappingMappingRuleArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Cognito.IdentityPoolRoleAttachmentRoleMappingMappingRule.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Claim<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The claim name that must be present in the token, for example, &#34;isAdmin&#34; or &#34;paid&#34;.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Match<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The match condition that specifies how closely the claim value in the IdP token must match Value.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The role ARN.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Value<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}A brief string that the claim must match, for example, &#34;paid&#34; or &#34;yes&#34;.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Claim<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The claim name that must be present in the token, for example, &#34;isAdmin&#34; or &#34;paid&#34;.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Match<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The match condition that specifies how closely the claim value in the IdP token must match Value.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The role ARN.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Value<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}A brief string that the claim must match, for example, &#34;paid&#34; or &#34;yes&#34;.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">claim<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The claim name that must be present in the token, for example, &#34;isAdmin&#34; or &#34;paid&#34;.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">match<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The match condition that specifies how closely the claim value in the IdP token must match Value.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">role<wbr>Arn<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The role ARN.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">value<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}A brief string that the claim must match, for example, &#34;paid&#34; or &#34;yes&#34;.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">claim<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The claim name that must be present in the token, for example, &#34;isAdmin&#34; or &#34;paid&#34;.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">match<wbr>Type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The match condition that specifies how closely the claim value in the IdP token must match Value.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">role_<wbr>arn<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The role ARN.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">value<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A brief string that the claim must match, for example, &#34;paid&#34; or &#34;yes&#34;.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### IdentityPoolRoleAttachmentRoles
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#IdentityPoolRoleAttachmentRoles">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#IdentityPoolRoleAttachmentRoles">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/cognito?tab=doc#IdentityPoolRoleAttachmentRolesArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/cognito?tab=doc#IdentityPoolRoleAttachmentRolesOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Cognito.IdentityPoolRoleAttachmentRolesArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Cognito.IdentityPoolRoleAttachmentRoles.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Authenticated<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Unauthenticated<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Authenticated<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Unauthenticated<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">authenticated<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">unauthenticated<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">authenticated<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">unauthenticated<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}









---
title: "GetPolicyDocument"
block_external_search_index: true
---






## Using GetPolicyDocument

{{< chooser language "typescript,python,go,csharp" >}}

{{% choosable language typescript %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">function </span>getPolicyDocument<span class="p">(</span><span class="nx">args</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/iam/#GetPolicyDocumentArgs">GetPolicyDocumentArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#InvokeOptions">pulumi.InvokeOptions</a></span><span class="p">): Promise&lt;<span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/iam/#GetPolicyDocumentResult">GetPolicyDocumentResult</a></span>></span></code></pre></div>
{{% /choosable %}}" }}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">function </span> get_policy_document(</span>override_json=None<span class="p">, </span>policy_id=None<span class="p">, </span>source_json=None<span class="p">, </span>statements=None<span class="p">, </span>version=None<span class="p">, </span>opts=None<span class="p">)</span></code></pre></div>
{{% /choosable %}}" }}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>LookupPolicyDocument<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">args</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/iam?tab=doc#LookupPolicyDocumentArgs">LookupPolicyDocumentArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#InvokeOption">pulumi.InvokeOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/iam?tab=doc#LookupPolicyDocumentResult">LookupPolicyDocumentResult</a></span>, error)</span></code></pre></div>
{{% /choosable %}}" }}

{{% choosable language csharp %}}
<div class="highlight">
<pre class="chroma">
<code class="language-csharp" data-lang="csharp"><span class="k">public static class </span><span class="nx">GetPolicyDocument </span><span class="p">{</span>
    <span class="k">public static </span>Task&lt;<span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Iam.GetPolicyDocumentResult.html">GetPolicyDocumentResult</a></span>> <span class="p">InvokeAsync(</span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Iam.GetPolicyDocumentArgs.html">GetPolicyDocumentArgs</a></span> <span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/InvokeOptions.html">InvokeOptions</a></span>? <span class="nx">opts = null<span class="p">)</span>
<span class="p">}</span></code></pre>
</div>
{{% /choosable %}}" }}



The following arguments are supported:



{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Override<wbr>Json<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}An IAM policy document to import and override the
current policy document.  Statements with non-blank `sid`s in the override
document will overwrite statements with the same `sid` in the current document.
Statements without an `sid` cannot be overwritten.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Policy<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}An ID for the policy document.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Source<wbr>Json<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}An IAM policy document to import as a base for the
current policy document.  Statements with non-blank `sid`s in the current
policy document will overwrite statements with the same `sid` in the source
json.  Statements without an `sid` cannot be overwritten.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Statements<span class="property-indicator"></span>
        <span class="property-type"><a href="#getpolicydocumentstatement">List&lt;Get<wbr>Policy<wbr>Document<wbr>Statement<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}A nested configuration block (described below)
configuring one *statement* to be included in the policy document.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Version<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}IAM policy document version. Valid values: `2008-10-17`, `2012-10-17`. Defaults to `2012-10-17`. For more information, see the [AWS IAM User Guide](https://docs.aws.amazon.com/IAM/latest/UserGuide/reference_policies_elements_version.html).
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Override<wbr>Json<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}An IAM policy document to import and override the
current policy document.  Statements with non-blank `sid`s in the override
document will overwrite statements with the same `sid` in the current document.
Statements without an `sid` cannot be overwritten.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Policy<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}An ID for the policy document.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Source<wbr>Json<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}An IAM policy document to import as a base for the
current policy document.  Statements with non-blank `sid`s in the current
policy document will overwrite statements with the same `sid` in the source
json.  Statements without an `sid` cannot be overwritten.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Statements<span class="property-indicator"></span>
        <span class="property-type"><a href="#getpolicydocumentstatement">[]Get<wbr>Policy<wbr>Document<wbr>Statement</a></span>
    </dt>
    <dd>{{% md %}}A nested configuration block (described below)
configuring one *statement* to be included in the policy document.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Version<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}IAM policy document version. Valid values: `2008-10-17`, `2012-10-17`. Defaults to `2012-10-17`. For more information, see the [AWS IAM User Guide](https://docs.aws.amazon.com/IAM/latest/UserGuide/reference_policies_elements_version.html).
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">override<wbr>Json<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}An IAM policy document to import and override the
current policy document.  Statements with non-blank `sid`s in the override
document will overwrite statements with the same `sid` in the current document.
Statements without an `sid` cannot be overwritten.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">policy<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}An ID for the policy document.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">source<wbr>Json<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}An IAM policy document to import as a base for the
current policy document.  Statements with non-blank `sid`s in the current
policy document will overwrite statements with the same `sid` in the source
json.  Statements without an `sid` cannot be overwritten.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">statements<span class="property-indicator"></span>
        <span class="property-type"><a href="#getpolicydocumentstatement">Get<wbr>Policy<wbr>Document<wbr>Statement[]?</a></span>
    </dt>
    <dd>{{% md %}}A nested configuration block (described below)
configuring one *statement* to be included in the policy document.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">version<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}IAM policy document version. Valid values: `2008-10-17`, `2012-10-17`. Defaults to `2012-10-17`. For more information, see the [AWS IAM User Guide](https://docs.aws.amazon.com/IAM/latest/UserGuide/reference_policies_elements_version.html).
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">override_<wbr>json<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}An IAM policy document to import and override the
current policy document.  Statements with non-blank `sid`s in the override
document will overwrite statements with the same `sid` in the current document.
Statements without an `sid` cannot be overwritten.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">policy_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}An ID for the policy document.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">source_<wbr>json<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}An IAM policy document to import as a base for the
current policy document.  Statements with non-blank `sid`s in the current
policy document will overwrite statements with the same `sid` in the source
json.  Statements without an `sid` cannot be overwritten.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">statements<span class="property-indicator"></span>
        <span class="property-type"><a href="#getpolicydocumentstatement">List[Get<wbr>Policy<wbr>Document<wbr>Statement]</a></span>
    </dt>
    <dd>{{% md %}}A nested configuration block (described below)
configuring one *statement* to be included in the policy document.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">version<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}IAM policy document version. Valid values: `2008-10-17`, `2012-10-17`. Defaults to `2012-10-17`. For more information, see the [AWS IAM User Guide](https://docs.aws.amazon.com/IAM/latest/UserGuide/reference_policies_elements_version.html).
{{% /md %}}</dd>

</dl>
{{% /choosable %}}








## GetPolicyDocument Result

The following output properties are available:




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}id is the provider-assigned unique ID for this managed resource.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Json<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The above arguments serialized as a standard JSON policy document.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Override<wbr>Json<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">Policy<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">Source<wbr>Json<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">Statements<span class="property-indicator"></span>
        <span class="property-type"><a href="#getpolicydocumentstatement">List&lt;Get<wbr>Policy<wbr>Document<wbr>Statement&gt;?</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">Version<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}id is the provider-assigned unique ID for this managed resource.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Json<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The above arguments serialized as a standard JSON policy document.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Override<wbr>Json<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">Policy<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">Source<wbr>Json<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">Statements<span class="property-indicator"></span>
        <span class="property-type"><a href="#getpolicydocumentstatement">[]Get<wbr>Policy<wbr>Document<wbr>Statement</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">Version<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}id is the provider-assigned unique ID for this managed resource.
{{% /md %}}</dd>

    <dt class="property-"
            title="">json<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The above arguments serialized as a standard JSON policy document.
{{% /md %}}</dd>

    <dt class="property-"
            title="">override<wbr>Json<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">policy<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">source<wbr>Json<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">statements<span class="property-indicator"></span>
        <span class="property-type"><a href="#getpolicydocumentstatement">Get<wbr>Policy<wbr>Document<wbr>Statement[]?</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">version<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}id is the provider-assigned unique ID for this managed resource.
{{% /md %}}</dd>

    <dt class="property-"
            title="">json<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The above arguments serialized as a standard JSON policy document.
{{% /md %}}</dd>

    <dt class="property-"
            title="">override_<wbr>json<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">policy_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">source_<wbr>json<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">statements<span class="property-indicator"></span>
        <span class="property-type"><a href="#getpolicydocumentstatement">List[Get<wbr>Policy<wbr>Document<wbr>Statement]</a></span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

    <dt class="property-"
            title="">version<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}{{% /md %}}</dd>

</dl>
{{% /choosable %}}








## Supporting Types

#### GetPolicyDocumentStatement
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#GetPolicyDocumentStatement">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#GetPolicyDocumentStatement">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/iam?tab=doc#GetPolicyDocumentStatementArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/iam?tab=doc#GetPolicyDocumentStatement">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Iam.GetPolicyDocumentStatementArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Iam.GetPolicyDocumentStatement.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Actions<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}A list of actions that this statement either allows
or denies. For example, ``[&#34;ec2:RunInstances&#34;, &#34;s3:*&#34;]``.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Conditions<span class="property-indicator"></span>
        <span class="property-type"><a href="#getpolicydocumentstatementcondition">List&lt;Get<wbr>Policy<wbr>Document<wbr>Statement<wbr>Condition<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}A nested configuration block (described below)
that defines a further, possibly-service-specific condition that constrains
whether this statement applies.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Effect<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Either &#34;Allow&#34; or &#34;Deny&#34;, to specify whether this
statement allows or denies the given actions. The default is &#34;Allow&#34;.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Not<wbr>Actions<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}A list of actions that this statement does *not*
apply to. Used to apply a policy statement to all actions *except* those
listed.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Not<wbr>Principals<span class="property-indicator"></span>
        <span class="property-type"><a href="#getpolicydocumentstatementnotprincipal">List&lt;Get<wbr>Policy<wbr>Document<wbr>Statement<wbr>Not<wbr>Principal<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}Like `principals` except gives resources that
the statement does *not* apply to.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Not<wbr>Resources<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}A list of resource ARNs that this statement
does *not* apply to. Used to apply a policy statement to all resources
*except* those listed.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Principals<span class="property-indicator"></span>
        <span class="property-type"><a href="#getpolicydocumentstatementprincipal">List&lt;Get<wbr>Policy<wbr>Document<wbr>Statement<wbr>Principal<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}A nested configuration block (described below)
specifying a resource (or resource pattern) to which this statement applies.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Resources<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}A list of resource ARNs that this statement applies
to. This is required by AWS if used for an IAM policy.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Sid<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}An ID for the policy statement.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Actions<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}A list of actions that this statement either allows
or denies. For example, ``[&#34;ec2:RunInstances&#34;, &#34;s3:*&#34;]``.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Conditions<span class="property-indicator"></span>
        <span class="property-type"><a href="#getpolicydocumentstatementcondition">[]Get<wbr>Policy<wbr>Document<wbr>Statement<wbr>Condition</a></span>
    </dt>
    <dd>{{% md %}}A nested configuration block (described below)
that defines a further, possibly-service-specific condition that constrains
whether this statement applies.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Effect<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Either &#34;Allow&#34; or &#34;Deny&#34;, to specify whether this
statement allows or denies the given actions. The default is &#34;Allow&#34;.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Not<wbr>Actions<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}A list of actions that this statement does *not*
apply to. Used to apply a policy statement to all actions *except* those
listed.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Not<wbr>Principals<span class="property-indicator"></span>
        <span class="property-type"><a href="#getpolicydocumentstatementnotprincipal">[]Get<wbr>Policy<wbr>Document<wbr>Statement<wbr>Not<wbr>Principal</a></span>
    </dt>
    <dd>{{% md %}}Like `principals` except gives resources that
the statement does *not* apply to.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Not<wbr>Resources<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}A list of resource ARNs that this statement
does *not* apply to. Used to apply a policy statement to all resources
*except* those listed.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Principals<span class="property-indicator"></span>
        <span class="property-type"><a href="#getpolicydocumentstatementprincipal">[]Get<wbr>Policy<wbr>Document<wbr>Statement<wbr>Principal</a></span>
    </dt>
    <dd>{{% md %}}A nested configuration block (described below)
specifying a resource (or resource pattern) to which this statement applies.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Resources<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}A list of resource ARNs that this statement applies
to. This is required by AWS if used for an IAM policy.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Sid<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}An ID for the policy statement.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">actions<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}A list of actions that this statement either allows
or denies. For example, ``[&#34;ec2:RunInstances&#34;, &#34;s3:*&#34;]``.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">conditions<span class="property-indicator"></span>
        <span class="property-type"><a href="#getpolicydocumentstatementcondition">Get<wbr>Policy<wbr>Document<wbr>Statement<wbr>Condition[]?</a></span>
    </dt>
    <dd>{{% md %}}A nested configuration block (described below)
that defines a further, possibly-service-specific condition that constrains
whether this statement applies.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">effect<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Either &#34;Allow&#34; or &#34;Deny&#34;, to specify whether this
statement allows or denies the given actions. The default is &#34;Allow&#34;.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">not<wbr>Actions<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}A list of actions that this statement does *not*
apply to. Used to apply a policy statement to all actions *except* those
listed.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">not<wbr>Principals<span class="property-indicator"></span>
        <span class="property-type"><a href="#getpolicydocumentstatementnotprincipal">Get<wbr>Policy<wbr>Document<wbr>Statement<wbr>Not<wbr>Principal[]?</a></span>
    </dt>
    <dd>{{% md %}}Like `principals` except gives resources that
the statement does *not* apply to.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">not<wbr>Resources<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}A list of resource ARNs that this statement
does *not* apply to. Used to apply a policy statement to all resources
*except* those listed.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">principals<span class="property-indicator"></span>
        <span class="property-type"><a href="#getpolicydocumentstatementprincipal">Get<wbr>Policy<wbr>Document<wbr>Statement<wbr>Principal[]?</a></span>
    </dt>
    <dd>{{% md %}}A nested configuration block (described below)
specifying a resource (or resource pattern) to which this statement applies.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">resources<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}A list of resource ARNs that this statement applies
to. This is required by AWS if used for an IAM policy.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">sid<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}An ID for the policy statement.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">actions<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}A list of actions that this statement either allows
or denies. For example, ``[&#34;ec2:RunInstances&#34;, &#34;s3:*&#34;]``.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">conditions<span class="property-indicator"></span>
        <span class="property-type"><a href="#getpolicydocumentstatementcondition">List[Get<wbr>Policy<wbr>Document<wbr>Statement<wbr>Condition]</a></span>
    </dt>
    <dd>{{% md %}}A nested configuration block (described below)
that defines a further, possibly-service-specific condition that constrains
whether this statement applies.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">effect<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Either &#34;Allow&#34; or &#34;Deny&#34;, to specify whether this
statement allows or denies the given actions. The default is &#34;Allow&#34;.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">not<wbr>Actions<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}A list of actions that this statement does *not*
apply to. Used to apply a policy statement to all actions *except* those
listed.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">not<wbr>Principals<span class="property-indicator"></span>
        <span class="property-type"><a href="#getpolicydocumentstatementnotprincipal">List[Get<wbr>Policy<wbr>Document<wbr>Statement<wbr>Not<wbr>Principal]</a></span>
    </dt>
    <dd>{{% md %}}Like `principals` except gives resources that
the statement does *not* apply to.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">not<wbr>Resources<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}A list of resource ARNs that this statement
does *not* apply to. Used to apply a policy statement to all resources
*except* those listed.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">principals<span class="property-indicator"></span>
        <span class="property-type"><a href="#getpolicydocumentstatementprincipal">List[Get<wbr>Policy<wbr>Document<wbr>Statement<wbr>Principal]</a></span>
    </dt>
    <dd>{{% md %}}A nested configuration block (described below)
specifying a resource (or resource pattern) to which this statement applies.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">resources<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}A list of resource ARNs that this statement applies
to. This is required by AWS if used for an IAM policy.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">sid<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}An ID for the policy statement.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### GetPolicyDocumentStatementCondition
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#GetPolicyDocumentStatementCondition">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#GetPolicyDocumentStatementCondition">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/iam?tab=doc#GetPolicyDocumentStatementConditionArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/iam?tab=doc#GetPolicyDocumentStatementCondition">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Iam.GetPolicyDocumentStatementConditionArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Iam.GetPolicyDocumentStatementCondition.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Test<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the
[IAM condition operator](https://docs.aws.amazon.com/IAM/latest/UserGuide/reference_policies_elements_condition_operators.html)
to evaluate.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Values<span class="property-indicator"></span>
        <span class="property-type">List<string></span>
    </dt>
    <dd>{{% md %}}The values to evaluate the condition against. If multiple
values are provided, the condition matches if at least one of them applies.
(That is, the tests are combined with the &#34;OR&#34; boolean operation.)
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Variable<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of a
[Context Variable](http://docs.aws.amazon.com/IAM/latest/UserGuide/reference_policies_elements.html#AvailableKeys)
to apply the condition to. Context variables may either be standard AWS
variables starting with `aws:`, or service-specific variables prefixed with
the service name.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Test<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the
[IAM condition operator](https://docs.aws.amazon.com/IAM/latest/UserGuide/reference_policies_elements_condition_operators.html)
to evaluate.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Values<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}The values to evaluate the condition against. If multiple
values are provided, the condition matches if at least one of them applies.
(That is, the tests are combined with the &#34;OR&#34; boolean operation.)
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Variable<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of a
[Context Variable](http://docs.aws.amazon.com/IAM/latest/UserGuide/reference_policies_elements.html#AvailableKeys)
to apply the condition to. Context variables may either be standard AWS
variables starting with `aws:`, or service-specific variables prefixed with
the service name.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">test<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the
[IAM condition operator](https://docs.aws.amazon.com/IAM/latest/UserGuide/reference_policies_elements_condition_operators.html)
to evaluate.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">values<span class="property-indicator"></span>
        <span class="property-type">string[]</span>
    </dt>
    <dd>{{% md %}}The values to evaluate the condition against. If multiple
values are provided, the condition matches if at least one of them applies.
(That is, the tests are combined with the &#34;OR&#34; boolean operation.)
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">variable<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of a
[Context Variable](http://docs.aws.amazon.com/IAM/latest/UserGuide/reference_policies_elements.html#AvailableKeys)
to apply the condition to. Context variables may either be standard AWS
variables starting with `aws:`, or service-specific variables prefixed with
the service name.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">test<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the
[IAM condition operator](https://docs.aws.amazon.com/IAM/latest/UserGuide/reference_policies_elements_condition_operators.html)
to evaluate.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">values<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}The values to evaluate the condition against. If multiple
values are provided, the condition matches if at least one of them applies.
(That is, the tests are combined with the &#34;OR&#34; boolean operation.)
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">variable<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of a
[Context Variable](http://docs.aws.amazon.com/IAM/latest/UserGuide/reference_policies_elements.html#AvailableKeys)
to apply the condition to. Context variables may either be standard AWS
variables starting with `aws:`, or service-specific variables prefixed with
the service name.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### GetPolicyDocumentStatementNotPrincipal
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#GetPolicyDocumentStatementNotPrincipal">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#GetPolicyDocumentStatementNotPrincipal">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/iam?tab=doc#GetPolicyDocumentStatementNotPrincipalArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/iam?tab=doc#GetPolicyDocumentStatementNotPrincipal">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Iam.GetPolicyDocumentStatementNotPrincipalArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Iam.GetPolicyDocumentStatementNotPrincipal.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Identifiers<span class="property-indicator"></span>
        <span class="property-type">List<string></span>
    </dt>
    <dd>{{% md %}}List of identifiers for principals. When `type`
is &#34;AWS&#34;, these are IAM user or role ARNs.  When `type` is &#34;Service&#34;, these are AWS Service roles e.g. `lambda.amazonaws.com`.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type of principal. For AWS ARNs this is &#34;AWS&#34;.  For AWS services (e.g. Lambda), this is &#34;Service&#34;.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Identifiers<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}List of identifiers for principals. When `type`
is &#34;AWS&#34;, these are IAM user or role ARNs.  When `type` is &#34;Service&#34;, these are AWS Service roles e.g. `lambda.amazonaws.com`.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type of principal. For AWS ARNs this is &#34;AWS&#34;.  For AWS services (e.g. Lambda), this is &#34;Service&#34;.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">identifiers<span class="property-indicator"></span>
        <span class="property-type">string[]</span>
    </dt>
    <dd>{{% md %}}List of identifiers for principals. When `type`
is &#34;AWS&#34;, these are IAM user or role ARNs.  When `type` is &#34;Service&#34;, these are AWS Service roles e.g. `lambda.amazonaws.com`.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type of principal. For AWS ARNs this is &#34;AWS&#34;.  For AWS services (e.g. Lambda), this is &#34;Service&#34;.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">identifiers<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}List of identifiers for principals. When `type`
is &#34;AWS&#34;, these are IAM user or role ARNs.  When `type` is &#34;Service&#34;, these are AWS Service roles e.g. `lambda.amazonaws.com`.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The type of principal. For AWS ARNs this is &#34;AWS&#34;.  For AWS services (e.g. Lambda), this is &#34;Service&#34;.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### GetPolicyDocumentStatementPrincipal
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#GetPolicyDocumentStatementPrincipal">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#GetPolicyDocumentStatementPrincipal">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/iam?tab=doc#GetPolicyDocumentStatementPrincipalArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/iam?tab=doc#GetPolicyDocumentStatementPrincipal">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Iam.GetPolicyDocumentStatementPrincipalArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Iam.GetPolicyDocumentStatementPrincipal.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Identifiers<span class="property-indicator"></span>
        <span class="property-type">List<string></span>
    </dt>
    <dd>{{% md %}}List of identifiers for principals. When `type`
is &#34;AWS&#34;, these are IAM user or role ARNs.  When `type` is &#34;Service&#34;, these are AWS Service roles e.g. `lambda.amazonaws.com`.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type of principal. For AWS ARNs this is &#34;AWS&#34;.  For AWS services (e.g. Lambda), this is &#34;Service&#34;.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Identifiers<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}List of identifiers for principals. When `type`
is &#34;AWS&#34;, these are IAM user or role ARNs.  When `type` is &#34;Service&#34;, these are AWS Service roles e.g. `lambda.amazonaws.com`.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type of principal. For AWS ARNs this is &#34;AWS&#34;.  For AWS services (e.g. Lambda), this is &#34;Service&#34;.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">identifiers<span class="property-indicator"></span>
        <span class="property-type">string[]</span>
    </dt>
    <dd>{{% md %}}List of identifiers for principals. When `type`
is &#34;AWS&#34;, these are IAM user or role ARNs.  When `type` is &#34;Service&#34;, these are AWS Service roles e.g. `lambda.amazonaws.com`.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type of principal. For AWS ARNs this is &#34;AWS&#34;.  For AWS services (e.g. Lambda), this is &#34;Service&#34;.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">identifiers<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}List of identifiers for principals. When `type`
is &#34;AWS&#34;, these are IAM user or role ARNs.  When `type` is &#34;Service&#34;, these are AWS Service roles e.g. `lambda.amazonaws.com`.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The type of principal. For AWS ARNs this is &#34;AWS&#34;.  For AWS services (e.g. Lambda), this is &#34;Service&#34;.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}








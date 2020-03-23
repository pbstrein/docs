
---
title: "SqlInjectionMatchSet"
block_external_search_index: true
---

Provides a WAF SQL Injection Match Set Resource

## Example Usage

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const sqlInjectionMatchSet = new aws.waf.SqlInjectionMatchSet("sql_injection_match_set", {
    sqlInjectionMatchTuples: [{
        fieldToMatch: {
            type: "QUERY_STRING",
        },
        textTransformation: "URL_DECODE",
    }],
});
```

> This content is derived from https://github.com/terraform-providers/terraform-provider-aws/blob/master/website/docs/r/waf_sql_injection_match_set.html.markdown.



## Create a SqlInjectionMatchSet Resource

{{< chooser language "javascript,typescript,python,go,csharp" / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/waf/#SqlInjectionMatchSet">SqlInjectionMatchSet</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/waf/#SqlInjectionMatchSetArgs">SqlInjectionMatchSetArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">SqlInjectionMatchSet</span><span class="p">(resource_name, opts=None, </span>name=None<span class="p">, </span>sql_injection_match_tuples=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewSqlInjectionMatchSet<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/waf?tab=doc#SqlInjectionMatchSetArgs">SqlInjectionMatchSetArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/waf?tab=doc#SqlInjectionMatchSet">SqlInjectionMatchSet</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Waf.SqlInjectionMatchSet.html">SqlInjectionMatchSet</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Waf.SqlInjectionMatchSetArgs.html">SqlInjectionMatchSetArgs</a></span>? <span class="nx">args = null<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
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
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name or description of the SQL Injection Match Set.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Sql<wbr>Injection<wbr>Match<wbr>Tuples<span class="property-indicator"></span>
        <span class="property-type"><a href="#sqlinjectionmatchsetsqlinjectionmatchtuple">List&lt;Sql<wbr>Injection<wbr>Match<wbr>Set<wbr>Sql<wbr>Injection<wbr>Match<wbr>Tuple<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}The parts of web requests that you want AWS WAF to inspect for malicious SQL code and, if you want AWS WAF to inspect a header, the name of the header.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name or description of the SQL Injection Match Set.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Sql<wbr>Injection<wbr>Match<wbr>Tuples<span class="property-indicator"></span>
        <span class="property-type"><a href="#sqlinjectionmatchsetsqlinjectionmatchtuple">[]Sql<wbr>Injection<wbr>Match<wbr>Set<wbr>Sql<wbr>Injection<wbr>Match<wbr>Tuple</a></span>
    </dt>
    <dd>{{% md %}}The parts of web requests that you want AWS WAF to inspect for malicious SQL code and, if you want AWS WAF to inspect a header, the name of the header.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name or description of the SQL Injection Match Set.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">sql<wbr>Injection<wbr>Match<wbr>Tuples<span class="property-indicator"></span>
        <span class="property-type"><a href="#sqlinjectionmatchsetsqlinjectionmatchtuple">Sql<wbr>Injection<wbr>Match<wbr>Set<wbr>Sql<wbr>Injection<wbr>Match<wbr>Tuple[]?</a></span>
    </dt>
    <dd>{{% md %}}The parts of web requests that you want AWS WAF to inspect for malicious SQL code and, if you want AWS WAF to inspect a header, the name of the header.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name or description of the SQL Injection Match Set.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">sql_<wbr>injection_<wbr>match_<wbr>tuples<span class="property-indicator"></span>
        <span class="property-type"><a href="#sqlinjectionmatchsetsqlinjectionmatchtuple">List[Sql<wbr>Injection<wbr>Match<wbr>Set<wbr>Sql<wbr>Injection<wbr>Match<wbr>Tuple]</a></span>
    </dt>
    <dd>{{% md %}}The parts of web requests that you want AWS WAF to inspect for malicious SQL code and, if you want AWS WAF to inspect a header, the name of the header.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}




## SqlInjectionMatchSet Output Properties

The following output properties are available:




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name or description of the SQL Injection Match Set.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Sql<wbr>Injection<wbr>Match<wbr>Tuples<span class="property-indicator"></span>
        <span class="property-type"><a href="#sqlinjectionmatchsetsqlinjectionmatchtuple">List&lt;Sql<wbr>Injection<wbr>Match<wbr>Set<wbr>Sql<wbr>Injection<wbr>Match<wbr>Tuple&gt;?</a></span>
    </dt>
    <dd>{{% md %}}The parts of web requests that you want AWS WAF to inspect for malicious SQL code and, if you want AWS WAF to inspect a header, the name of the header.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name or description of the SQL Injection Match Set.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Sql<wbr>Injection<wbr>Match<wbr>Tuples<span class="property-indicator"></span>
        <span class="property-type"><a href="#sqlinjectionmatchsetsqlinjectionmatchtuple">[]Sql<wbr>Injection<wbr>Match<wbr>Set<wbr>Sql<wbr>Injection<wbr>Match<wbr>Tuple</a></span>
    </dt>
    <dd>{{% md %}}The parts of web requests that you want AWS WAF to inspect for malicious SQL code and, if you want AWS WAF to inspect a header, the name of the header.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name or description of the SQL Injection Match Set.
{{% /md %}}</dd>

    <dt class="property-"
            title="">sql<wbr>Injection<wbr>Match<wbr>Tuples<span class="property-indicator"></span>
        <span class="property-type"><a href="#sqlinjectionmatchsetsqlinjectionmatchtuple">Sql<wbr>Injection<wbr>Match<wbr>Set<wbr>Sql<wbr>Injection<wbr>Match<wbr>Tuple[]?</a></span>
    </dt>
    <dd>{{% md %}}The parts of web requests that you want AWS WAF to inspect for malicious SQL code and, if you want AWS WAF to inspect a header, the name of the header.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name or description of the SQL Injection Match Set.
{{% /md %}}</dd>

    <dt class="property-"
            title="">sql_<wbr>injection_<wbr>match_<wbr>tuples<span class="property-indicator"></span>
        <span class="property-type"><a href="#sqlinjectionmatchsetsqlinjectionmatchtuple">List[Sql<wbr>Injection<wbr>Match<wbr>Set<wbr>Sql<wbr>Injection<wbr>Match<wbr>Tuple]</a></span>
    </dt>
    <dd>{{% md %}}The parts of web requests that you want AWS WAF to inspect for malicious SQL code and, if you want AWS WAF to inspect a header, the name of the header.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





## Look up an Existing SqlInjectionMatchSet Resource

{{< chooser language "javascript,typescript,python,go,csharp  " / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">pulumi.Input&lt;pulumi.ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/waf/#SqlInjectionMatchSetState">SqlInjectionMatchSetState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/waf/#SqlInjectionMatchSet">SqlInjectionMatchSet</a></span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>name=None<span class="p">, </span>sql_injection_match_tuples=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetSqlInjectionMatchSet<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">pulumi.IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/waf?tab=doc#SqlInjectionMatchSetState">SqlInjectionMatchSetState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/waf?tab=doc#SqlInjectionMatchSet">SqlInjectionMatchSet</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Waf.SqlInjectionMatchSet.html">SqlInjectionMatchSet</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Pulumi.Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Waf.SqlInjectionMatchSetState.html">SqlInjectionMatchSetState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
{{% /choosable %}}

Get an existing SqlInjectionMatchSet resource's state with the given name, ID, and optional extra properties used to qualify the lookup.

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
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name or description of the SQL Injection Match Set.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Sql<wbr>Injection<wbr>Match<wbr>Tuples<span class="property-indicator"></span>
        <span class="property-type"><a href="#sqlinjectionmatchsetsqlinjectionmatchtuple">List&lt;Sql<wbr>Injection<wbr>Match<wbr>Set<wbr>Sql<wbr>Injection<wbr>Match<wbr>Tuple<wbr>Args&gt;?</a></span>
    </dt>
    <dd>{{% md %}}The parts of web requests that you want AWS WAF to inspect for malicious SQL code and, if you want AWS WAF to inspect a header, the name of the header.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name or description of the SQL Injection Match Set.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Sql<wbr>Injection<wbr>Match<wbr>Tuples<span class="property-indicator"></span>
        <span class="property-type"><a href="#sqlinjectionmatchsetsqlinjectionmatchtuple">[]Sql<wbr>Injection<wbr>Match<wbr>Set<wbr>Sql<wbr>Injection<wbr>Match<wbr>Tuple</a></span>
    </dt>
    <dd>{{% md %}}The parts of web requests that you want AWS WAF to inspect for malicious SQL code and, if you want AWS WAF to inspect a header, the name of the header.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name or description of the SQL Injection Match Set.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">sql<wbr>Injection<wbr>Match<wbr>Tuples<span class="property-indicator"></span>
        <span class="property-type"><a href="#sqlinjectionmatchsetsqlinjectionmatchtuple">Sql<wbr>Injection<wbr>Match<wbr>Set<wbr>Sql<wbr>Injection<wbr>Match<wbr>Tuple[]?</a></span>
    </dt>
    <dd>{{% md %}}The parts of web requests that you want AWS WAF to inspect for malicious SQL code and, if you want AWS WAF to inspect a header, the name of the header.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name or description of the SQL Injection Match Set.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">sql_<wbr>injection_<wbr>match_<wbr>tuples<span class="property-indicator"></span>
        <span class="property-type"><a href="#sqlinjectionmatchsetsqlinjectionmatchtuple">List[Sql<wbr>Injection<wbr>Match<wbr>Set<wbr>Sql<wbr>Injection<wbr>Match<wbr>Tuple]</a></span>
    </dt>
    <dd>{{% md %}}The parts of web requests that you want AWS WAF to inspect for malicious SQL code and, if you want AWS WAF to inspect a header, the name of the header.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}







## Supporting Types

#### SqlInjectionMatchSetSqlInjectionMatchTuple
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#SqlInjectionMatchSetSqlInjectionMatchTuple">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#SqlInjectionMatchSetSqlInjectionMatchTuple">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/waf?tab=doc#SqlInjectionMatchSetSqlInjectionMatchTupleArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/waf?tab=doc#SqlInjectionMatchSetSqlInjectionMatchTupleOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Waf.SqlInjectionMatchSetSqlInjectionMatchTupleArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Waf.SqlInjectionMatchSetSqlInjectionMatchTuple.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Field<wbr>To<wbr>Match<span class="property-indicator"></span>
        <span class="property-type"><a href="#sqlinjectionmatchsetsqlinjectionmatchtuplefieldtomatch">Sql<wbr>Injection<wbr>Match<wbr>Set<wbr>Sql<wbr>Injection<wbr>Match<wbr>Tuple<wbr>Field<wbr>To<wbr>Match<wbr>Args</a></span>
    </dt>
    <dd>{{% md %}}Specifies where in a web request to look for snippets of malicious SQL code.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Text<wbr>Transformation<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Text transformations used to eliminate unusual formatting that attackers use in web requests in an effort to bypass AWS WAF.
If you specify a transformation, AWS WAF performs the transformation on `field_to_match` before inspecting a request for a match.
e.g. `CMD_LINE`, `HTML_ENTITY_DECODE` or `NONE`.
See [docs](http://docs.aws.amazon.com/waf/latest/APIReference/API_SqlInjectionMatchTuple.html#WAF-Type-SqlInjectionMatchTuple-TextTransformation)
for all supported values.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Field<wbr>To<wbr>Match<span class="property-indicator"></span>
        <span class="property-type"><a href="#sqlinjectionmatchsetsqlinjectionmatchtuplefieldtomatch">Sql<wbr>Injection<wbr>Match<wbr>Set<wbr>Sql<wbr>Injection<wbr>Match<wbr>Tuple<wbr>Field<wbr>To<wbr>Match</a></span>
    </dt>
    <dd>{{% md %}}Specifies where in a web request to look for snippets of malicious SQL code.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Text<wbr>Transformation<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Text transformations used to eliminate unusual formatting that attackers use in web requests in an effort to bypass AWS WAF.
If you specify a transformation, AWS WAF performs the transformation on `field_to_match` before inspecting a request for a match.
e.g. `CMD_LINE`, `HTML_ENTITY_DECODE` or `NONE`.
See [docs](http://docs.aws.amazon.com/waf/latest/APIReference/API_SqlInjectionMatchTuple.html#WAF-Type-SqlInjectionMatchTuple-TextTransformation)
for all supported values.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">field<wbr>To<wbr>Match<span class="property-indicator"></span>
        <span class="property-type"><a href="#sqlinjectionmatchsetsqlinjectionmatchtuplefieldtomatch">Sql<wbr>Injection<wbr>Match<wbr>Set<wbr>Sql<wbr>Injection<wbr>Match<wbr>Tuple<wbr>Field<wbr>To<wbr>Match</a></span>
    </dt>
    <dd>{{% md %}}Specifies where in a web request to look for snippets of malicious SQL code.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">text<wbr>Transformation<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}Text transformations used to eliminate unusual formatting that attackers use in web requests in an effort to bypass AWS WAF.
If you specify a transformation, AWS WAF performs the transformation on `field_to_match` before inspecting a request for a match.
e.g. `CMD_LINE`, `HTML_ENTITY_DECODE` or `NONE`.
See [docs](http://docs.aws.amazon.com/waf/latest/APIReference/API_SqlInjectionMatchTuple.html#WAF-Type-SqlInjectionMatchTuple-TextTransformation)
for all supported values.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">field<wbr>To<wbr>Match<span class="property-indicator"></span>
        <span class="property-type"><a href="#sqlinjectionmatchsetsqlinjectionmatchtuplefieldtomatch">Dict[Sql<wbr>Injection<wbr>Match<wbr>Set<wbr>Sql<wbr>Injection<wbr>Match<wbr>Tuple<wbr>Field<wbr>To<wbr>Match]</a></span>
    </dt>
    <dd>{{% md %}}Specifies where in a web request to look for snippets of malicious SQL code.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">text<wbr>Transformation<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Text transformations used to eliminate unusual formatting that attackers use in web requests in an effort to bypass AWS WAF.
If you specify a transformation, AWS WAF performs the transformation on `field_to_match` before inspecting a request for a match.
e.g. `CMD_LINE`, `HTML_ENTITY_DECODE` or `NONE`.
See [docs](http://docs.aws.amazon.com/waf/latest/APIReference/API_SqlInjectionMatchTuple.html#WAF-Type-SqlInjectionMatchTuple-TextTransformation)
for all supported values.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### SqlInjectionMatchSetSqlInjectionMatchTupleFieldToMatch
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#SqlInjectionMatchSetSqlInjectionMatchTupleFieldToMatch">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#SqlInjectionMatchSetSqlInjectionMatchTupleFieldToMatch">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/waf?tab=doc#SqlInjectionMatchSetSqlInjectionMatchTupleFieldToMatchArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/waf?tab=doc#SqlInjectionMatchSetSqlInjectionMatchTupleFieldToMatchOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Waf.SqlInjectionMatchSetSqlInjectionMatchTupleFieldToMatchArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Waf.SqlInjectionMatchSetSqlInjectionMatchTupleFieldToMatch.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Data<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}When `type` is `HEADER`, enter the name of the header that you want to search, e.g. `User-Agent` or `Referer`.
If `type` is any other value, omit this field.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The part of the web request that you want AWS WAF to search for a specified string.
e.g. `HEADER`, `METHOD` or `BODY`.
See [docs](http://docs.aws.amazon.com/waf/latest/APIReference/API_FieldToMatch.html)
for all supported values.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Data<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}When `type` is `HEADER`, enter the name of the header that you want to search, e.g. `User-Agent` or `Referer`.
If `type` is any other value, omit this field.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The part of the web request that you want AWS WAF to search for a specified string.
e.g. `HEADER`, `METHOD` or `BODY`.
See [docs](http://docs.aws.amazon.com/waf/latest/APIReference/API_FieldToMatch.html)
for all supported values.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">data<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}When `type` is `HEADER`, enter the name of the header that you want to search, e.g. `User-Agent` or `Referer`.
If `type` is any other value, omit this field.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The part of the web request that you want AWS WAF to search for a specified string.
e.g. `HEADER`, `METHOD` or `BODY`.
See [docs](http://docs.aws.amazon.com/waf/latest/APIReference/API_FieldToMatch.html)
for all supported values.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">data<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}When `type` is `HEADER`, enter the name of the header that you want to search, e.g. `User-Agent` or `Referer`.
If `type` is any other value, omit this field.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The part of the web request that you want AWS WAF to search for a specified string.
e.g. `HEADER`, `METHOD` or `BODY`.
See [docs](http://docs.aws.amazon.com/waf/latest/APIReference/API_FieldToMatch.html)
for all supported values.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}








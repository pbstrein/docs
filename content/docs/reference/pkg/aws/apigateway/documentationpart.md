
---
title: "DocumentationPart"
block_external_search_index: true
---

Provides a settings of an API Gateway Documentation Part.

## Example Usage

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const exampleRestApi = new aws.apigateway.RestApi("example", {});
const exampleDocumentationPart = new aws.apigateway.DocumentationPart("example", {
    location: {
        method: "GET",
        path: "/example",
        type: "METHOD",
    },
    properties: "{\"description\":\"Example description\"}",
    restApiId: exampleRestApi.id,
});
```

> This content is derived from https://github.com/terraform-providers/terraform-provider-aws/blob/master/website/docs/r/api_gateway_documentation_part.html.markdown.



## Create a DocumentationPart Resource

{{< chooser language "javascript,typescript,python,go,csharp" / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/apigateway/#DocumentationPart">DocumentationPart</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/apigateway/#DocumentationPartArgs">DocumentationPartArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">DocumentationPart</span><span class="p">(resource_name, opts=None, </span>location=None<span class="p">, </span>properties=None<span class="p">, </span>rest_api_id=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewDocumentationPart<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/apigateway?tab=doc#DocumentationPartArgs">DocumentationPartArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/apigateway?tab=doc#DocumentationPart">DocumentationPart</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Apigateway.DocumentationPart.html">DocumentationPart</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Apigateway.DocumentationPartArgs.html">DocumentationPartArgs</a></span> <span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
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
            title="Required">Location<span class="property-indicator"></span>
        <span class="property-type"><a href="#documentationpartlocation">Documentation<wbr>Part<wbr>Location<wbr>Args</a></span>
    </dt>
    <dd>{{% md %}}The location of the targeted API entity of the to-be-created documentation part. See below.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Properties<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}A content map of API-specific key-value pairs describing the targeted API entity. The map must be encoded as a JSON string, e.g., &#34;{ \&#34;description\&#34;: \&#34;The API does ...\&#34; }&#34;. Only Swagger-compliant key-value pairs can be exported and, hence, published.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Rest<wbr>Api<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the associated Rest API
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Location<span class="property-indicator"></span>
        <span class="property-type"><a href="#documentationpartlocation">Documentation<wbr>Part<wbr>Location</a></span>
    </dt>
    <dd>{{% md %}}The location of the targeted API entity of the to-be-created documentation part. See below.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Properties<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}A content map of API-specific key-value pairs describing the targeted API entity. The map must be encoded as a JSON string, e.g., &#34;{ \&#34;description\&#34;: \&#34;The API does ...\&#34; }&#34;. Only Swagger-compliant key-value pairs can be exported and, hence, published.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Rest<wbr>Api<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the associated Rest API
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">location<span class="property-indicator"></span>
        <span class="property-type"><a href="#documentationpartlocation">Documentation<wbr>Part<wbr>Location</a></span>
    </dt>
    <dd>{{% md %}}The location of the targeted API entity of the to-be-created documentation part. See below.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">properties<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}A content map of API-specific key-value pairs describing the targeted API entity. The map must be encoded as a JSON string, e.g., &#34;{ \&#34;description\&#34;: \&#34;The API does ...\&#34; }&#34;. Only Swagger-compliant key-value pairs can be exported and, hence, published.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">rest<wbr>Api<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the associated Rest API
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">location<span class="property-indicator"></span>
        <span class="property-type"><a href="#documentationpartlocation">Dict[Documentation<wbr>Part<wbr>Location]</a></span>
    </dt>
    <dd>{{% md %}}The location of the targeted API entity of the to-be-created documentation part. See below.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">properties<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A content map of API-specific key-value pairs describing the targeted API entity. The map must be encoded as a JSON string, e.g., &#34;{ \&#34;description\&#34;: \&#34;The API does ...\&#34; }&#34;. Only Swagger-compliant key-value pairs can be exported and, hence, published.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">rest_<wbr>api_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ID of the associated Rest API
{{% /md %}}</dd>

</dl>
{{% /choosable %}}




## DocumentationPart Output Properties

The following output properties are available:




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Location<span class="property-indicator"></span>
        <span class="property-type"><a href="#documentationpartlocation">Documentation<wbr>Part<wbr>Location</a></span>
    </dt>
    <dd>{{% md %}}The location of the targeted API entity of the to-be-created documentation part. See below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Properties<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}A content map of API-specific key-value pairs describing the targeted API entity. The map must be encoded as a JSON string, e.g., &#34;{ \&#34;description\&#34;: \&#34;The API does ...\&#34; }&#34;. Only Swagger-compliant key-value pairs can be exported and, hence, published.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Rest<wbr>Api<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the associated Rest API
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Location<span class="property-indicator"></span>
        <span class="property-type"><a href="#documentationpartlocation">Documentation<wbr>Part<wbr>Location</a></span>
    </dt>
    <dd>{{% md %}}The location of the targeted API entity of the to-be-created documentation part. See below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Properties<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}A content map of API-specific key-value pairs describing the targeted API entity. The map must be encoded as a JSON string, e.g., &#34;{ \&#34;description\&#34;: \&#34;The API does ...\&#34; }&#34;. Only Swagger-compliant key-value pairs can be exported and, hence, published.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Rest<wbr>Api<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the associated Rest API
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">location<span class="property-indicator"></span>
        <span class="property-type"><a href="#documentationpartlocation">Documentation<wbr>Part<wbr>Location</a></span>
    </dt>
    <dd>{{% md %}}The location of the targeted API entity of the to-be-created documentation part. See below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">properties<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}A content map of API-specific key-value pairs describing the targeted API entity. The map must be encoded as a JSON string, e.g., &#34;{ \&#34;description\&#34;: \&#34;The API does ...\&#34; }&#34;. Only Swagger-compliant key-value pairs can be exported and, hence, published.
{{% /md %}}</dd>

    <dt class="property-"
            title="">rest<wbr>Api<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The ID of the associated Rest API
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">location<span class="property-indicator"></span>
        <span class="property-type"><a href="#documentationpartlocation">Dict[Documentation<wbr>Part<wbr>Location]</a></span>
    </dt>
    <dd>{{% md %}}The location of the targeted API entity of the to-be-created documentation part. See below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">properties<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A content map of API-specific key-value pairs describing the targeted API entity. The map must be encoded as a JSON string, e.g., &#34;{ \&#34;description\&#34;: \&#34;The API does ...\&#34; }&#34;. Only Swagger-compliant key-value pairs can be exported and, hence, published.
{{% /md %}}</dd>

    <dt class="property-"
            title="">rest_<wbr>api_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ID of the associated Rest API
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





## Look up an Existing DocumentationPart Resource

{{< chooser language "javascript,typescript,python,go,csharp  " / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">pulumi.Input&lt;pulumi.ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/apigateway/#DocumentationPartState">DocumentationPartState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/apigateway/#DocumentationPart">DocumentationPart</a></span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>location=None<span class="p">, </span>properties=None<span class="p">, </span>rest_api_id=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetDocumentationPart<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">pulumi.IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/apigateway?tab=doc#DocumentationPartState">DocumentationPartState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/apigateway?tab=doc#DocumentationPart">DocumentationPart</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Apigateway.DocumentationPart.html">DocumentationPart</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Pulumi.Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Apigateway.DocumentationPartState.html">DocumentationPartState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
{{% /choosable %}}

Get an existing DocumentationPart resource's state with the given name, ID, and optional extra properties used to qualify the lookup.

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
            title="Optional">Location<span class="property-indicator"></span>
        <span class="property-type"><a href="#documentationpartlocation">Documentation<wbr>Part<wbr>Location<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}The location of the targeted API entity of the to-be-created documentation part. See below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Properties<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A content map of API-specific key-value pairs describing the targeted API entity. The map must be encoded as a JSON string, e.g., &#34;{ \&#34;description\&#34;: \&#34;The API does ...\&#34; }&#34;. Only Swagger-compliant key-value pairs can be exported and, hence, published.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Rest<wbr>Api<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ID of the associated Rest API
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Location<span class="property-indicator"></span>
        <span class="property-type"><a href="#documentationpartlocation">*Documentation<wbr>Part<wbr>Location</a></span>
    </dt>
    <dd>{{% md %}}The location of the targeted API entity of the to-be-created documentation part. See below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Properties<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}A content map of API-specific key-value pairs describing the targeted API entity. The map must be encoded as a JSON string, e.g., &#34;{ \&#34;description\&#34;: \&#34;The API does ...\&#34; }&#34;. Only Swagger-compliant key-value pairs can be exported and, hence, published.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Rest<wbr>Api<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The ID of the associated Rest API
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">location<span class="property-indicator"></span>
        <span class="property-type"><a href="#documentationpartlocation">Documentation<wbr>Part<wbr>Location?</a></span>
    </dt>
    <dd>{{% md %}}The location of the targeted API entity of the to-be-created documentation part. See below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">properties<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A content map of API-specific key-value pairs describing the targeted API entity. The map must be encoded as a JSON string, e.g., &#34;{ \&#34;description\&#34;: \&#34;The API does ...\&#34; }&#34;. Only Swagger-compliant key-value pairs can be exported and, hence, published.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">rest<wbr>Api<wbr>Id<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The ID of the associated Rest API
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">location<span class="property-indicator"></span>
        <span class="property-type"><a href="#documentationpartlocation">Dict[Documentation<wbr>Part<wbr>Location]</a></span>
    </dt>
    <dd>{{% md %}}The location of the targeted API entity of the to-be-created documentation part. See below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">properties<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A content map of API-specific key-value pairs describing the targeted API entity. The map must be encoded as a JSON string, e.g., &#34;{ \&#34;description\&#34;: \&#34;The API does ...\&#34; }&#34;. Only Swagger-compliant key-value pairs can be exported and, hence, published.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">rest_<wbr>api_<wbr>id<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The ID of the associated Rest API
{{% /md %}}</dd>

</dl>
{{% /choosable %}}







## Supporting Types

#### DocumentationPartLocation
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#DocumentationPartLocation">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#DocumentationPartLocation">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/apigateway?tab=doc#DocumentationPartLocationArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/apigateway?tab=doc#DocumentationPartLocationOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Apigateway.DocumentationPartLocationArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Apigateway.DocumentationPartLocation.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Method<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The HTTP verb of a method. The default value is `*` for any method.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the targeted API entity.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Path<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The URL path of the target. The default value is `/` for the root resource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Status<wbr>Code<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The HTTP status code of a response. The default value is `*` for any status code.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type of API entity to which the documentation content applies. e.g. `API`, `METHOD` or `REQUEST_BODY`
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Method<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The HTTP verb of a method. The default value is `*` for any method.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name of the targeted API entity.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Path<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The URL path of the target. The default value is `/` for the root resource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Status<wbr>Code<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The HTTP status code of a response. The default value is `*` for any status code.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type of API entity to which the documentation content applies. e.g. `API`, `METHOD` or `REQUEST_BODY`
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">method<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The HTTP verb of a method. The default value is `*` for any method.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the targeted API entity.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">path<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The URL path of the target. The default value is `/` for the root resource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">status<wbr>Code<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The HTTP status code of a response. The default value is `*` for any status code.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">type<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The type of API entity to which the documentation content applies. e.g. `API`, `METHOD` or `REQUEST_BODY`
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">method<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The HTTP verb of a method. The default value is `*` for any method.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the targeted API entity.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">path<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The URL path of the target. The default value is `/` for the root resource.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">status_<wbr>code<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The HTTP status code of a response. The default value is `*` for any status code.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">type<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The type of API entity to which the documentation content applies. e.g. `API`, `METHOD` or `REQUEST_BODY`
{{% /md %}}</dd>

</dl>
{{% /choosable %}}








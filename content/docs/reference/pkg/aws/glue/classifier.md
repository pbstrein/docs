
---
title: "Classifier"
block_external_search_index: true
---

Provides a Glue Classifier resource.

> **NOTE:** It is only valid to create one type of classifier (csv, grok, JSON, or XML). Changing classifier types will recreate the classifier.

## Example Usage

### Csv Classifier

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const example = new aws.glue.Classifier("example", {
    csvClassifier: {
        allowSingleColumn: false,
        containsHeader: "PRESENT",
        delimiter: ",",
        disableValueTrimming: false,
        headers: [
            "example1",
            "example2",
        ],
        quoteSymbol: "'",
    },
});
```

### Grok Classifier

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const example = new aws.glue.Classifier("example", {
    grokClassifier: {
        classification: "example",
        grokPattern: "example",
    },
});
```

### JSON Classifier

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const example = new aws.glue.Classifier("example", {
    jsonClassifier: {
        jsonPath: "example",
    },
});
```

### XML Classifier

```typescript
import * as pulumi from "@pulumi/pulumi";
import * as aws from "@pulumi/aws";

const example = new aws.glue.Classifier("example", {
    xmlClassifier: {
        classification: "example",
        rowTag: "example",
    },
});
```

> This content is derived from https://github.com/terraform-providers/terraform-provider-aws/blob/master/website/docs/r/glue_classifier.html.markdown.



## Create a Classifier Resource

{{< chooser language "javascript,typescript,python,go,csharp" / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/glue/#Classifier">Classifier</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/glue/#ClassifierArgs">ClassifierArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">Classifier</span><span class="p">(resource_name, opts=None, </span>csv_classifier=None<span class="p">, </span>grok_classifier=None<span class="p">, </span>json_classifier=None<span class="p">, </span>name=None<span class="p">, </span>xml_classifier=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewClassifier<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/glue?tab=doc#ClassifierArgs">ClassifierArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/glue?tab=doc#Classifier">Classifier</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Glue.Classifier.html">Classifier</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Glue.ClassifierArgs.html">ClassifierArgs</a></span>? <span class="nx">args = null<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
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
            title="Optional">Csv<wbr>Classifier<span class="property-indicator"></span>
        <span class="property-type"><a href="#classifiercsvclassifier">Classifier<wbr>Csv<wbr>Classifier<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}A classifier for Csv content. Defined below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Grok<wbr>Classifier<span class="property-indicator"></span>
        <span class="property-type"><a href="#classifiergrokclassifier">Classifier<wbr>Grok<wbr>Classifier<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}A classifier that uses grok patterns. Defined below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Json<wbr>Classifier<span class="property-indicator"></span>
        <span class="property-type"><a href="#classifierjsonclassifier">Classifier<wbr>Json<wbr>Classifier<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}A classifier for JSON content. Defined below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the classifier.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Xml<wbr>Classifier<span class="property-indicator"></span>
        <span class="property-type"><a href="#classifierxmlclassifier">Classifier<wbr>Xml<wbr>Classifier<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}A classifier for XML content. Defined below.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Csv<wbr>Classifier<span class="property-indicator"></span>
        <span class="property-type"><a href="#classifiercsvclassifier">*Classifier<wbr>Csv<wbr>Classifier</a></span>
    </dt>
    <dd>{{% md %}}A classifier for Csv content. Defined below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Grok<wbr>Classifier<span class="property-indicator"></span>
        <span class="property-type"><a href="#classifiergrokclassifier">*Classifier<wbr>Grok<wbr>Classifier</a></span>
    </dt>
    <dd>{{% md %}}A classifier that uses grok patterns. Defined below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Json<wbr>Classifier<span class="property-indicator"></span>
        <span class="property-type"><a href="#classifierjsonclassifier">*Classifier<wbr>Json<wbr>Classifier</a></span>
    </dt>
    <dd>{{% md %}}A classifier for JSON content. Defined below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name of the classifier.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Xml<wbr>Classifier<span class="property-indicator"></span>
        <span class="property-type"><a href="#classifierxmlclassifier">*Classifier<wbr>Xml<wbr>Classifier</a></span>
    </dt>
    <dd>{{% md %}}A classifier for XML content. Defined below.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">csv<wbr>Classifier<span class="property-indicator"></span>
        <span class="property-type"><a href="#classifiercsvclassifier">Classifier<wbr>Csv<wbr>Classifier?</a></span>
    </dt>
    <dd>{{% md %}}A classifier for Csv content. Defined below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">grok<wbr>Classifier<span class="property-indicator"></span>
        <span class="property-type"><a href="#classifiergrokclassifier">Classifier<wbr>Grok<wbr>Classifier?</a></span>
    </dt>
    <dd>{{% md %}}A classifier that uses grok patterns. Defined below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">json<wbr>Classifier<span class="property-indicator"></span>
        <span class="property-type"><a href="#classifierjsonclassifier">Classifier<wbr>Json<wbr>Classifier?</a></span>
    </dt>
    <dd>{{% md %}}A classifier for JSON content. Defined below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the classifier.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">xml<wbr>Classifier<span class="property-indicator"></span>
        <span class="property-type"><a href="#classifierxmlclassifier">Classifier<wbr>Xml<wbr>Classifier?</a></span>
    </dt>
    <dd>{{% md %}}A classifier for XML content. Defined below.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">csv_<wbr>classifier<span class="property-indicator"></span>
        <span class="property-type"><a href="#classifiercsvclassifier">Dict[Classifier<wbr>Csv<wbr>Classifier]</a></span>
    </dt>
    <dd>{{% md %}}A classifier for Csv content. Defined below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">grok_<wbr>classifier<span class="property-indicator"></span>
        <span class="property-type"><a href="#classifiergrokclassifier">Dict[Classifier<wbr>Grok<wbr>Classifier]</a></span>
    </dt>
    <dd>{{% md %}}A classifier that uses grok patterns. Defined below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">json_<wbr>classifier<span class="property-indicator"></span>
        <span class="property-type"><a href="#classifierjsonclassifier">Dict[Classifier<wbr>Json<wbr>Classifier]</a></span>
    </dt>
    <dd>{{% md %}}A classifier for JSON content. Defined below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the classifier.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">xml_<wbr>classifier<span class="property-indicator"></span>
        <span class="property-type"><a href="#classifierxmlclassifier">Dict[Classifier<wbr>Xml<wbr>Classifier]</a></span>
    </dt>
    <dd>{{% md %}}A classifier for XML content. Defined below.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}




## Classifier Output Properties

The following output properties are available:




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Csv<wbr>Classifier<span class="property-indicator"></span>
        <span class="property-type"><a href="#classifiercsvclassifier">Classifier<wbr>Csv<wbr>Classifier?</a></span>
    </dt>
    <dd>{{% md %}}A classifier for Csv content. Defined below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Grok<wbr>Classifier<span class="property-indicator"></span>
        <span class="property-type"><a href="#classifiergrokclassifier">Classifier<wbr>Grok<wbr>Classifier?</a></span>
    </dt>
    <dd>{{% md %}}A classifier that uses grok patterns. Defined below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Json<wbr>Classifier<span class="property-indicator"></span>
        <span class="property-type"><a href="#classifierjsonclassifier">Classifier<wbr>Json<wbr>Classifier?</a></span>
    </dt>
    <dd>{{% md %}}A classifier for JSON content. Defined below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the classifier.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Xml<wbr>Classifier<span class="property-indicator"></span>
        <span class="property-type"><a href="#classifierxmlclassifier">Classifier<wbr>Xml<wbr>Classifier?</a></span>
    </dt>
    <dd>{{% md %}}A classifier for XML content. Defined below.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">Csv<wbr>Classifier<span class="property-indicator"></span>
        <span class="property-type"><a href="#classifiercsvclassifier">*Classifier<wbr>Csv<wbr>Classifier</a></span>
    </dt>
    <dd>{{% md %}}A classifier for Csv content. Defined below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Grok<wbr>Classifier<span class="property-indicator"></span>
        <span class="property-type"><a href="#classifiergrokclassifier">*Classifier<wbr>Grok<wbr>Classifier</a></span>
    </dt>
    <dd>{{% md %}}A classifier that uses grok patterns. Defined below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Json<wbr>Classifier<span class="property-indicator"></span>
        <span class="property-type"><a href="#classifierjsonclassifier">*Classifier<wbr>Json<wbr>Classifier</a></span>
    </dt>
    <dd>{{% md %}}A classifier for JSON content. Defined below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the classifier.
{{% /md %}}</dd>

    <dt class="property-"
            title="">Xml<wbr>Classifier<span class="property-indicator"></span>
        <span class="property-type"><a href="#classifierxmlclassifier">*Classifier<wbr>Xml<wbr>Classifier</a></span>
    </dt>
    <dd>{{% md %}}A classifier for XML content. Defined below.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">csv<wbr>Classifier<span class="property-indicator"></span>
        <span class="property-type"><a href="#classifiercsvclassifier">Classifier<wbr>Csv<wbr>Classifier?</a></span>
    </dt>
    <dd>{{% md %}}A classifier for Csv content. Defined below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">grok<wbr>Classifier<span class="property-indicator"></span>
        <span class="property-type"><a href="#classifiergrokclassifier">Classifier<wbr>Grok<wbr>Classifier?</a></span>
    </dt>
    <dd>{{% md %}}A classifier that uses grok patterns. Defined below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">json<wbr>Classifier<span class="property-indicator"></span>
        <span class="property-type"><a href="#classifierjsonclassifier">Classifier<wbr>Json<wbr>Classifier?</a></span>
    </dt>
    <dd>{{% md %}}A classifier for JSON content. Defined below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">name<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The name of the classifier.
{{% /md %}}</dd>

    <dt class="property-"
            title="">xml<wbr>Classifier<span class="property-indicator"></span>
        <span class="property-type"><a href="#classifierxmlclassifier">Classifier<wbr>Xml<wbr>Classifier?</a></span>
    </dt>
    <dd>{{% md %}}A classifier for XML content. Defined below.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-"
            title="">csv_<wbr>classifier<span class="property-indicator"></span>
        <span class="property-type"><a href="#classifiercsvclassifier">Dict[Classifier<wbr>Csv<wbr>Classifier]</a></span>
    </dt>
    <dd>{{% md %}}A classifier for Csv content. Defined below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">grok_<wbr>classifier<span class="property-indicator"></span>
        <span class="property-type"><a href="#classifiergrokclassifier">Dict[Classifier<wbr>Grok<wbr>Classifier]</a></span>
    </dt>
    <dd>{{% md %}}A classifier that uses grok patterns. Defined below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">json_<wbr>classifier<span class="property-indicator"></span>
        <span class="property-type"><a href="#classifierjsonclassifier">Dict[Classifier<wbr>Json<wbr>Classifier]</a></span>
    </dt>
    <dd>{{% md %}}A classifier for JSON content. Defined below.
{{% /md %}}</dd>

    <dt class="property-"
            title="">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the classifier.
{{% /md %}}</dd>

    <dt class="property-"
            title="">xml_<wbr>classifier<span class="property-indicator"></span>
        <span class="property-type"><a href="#classifierxmlclassifier">Dict[Classifier<wbr>Xml<wbr>Classifier]</a></span>
    </dt>
    <dd>{{% md %}}A classifier for XML content. Defined below.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





## Look up an Existing Classifier Resource

{{< chooser language "javascript,typescript,python,go,csharp  " / >}}

{{% choosable language nodejs %}}
<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">pulumi.Input&lt;pulumi.ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/glue/#ClassifierState">ClassifierState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/aws/glue/#Classifier">Classifier</a></span></code></pre></div>
{{% /choosable %}}

{{% choosable language python %}}
<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>csv_classifier=None<span class="p">, </span>grok_classifier=None<span class="p">, </span>json_classifier=None<span class="p">, </span>name=None<span class="p">, </span>xml_classifier=None<span class="p">, __props__=None);</span></code></pre></div>
{{% /choosable %}}

{{% choosable language go %}}
<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetClassifier<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">pulumi.IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/glue?tab=doc#ClassifierState">ClassifierState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/glue?tab=doc#Classifier">Classifier</a></span>, error)</span></code></pre></div>
{{% /choosable %}}

{{% choosable language csharp %}}
<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Glue.Classifier.html">Classifier</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Pulumi.Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Glue.ClassifierState.html">ClassifierState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>
{{% /choosable %}}

Get an existing Classifier resource's state with the given name, ID, and optional extra properties used to qualify the lookup.

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
            title="Optional">Csv<wbr>Classifier<span class="property-indicator"></span>
        <span class="property-type"><a href="#classifiercsvclassifier">Classifier<wbr>Csv<wbr>Classifier<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}A classifier for Csv content. Defined below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Grok<wbr>Classifier<span class="property-indicator"></span>
        <span class="property-type"><a href="#classifiergrokclassifier">Classifier<wbr>Grok<wbr>Classifier<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}A classifier that uses grok patterns. Defined below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Json<wbr>Classifier<span class="property-indicator"></span>
        <span class="property-type"><a href="#classifierjsonclassifier">Classifier<wbr>Json<wbr>Classifier<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}A classifier for JSON content. Defined below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the classifier.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Xml<wbr>Classifier<span class="property-indicator"></span>
        <span class="property-type"><a href="#classifierxmlclassifier">Classifier<wbr>Xml<wbr>Classifier<wbr>Args?</a></span>
    </dt>
    <dd>{{% md %}}A classifier for XML content. Defined below.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Csv<wbr>Classifier<span class="property-indicator"></span>
        <span class="property-type"><a href="#classifiercsvclassifier">*Classifier<wbr>Csv<wbr>Classifier</a></span>
    </dt>
    <dd>{{% md %}}A classifier for Csv content. Defined below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Grok<wbr>Classifier<span class="property-indicator"></span>
        <span class="property-type"><a href="#classifiergrokclassifier">*Classifier<wbr>Grok<wbr>Classifier</a></span>
    </dt>
    <dd>{{% md %}}A classifier that uses grok patterns. Defined below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Json<wbr>Classifier<span class="property-indicator"></span>
        <span class="property-type"><a href="#classifierjsonclassifier">*Classifier<wbr>Json<wbr>Classifier</a></span>
    </dt>
    <dd>{{% md %}}A classifier for JSON content. Defined below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Name<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The name of the classifier.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Xml<wbr>Classifier<span class="property-indicator"></span>
        <span class="property-type"><a href="#classifierxmlclassifier">*Classifier<wbr>Xml<wbr>Classifier</a></span>
    </dt>
    <dd>{{% md %}}A classifier for XML content. Defined below.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">csv<wbr>Classifier<span class="property-indicator"></span>
        <span class="property-type"><a href="#classifiercsvclassifier">Classifier<wbr>Csv<wbr>Classifier?</a></span>
    </dt>
    <dd>{{% md %}}A classifier for Csv content. Defined below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">grok<wbr>Classifier<span class="property-indicator"></span>
        <span class="property-type"><a href="#classifiergrokclassifier">Classifier<wbr>Grok<wbr>Classifier?</a></span>
    </dt>
    <dd>{{% md %}}A classifier that uses grok patterns. Defined below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">json<wbr>Classifier<span class="property-indicator"></span>
        <span class="property-type"><a href="#classifierjsonclassifier">Classifier<wbr>Json<wbr>Classifier?</a></span>
    </dt>
    <dd>{{% md %}}A classifier for JSON content. Defined below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The name of the classifier.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">xml<wbr>Classifier<span class="property-indicator"></span>
        <span class="property-type"><a href="#classifierxmlclassifier">Classifier<wbr>Xml<wbr>Classifier?</a></span>
    </dt>
    <dd>{{% md %}}A classifier for XML content. Defined below.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">csv_<wbr>classifier<span class="property-indicator"></span>
        <span class="property-type"><a href="#classifiercsvclassifier">Dict[Classifier<wbr>Csv<wbr>Classifier]</a></span>
    </dt>
    <dd>{{% md %}}A classifier for Csv content. Defined below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">grok_<wbr>classifier<span class="property-indicator"></span>
        <span class="property-type"><a href="#classifiergrokclassifier">Dict[Classifier<wbr>Grok<wbr>Classifier]</a></span>
    </dt>
    <dd>{{% md %}}A classifier that uses grok patterns. Defined below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">json_<wbr>classifier<span class="property-indicator"></span>
        <span class="property-type"><a href="#classifierjsonclassifier">Dict[Classifier<wbr>Json<wbr>Classifier]</a></span>
    </dt>
    <dd>{{% md %}}A classifier for JSON content. Defined below.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">name<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The name of the classifier.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">xml_<wbr>classifier<span class="property-indicator"></span>
        <span class="property-type"><a href="#classifierxmlclassifier">Dict[Classifier<wbr>Xml<wbr>Classifier]</a></span>
    </dt>
    <dd>{{% md %}}A classifier for XML content. Defined below.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}







## Supporting Types

#### ClassifierCsvClassifier
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#ClassifierCsvClassifier">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#ClassifierCsvClassifier">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/glue?tab=doc#ClassifierCsvClassifierArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/glue?tab=doc#ClassifierCsvClassifierOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Glue.ClassifierCsvClassifierArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Glue.ClassifierCsvClassifier.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Allow<wbr>Single<wbr>Column<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Enables the processing of files that contain only one column.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Contains<wbr>Header<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Indicates whether the CSV file contains a header. This can be one of &#34;ABSENT&#34;, &#34;PRESENT&#34;, or &#34;UNKNOWN&#34;.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Delimiter<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The delimiter used in the Csv to separate columns.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Disable<wbr>Value<wbr>Trimming<span class="property-indicator"></span>
        <span class="property-type">bool?</span>
    </dt>
    <dd>{{% md %}}Specifies whether to trim column values. 
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Headers<span class="property-indicator"></span>
        <span class="property-type">List<string>?</span>
    </dt>
    <dd>{{% md %}}A list of strings representing column names.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Quote<wbr>Symbol<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A custom symbol to denote what combines content into a single column value. It must be different from the column delimiter.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">Allow<wbr>Single<wbr>Column<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Enables the processing of files that contain only one column.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Contains<wbr>Header<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Indicates whether the CSV file contains a header. This can be one of &#34;ABSENT&#34;, &#34;PRESENT&#34;, or &#34;UNKNOWN&#34;.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Delimiter<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}The delimiter used in the Csv to separate columns.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Disable<wbr>Value<wbr>Trimming<span class="property-indicator"></span>
        <span class="property-type">*bool</span>
    </dt>
    <dd>{{% md %}}Specifies whether to trim column values. 
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Headers<span class="property-indicator"></span>
        <span class="property-type">[]string</span>
    </dt>
    <dd>{{% md %}}A list of strings representing column names.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Quote<wbr>Symbol<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}A custom symbol to denote what combines content into a single column value. It must be different from the column delimiter.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">allow<wbr>Single<wbr>Column<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Enables the processing of files that contain only one column.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">contains<wbr>Header<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Indicates whether the CSV file contains a header. This can be one of &#34;ABSENT&#34;, &#34;PRESENT&#34;, or &#34;UNKNOWN&#34;.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">delimiter<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}The delimiter used in the Csv to separate columns.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">disable<wbr>Value<wbr>Trimming<span class="property-indicator"></span>
        <span class="property-type">boolean?</span>
    </dt>
    <dd>{{% md %}}Specifies whether to trim column values. 
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">headers<span class="property-indicator"></span>
        <span class="property-type">string[]?</span>
    </dt>
    <dd>{{% md %}}A list of strings representing column names.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">quote<wbr>Symbol<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}A custom symbol to denote what combines content into a single column value. It must be different from the column delimiter.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-optional"
            title="Optional">allow<wbr>Single<wbr>Column<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Enables the processing of files that contain only one column.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">contains<wbr>Header<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Indicates whether the CSV file contains a header. This can be one of &#34;ABSENT&#34;, &#34;PRESENT&#34;, or &#34;UNKNOWN&#34;.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">delimiter<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The delimiter used in the Csv to separate columns.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">disable<wbr>Value<wbr>Trimming<span class="property-indicator"></span>
        <span class="property-type">bool</span>
    </dt>
    <dd>{{% md %}}Specifies whether to trim column values. 
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">headers<span class="property-indicator"></span>
        <span class="property-type">List[str]</span>
    </dt>
    <dd>{{% md %}}A list of strings representing column names.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">quote<wbr>Symbol<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A custom symbol to denote what combines content into a single column value. It must be different from the column delimiter.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### ClassifierGrokClassifier
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#ClassifierGrokClassifier">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#ClassifierGrokClassifier">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/glue?tab=doc#ClassifierGrokClassifierArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/glue?tab=doc#ClassifierGrokClassifierOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Glue.ClassifierGrokClassifierArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Glue.ClassifierGrokClassifier.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Classification<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}An identifier of the data format that the classifier matches.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Custom<wbr>Patterns<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Custom grok patterns used by this classifier.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Grok<wbr>Pattern<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The grok pattern used by this classifier.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Classification<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}An identifier of the data format that the classifier matches.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">Custom<wbr>Patterns<span class="property-indicator"></span>
        <span class="property-type">*string</span>
    </dt>
    <dd>{{% md %}}Custom grok patterns used by this classifier.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Grok<wbr>Pattern<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The grok pattern used by this classifier.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">classification<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}An identifier of the data format that the classifier matches.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">custom<wbr>Patterns<span class="property-indicator"></span>
        <span class="property-type">string?</span>
    </dt>
    <dd>{{% md %}}Custom grok patterns used by this classifier.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">grok<wbr>Pattern<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The grok pattern used by this classifier.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">classification<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}An identifier of the data format that the classifier matches.
{{% /md %}}</dd>

    <dt class="property-optional"
            title="Optional">custom<wbr>Patterns<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}Custom grok patterns used by this classifier.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">grok<wbr>Pattern<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The grok pattern used by this classifier.
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### ClassifierJsonClassifier
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#ClassifierJsonClassifier">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#ClassifierJsonClassifier">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/glue?tab=doc#ClassifierJsonClassifierArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/glue?tab=doc#ClassifierJsonClassifierOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Glue.ClassifierJsonClassifierArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Glue.ClassifierJsonClassifier.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Json<wbr>Path<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}A `JsonPath` string defining the JSON data for the classifier to classify. AWS Glue supports a subset of `JsonPath`, as described in [Writing JsonPath Custom Classifiers](https://docs.aws.amazon.com/glue/latest/dg/custom-classifier.html#custom-classifier-json).
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Json<wbr>Path<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}A `JsonPath` string defining the JSON data for the classifier to classify. AWS Glue supports a subset of `JsonPath`, as described in [Writing JsonPath Custom Classifiers](https://docs.aws.amazon.com/glue/latest/dg/custom-classifier.html#custom-classifier-json).
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">json<wbr>Path<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}A `JsonPath` string defining the JSON data for the classifier to classify. AWS Glue supports a subset of `JsonPath`, as described in [Writing JsonPath Custom Classifiers](https://docs.aws.amazon.com/glue/latest/dg/custom-classifier.html#custom-classifier-json).
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">json<wbr>Path<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}A `JsonPath` string defining the JSON data for the classifier to classify. AWS Glue supports a subset of `JsonPath`, as described in [Writing JsonPath Custom Classifiers](https://docs.aws.amazon.com/glue/latest/dg/custom-classifier.html#custom-classifier-json).
{{% /md %}}</dd>

</dl>
{{% /choosable %}}





#### ClassifierXmlClassifier
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/input/#ClassifierXmlClassifier">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/aws/types/output/#ClassifierXmlClassifier">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/glue?tab=doc#ClassifierXmlClassifierArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-aws/sdk/go/aws/glue?tab=doc#ClassifierXmlClassifierOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Glue.ClassifierXmlClassifierArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Aws/Pulumi.Aws.Glue.ClassifierXmlClassifier.html">output</a> API doc for this type.
{{% /lang %}}




{{% choosable language csharp %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Classification<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}An identifier of the data format that the classifier matches.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Row<wbr>Tag<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The XML tag designating the element that contains each record in an XML document being parsed. Note that this cannot identify a self-closing element (closed by `/&gt;`). An empty row element that contains only attributes can be parsed as long as it ends with a closing tag (for example, `&lt;row item_a=&#34;A&#34; item_b=&#34;B&#34;&gt;&lt;/row&gt;` is okay, but `&lt;row item_a=&#34;A&#34; item_b=&#34;B&#34; /&gt;` is not).
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language go %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">Classification<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}An identifier of the data format that the classifier matches.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">Row<wbr>Tag<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The XML tag designating the element that contains each record in an XML document being parsed. Note that this cannot identify a self-closing element (closed by `/&gt;`). An empty row element that contains only attributes can be parsed as long as it ends with a closing tag (for example, `&lt;row item_a=&#34;A&#34; item_b=&#34;B&#34;&gt;&lt;/row&gt;` is okay, but `&lt;row item_a=&#34;A&#34; item_b=&#34;B&#34; /&gt;` is not).
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language nodejs %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">classification<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}An identifier of the data format that the classifier matches.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">row<wbr>Tag<span class="property-indicator"></span>
        <span class="property-type">string</span>
    </dt>
    <dd>{{% md %}}The XML tag designating the element that contains each record in an XML document being parsed. Note that this cannot identify a self-closing element (closed by `/&gt;`). An empty row element that contains only attributes can be parsed as long as it ends with a closing tag (for example, `&lt;row item_a=&#34;A&#34; item_b=&#34;B&#34;&gt;&lt;/row&gt;` is okay, but `&lt;row item_a=&#34;A&#34; item_b=&#34;B&#34; /&gt;` is not).
{{% /md %}}</dd>

</dl>
{{% /choosable %}}


{{% choosable language python %}}
<dl class="resources-properties">

    <dt class="property-required"
            title="Required">classification<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}An identifier of the data format that the classifier matches.
{{% /md %}}</dd>

    <dt class="property-required"
            title="Required">row<wbr>Tag<span class="property-indicator"></span>
        <span class="property-type">str</span>
    </dt>
    <dd>{{% md %}}The XML tag designating the element that contains each record in an XML document being parsed. Note that this cannot identify a self-closing element (closed by `/&gt;`). An empty row element that contains only attributes can be parsed as long as it ends with a closing tag (for example, `&lt;row item_a=&#34;A&#34; item_b=&#34;B&#34;&gt;&lt;/row&gt;` is okay, but `&lt;row item_a=&#34;A&#34; item_b=&#34;B&#34; /&gt;` is not).
{{% /md %}}</dd>

</dl>
{{% /choosable %}}








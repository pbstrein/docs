
---
title: "Metric"
block_external_search_index: true
---
<style>
table td p { margin-top: 0; margin-bottom: 0; }
</style>




## Create a Metric Resource

{{< langchoose csharp nojavascript >}}

<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">new </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/logging/#Metric">Metric</a></span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">args</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/logging/#MetricArgs">MetricArgs</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">def </span><span class="nf">Metric</span><span class="p">(resource_name, opts=None, </span>bucket_options=None<span class="p">, </span>description=None<span class="p">, </span>filter=None<span class="p">, </span>label_extractors=None<span class="p">, </span>metric_descriptor=None<span class="p">, </span>name=None<span class="p">, </span>project=None<span class="p">, </span>value_extractor=None<span class="p">, __props__=None);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>NewMetric<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">args</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/logging?tab=doc#MetricArgs">MetricArgs</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/logging?tab=doc#Metric">Metric</a></span>, error)</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Logging.Metric.html">Metric</a></span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Logging.MetricArgs.html">MetricArgs</a></span> <span class="nx">args<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>

Creates a Metric resource with the given unique name, arguments, and options.

{{% lang nodejs %}}

<ul class="pl-10">
    <li><strong>name</strong> &ndash; (Required) The unique name of the resulting resource.</li>
    <li><strong>args</strong> &ndash;  (Optional)  The arguments to use to populate this resource's properties.</li>
    <li><strong>opts</strong> &ndash; (Optional) A bag of options that control this resource's behavior.</li>
</ul>

{{% /lang %}}

{{% lang go %}}

<ul class="pl-10">
    <li><strong>name</strong> &ndash; (Required) The unique name of the resulting resource.</li>
    <li><strong>args</strong> &ndash;  (Optional)  The arguments to use to populate this resource's properties.</li>
    <li><strong>opts</strong> &ndash; (Optional) A bag of options that control this resource's behavior.</li>
</ul>

{{% /lang %}}

{{% lang csharp %}}

<ul class="pl-10">
    <li><strong>name</strong> &ndash; (Required) The unique name of the resulting resource.</li>
    <li><strong>args</strong> &ndash;  (Optional)  The arguments to use to populate this resource's properties.</li>
    <li><strong>opts</strong> &ndash; (Optional) A bag of options that control this resource's behavior.</li>
</ul>

{{% /lang %}}

The following arguments are supported:


{{< langchoose csharp nojavascript >}}


{{% lang csharp %}}


<table class="ml-6">
    <thead>
        <tr>
            <th>Argument</th>
            <th>Type</th>
            <th>Description</th>
        </tr>
    </thead>
    <tbody>
    
        <tr>
            <td class="align-top">Bucket<wbr>Options</td>
            <td class="align-top">
                
                <code><a href="#metricbucketoptions">Metric<wbr>Bucket<wbr>Options<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The bucketOptions are required when the logs-based metric is using a DISTRIBUTION value type and it describes the bucket
boundaries used to create a histogram of the extracted values.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Description</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A description of this metric, which is used in documentation. The maximum length of the description is 8000 characters.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Filter</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
An advanced logs filter (https://cloud.google.com/logging/docs/view/advanced-filters) which is used to match log
entries.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Label<wbr>Extractors</td>
            <td class="align-top">
                
                <code>Dictionary<string, string>?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A map from a label key string to an extractor expression which is used to extract data from a log entry field and assign
as the label value. Each label key specified in the LabelDescriptor must have an associated extractor expression in this
map. The syntax of the extractor expression is the same as for the valueExtractor field.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Metric<wbr>Descriptor</td>
            <td class="align-top">
                
                <code><a href="#metricmetricdescriptor">Metric<wbr>Metric<wbr>Descriptor<wbr>Args</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The metric descriptor associated with the logs-based metric.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Name</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The client-assigned metric identifier. Examples - &#34;error_count&#34;, &#34;nginx/requests&#34;. Metric identifiers are limited to 100
characters and can include only the following characters A-Z, a-z, 0-9, and the special characters _-.,&#43;!*&#39;,()%/. The
forward-slash character (/) denotes a hierarchy of name pieces, and it cannot be the first character of the name.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Project</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Value<wbr>Extractor</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A valueExtractor is required when using a distribution logs-based metric to extract the values to record from a log
entry. Two functions are supported for value extraction - EXTRACT(field) or REGEXP_EXTRACT(field, regex). The argument
are 1. field - The name of the log entry field from which the value is to be extracted. 2. regex - A regular expression
using the Google RE2 syntax (https://github.com/google/re2/wiki/Syntax) with a single capture group to extract data from
the specified log entry field. The value of the field is converted to a string before applying the regex. It is an error
to specify a regex that does not include exactly one capture group.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}


{{% lang go %}}


<table class="ml-6">
    <thead>
        <tr>
            <th>Argument</th>
            <th>Type</th>
            <th>Description</th>
        </tr>
    </thead>
    <tbody>
    
        <tr>
            <td class="align-top">Bucket<wbr>Options</td>
            <td class="align-top">
                
                <code><a href="#metricbucketoptions">*Metric<wbr>Bucket<wbr>Options</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The bucketOptions are required when the logs-based metric is using a DISTRIBUTION value type and it describes the bucket
boundaries used to create a histogram of the extracted values.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Description</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A description of this metric, which is used in documentation. The maximum length of the description is 8000 characters.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Filter</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
An advanced logs filter (https://cloud.google.com/logging/docs/view/advanced-filters) which is used to match log
entries.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Label<wbr>Extractors</td>
            <td class="align-top">
                
                <code>map[string]string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A map from a label key string to an extractor expression which is used to extract data from a log entry field and assign
as the label value. Each label key specified in the LabelDescriptor must have an associated extractor expression in this
map. The syntax of the extractor expression is the same as for the valueExtractor field.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Metric<wbr>Descriptor</td>
            <td class="align-top">
                
                <code><a href="#metricmetricdescriptor">Metric<wbr>Metric<wbr>Descriptor</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The metric descriptor associated with the logs-based metric.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Name</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The client-assigned metric identifier. Examples - &#34;error_count&#34;, &#34;nginx/requests&#34;. Metric identifiers are limited to 100
characters and can include only the following characters A-Z, a-z, 0-9, and the special characters _-.,&#43;!*&#39;,()%/. The
forward-slash character (/) denotes a hierarchy of name pieces, and it cannot be the first character of the name.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Project</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Value<wbr>Extractor</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A valueExtractor is required when using a distribution logs-based metric to extract the values to record from a log
entry. Two functions are supported for value extraction - EXTRACT(field) or REGEXP_EXTRACT(field, regex). The argument
are 1. field - The name of the log entry field from which the value is to be extracted. 2. regex - A regular expression
using the Google RE2 syntax (https://github.com/google/re2/wiki/Syntax) with a single capture group to extract data from
the specified log entry field. The value of the field is converted to a string before applying the regex. It is an error
to specify a regex that does not include exactly one capture group.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}


{{% lang nodejs %}}


<table class="ml-6">
    <thead>
        <tr>
            <th>Argument</th>
            <th>Type</th>
            <th>Description</th>
        </tr>
    </thead>
    <tbody>
    
        <tr>
            <td class="align-top">bucket<wbr>Options</td>
            <td class="align-top">
                
                <code><a href="#metricbucketoptions">Metric<wbr>Bucket<wbr>Options?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The bucketOptions are required when the logs-based metric is using a DISTRIBUTION value type and it describes the bucket
boundaries used to create a histogram of the extracted values.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">description</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A description of this metric, which is used in documentation. The maximum length of the description is 8000 characters.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">filter</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
An advanced logs filter (https://cloud.google.com/logging/docs/view/advanced-filters) which is used to match log
entries.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">label<wbr>Extractors</td>
            <td class="align-top">
                
                <code>{[key: string]: string}?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A map from a label key string to an extractor expression which is used to extract data from a log entry field and assign
as the label value. Each label key specified in the LabelDescriptor must have an associated extractor expression in this
map. The syntax of the extractor expression is the same as for the valueExtractor field.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">metric<wbr>Descriptor</td>
            <td class="align-top">
                
                <code><a href="#metricmetricdescriptor">Metric<wbr>Metric<wbr>Descriptor</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The metric descriptor associated with the logs-based metric.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">name</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The client-assigned metric identifier. Examples - &#34;error_count&#34;, &#34;nginx/requests&#34;. Metric identifiers are limited to 100
characters and can include only the following characters A-Z, a-z, 0-9, and the special characters _-.,&#43;!*&#39;,()%/. The
forward-slash character (/) denotes a hierarchy of name pieces, and it cannot be the first character of the name.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">project</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">value<wbr>Extractor</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A valueExtractor is required when using a distribution logs-based metric to extract the values to record from a log
entry. Two functions are supported for value extraction - EXTRACT(field) or REGEXP_EXTRACT(field, regex). The argument
are 1. field - The name of the log entry field from which the value is to be extracted. 2. regex - A regular expression
using the Google RE2 syntax (https://github.com/google/re2/wiki/Syntax) with a single capture group to extract data from
the specified log entry field. The value of the field is converted to a string before applying the regex. It is an error
to specify a regex that does not include exactly one capture group.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}


{{% lang python %}}


<table class="ml-6">
    <thead>
        <tr>
            <th>Argument</th>
            <th>Type</th>
            <th>Description</th>
        </tr>
    </thead>
    <tbody>
    
        <tr>
            <td class="align-top">bucket_<wbr>options</td>
            <td class="align-top">
                
                <code><a href="#metricbucketoptions">Dict[Metric<wbr>Bucket<wbr>Options]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The bucketOptions are required when the logs-based metric is using a DISTRIBUTION value type and it describes the bucket
boundaries used to create a histogram of the extracted values.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">description</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A description of this metric, which is used in documentation. The maximum length of the description is 8000 characters.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">filter</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
An advanced logs filter (https://cloud.google.com/logging/docs/view/advanced-filters) which is used to match log
entries.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">label_<wbr>extractors</td>
            <td class="align-top">
                
                <code>Dict[str, str]</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A map from a label key string to an extractor expression which is used to extract data from a log entry field and assign
as the label value. Each label key specified in the LabelDescriptor must have an associated extractor expression in this
map. The syntax of the extractor expression is the same as for the valueExtractor field.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">metric_<wbr>descriptor</td>
            <td class="align-top">
                
                <code><a href="#metricmetricdescriptor">Dict[Metric<wbr>Metric<wbr>Descriptor]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
The metric descriptor associated with the logs-based metric.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">name</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The client-assigned metric identifier. Examples - &#34;error_count&#34;, &#34;nginx/requests&#34;. Metric identifiers are limited to 100
characters and can include only the following characters A-Z, a-z, 0-9, and the special characters _-.,&#43;!*&#39;,()%/. The
forward-slash character (/) denotes a hierarchy of name pieces, and it cannot be the first character of the name.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">project</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">value_<wbr>extractor</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A valueExtractor is required when using a distribution logs-based metric to extract the values to record from a log
entry. Two functions are supported for value extraction - EXTRACT(field) or REGEXP_EXTRACT(field, regex). The argument
are 1. field - The name of the log entry field from which the value is to be extracted. 2. regex - A regular expression
using the Google RE2 syntax (https://github.com/google/re2/wiki/Syntax) with a single capture group to extract data from
the specified log entry field. The value of the field is converted to a string before applying the regex. It is an error
to specify a regex that does not include exactly one capture group.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}







## Metric Output Properties

The following output properties are available:



{{< langchoose csharp nojavascript >}}


{{% lang csharp %}}


<table class="ml-6">
    <thead>
        <tr>
            <th>Argument</th>
            <th>Type</th>
            <th>Description</th>
        </tr>
    </thead>
    <tbody>
    
        <tr>
            <td class="align-top">Bucket<wbr>Options</td>
            <td class="align-top">
                
                <code><a href="#metricbucketoptions">Metric<wbr>Bucket<wbr>Options?</a></code>
            </td>
            <td class="align-top">{{% md %}} The bucketOptions are required when the logs-based metric is using a DISTRIBUTION value type and it describes the bucket
boundaries used to create a histogram of the extracted values.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Description</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} A description of this metric, which is used in documentation. The maximum length of the description is 8000 characters.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Filter</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} An advanced logs filter (https://cloud.google.com/logging/docs/view/advanced-filters) which is used to match log
entries.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Label<wbr>Extractors</td>
            <td class="align-top">
                
                <code>Dictionary<string, string>?</code>
            </td>
            <td class="align-top">{{% md %}} A map from a label key string to an extractor expression which is used to extract data from a log entry field and assign
as the label value. Each label key specified in the LabelDescriptor must have an associated extractor expression in this
map. The syntax of the extractor expression is the same as for the valueExtractor field.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Metric<wbr>Descriptor</td>
            <td class="align-top">
                
                <code><a href="#metricmetricdescriptor">Metric<wbr>Metric<wbr>Descriptor</a></code>
            </td>
            <td class="align-top">{{% md %}} The metric descriptor associated with the logs-based metric.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The client-assigned metric identifier. Examples - &#34;error_count&#34;, &#34;nginx/requests&#34;. Metric identifiers are limited to 100
characters and can include only the following characters A-Z, a-z, 0-9, and the special characters _-.,&#43;!*&#39;,()%/. The
forward-slash character (/) denotes a hierarchy of name pieces, and it cannot be the first character of the name.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Project</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}}  {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Value<wbr>Extractor</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} A valueExtractor is required when using a distribution logs-based metric to extract the values to record from a log
entry. Two functions are supported for value extraction - EXTRACT(field) or REGEXP_EXTRACT(field, regex). The argument
are 1. field - The name of the log entry field from which the value is to be extracted. 2. regex - A regular expression
using the Google RE2 syntax (https://github.com/google/re2/wiki/Syntax) with a single capture group to extract data from
the specified log entry field. The value of the field is converted to a string before applying the regex. It is an error
to specify a regex that does not include exactly one capture group.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}


{{% lang go %}}


<table class="ml-6">
    <thead>
        <tr>
            <th>Argument</th>
            <th>Type</th>
            <th>Description</th>
        </tr>
    </thead>
    <tbody>
    
        <tr>
            <td class="align-top">Bucket<wbr>Options</td>
            <td class="align-top">
                
                <code><a href="#metricbucketoptions">*Metric<wbr>Bucket<wbr>Options</a></code>
            </td>
            <td class="align-top">{{% md %}} The bucketOptions are required when the logs-based metric is using a DISTRIBUTION value type and it describes the bucket
boundaries used to create a histogram of the extracted values.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Description</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} A description of this metric, which is used in documentation. The maximum length of the description is 8000 characters.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Filter</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} An advanced logs filter (https://cloud.google.com/logging/docs/view/advanced-filters) which is used to match log
entries.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Label<wbr>Extractors</td>
            <td class="align-top">
                
                <code>map[string]string</code>
            </td>
            <td class="align-top">{{% md %}} A map from a label key string to an extractor expression which is used to extract data from a log entry field and assign
as the label value. Each label key specified in the LabelDescriptor must have an associated extractor expression in this
map. The syntax of the extractor expression is the same as for the valueExtractor field.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Metric<wbr>Descriptor</td>
            <td class="align-top">
                
                <code><a href="#metricmetricdescriptor">Metric<wbr>Metric<wbr>Descriptor</a></code>
            </td>
            <td class="align-top">{{% md %}} The metric descriptor associated with the logs-based metric.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The client-assigned metric identifier. Examples - &#34;error_count&#34;, &#34;nginx/requests&#34;. Metric identifiers are limited to 100
characters and can include only the following characters A-Z, a-z, 0-9, and the special characters _-.,&#43;!*&#39;,()%/. The
forward-slash character (/) denotes a hierarchy of name pieces, and it cannot be the first character of the name.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Project</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}}  {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Value<wbr>Extractor</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} A valueExtractor is required when using a distribution logs-based metric to extract the values to record from a log
entry. Two functions are supported for value extraction - EXTRACT(field) or REGEXP_EXTRACT(field, regex). The argument
are 1. field - The name of the log entry field from which the value is to be extracted. 2. regex - A regular expression
using the Google RE2 syntax (https://github.com/google/re2/wiki/Syntax) with a single capture group to extract data from
the specified log entry field. The value of the field is converted to a string before applying the regex. It is an error
to specify a regex that does not include exactly one capture group.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}


{{% lang nodejs %}}


<table class="ml-6">
    <thead>
        <tr>
            <th>Argument</th>
            <th>Type</th>
            <th>Description</th>
        </tr>
    </thead>
    <tbody>
    
        <tr>
            <td class="align-top">bucket<wbr>Options</td>
            <td class="align-top">
                
                <code><a href="#metricbucketoptions">Metric<wbr>Bucket<wbr>Options?</a></code>
            </td>
            <td class="align-top">{{% md %}} The bucketOptions are required when the logs-based metric is using a DISTRIBUTION value type and it describes the bucket
boundaries used to create a histogram of the extracted values.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">description</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} A description of this metric, which is used in documentation. The maximum length of the description is 8000 characters.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">filter</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} An advanced logs filter (https://cloud.google.com/logging/docs/view/advanced-filters) which is used to match log
entries.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">label<wbr>Extractors</td>
            <td class="align-top">
                
                <code>{[key: string]: string}?</code>
            </td>
            <td class="align-top">{{% md %}} A map from a label key string to an extractor expression which is used to extract data from a log entry field and assign
as the label value. Each label key specified in the LabelDescriptor must have an associated extractor expression in this
map. The syntax of the extractor expression is the same as for the valueExtractor field.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">metric<wbr>Descriptor</td>
            <td class="align-top">
                
                <code><a href="#metricmetricdescriptor">Metric<wbr>Metric<wbr>Descriptor</a></code>
            </td>
            <td class="align-top">{{% md %}} The metric descriptor associated with the logs-based metric.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">name</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} The client-assigned metric identifier. Examples - &#34;error_count&#34;, &#34;nginx/requests&#34;. Metric identifiers are limited to 100
characters and can include only the following characters A-Z, a-z, 0-9, and the special characters _-.,&#43;!*&#39;,()%/. The
forward-slash character (/) denotes a hierarchy of name pieces, and it cannot be the first character of the name.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">project</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}}  {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">value<wbr>Extractor</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} A valueExtractor is required when using a distribution logs-based metric to extract the values to record from a log
entry. Two functions are supported for value extraction - EXTRACT(field) or REGEXP_EXTRACT(field, regex). The argument
are 1. field - The name of the log entry field from which the value is to be extracted. 2. regex - A regular expression
using the Google RE2 syntax (https://github.com/google/re2/wiki/Syntax) with a single capture group to extract data from
the specified log entry field. The value of the field is converted to a string before applying the regex. It is an error
to specify a regex that does not include exactly one capture group.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}


{{% lang python %}}


<table class="ml-6">
    <thead>
        <tr>
            <th>Argument</th>
            <th>Type</th>
            <th>Description</th>
        </tr>
    </thead>
    <tbody>
    
        <tr>
            <td class="align-top">bucket_<wbr>options</td>
            <td class="align-top">
                
                <code><a href="#metricbucketoptions">Dict[Metric<wbr>Bucket<wbr>Options]</a></code>
            </td>
            <td class="align-top">{{% md %}} The bucketOptions are required when the logs-based metric is using a DISTRIBUTION value type and it describes the bucket
boundaries used to create a histogram of the extracted values.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">description</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} A description of this metric, which is used in documentation. The maximum length of the description is 8000 characters.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">filter</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} An advanced logs filter (https://cloud.google.com/logging/docs/view/advanced-filters) which is used to match log
entries.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">label_<wbr>extractors</td>
            <td class="align-top">
                
                <code>Dict[str, str]</code>
            </td>
            <td class="align-top">{{% md %}} A map from a label key string to an extractor expression which is used to extract data from a log entry field and assign
as the label value. Each label key specified in the LabelDescriptor must have an associated extractor expression in this
map. The syntax of the extractor expression is the same as for the valueExtractor field.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">metric_<wbr>descriptor</td>
            <td class="align-top">
                
                <code><a href="#metricmetricdescriptor">Dict[Metric<wbr>Metric<wbr>Descriptor]</a></code>
            </td>
            <td class="align-top">{{% md %}} The metric descriptor associated with the logs-based metric.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">name</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} The client-assigned metric identifier. Examples - &#34;error_count&#34;, &#34;nginx/requests&#34;. Metric identifiers are limited to 100
characters and can include only the following characters A-Z, a-z, 0-9, and the special characters _-.,&#43;!*&#39;,()%/. The
forward-slash character (/) denotes a hierarchy of name pieces, and it cannot be the first character of the name.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">project</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}}  {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">value_<wbr>extractor</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} A valueExtractor is required when using a distribution logs-based metric to extract the values to record from a log
entry. Two functions are supported for value extraction - EXTRACT(field) or REGEXP_EXTRACT(field, regex). The argument
are 1. field - The name of the log entry field from which the value is to be extracted. 2. regex - A regular expression
using the Google RE2 syntax (https://github.com/google/re2/wiki/Syntax) with a single capture group to extract data from
the specified log entry field. The value of the field is converted to a string before applying the regex. It is an error
to specify a regex that does not include exactly one capture group.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}








## Look up an Existing Metric Resource

{{< langchoose csharp nojavascript >}}

<div class="highlight"><pre class="chroma"><code class="language-typescript" data-lang="typescript"><span class="k">public static </span><span class="nf">get</span><span class="p">(</span><span class="nx">name</span>: <span class="nx"><a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/string">string</a></span><span class="p">, </span><span class="nx">id</span>: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#ID">pulumi.Input&lt;pulumi.ID&gt;</a></span><span class="p">, </span><span class="nx">state</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/logging/#MetricState">MetricState</a></span><span class="p">, </span><span class="nx">opts</span>?: <span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/pulumi/#CustomResourceOptions">pulumi.CustomResourceOptions</a></span><span class="p">): </span><span class="nx"><a href="/docs/reference/pkg/nodejs/pulumi/gcp/logging/#Metric">Metric</a></span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-python" data-lang="python"><span class="k">static </span><span class="nf">get</span><span class="p">(resource_name, id, opts=None, </span>bucket_options=None<span class="p">, </span>description=None<span class="p">, </span>filter=None<span class="p">, </span>label_extractors=None<span class="p">, </span>metric_descriptor=None<span class="p">, </span>name=None<span class="p">, </span>project=None<span class="p">, </span>value_extractor=None<span class="p">, __props__=None);</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-go" data-lang="go"><span class="k">func </span>GetMetric<span class="p">(</span><span class="nx">ctx</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#Context">pulumi.Context</a></span><span class="p">, </span><span class="nx">name</span> <span class="nx"><a href="https://golang.org/pkg/builtin/#string">string</a></span><span class="p">, </span><span class="nx">id</span> <span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#IDInput">pulumi.IDInput</a></span><span class="p">, </span><span class="nx">state</span> *<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/logging?tab=doc#MetricState">MetricState</a></span><span class="p">, </span><span class="nx">opts</span> ...<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi/sdk/go/pulumi?tab=doc#ResourceOption">pulumi.ResourceOption</a></span><span class="p">) (*<span class="nx"><a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/logging?tab=doc#Metric">Metric</a></span>, error)</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-csharp" data-lang="csharp"><span class="k">public static </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Logging.Metric.html">Metric</a></span><span class="nf"> Get</span><span class="p">(</span><span class="nx"><a href="https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types">string</a></span> <span class="nx">name<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.Input.html">Pulumi.Input&lt;string&gt;</a></span> <span class="nx">id<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Logging.MetricState.html">MetricState</a></span>? <span class="nx">state<span class="p">, </span><span class="nx"><a href="/docs/reference/pkg/dotnet/Pulumi/Pulumi.CustomResourceOptions.html">Pulumi.CustomResourceOptions</a></span>? <span class="nx">opts = null<span class="p">)</span></code></pre></div>

Get an existing Metric resource's state with the given name, ID, and optional extra properties used to qualify the lookup.

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


{{< langchoose csharp nojavascript >}}


{{% lang csharp %}}


<table class="ml-6">
    <thead>
        <tr>
            <th>Argument</th>
            <th>Type</th>
            <th>Description</th>
        </tr>
    </thead>
    <tbody>
    
        <tr>
            <td class="align-top">Bucket<wbr>Options</td>
            <td class="align-top">
                
                <code><a href="#metricbucketoptions">Metric<wbr>Bucket<wbr>Options<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The bucketOptions are required when the logs-based metric is using a DISTRIBUTION value type and it describes the bucket
boundaries used to create a histogram of the extracted values.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Description</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A description of this metric, which is used in documentation. The maximum length of the description is 8000 characters.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Filter</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
An advanced logs filter (https://cloud.google.com/logging/docs/view/advanced-filters) which is used to match log
entries.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Label<wbr>Extractors</td>
            <td class="align-top">
                
                <code>Dictionary<string, string>?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A map from a label key string to an extractor expression which is used to extract data from a log entry field and assign
as the label value. Each label key specified in the LabelDescriptor must have an associated extractor expression in this
map. The syntax of the extractor expression is the same as for the valueExtractor field.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Metric<wbr>Descriptor</td>
            <td class="align-top">
                
                <code><a href="#metricmetricdescriptor">Metric<wbr>Metric<wbr>Descriptor<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The metric descriptor associated with the logs-based metric.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Name</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The client-assigned metric identifier. Examples - &#34;error_count&#34;, &#34;nginx/requests&#34;. Metric identifiers are limited to 100
characters and can include only the following characters A-Z, a-z, 0-9, and the special characters _-.,&#43;!*&#39;,()%/. The
forward-slash character (/) denotes a hierarchy of name pieces, and it cannot be the first character of the name.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Project</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Value<wbr>Extractor</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A valueExtractor is required when using a distribution logs-based metric to extract the values to record from a log
entry. Two functions are supported for value extraction - EXTRACT(field) or REGEXP_EXTRACT(field, regex). The argument
are 1. field - The name of the log entry field from which the value is to be extracted. 2. regex - A regular expression
using the Google RE2 syntax (https://github.com/google/re2/wiki/Syntax) with a single capture group to extract data from
the specified log entry field. The value of the field is converted to a string before applying the regex. It is an error
to specify a regex that does not include exactly one capture group.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}


{{% lang go %}}


<table class="ml-6">
    <thead>
        <tr>
            <th>Argument</th>
            <th>Type</th>
            <th>Description</th>
        </tr>
    </thead>
    <tbody>
    
        <tr>
            <td class="align-top">Bucket<wbr>Options</td>
            <td class="align-top">
                
                <code><a href="#metricbucketoptions">*Metric<wbr>Bucket<wbr>Options</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The bucketOptions are required when the logs-based metric is using a DISTRIBUTION value type and it describes the bucket
boundaries used to create a histogram of the extracted values.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Description</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A description of this metric, which is used in documentation. The maximum length of the description is 8000 characters.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Filter</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
An advanced logs filter (https://cloud.google.com/logging/docs/view/advanced-filters) which is used to match log
entries.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Label<wbr>Extractors</td>
            <td class="align-top">
                
                <code>map[string]string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A map from a label key string to an extractor expression which is used to extract data from a log entry field and assign
as the label value. Each label key specified in the LabelDescriptor must have an associated extractor expression in this
map. The syntax of the extractor expression is the same as for the valueExtractor field.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Metric<wbr>Descriptor</td>
            <td class="align-top">
                
                <code><a href="#metricmetricdescriptor">*Metric<wbr>Metric<wbr>Descriptor</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The metric descriptor associated with the logs-based metric.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Name</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The client-assigned metric identifier. Examples - &#34;error_count&#34;, &#34;nginx/requests&#34;. Metric identifiers are limited to 100
characters and can include only the following characters A-Z, a-z, 0-9, and the special characters _-.,&#43;!*&#39;,()%/. The
forward-slash character (/) denotes a hierarchy of name pieces, and it cannot be the first character of the name.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Project</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Value<wbr>Extractor</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A valueExtractor is required when using a distribution logs-based metric to extract the values to record from a log
entry. Two functions are supported for value extraction - EXTRACT(field) or REGEXP_EXTRACT(field, regex). The argument
are 1. field - The name of the log entry field from which the value is to be extracted. 2. regex - A regular expression
using the Google RE2 syntax (https://github.com/google/re2/wiki/Syntax) with a single capture group to extract data from
the specified log entry field. The value of the field is converted to a string before applying the regex. It is an error
to specify a regex that does not include exactly one capture group.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}


{{% lang nodejs %}}


<table class="ml-6">
    <thead>
        <tr>
            <th>Argument</th>
            <th>Type</th>
            <th>Description</th>
        </tr>
    </thead>
    <tbody>
    
        <tr>
            <td class="align-top">bucket<wbr>Options</td>
            <td class="align-top">
                
                <code><a href="#metricbucketoptions">Metric<wbr>Bucket<wbr>Options?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The bucketOptions are required when the logs-based metric is using a DISTRIBUTION value type and it describes the bucket
boundaries used to create a histogram of the extracted values.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">description</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A description of this metric, which is used in documentation. The maximum length of the description is 8000 characters.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">filter</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
An advanced logs filter (https://cloud.google.com/logging/docs/view/advanced-filters) which is used to match log
entries.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">label<wbr>Extractors</td>
            <td class="align-top">
                
                <code>{[key: string]: string}?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A map from a label key string to an extractor expression which is used to extract data from a log entry field and assign
as the label value. Each label key specified in the LabelDescriptor must have an associated extractor expression in this
map. The syntax of the extractor expression is the same as for the valueExtractor field.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">metric<wbr>Descriptor</td>
            <td class="align-top">
                
                <code><a href="#metricmetricdescriptor">Metric<wbr>Metric<wbr>Descriptor?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The metric descriptor associated with the logs-based metric.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">name</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The client-assigned metric identifier. Examples - &#34;error_count&#34;, &#34;nginx/requests&#34;. Metric identifiers are limited to 100
characters and can include only the following characters A-Z, a-z, 0-9, and the special characters _-.,&#43;!*&#39;,()%/. The
forward-slash character (/) denotes a hierarchy of name pieces, and it cannot be the first character of the name.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">project</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">value<wbr>Extractor</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A valueExtractor is required when using a distribution logs-based metric to extract the values to record from a log
entry. Two functions are supported for value extraction - EXTRACT(field) or REGEXP_EXTRACT(field, regex). The argument
are 1. field - The name of the log entry field from which the value is to be extracted. 2. regex - A regular expression
using the Google RE2 syntax (https://github.com/google/re2/wiki/Syntax) with a single capture group to extract data from
the specified log entry field. The value of the field is converted to a string before applying the regex. It is an error
to specify a regex that does not include exactly one capture group.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}


{{% lang python %}}


<table class="ml-6">
    <thead>
        <tr>
            <th>Argument</th>
            <th>Type</th>
            <th>Description</th>
        </tr>
    </thead>
    <tbody>
    
        <tr>
            <td class="align-top">bucket_<wbr>options</td>
            <td class="align-top">
                
                <code><a href="#metricbucketoptions">Dict[Metric<wbr>Bucket<wbr>Options]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The bucketOptions are required when the logs-based metric is using a DISTRIBUTION value type and it describes the bucket
boundaries used to create a histogram of the extracted values.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">description</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A description of this metric, which is used in documentation. The maximum length of the description is 8000 characters.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">filter</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
An advanced logs filter (https://cloud.google.com/logging/docs/view/advanced-filters) which is used to match log
entries.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">label_<wbr>extractors</td>
            <td class="align-top">
                
                <code>Dict[str, str]</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A map from a label key string to an extractor expression which is used to extract data from a log entry field and assign
as the label value. Each label key specified in the LabelDescriptor must have an associated extractor expression in this
map. The syntax of the extractor expression is the same as for the valueExtractor field.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">metric_<wbr>descriptor</td>
            <td class="align-top">
                
                <code><a href="#metricmetricdescriptor">Dict[Metric<wbr>Metric<wbr>Descriptor]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The metric descriptor associated with the logs-based metric.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">name</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
The client-assigned metric identifier. Examples - &#34;error_count&#34;, &#34;nginx/requests&#34;. Metric identifiers are limited to 100
characters and can include only the following characters A-Z, a-z, 0-9, and the special characters _-.,&#43;!*&#39;,()%/. The
forward-slash character (/) denotes a hierarchy of name pieces, and it cannot be the first character of the name.
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">project</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">value_<wbr>extractor</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
A valueExtractor is required when using a distribution logs-based metric to extract the values to record from a log
entry. Two functions are supported for value extraction - EXTRACT(field) or REGEXP_EXTRACT(field, regex). The argument
are 1. field - The name of the log entry field from which the value is to be extracted. 2. regex - A regular expression
using the Google RE2 syntax (https://github.com/google/re2/wiki/Syntax) with a single capture group to extract data from
the specified log entry field. The value of the field is converted to a string before applying the regex. It is an error
to specify a regex that does not include exactly one capture group.
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}










## Supporting Types

#### MetricBucketOptions
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#MetricBucketOptions">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#MetricBucketOptions">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/logging?tab=doc#MetricBucketOptionsArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/logging?tab=doc#MetricBucketOptionsOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Logging.MetricBucketOptionsArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Logging.MetricBucketOptions.html">output</a> API doc for this type.
{{% /lang %}}



{{< langchoose csharp nojavascript >}}


{{% lang csharp %}}


<table class="ml-6">
    <thead>
        <tr>
            <th>Argument</th>
            <th>Type</th>
            <th>Description</th>
        </tr>
    </thead>
    <tbody>
    
        <tr>
            <td class="align-top">Explicit<wbr>Buckets</td>
            <td class="align-top">
                
                <code><a href="#metricbucketoptionsexplicitbuckets">Metric<wbr>Bucket<wbr>Options<wbr>Explicit<wbr>Buckets<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Exponential<wbr>Buckets</td>
            <td class="align-top">
                
                <code><a href="#metricbucketoptionsexponentialbuckets">Metric<wbr>Bucket<wbr>Options<wbr>Exponential<wbr>Buckets<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Linear<wbr>Buckets</td>
            <td class="align-top">
                
                <code><a href="#metricbucketoptionslinearbuckets">Metric<wbr>Bucket<wbr>Options<wbr>Linear<wbr>Buckets<wbr>Args?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}


{{% lang go %}}


<table class="ml-6">
    <thead>
        <tr>
            <th>Argument</th>
            <th>Type</th>
            <th>Description</th>
        </tr>
    </thead>
    <tbody>
    
        <tr>
            <td class="align-top">Explicit<wbr>Buckets</td>
            <td class="align-top">
                
                <code><a href="#metricbucketoptionsexplicitbuckets">*Metric<wbr>Bucket<wbr>Options<wbr>Explicit<wbr>Buckets</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Exponential<wbr>Buckets</td>
            <td class="align-top">
                
                <code><a href="#metricbucketoptionsexponentialbuckets">*Metric<wbr>Bucket<wbr>Options<wbr>Exponential<wbr>Buckets</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Linear<wbr>Buckets</td>
            <td class="align-top">
                
                <code><a href="#metricbucketoptionslinearbuckets">*Metric<wbr>Bucket<wbr>Options<wbr>Linear<wbr>Buckets</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}


{{% lang nodejs %}}


<table class="ml-6">
    <thead>
        <tr>
            <th>Argument</th>
            <th>Type</th>
            <th>Description</th>
        </tr>
    </thead>
    <tbody>
    
        <tr>
            <td class="align-top">explicit<wbr>Buckets</td>
            <td class="align-top">
                
                <code><a href="#metricbucketoptionsexplicitbuckets">Metric<wbr>Bucket<wbr>Options<wbr>Explicit<wbr>Buckets?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">exponential<wbr>Buckets</td>
            <td class="align-top">
                
                <code><a href="#metricbucketoptionsexponentialbuckets">Metric<wbr>Bucket<wbr>Options<wbr>Exponential<wbr>Buckets?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">linear<wbr>Buckets</td>
            <td class="align-top">
                
                <code><a href="#metricbucketoptionslinearbuckets">Metric<wbr>Bucket<wbr>Options<wbr>Linear<wbr>Buckets?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}


{{% lang python %}}


<table class="ml-6">
    <thead>
        <tr>
            <th>Argument</th>
            <th>Type</th>
            <th>Description</th>
        </tr>
    </thead>
    <tbody>
    
        <tr>
            <td class="align-top">explicit<wbr>Buckets</td>
            <td class="align-top">
                
                <code><a href="#metricbucketoptionsexplicitbuckets">Dict[Metric<wbr>Bucket<wbr>Options<wbr>Explicit<wbr>Buckets]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">exponential<wbr>Buckets</td>
            <td class="align-top">
                
                <code><a href="#metricbucketoptionsexponentialbuckets">Dict[Metric<wbr>Bucket<wbr>Options<wbr>Exponential<wbr>Buckets]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">linear<wbr>Buckets</td>
            <td class="align-top">
                
                <code><a href="#metricbucketoptionslinearbuckets">Dict[Metric<wbr>Bucket<wbr>Options<wbr>Linear<wbr>Buckets]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}





#### MetricBucketOptionsExplicitBuckets
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#MetricBucketOptionsExplicitBuckets">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#MetricBucketOptionsExplicitBuckets">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/logging?tab=doc#MetricBucketOptionsExplicitBucketsArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/logging?tab=doc#MetricBucketOptionsExplicitBucketsOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Logging.MetricBucketOptionsExplicitBucketsArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Logging.MetricBucketOptionsExplicitBuckets.html">output</a> API doc for this type.
{{% /lang %}}



{{< langchoose csharp nojavascript >}}


{{% lang csharp %}}


<table class="ml-6">
    <thead>
        <tr>
            <th>Argument</th>
            <th>Type</th>
            <th>Description</th>
        </tr>
    </thead>
    <tbody>
    
        <tr>
            <td class="align-top">Bounds</td>
            <td class="align-top">
                
                <code>List<double></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}


{{% lang go %}}


<table class="ml-6">
    <thead>
        <tr>
            <th>Argument</th>
            <th>Type</th>
            <th>Description</th>
        </tr>
    </thead>
    <tbody>
    
        <tr>
            <td class="align-top">Bounds</td>
            <td class="align-top">
                
                <code>[]float64</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}


{{% lang nodejs %}}


<table class="ml-6">
    <thead>
        <tr>
            <th>Argument</th>
            <th>Type</th>
            <th>Description</th>
        </tr>
    </thead>
    <tbody>
    
        <tr>
            <td class="align-top">bounds</td>
            <td class="align-top">
                
                <code>number[]</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}


{{% lang python %}}


<table class="ml-6">
    <thead>
        <tr>
            <th>Argument</th>
            <th>Type</th>
            <th>Description</th>
        </tr>
    </thead>
    <tbody>
    
        <tr>
            <td class="align-top">bounds</td>
            <td class="align-top">
                
                <code>List[Number]</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}





#### MetricBucketOptionsExponentialBuckets
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#MetricBucketOptionsExponentialBuckets">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#MetricBucketOptionsExponentialBuckets">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/logging?tab=doc#MetricBucketOptionsExponentialBucketsArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/logging?tab=doc#MetricBucketOptionsExponentialBucketsOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Logging.MetricBucketOptionsExponentialBucketsArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Logging.MetricBucketOptionsExponentialBuckets.html">output</a> API doc for this type.
{{% /lang %}}



{{< langchoose csharp nojavascript >}}


{{% lang csharp %}}


<table class="ml-6">
    <thead>
        <tr>
            <th>Argument</th>
            <th>Type</th>
            <th>Description</th>
        </tr>
    </thead>
    <tbody>
    
        <tr>
            <td class="align-top">Growth<wbr>Factor</td>
            <td class="align-top">
                
                <code>double?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Num<wbr>Finite<wbr>Buckets</td>
            <td class="align-top">
                
                <code>int?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Scale</td>
            <td class="align-top">
                
                <code>double?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}


{{% lang go %}}


<table class="ml-6">
    <thead>
        <tr>
            <th>Argument</th>
            <th>Type</th>
            <th>Description</th>
        </tr>
    </thead>
    <tbody>
    
        <tr>
            <td class="align-top">Growth<wbr>Factor</td>
            <td class="align-top">
                
                <code>*float64</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Num<wbr>Finite<wbr>Buckets</td>
            <td class="align-top">
                
                <code>*int</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Scale</td>
            <td class="align-top">
                
                <code>*float64</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}


{{% lang nodejs %}}


<table class="ml-6">
    <thead>
        <tr>
            <th>Argument</th>
            <th>Type</th>
            <th>Description</th>
        </tr>
    </thead>
    <tbody>
    
        <tr>
            <td class="align-top">growth<wbr>Factor</td>
            <td class="align-top">
                
                <code>number?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">num<wbr>Finite<wbr>Buckets</td>
            <td class="align-top">
                
                <code>number?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">scale</td>
            <td class="align-top">
                
                <code>number?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}


{{% lang python %}}


<table class="ml-6">
    <thead>
        <tr>
            <th>Argument</th>
            <th>Type</th>
            <th>Description</th>
        </tr>
    </thead>
    <tbody>
    
        <tr>
            <td class="align-top">growth<wbr>Factor</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">num<wbr>Finite<wbr>Buckets</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">scale</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}





#### MetricBucketOptionsLinearBuckets
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#MetricBucketOptionsLinearBuckets">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#MetricBucketOptionsLinearBuckets">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/logging?tab=doc#MetricBucketOptionsLinearBucketsArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/logging?tab=doc#MetricBucketOptionsLinearBucketsOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Logging.MetricBucketOptionsLinearBucketsArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Logging.MetricBucketOptionsLinearBuckets.html">output</a> API doc for this type.
{{% /lang %}}



{{< langchoose csharp nojavascript >}}


{{% lang csharp %}}


<table class="ml-6">
    <thead>
        <tr>
            <th>Argument</th>
            <th>Type</th>
            <th>Description</th>
        </tr>
    </thead>
    <tbody>
    
        <tr>
            <td class="align-top">Num<wbr>Finite<wbr>Buckets</td>
            <td class="align-top">
                
                <code>int?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Offset</td>
            <td class="align-top">
                
                <code>double?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Width</td>
            <td class="align-top">
                
                <code>int?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}


{{% lang go %}}


<table class="ml-6">
    <thead>
        <tr>
            <th>Argument</th>
            <th>Type</th>
            <th>Description</th>
        </tr>
    </thead>
    <tbody>
    
        <tr>
            <td class="align-top">Num<wbr>Finite<wbr>Buckets</td>
            <td class="align-top">
                
                <code>*int</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Offset</td>
            <td class="align-top">
                
                <code>*float64</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Width</td>
            <td class="align-top">
                
                <code>*int</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}


{{% lang nodejs %}}


<table class="ml-6">
    <thead>
        <tr>
            <th>Argument</th>
            <th>Type</th>
            <th>Description</th>
        </tr>
    </thead>
    <tbody>
    
        <tr>
            <td class="align-top">num<wbr>Finite<wbr>Buckets</td>
            <td class="align-top">
                
                <code>number?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">offset</td>
            <td class="align-top">
                
                <code>number?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">width</td>
            <td class="align-top">
                
                <code>number?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}


{{% lang python %}}


<table class="ml-6">
    <thead>
        <tr>
            <th>Argument</th>
            <th>Type</th>
            <th>Description</th>
        </tr>
    </thead>
    <tbody>
    
        <tr>
            <td class="align-top">num<wbr>Finite<wbr>Buckets</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">offset</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">width</td>
            <td class="align-top">
                
                <code>float</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}





#### MetricMetricDescriptor
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#MetricMetricDescriptor">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#MetricMetricDescriptor">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/logging?tab=doc#MetricMetricDescriptorArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/logging?tab=doc#MetricMetricDescriptorOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Logging.MetricMetricDescriptorArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Logging.MetricMetricDescriptor.html">output</a> API doc for this type.
{{% /lang %}}



{{< langchoose csharp nojavascript >}}


{{% lang csharp %}}


<table class="ml-6">
    <thead>
        <tr>
            <th>Argument</th>
            <th>Type</th>
            <th>Description</th>
        </tr>
    </thead>
    <tbody>
    
        <tr>
            <td class="align-top">Display<wbr>Name</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Labels</td>
            <td class="align-top">
                
                <code><a href="#metricmetricdescriptorlabel">List&lt;Metric<wbr>Metric<wbr>Descriptor<wbr>Label<wbr>Args&gt;?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Metric<wbr>Kind</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Unit</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Value<wbr>Type</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}


{{% lang go %}}


<table class="ml-6">
    <thead>
        <tr>
            <th>Argument</th>
            <th>Type</th>
            <th>Description</th>
        </tr>
    </thead>
    <tbody>
    
        <tr>
            <td class="align-top">Display<wbr>Name</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Labels</td>
            <td class="align-top">
                
                <code><a href="#metricmetricdescriptorlabel">[]Metric<wbr>Metric<wbr>Descriptor<wbr>Label</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Metric<wbr>Kind</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Unit</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Value<wbr>Type</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}


{{% lang nodejs %}}


<table class="ml-6">
    <thead>
        <tr>
            <th>Argument</th>
            <th>Type</th>
            <th>Description</th>
        </tr>
    </thead>
    <tbody>
    
        <tr>
            <td class="align-top">display<wbr>Name</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">labels</td>
            <td class="align-top">
                
                <code><a href="#metricmetricdescriptorlabel">Metric<wbr>Metric<wbr>Descriptor<wbr>Label[]?</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">metric<wbr>Kind</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">unit</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">value<wbr>Type</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}


{{% lang python %}}


<table class="ml-6">
    <thead>
        <tr>
            <th>Argument</th>
            <th>Type</th>
            <th>Description</th>
        </tr>
    </thead>
    <tbody>
    
        <tr>
            <td class="align-top">display_<wbr>name</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">labels</td>
            <td class="align-top">
                
                <code><a href="#metricmetricdescriptorlabel">List[Metric<wbr>Metric<wbr>Descriptor<wbr>Label]</a></code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">metric<wbr>Kind</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">unit</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">value<wbr>Type</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}





#### MetricMetricDescriptorLabel
{{% lang nodejs %}}
> See the <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/input/#MetricMetricDescriptorLabel">input</a> and <a href="/docs/reference/pkg/nodejs/pulumi/gcp/types/output/#MetricMetricDescriptorLabel">output</a> API doc for this type.
{{% /lang %}}

{{% lang go %}}
> See the <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/logging?tab=doc#MetricMetricDescriptorLabelArgs">input</a> and <a href="https://pkg.go.dev/github.com/pulumi/pulumi-gcp/sdk/go/gcp/logging?tab=doc#MetricMetricDescriptorLabelOutput">output</a> API doc for this type.
{{% /lang %}}

{{% lang csharp %}}
> See the <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Logging.MetricMetricDescriptorLabelArgs.html">input</a> and <a href="/docs/reference/pkg/dotnet/Pulumi.Gcp/Pulumi.Gcp.Logging.MetricMetricDescriptorLabel.html">output</a> API doc for this type.
{{% /lang %}}



{{< langchoose csharp nojavascript >}}


{{% lang csharp %}}


<table class="ml-6">
    <thead>
        <tr>
            <th>Argument</th>
            <th>Type</th>
            <th>Description</th>
        </tr>
    </thead>
    <tbody>
    
        <tr>
            <td class="align-top">Description</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Key</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Value<wbr>Type</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}


{{% lang go %}}


<table class="ml-6">
    <thead>
        <tr>
            <th>Argument</th>
            <th>Type</th>
            <th>Description</th>
        </tr>
    </thead>
    <tbody>
    
        <tr>
            <td class="align-top">Description</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Key</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">Value<wbr>Type</td>
            <td class="align-top">
                
                <code>*string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}


{{% lang nodejs %}}


<table class="ml-6">
    <thead>
        <tr>
            <th>Argument</th>
            <th>Type</th>
            <th>Description</th>
        </tr>
    </thead>
    <tbody>
    
        <tr>
            <td class="align-top">description</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">key</td>
            <td class="align-top">
                
                <code>string</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">value<wbr>Type</td>
            <td class="align-top">
                
                <code>string?</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}


{{% lang python %}}


<table class="ml-6">
    <thead>
        <tr>
            <th>Argument</th>
            <th>Type</th>
            <th>Description</th>
        </tr>
    </thead>
    <tbody>
    
        <tr>
            <td class="align-top">description</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">key</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Required)
 {{% /md %}}

            
            </td>
        </tr>
    
        <tr>
            <td class="align-top">value<wbr>Type</td>
            <td class="align-top">
                
                <code>str</code>
            </td>
            <td class="align-top">{{% md %}} 
 (Optional)
 {{% /md %}}

            
            </td>
        </tr>
    
    </tbody>
</table>


{{% /lang %}}







